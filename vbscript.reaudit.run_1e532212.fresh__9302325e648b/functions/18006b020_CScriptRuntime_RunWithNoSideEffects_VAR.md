# CScriptRuntime::RunWithNoSideEffects(VAR *)

- ea: `0x18006b020`
- end: `0x18006c710`
- name: `?RunWithNoSideEffects@CScriptRuntime@@QEAAJPEAVVAR@@@Z`
- size: `5872`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct VAR *)`
- caller_count: `1`
- callee_count: `53`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180069914`

## callees

- `0x180001484`
- `0x180001a14`
- `0x180001bd0`
- `0x180001ce0`
- `0x180001e58`
- `0x180001f70`
- `0x180002450`
- `0x180002600`
- `0x180002b70`
- `0x180003850`
- `0x180004300`
- `0x180006230`
- `0x180006550`
- `0x180019e78`
- `0x18001aa50`
- `0x18001c1f0`
- `0x18001c600`
- `0x18001e850`
- `0x180020a50`
- `0x180021070`
- `0x180022d10`
- `0x180022f20`
- `0x180027860`
- `0x180027890`
- `0x180027900`
- `0x180027960`
- `0x180027e00`
- `0x18002c580`
- `0x18002c6e0`
- `0x18002c990`
- `0x18002c9c0`
- `0x18002cc60`
- `0x18002ce50`
- `0x18002d2f0`
- `0x18002d340`
- `0x18002f550`
- `0x18002f580`
- `0x180035080`
- `0x1800354d0`
- `0x18003627c`
- `0x18003b1d8`
- `0x18003ef64`
- `0x18003f09c`
- `0x18003f4a4`
- `0x18003ff0c`
- `0x180041c00`
- `0x180041f5c`
- `0x180042604`
- `0x180042880`
- `0x180069df0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18006c037`
- `OLEAUT32!__imp_VariantCopy` at `0x18006c037`

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
  __int64 v10; // r9
  int v11; // r12d
  unsigned __int8 *v12; // r8
  unsigned int v13; // ecx
  unsigned int *v14; // rdx
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
  __int16 v57; // r9
  __int64 v58; // xmm1_8
  __int64 v59; // r8
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  __int64 v63; // rax
  __int64 v64; // rbx
  unsigned __int8 v65; // si
  const unsigned __int16 *v66; // rbx
  int v67; // r8d
  VAR *v68; // r10
  __int64 v69; // rsi
  const unsigned __int16 *v70; // rsi
  struct VAR *v71; // r10
  struct VAR *v72; // rbx
  struct SYM *v73; // rax
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  __int64 v79; // rbx
  const unsigned __int16 *v80; // rbx
  int v81; // esi
  int v82; // r8d
  struct VAR *p_pvargDest; // r11
  VAR *v84; // r11
  struct VAR *v85; // r11
  unsigned int v86; // ebx
  __int64 v88; // rbx
  const unsigned __int16 *v89; // rbx
  __int64 v90; // rsi
  int v91; // r8d
  __int64 v92; // rcx
  struct VAR *llVal; // r11
  VAR *v94; // r11
  struct VAR *v95; // r11
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  unsigned int v98; // ecx
  unsigned int v99; // ecx
  unsigned int v100; // ecx
  __int64 v101; // r14
  __int64 v102; // rcx
  const unsigned __int16 *v103; // r14
  int v104; // esi
  __int64 v105; // r15
  struct VAR *v106; // r10
  struct VAR *v107; // rbx
  struct SYM *v108; // rax
  int v109; // edx
  struct VAR *v110; // rax
  unsigned __int16 *v111; // r8
  __int16 v112; // r9
  CScriptRuntime *v113; // rcx
  struct VAR *v114; // r11
  int v115; // edx
  struct VAR *v116; // rax
  unsigned __int16 *v117; // r8
  __int16 v118; // r9
  struct VAR *v119; // r11
  unsigned int v120; // ecx
  unsigned int v121; // ecx
  unsigned int v122; // ecx
  unsigned int v123; // ecx
  __int64 v124; // rcx
  int v125; // ebx
  struct VAR *v126; // rsi
  CScriptRuntime *v127; // rcx
  VARIANTARG *pvarSrc; // r9
  char v129; // r10
  __int64 v130; // rcx
  int v131; // esi
  __int64 v132; // r14
  struct VAR *v133; // rbx
  struct VAR *v134; // r9
  char v135; // r10
  struct VAR *v136; // rax
  __int64 v137; // rcx
  __int64 v138; // rcx
  __int64 v139; // rax
  __int16 v140; // r9
  unsigned int v141; // ecx
  unsigned int v142; // ecx
  unsigned int v143; // ecx
  unsigned int v144; // ecx
  unsigned int v145; // ecx
  unsigned int v146; // ebx
  _WORD *v147; // rcx
  bool v148; // zf
  int BoolValNull; // edx
  int v150; // r9d
  _WORD *v151; // rcx
  __int64 v152; // rcx
  __int64 v153; // rdx
  int v154; // eax
  unsigned int v155; // ecx
  unsigned int v156; // ecx
  unsigned int v157; // ecx
  unsigned int v158; // ecx
  unsigned int v159; // ecx
  int v160; // eax
  unsigned int v161; // ecx
  __int16 v162; // cx
  bool v163; // zf
  __int16 v164; // cx
  int v165; // eax
  bool v166; // zf
  __int16 v167; // dx
  VAR *v168; // rbx
  struct VAR *LogicalVal; // rax
  unsigned int v170; // ecx
  unsigned int v171; // ecx
  unsigned int v172; // ecx
  unsigned int v173; // ecx
  unsigned int v174; // ecx
  unsigned int v175; // eax
  __int16 v176; // cx
  __int16 v177; // cx
  unsigned int v178; // ecx
  unsigned int v179; // ecx
  unsigned int v180; // ecx
  unsigned int v181; // ecx
  unsigned int v182; // ecx
  unsigned int v183; // ecx
  unsigned int v184; // ecx
  unsigned int v185; // ecx
  unsigned int v186; // ecx
  bool v187; // zf
  unsigned int v188; // ecx
  unsigned int v189; // ecx
  unsigned int v190; // ecx
  unsigned int v191; // ecx
  unsigned int v192; // ecx
  unsigned int v193; // ecx
  unsigned int v194; // ecx
  unsigned int v195; // ecx
  VAR *v196; // rbx
  VAR *v197; // rbx
  struct VAR *v198; // rcx
  int v199; // [rsp+40h] [rbp-79h] BYREF
  struct VAR *v200; // [rsp+48h] [rbp-71h] BYREF
  struct IDispatch *v201; // [rsp+50h] [rbp-69h] BYREF
  int v202; // [rsp+58h] [rbp-61h]
  struct IEntryPoint *v203; // [rsp+60h] [rbp-59h] BYREF
  enum tagBREAKREASON v204; // [rsp+68h] [rbp-51h] BYREF
  int v205; // [rsp+6Ch] [rbp-4Dh] BYREF
  int v206; // [rsp+70h] [rbp-49h]
  VAR *v207; // [rsp+78h] [rbp-41h]
  CScriptRuntime *v208; // [rsp+80h] [rbp-39h]
  __int128 v209; // [rsp+90h] [rbp-29h] BYREF
  __int64 v210; // [rsp+A0h] [rbp-19h]
  _BYTE v211[24]; // [rsp+A8h] [rbp-11h] BYREF
  VARIANTARG pvargDest; // [rsp+C0h] [rbp+7h] BYREF

  v208 = this;
  v207 = a2;
  v210 = 0;
  v199 = 0;
  v205 = 0;
  v202 = 0;
  v200 = 0;
  v201 = 0;
  v203 = 0;
  v204 = BREAKREASON_STEP;
  v209 = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  v3 = *(_DWORD *)(*((_QWORD *)this + 6) + 24LL);
  *((_QWORD *)this + 54) = *((_QWORD *)this + 58);
  *((_QWORD *)this + 71) = &v199;
  *((_QWORD *)this + 70) = &v205;
  *((_QWORD *)this + 59) = *((_QWORD *)this + 60);
  *((_DWORD *)this + 122) = -1;
  *((_QWORD *)this + 16) = *((_QWORD *)this + 58);
  *((_QWORD *)this + 15) = *((_QWORD *)this + 59);
  v206 = v3;
  if ( a2 )
    *(_WORD *)a2 = 0;
  *((_DWORD *)this + 126) = *((_DWORD *)this + 126) & 0xFFFFFFD8 | 0x20;
  TLS_NoDestructor::TLS_NoDestructor((TLS_NoDestructor *)v211, *((struct COleScript **)this + 1));
  v4 = setjmp_0((_JBTYPE *)this + 11);
  v5 = v208;
  v6 = 2;
  if ( v4 )
  {
    v199 = *((_DWORD *)v208 + 40);
    if ( *(_DWORD *)(*(_QWORD *)v208 + 128LL) )
      goto LABEL_121;
    *((_DWORD *)v208 + 40) = 0;
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
        *((_QWORD *)v5 + 59) = &v8[(unsigned __int8)byte_180081A80[4 * (unsigned __int8)*v8]];
      }
      v199 = 0;
    }
    else
    {
      if ( (v7 & 2) != 0
        || v199 == -2147352319
        || *(_DWORD *)(*(_QWORD *)v5 + 108LL)
        || !(unsigned int)CScriptRuntime::FResumeFromRuntimeError(v5, &v199) )
      {
        goto LABEL_121;
      }
      v6 = 2;
    }
  }
  v9 = v206;
  v10 = 16396;
  v11 = v202;
  while ( 1 )
  {
    v12 = (unsigned __int8 *)*((_QWORD *)v5 + 59);
    v13 = *v12;
    v14 = (unsigned int *)(v12 + 1);
    *((_QWORD *)v5 + 59) = v12 + 1;
    if ( v13 > 0x38 )
      break;
    if ( v13 == 56 )
      goto LABEL_120;
    if ( v13 > 0x1C )
    {
      if ( v13 > 0x2A )
      {
        if ( v13 <= 0x31 )
        {
          if ( v13 == 49 )
            goto LABEL_120;
          v96 = v13 - 43;
          if ( v96 )
          {
            v97 = v96 - 1;
            if ( !v97 )
              goto LABEL_120;
            v98 = v97 - 1;
            if ( v98 )
            {
              v99 = v98 - 1;
              if ( !v99 )
                goto LABEL_120;
              v100 = v99 - 1;
              if ( !v100 )
                goto LABEL_120;
              if ( v100 == 1 )
              {
                v101 = *v14;
                *((_QWORD *)v5 + 59) = v12 + 5;
                v102 = *(unsigned __int16 *)(v12 + 5);
                v103 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v101);
                v104 = *(unsigned __int16 *)(v12 + 5);
                *((_QWORD *)v5 + 59) = v12 + 7;
                v105 = 24 * v102;
                if ( !(unsigned int)VAR::IsIDispatch((VAR *)(24 * v102 + *((_QWORD *)v5 + 58)), &v201) )
                {
                  v199 = -2146827864;
                  CScriptRuntime::IfErrorHrArg(v5, -2146827864, v106, 0, v104);
                }
                v107 = (struct VAR *)*((_QWORD *)v5 + 58);
                v108 = SYM::InitFromSymbol((SYM *)&v209, v103);
                v199 = InvokeByName(*(struct CSession **)v5, v201, v108, 2u, (struct VAR *)&pvargDest, v104, v107);
                CScriptRuntime::IfErrorHrArg(v5, v199, (struct VAR *)((char *)v107 + v105), v103, v104);
                *((_QWORD *)v5 + 58) += v105;
                *(VARIANTARG *)*((_QWORD *)v5 + 58) = pvargDest;
                goto LABEL_292;
              }
              goto LABEL_290;
            }
            v109 = *(__int16 *)v14;
            *((_QWORD *)v5 + 59) = v12 + 3;
            v202 = v109;
            v11 = v109;
            v110 = CScriptRuntime::PvarLocal(v5, v109);
            v85 = v110;
            if ( *(_WORD *)v110 == v112 )
              v85 = (struct VAR *)*((_QWORD *)v110 + 1);
            v81 = *v111;
            *((_QWORD *)v5 + 59) = v111 + 1;
            v80 = 0;
            v200 = v85;
            goto LABEL_145;
          }
          v115 = *(__int16 *)v14;
          *((_QWORD *)v5 + 59) = v12 + 3;
          v202 = v115;
          v11 = v115;
          v116 = CScriptRuntime::PvarLocal(v5, v115);
          v95 = v116;
          if ( *(_WORD *)v116 == v118 )
            v95 = (struct VAR *)*((_QWORD *)v116 + 1);
          LODWORD(v90) = *v117;
          *((_QWORD *)v5 + 59) = v117 + 1;
          v89 = 0;
          v200 = v95;
          goto LABEL_154;
        }
        v120 = v13 - 50;
        if ( !v120 )
          goto LABEL_120;
        v121 = v120 - 1;
        if ( !v121 )
          goto LABEL_120;
        v122 = v121 - 1;
        if ( v122 )
        {
          v123 = v122 - 1;
          if ( !v123 )
            goto LABEL_120;
          v78 = v123 - 1;
          if ( !v78 )
          {
            v124 = *(unsigned __int16 *)v14;
            v125 = *(unsigned __int16 *)v14;
            *((_QWORD *)v5 + 59) = v12 + 3;
            v126 = (struct VAR *)(*((_QWORD *)v5 + 58) + 24 * v124);
            v200 = v126;
            if ( (unsigned int)VAR::IsIDispatch(v126, &v201) )
            {
              pvargDest.vt = 0;
              v199 = InvokeDispatch(*(struct CSession **)v5, v201, 0, v129, &pvargDest, v125, *((struct VAR **)v5 + 58));
              CScriptRuntime::IfErrorHrArg(v5, v199, v126, 0, v125);
              v10 = 16396;
            }
            else
            {
              v199 = CScriptRuntime::LockArray(v127, &v200, v126, v125, pvarSrc);
              CScriptRuntime::IfErrorHrArg(v5, v199, v126, 0, v125);
              v10 = 16396;
              pvargDest.vt = 16396;
              pvargDest.llVal = (LONGLONG)v200;
            }
            *((_QWORD *)v5 + 58) += 24LL * (unsigned int)(v125 + 1) - 24;
            goto LABEL_150;
          }
LABEL_289:
          if ( v78 == 1 )
            goto LABEL_120;
          goto LABEL_290;
        }
        v130 = *(unsigned __int16 *)v14;
        v131 = *(unsigned __int16 *)v14;
        *((_QWORD *)v5 + 59) = v12 + 3;
        v132 = 24 * v130;
        v133 = (struct VAR *)(24 * v130 + *((_QWORD *)v5 + 58));
        v200 = v133;
        if ( (unsigned int)VAR::IsIDispatch(v133, &v201) )
        {
          pvargDest.vt = 0;
          v199 = InvokeDispatch(*(struct CSession **)v5, v201, 0, v135, &pvargDest, v131, *((struct VAR **)v5 + 58));
          CScriptRuntime::IfErrorHrArg(v5, v199, v133, 0, v131);
          *((_QWORD *)v5 + 58) += v132;
          goto LABEL_125;
        }
        v199 = AccessArray(&v200, v133, v131, v134, 0);
        CScriptRuntime::IfErrorHrArg(v5, v199, v133, 0, v131);
        *((_QWORD *)v5 + 58) += v132;
LABEL_169:
        v136 = v200;
        v137 = *((_QWORD *)v5 + 58);
        *(_OWORD *)v137 = *(_OWORD *)v200;
        *(_QWORD *)(v137 + 16) = *((_QWORD *)v136 + 2);
        goto LABEL_170;
      }
      if ( v13 == 42 )
        goto LABEL_120;
      if ( v13 > 0x23 )
      {
        v74 = v13 - 36;
        if ( !v74 )
          goto LABEL_120;
        v75 = v74 - 1;
        if ( !v75 )
          goto LABEL_120;
        v76 = v75 - 1;
        if ( v76 )
        {
          v77 = v76 - 1;
          if ( !v77 )
            goto LABEL_120;
          v78 = v77 - 1;
          if ( !v78 )
          {
            v79 = *v14;
            *((_QWORD *)v5 + 59) = v12 + 5;
            v80 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v79);
            v81 = *(unsigned __int16 *)(v12 + 5);
            *((_QWORD *)v5 + 59) = v12 + 7;
            CScriptRuntime::GetVarAdr(v5, v80, (struct VAR *)&pvargDest);
            if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
            {
              v199 = VAR::InvokeByDispID(
                       (VAR *)&pvargDest,
                       *(struct CSession **)v5,
                       v82,
                       2u,
                       (struct VAR *)&pvargDest,
                       v81,
                       *((struct VAR **)v5 + 58));
              CScriptRuntime::IfErrorHrPsz(v5, v199, v80);
              goto LABEL_147;
            }
            p_pvargDest = (struct VAR *)&pvargDest;
            if ( pvargDest.vt == 16396 )
              p_pvargDest = (struct VAR *)pvargDest.llVal;
            v200 = p_pvargDest;
            if ( (unsigned int)VAR::IsFunction(p_pvargDest, &v203) || (unsigned int)VAR::IsProperty(v84, &v203, 4u) )
              goto LABEL_120;
LABEL_145:
            if ( (unsigned int)VAR::IsIDispatch(v85, &v201) )
            {
              pvargDest.vt = 0;
              v199 = InvokeDispatch(*(struct CSession **)v5, v201, 0, 2, &pvargDest, v81, *((struct VAR **)v5 + 58));
              CScriptRuntime::IfErrorHrLocal(v5, v199, v80, v11);
LABEL_147:
              v10 = 16396;
            }
            else
            {
              v199 = CScriptRuntime::LockArray(v113, &v200, v114, v81, *((VARIANTARG **)v5 + 58));
              CScriptRuntime::IfErrorHrLocal(v5, v199, v80, v11);
              v10 = 16396;
              pvargDest.vt = 16396;
              pvargDest.llVal = (LONGLONG)v200;
            }
            *((_QWORD *)v5 + 58) += 24LL * v81 - 24;
LABEL_150:
            *(VARIANTARG *)*((_QWORD *)v5 + 58) = pvargDest;
LABEL_293:
            v6 = 2;
            goto LABEL_294;
          }
          goto LABEL_289;
        }
        v88 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v89 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v88);
        v90 = *(unsigned __int16 *)(v12 + 5);
        *((_QWORD *)v5 + 59) = v12 + 7;
        CScriptRuntime::GetVarAdr(v5, v89, (struct VAR *)&pvargDest);
        if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
        {
          v199 = VAR::InvokeByDispID(
                   (VAR *)&pvargDest,
                   *(struct CSession **)v5,
                   v91,
                   2u,
                   (struct VAR *)&pvargDest,
                   v90,
                   *((struct VAR **)v5 + 58));
          CScriptRuntime::IfErrorHrPsz(v5, v199, v89);
          v92 = 3 * v90;
LABEL_124:
          *((_QWORD *)v5 + 58) += 8 * v92 - 24;
          goto LABEL_125;
        }
        llVal = (struct VAR *)&pvargDest;
        if ( pvargDest.vt == 16396 )
          llVal = (struct VAR *)pvargDest.llVal;
        v200 = llVal;
        if ( (unsigned int)VAR::IsFunction(llVal, &v203) || (unsigned int)VAR::IsProperty(v94, &v203, 4u) )
        {
LABEL_120:
          v199 = -2147467259;
          goto LABEL_121;
        }
LABEL_154:
        if ( (unsigned int)VAR::IsIDispatch(v95, &v201) )
        {
          pvargDest.vt = 0;
          v199 = InvokeDispatch(*(struct CSession **)v5, v201, 0, 2, &pvargDest, v90, *((struct VAR **)v5 + 58));
          CScriptRuntime::IfErrorHrLocal(v5, v199, v89, v11);
          v92 = 3LL * (int)v90;
          goto LABEL_124;
        }
        v199 = AccessArray(&v200, v119, v90, *((struct VAR **)v5 + 58), 0);
        CScriptRuntime::IfErrorHrLocal(v5, v199, v89, v11);
        *((_QWORD *)v5 + 58) += 24LL * (int)v90 - 24;
        goto LABEL_169;
      }
      if ( v13 == 35 )
      {
        v69 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v70 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v69);
        if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v5 + 58), &v201) )
        {
          v199 = -2146827864;
          CScriptRuntime::IfErrorHrArg(v5, -2146827864, v71, 0, 0);
        }
        **((_WORD **)v5 + 58) = 0;
        v72 = (struct VAR *)*((_QWORD *)v5 + 58);
        v73 = SYM::InitFromSymbol((SYM *)&v209, v70);
        v199 = InvokeByName(*(struct CSession **)v5, v201, v73, 2u, v72, 0, 0);
        CScriptRuntime::IfErrorHrArg(v5, v199, v72, v70, 0);
        goto LABEL_292;
      }
      v60 = v13 - 29;
      if ( !v60 )
      {
LABEL_100:
        v64 = *v14;
        v65 = *v12;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v66 = (const unsigned __int16 *)(*((_QWORD *)v5 + 62) + v64);
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 0;
        CScriptRuntime::GetVarAdr(v5, v66, *((struct VAR **)v5 + 58));
        if ( (unsigned int)VAR::IsDispmember(*((VAR **)v5 + 58)) )
        {
          v199 = VAR::InvokeByDispID(v68, *(struct CSession **)v5, v67, 2u, v68, 0, 0);
          CScriptRuntime::IfErrorHrPsz(v5, v199, v66);
LABEL_292:
          v10 = 16396;
          goto LABEL_293;
        }
        if ( (unsigned int)VAR::IsFunction(v68, &v203) || (unsigned int)VAR::IsProperty(*((VAR **)v5 + 58), &v203, 4u) )
          goto LABEL_120;
        if ( v65 != 28 )
          goto LABEL_292;
LABEL_170:
        v57 = 16396;
LABEL_171:
        v138 = *((_QWORD *)v5 + 58);
        if ( v57 == *(_WORD *)v138 )
        {
          v139 = *(_QWORD *)(v138 + 8);
          *(_OWORD *)v138 = *(_OWORD *)v139;
          *(_QWORD *)(v138 + 16) = *(_QWORD *)(v139 + 16);
        }
        if ( (unsigned int)VAR::IsSimpleType(**((unsigned __int16 **)v5 + 58)) || v140 == 74 )
          goto LABEL_292;
        pvargDest.vt = 0;
        v199 = VariantCopy(&pvargDest, *((const VARIANTARG **)v5 + 58));
        CScriptRuntime::IfErrorHr(v5, v199);
        v199 = VAR::MoveToHeap((VAR *)&pvargDest, *((struct GcContext **)v5 + 6));
        CScriptRuntime::IfErrorHr(v5, v199);
LABEL_125:
        *(VARIANTARG *)*((_QWORD *)v5 + 58) = pvargDest;
        goto LABEL_292;
      }
      v61 = v60 - 1;
      if ( !v61 )
        goto LABEL_120;
      v62 = v61 - 1;
      if ( !v62 )
        goto LABEL_120;
      v54 = v62 - 1;
      if ( v54 )
        goto LABEL_288;
      *((_QWORD *)v5 + 58) -= 24LL;
      v63 = *((_QWORD *)v5 + 58);
      *(_OWORD *)v63 = *(_OWORD *)((char *)v5 + 440);
      *(_QWORD *)(v63 + 16) = *((_QWORD *)v5 + 57);
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
          goto LABEL_294;
        }
        if ( v13 <= 7 )
        {
          if ( v13 == 7 )
            goto LABEL_120;
          if ( !v13 )
            goto LABEL_294;
          v15 = v13 - 1;
          if ( !v15 )
          {
            v196 = v207;
            if ( !v207 )
              goto LABEL_121;
LABEL_305:
            *(_WORD *)v196 = 0;
            goto LABEL_121;
          }
          v16 = v15 - 1;
          if ( !v16 )
            goto LABEL_294;
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
                  v199 = CScriptRuntime::Break(v5, BREAKREASON_BREAKPOINT);
                  if ( v199 < 0 )
                    goto LABEL_121;
                  v21 = CSession::HandleHalt(*(CSession **)v5);
                  goto LABEL_33;
                }
                goto LABEL_290;
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
          v199 = CSession::HandleHalt(*(CSession **)v5);
          if ( v199 < 0 )
            goto LABEL_121;
          v199 = CSession::HandleAbort(*(CSession **)v5);
          if ( v199 < 0 )
            goto LABEL_121;
          if ( (unsigned int)CSession::FOneTimeBreak(*(CSession **)v5, *((_DWORD *)v5 + 6), &v204) )
          {
            v25 = v204;
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
              v199 = CSession::PollHalt(*(CSession **)v5);
              if ( v199 < 0 )
                goto LABEL_121;
              goto LABEL_292;
            }
            v25 = BREAKREASON_BREAKPOINT;
          }
          v21 = CScriptRuntime::Break(v5, v25);
LABEL_33:
          v199 = v21;
          if ( v21 < 0 )
            goto LABEL_121;
          goto LABEL_34;
        }
        v31 = v13 - 8;
        if ( !v31 )
          goto LABEL_120;
        v32 = v31 - 1;
        if ( !v32 )
          goto LABEL_120;
        v33 = v32 - 1;
        if ( !v33 )
          goto LABEL_120;
        v34 = v33 - 1;
        if ( !v34 )
        {
          *((_QWORD *)v5 + 58) -= 24LL;
          **((_WORD **)v5 + 58) = v6;
          v42 = (char *)*((_QWORD *)v5 + 59);
          v43 = *v42;
          *((_QWORD *)v5 + 59) = v42 + 1;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 8LL) = v43;
          goto LABEL_294;
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
          goto LABEL_294;
        }
        if ( v35 != 1 )
          goto LABEL_290;
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 5;
LABEL_62:
        v36 = (struct VAR **)*((_QWORD *)v5 + 59);
        *((_QWORD *)v5 + 59) = v36 + 1;
        v37 = *((_QWORD *)v5 + 58);
        v38 = *v36;
LABEL_63:
        *(_QWORD *)(v37 + 8) = v38;
        goto LABEL_294;
      }
      if ( v13 > 0x15 )
      {
        v51 = v13 - 22;
        if ( !v51 )
          goto LABEL_120;
        v52 = v51 - 1;
        if ( !v52 )
          goto LABEL_120;
        v53 = v52 - 1;
        if ( !v53 )
        {
          v55 = *(__int16 *)v14;
          *((_QWORD *)v5 + 59) = v12 + 3;
          v11 = v55;
          *((_QWORD *)v5 + 58) -= 24LL;
          v202 = v55;
          v56 = CScriptRuntime::PvarLocal(v5, v55);
          v58 = *((_QWORD *)v56 + 2);
          *(_OWORD *)v59 = *(_OWORD *)v56;
          *(_QWORD *)(v59 + 16) = v58;
          goto LABEL_171;
        }
        v54 = v53 - 1;
        if ( v54 )
          goto LABEL_288;
        v202 = *(__int16 *)v14;
        v11 = v202;
        *((_QWORD *)v5 + 59) = v12 + 3;
        v38 = CScriptRuntime::PvarLocal(v5, v11);
        *((_QWORD *)v5 + 58) -= 24LL;
        v37 = *((_QWORD *)v5 + 58);
        v200 = v38;
        if ( *(_WORD *)v38 == (_WORD)v10 )
        {
          *(_OWORD *)v37 = *(_OWORD *)v38;
          *(_QWORD *)(v37 + 16) = *((_QWORD *)v38 + 2);
          goto LABEL_294;
        }
        *(_WORD *)v37 = v10;
        goto LABEL_63;
      }
      if ( v13 == 21 )
      {
        *((_QWORD *)v5 + 58) -= 24LL;
        **((_WORD **)v5 + 58) = 9;
        *(_QWORD *)(*((_QWORD *)v5 + 58) + 8LL) = 0;
        goto LABEL_294;
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
                goto LABEL_290;
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
LABEL_294:
    if ( vbs_interpreter_override_bailout )
    {
      v199 = -2147418113;
      goto LABEL_121;
    }
  }
  if ( v13 <= 0x54 )
  {
    if ( v13 == 84 )
    {
      **((_WORD **)v5 + 58) |= 0x8000u;
      goto LABEL_294;
    }
    if ( v13 > 0x46 )
    {
      if ( v13 <= 0x4D )
      {
        if ( v13 == 77 )
        {
          VbsVarEqv((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
        v170 = v13 - 71;
        if ( !v170 )
        {
          v175 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
          v6 = 2;
          if ( v175 <= 2 )
            v176 = -1;
          else
            v176 = 0;
          v10 = 16396;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = v176;
          v177 = 1;
          if ( v175 != -2 )
            v177 = 11;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 24LL) = v177;
          *((_QWORD *)v5 + 58) += 24LL;
          goto LABEL_294;
        }
        v171 = v170 - 1;
        if ( !v171 )
        {
          VbsVarAdd((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
        v172 = v171 - 1;
        if ( !v172 )
        {
          VbsVarSub((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
        v173 = v172 - 1;
        if ( !v173 )
        {
          VbsVarMul((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
        v174 = v173 - 1;
        if ( !v174 )
        {
          VbsVarDiv((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
        if ( v174 == 1 )
        {
          VbsVarMod((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
LABEL_290:
        v154 = -2146828237;
        goto LABEL_291;
      }
      v178 = v13 - 78;
      if ( !v178 )
      {
        VbsVarPow((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
        goto LABEL_189;
      }
      v179 = v178 - 1;
      if ( !v179 )
      {
        VbsVarImp((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
        goto LABEL_189;
      }
      v180 = v179 - 1;
      if ( !v180 )
      {
        *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = VbsVarIs(
                                                    (struct VAR *)(*((_QWORD *)v5 + 58) + 24LL),
                                                    *((struct VAR **)v5 + 58));
        *(_WORD *)(*((_QWORD *)v5 + 58) + 24LL) = 11;
        goto LABEL_189;
      }
      v181 = v180 - 1;
      if ( v181 )
      {
        v182 = v181 - 1;
        if ( !v182 )
        {
          VbsVarConcat((VARIANTARG *)(*((_QWORD *)v5 + 58) + 24LL));
          goto LABEL_189;
        }
        if ( v182 == 1 )
        {
          VbsVarIdiv((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL));
          goto LABEL_189;
        }
        goto LABEL_290;
      }
      v154 = -2146828253;
LABEL_291:
      v199 = v154;
      CScriptRuntime::IfErrorHr(v5, v154);
      goto LABEL_292;
    }
    if ( v13 == 70 )
    {
      v160 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
      v161 = v160 - 1;
      goto LABEL_210;
    }
    if ( v13 > 0x3F )
    {
      v155 = v13 - 64;
      if ( v155 )
      {
        v156 = v155 - 1;
        if ( !v156 )
        {
          v168 = (VAR *)*((_QWORD *)v5 + 58);
          LogicalVal = VAR::PvarGetLogicalVal(v168);
          *(_WORD *)v168 = *(_WORD *)LogicalVal;
          *((_DWORD *)v168 + 2) = ~*((_DWORD *)LogicalVal + 2);
          goto LABEL_292;
        }
        v157 = v156 - 1;
        if ( v157 )
        {
          v158 = v157 - 1;
          if ( v158 )
          {
            v159 = v158 - 1;
            if ( v159 )
            {
              if ( v159 != 1 )
                goto LABEL_290;
              v160 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
              v161 = v160 + 1;
LABEL_210:
              if ( v161 <= 1 )
                v162 = -1;
              else
                v162 = 0;
              v163 = v160 == -2;
              *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = v162;
LABEL_214:
              v164 = 1;
              if ( !v163 )
                v164 = 11;
              *(_WORD *)(*((_QWORD *)v5 + 58) + 24LL) = v164;
              goto LABEL_189;
            }
            v165 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
            v166 = v165 == -1;
LABEL_218:
            v167 = !v166 - 1;
          }
          else
          {
            v165 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
            v167 = -(v165 != 0);
          }
          v163 = v165 == -2;
          *(_WORD *)(*((_QWORD *)v5 + 58) + 32LL) = v167;
          goto LABEL_214;
        }
        v165 = VbsVarRel(*((_QWORD *)v5 + 58) + 24LL);
        v166 = v165 == 0;
        goto LABEL_218;
      }
      VbsVarAnd((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
LABEL_189:
      *((_QWORD *)v5 + 58) += 24LL;
      goto LABEL_292;
    }
    if ( v13 == 63 )
    {
      VbsVarXor((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
      goto LABEL_189;
    }
    v141 = v13 - 57;
    if ( !v141 )
    {
      v154 = -2146827787;
      goto LABEL_291;
    }
    v142 = v141 - 1;
    if ( v142 )
    {
      v143 = v142 - 1;
      if ( v143 )
      {
        v144 = v143 - 1;
        if ( v144 )
        {
          v145 = v144 - 1;
          if ( !v145 )
          {
            VbsVarNeg(*((struct VAR **)v5 + 58));
            goto LABEL_292;
          }
          if ( v145 != 1 )
            goto LABEL_290;
          VbsVarOr((struct VAR *)(*((_QWORD *)v5 + 58) + 24LL), *((struct VAR **)v5 + 58));
          goto LABEL_189;
        }
        v146 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v147 = (_WORD *)*((_QWORD *)v5 + 58);
        if ( *v147 == 11 )
          v148 = v147[4] == 0;
        else
          v148 = (unsigned int)GetBoolValNull(v147, v14, v12, v10) == 0;
        BoolValNull = v148;
      }
      else
      {
        v146 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        v151 = (_WORD *)*((_QWORD *)v5 + 58);
        if ( *v151 == 11 )
          BoolValNull = (__int16)v151[4];
        else
          BoolValNull = GetBoolValNull(v151, v14, v12, v10);
      }
      v150 = 1;
LABEL_195:
      CScriptRuntime::Branch(v5, BoolValNull, v146, v150);
      goto LABEL_292;
    }
    v152 = *v14;
    *((_QWORD *)v5 + 59) = v12 + 5;
    *((_QWORD *)v5 + 16) = *((_QWORD *)v5 + 58);
    v153 = v152 + *((_QWORD *)v5 + 60);
    *((_QWORD *)v5 + 59) = v153;
    *((_QWORD *)v5 + 15) = v153;
    goto LABEL_294;
  }
  if ( v13 > 0x62 )
  {
    if ( v13 <= 0x69 )
    {
      if ( v13 == 105 )
        goto LABEL_120;
      v189 = v13 - 99;
      if ( !v189 )
        goto LABEL_120;
      v190 = v189 - 1;
      if ( !v190 )
        goto LABEL_120;
      v191 = v190 - 1;
      if ( !v191 )
        goto LABEL_120;
      v192 = v191 - 1;
      if ( !v192 )
        goto LABEL_120;
      v193 = v192 - 1;
      if ( v193 )
      {
        if ( v193 != 1 )
          goto LABEL_290;
        v146 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        if ( !(unsigned int)VbsVarRel(*((_QWORD *)v5 + 58) + 24LL) )
        {
          *((_QWORD *)v5 + 58) += 48LL;
          goto LABEL_292;
        }
        v150 = 1;
      }
      else
      {
        v146 = *v14;
        *((_QWORD *)v5 + 59) = v12 + 5;
        if ( (unsigned int)VbsVarRel(*((_QWORD *)v5 + 58) + 24LL) )
          goto LABEL_189;
        v150 = 2;
      }
      BoolValNull = 1;
      goto LABEL_195;
    }
    v188 = v13 - 106;
    v187 = v188 == 0;
    goto LABEL_284;
  }
  if ( v13 == 98 )
    goto LABEL_120;
  if ( v13 > 0x5B )
  {
    v188 = v13 - 92;
    v187 = v188 == 0;
LABEL_284:
    if ( v187 )
      goto LABEL_120;
    v194 = v188 - 1;
    if ( !v194 )
      goto LABEL_120;
    v195 = v194 - 1;
    if ( !v195 )
      goto LABEL_120;
    v54 = v195 - 1;
    if ( !v54 )
      goto LABEL_120;
LABEL_288:
    v78 = v54 - 1;
    if ( !v78 )
      goto LABEL_120;
    goto LABEL_289;
  }
  if ( v13 == 91 )
    goto LABEL_120;
  v183 = v13 - 85;
  if ( !v183 )
    goto LABEL_120;
  v184 = v183 - 1;
  if ( !v184 )
    goto LABEL_120;
  v185 = v184 - 1;
  if ( v185 )
  {
    v186 = v185 - 1;
    if ( !v186 )
    {
      v197 = v207;
      if ( v207 )
      {
        v199 = AssignVar(*(struct CSession **)v5, v207, *((struct VAR **)v5 + 58), 0);
        CScriptRuntime::IfErrorHr(v5, v199);
        if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v197) )
        {
          GcContext::FreeToMark(*((GcContext **)v5 + 6), *((_DWORD *)v5 + 14));
          v199 = VAR::MoveToHeap(v197, *((struct GcContext **)v5 + 6));
          if ( v199 >= 0 )
            *((_DWORD *)v5 + 14) = *(_DWORD *)(*((_QWORD *)v5 + 6) + 24LL);
        }
      }
      *((_QWORD *)v5 + 58) += 24LL;
      goto LABEL_121;
    }
    v78 = v186 - 1;
    if ( v78 )
      goto LABEL_289;
    *((_QWORD *)v5 + 58) += 24LL;
    goto LABEL_294;
  }
  v196 = v207;
  if ( !v207 )
    goto LABEL_121;
  v198 = (struct VAR *)*((_QWORD *)v5 + 9);
  v200 = v198;
  if ( (_WORD)v10 == *(_WORD *)v198 )
    goto LABEL_305;
  *(_OWORD *)v207 = *(_OWORD *)v198;
  *((_QWORD *)v196 + 2) = *((_QWORD *)v198 + 2);
  *(_WORD *)v198 = 0;
  if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v196) )
  {
    GcContext::FreeToMark(*((GcContext **)v5 + 6), *((_DWORD *)v5 + 14));
    v199 = VAR::MoveToHeap(v196, *((struct GcContext **)v5 + 6));
    if ( v199 >= 0 )
      *((_DWORD *)v5 + 14) = *(_DWORD *)(*((_QWORD *)v5 + 6) + 24LL);
  }
LABEL_121:
  CSession::StepOutComplete(*(CSession **)v5, *((_DWORD *)v5 + 6));
  *((_DWORD *)v5 + 126) &= ~0x20u;
  CScriptRuntime::Cleanup(v5);
  v86 = v199;
  TLS_NoDestructor::Close((TLS_NoDestructor *)v211);
  return v86;
}

```

## disassembly

```asm
0x18006b020  mov     [rsp-8+arg_10], rbx
0x18006b025  push    rbp
0x18006b026  push    rsi
0x18006b027  push    rdi
0x18006b028  push    r12
0x18006b02a  push    r13
0x18006b02c  push    r14
0x18006b02e  push    r15
0x18006b030  lea     rbp, [rsp-27h]
0x18006b035  sub     rsp, 0E0h
0x18006b03c  mov     rax, cs:__security_cookie
0x18006b043  xor     rax, rsp
0x18006b046  mov     [rbp+57h+var_38], rax
0x18006b04a  mov     rbx, rcx
0x18006b04d  mov     [rbp+57h+var_90], rcx
0x18006b051  xor     eax, eax
0x18006b053  mov     [rbp+57h+var_98], rdx
0x18006b057  mov     [rbp+57h+var_70], rax
0x18006b05b  xor     r15d, r15d
0x18006b05e  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x18006b062  xorps   xmm0, xmm0
0x18006b065  mov     [rbp+57h+var_D0], r15d
0x18006b069  or      esi, 0FFFFFFFFh
0x18006b06c  mov     [rbp+57h+var_A4], r15d
0x18006b070  mov     [rbp+57h+var_B8], r15d
0x18006b074  mov     [rbp+57h+var_C8], r15
0x18006b078  mov     [rbp+57h+var_C0], r15
0x18006b07c  mov     [rbp+57h+var_B0], r15
0x18006b080  mov     [rbp+57h+var_A8], r15d
0x18006b084  movups  [rbp+57h+var_80], xmm0
0x18006b088  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x18006b08c  mov     rax, [rcx+30h]
0x18006b090  mov     ecx, [rax+18h]
0x18006b093  mov     rax, [rbx+1D0h]
0x18006b09a  mov     [rbx+1B0h], rax
0x18006b0a1  lea     rax, [rbp+57h+var_D0]
0x18006b0a5  mov     [rbx+238h], rax
0x18006b0ac  lea     rax, [rbp+57h+var_A4]
0x18006b0b0  mov     [rbx+230h], rax
0x18006b0b7  mov     rax, [rbx+1E0h]
0x18006b0be  mov     [rbx+1D8h], rax
0x18006b0c5  mov     [rbx+1E8h], esi
0x18006b0cb  mov     rax, [rbx+1D0h]
0x18006b0d2  mov     [rbx+80h], rax
0x18006b0d9  mov     rax, [rbx+1D8h]
0x18006b0e0  mov     [rbx+78h], rax
0x18006b0e4  mov     [rbp+57h+var_A0], ecx
0x18006b0e7  test    rdx, rdx
0x18006b0ea  jz      short loc_18006B0F0
0x18006b0ec  mov     [rdx], r15w
0x18006b0f0  mov     eax, [rbx+1F8h]
0x18006b0f6  lea     rcx, [rbp+57h+var_68]; this
0x18006b0fa  and     eax, 0FFFFFFF8h
0x18006b0fd  or      eax, 20h
0x18006b100  mov     [rbx+1F8h], eax
0x18006b106  mov     rdx, [rbx+8]; struct COleScript *
0x18006b10a  call    ??0TLS_NoDestructor@@QEAA@PEAVCOleScript@@@Z; TLS_NoDestructor::TLS_NoDestructor(COleScript *)
0x18006b10f  lea     rcx, [rbx+0B0h]; Buf
0x18006b116  mov     rdx, rsp
0x18006b119  call    _setjmp_0
0x18006b11e  mov     rdi, [rbp+57h+var_90]
0x18006b122  mov     r14d, 1
0x18006b128  lea     r10d, [r14+1]
0x18006b12c  test    eax, eax
0x18006b12e  jz      loc_18006B1F5
0x18006b134  mov     eax, [rdi+0A0h]
0x18006b13a  mov     [rbp+57h+var_D0], eax
0x18006b13d  mov     rax, [rdi]
0x18006b140  cmp     [rax+80h], r15d
0x18006b147  jnz     loc_18006B990
0x18006b14d  mov     [rdi+0A0h], r15d
0x18006b154  mov     [rdi+88h], r15
0x18006b15b  mov     [rdi+98h], r15
0x18006b162  mov     [rdi+90h], esi
0x18006b168  mov     [rdi+94h], r15d
0x18006b16f  mov     eax, [rdi+1F8h]
0x18006b175  test    r14b, al
0x18006b178  jz      short loc_18006B1B8
0x18006b17a  mov     rax, [rdi+1B0h]
0x18006b181  mov     [rdi+1D0h], rax
0x18006b188  mov     rdx, [rdi+1D8h]
0x18006b18f  mov     al, [rdx]
0x18006b191  sub     al, r10b
0x18006b194  cmp     al, 4
0x18006b196  jbe     short loc_18006B1B2
0x18006b198  movzx   eax, byte ptr [rdx]
0x18006b19b  lea     rcx, byte_180081A80
0x18006b1a2  movzx   ecx, byte ptr [rcx+rax*4]
0x18006b1a6  add     rcx, rdx
0x18006b1a9  mov     [rdi+1D8h], rcx
0x18006b1b0  jmp     short loc_18006B188
0x18006b1b2  mov     [rbp+57h+var_D0], r15d
0x18006b1b6  jmp     short loc_18006B1F5
0x18006b1b8  test    r10b, al
0x18006b1bb  jnz     loc_18006B990
0x18006b1c1  cmp     [rbp+57h+var_D0], 80020101h
0x18006b1c8  jz      loc_18006B990
0x18006b1ce  mov     rax, [rdi]
0x18006b1d1  cmp     [rax+6Ch], r15d
0x18006b1d5  jnz     loc_18006B990
0x18006b1db  lea     rdx, [rbp+57h+var_D0]; int *
0x18006b1df  mov     rcx, rdi; this
0x18006b1e2  call    ?FResumeFromRuntimeError@CScriptRuntime@@QEAAHPEAJ@Z; CScriptRuntime::FResumeFromRuntimeError(long *)
0x18006b1e7  test    eax, eax
0x18006b1e9  jz      loc_18006B990
0x18006b1ef  mov     r10d, 2
0x18006b1f5  mov     r13d, [rbp+57h+var_A0]
0x18006b1f9  mov     r9d, 400Ch
0x18006b1ff  mov     r12d, [rbp+57h+var_B8]
0x18006b203  mov     r11d, 7
0x18006b209  lea     esi, [r11+11h]
0x18006b20d  lea     ebx, [rsi-0Dh]
0x18006b210  mov     r8, [rdi+1D8h]
0x18006b217  movzx   ecx, byte ptr [r8]
0x18006b21b  lea     rdx, [r8+1]
0x18006b21f  mov     [rdi+1D8h], rdx
0x18006b226  cmp     ecx, 38h ; '8'
0x18006b229  ja      loc_18006C069
0x18006b22f  jz      loc_18006B989
0x18006b235  cmp     ecx, 1Ch
0x18006b238  ja      loc_18006B6D0
0x18006b23e  jz      loc_18006B739
0x18006b244  cmp     ecx, 0Eh
0x18006b247  ja      loc_18006B504
0x18006b24d  jz      loc_18006B4C5
0x18006b253  cmp     ecx, r11d
0x18006b256  ja      loc_18006B3D4
0x18006b25c  jz      loc_18006B989
0x18006b262  test    ecx, ecx
0x18006b264  jz      loc_18006C5F4
0x18006b26a  sub     ecx, 1
0x18006b26d  jz      loc_18006C60C
0x18006b273  sub     ecx, 1
0x18006b276  jz      loc_18006C5F4
0x18006b27c  sub     ecx, 1
0x18006b27f  jz      loc_18006B30F
0x18006b285  sub     ecx, 1
0x18006b288  jz      short loc_18006B306
0x18006b28a  sub     ecx, 1
0x18006b28d  jz      short loc_18006B2FE
0x18006b28f  cmp     ecx, 1
0x18006b292  jnz     loc_18006C5D6
0x18006b298  mov     ecx, [rdx]
0x18006b29a  lea     rax, [rdx+4]
0x18006b29e  mov     [rdi+1D8h], rax
0x18006b2a5  mov     edx, r14d; enum tagBREAKREASON
0x18006b2a8  mov     [rdi+1E8h], ecx
0x18006b2ae  mov     rcx, rdi; this
0x18006b2b1  call    ?Break@CScriptRuntime@@AEAAJW4tagBREAKREASON@@@Z; CScriptRuntime::Break(tagBREAKREASON)
0x18006b2b6  mov     [rbp+57h+var_D0], eax
0x18006b2b9  test    eax, eax
0x18006b2bb  js      loc_18006B990
0x18006b2c1  mov     rcx, [rdi]; this
0x18006b2c4  call    ?HandleHalt@CSession@@QEAAJXZ; CSession::HandleHalt(void)
0x18006b2c9  mov     [rbp+57h+var_D0], eax
0x18006b2cc  test    eax, eax
0x18006b2ce  js      loc_18006B990
0x18006b2d4  mov     rcx, [rdi+30h]; this
0x18006b2d8  cmp     r13d, [rcx+18h]
0x18006b2dc  jge     short loc_18006B2E6
0x18006b2de  mov     edx, r13d; int
0x18006b2e1  call    ?FreeToMark@GcContext@@QEAAXJ@Z; GcContext::FreeToMark(long)
0x18006b2e6  mov     rcx, [rdi]; this
0x18006b2e9  call    ?PollHalt@CSession@@QEAAJXZ; CSession::PollHalt(void)
0x18006b2ee  mov     [rbp+57h+var_D0], eax
0x18006b2f1  test    eax, eax
0x18006b2f3  js      loc_18006B990
0x18006b2f9  jmp     loc_18006C5E8
0x18006b2fe  mov     ecx, [rdx]
0x18006b300  lea     rax, [rdx+4]
0x18006b304  jmp     short loc_18006B316
0x18006b306  movzx   ecx, word ptr [rdx]
0x18006b309  lea     rax, [rdx+2]
0x18006b30d  jmp     short loc_18006B316
0x18006b30f  movzx   ecx, byte ptr [rdx]
0x18006b312  lea     rax, [rdx+1]
0x18006b316  mov     [rdi+1D8h], rax
0x18006b31d  mov     [rdi+1E8h], ecx
0x18006b323  mov     rcx, [rdi]; this
0x18006b326  call    ?FInterrupt@CSession@@QEAAHXZ; CSession::FInterrupt(void)
0x18006b32b  test    eax, eax
0x18006b32d  jz      short loc_18006B2D4
0x18006b32f  mov     rcx, [rdi]; this
0x18006b332  call    ?HandleHalt@CSession@@QEAAJXZ; CSession::HandleHalt(void)
0x18006b337  mov     [rbp+57h+var_D0], eax
0x18006b33a  test    eax, eax
0x18006b33c  js      loc_18006B990
0x18006b342  mov     rcx, [rdi]; this
0x18006b345  call    ?HandleAbort@CSession@@QEAAJXZ; CSession::HandleAbort(void)
0x18006b34a  mov     [rbp+57h+var_D0], eax
0x18006b34d  test    eax, eax
0x18006b34f  js      loc_18006B990
0x18006b355  mov     rcx, [rdi]; this
0x18006b358  lea     r8, [rbp+57h+var_A8]; enum tagBREAKREASON *
0x18006b35c  mov     edx, [rdi+18h]; int
0x18006b35f  call    ?FOneTimeBreak@CSession@@QEAAHJPEAW4tagBREAKREASON@@@Z; CSession::FOneTimeBreak(long,tagBREAKREASON *)
0x18006b364  test    eax, eax
0x18006b366  jz      short loc_18006B36D
0x18006b368  mov     edx, [rbp+57h+var_A8]
0x18006b36b  jmp     short loc_18006B3C7
0x18006b36d  mov     rax, [rdi+28h]
0x18006b371  mov     rdx, [rax]
0x18006b374  mov     r8, [rdx+10h]
0x18006b378  test    r8, r8
0x18006b37b  jz      loc_18006B2D4
0x18006b381  mov     rax, [rax+10h]
0x18006b385  mov     ecx, [rax+10h]
0x18006b388  add     ecx, [rdi+1E8h]
0x18006b38e  js      short loc_18006B3B9
0x18006b390  mov     rax, [rdx+40h]
0x18006b394  cmp     ecx, [rax+20h]
0x18006b397  jge     short loc_18006B3B9
0x18006b399  movsxd  rax, ecx
0x18006b39c  sar     rax, 3
0x18006b3a0  cmp     [rax+r8], r15b
0x18006b3a4  jz      loc_18006B2D4
0x18006b3aa  movzx   eax, byte ptr [rax+r8]
0x18006b3af  and     ecx, 7
0x18006b3b2  shr     eax, cl
0x18006b3b4  and     eax, r14d
0x18006b3b7  jmp     short loc_18006B3BC
0x18006b3b9  mov     eax, r15d
0x18006b3bc  test    eax, eax
0x18006b3be  jz      loc_18006B2D4
0x18006b3c4  mov     edx, r14d; enum tagBREAKREASON
0x18006b3c7  mov     rcx, rdi; this
0x18006b3ca  call    ?Break@CScriptRuntime@@AEAAJW4tagBREAKREASON@@@Z; CScriptRuntime::Break(tagBREAKREASON)
0x18006b3cf  jmp     loc_18006B2C9
0x18006b3d4  sub     ecx, 8
0x18006b3d7  jz      loc_18006B989
0x18006b3dd  sub     ecx, 1
0x18006b3e0  jz      loc_18006B989
0x18006b3e6  sub     ecx, 1
0x18006b3e9  jz      loc_18006B989
0x18006b3ef  sub     ecx, 1
0x18006b3f2  jz      loc_18006B48E
0x18006b3f8  sub     ecx, 1
0x18006b3fb  jz      short loc_18006B43F
0x18006b3fd  cmp     ecx, 1
0x18006b400  jnz     loc_18006C5D6
0x18006b406  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006b40e  mov     rax, [rdi+1D0h]
0x18006b415  mov     word ptr [rax], 5
0x18006b41a  mov     rdx, [rdi+1D8h]
0x18006b421  lea     rax, [rdx+8]
0x18006b425  mov     [rdi+1D8h], rax
0x18006b42c  mov     rcx, [rdi+1D0h]
0x18006b433  mov     rax, [rdx]
0x18006b436  mov     [rcx+8], rax
0x18006b43a  jmp     loc_18006C5F4
0x18006b43f  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006b447  mov     rax, [rdi+1D0h]
0x18006b44e  mov     word ptr [rax], 3
0x18006b453  mov     rax, [rdi+1D8h]
0x18006b45a  mov     ecx, [rax]
0x18006b45c  add     rax, 4
0x18006b460  mov     [rdi+1D8h], rax
0x18006b467  mov     rax, [rdi+1D0h]
0x18006b46e  mov     [rax+8], ecx
0x18006b471  mov     rcx, [rdi+1D0h]
0x18006b478  movsx   eax, word ptr [rcx+8]
0x18006b47c  cmp     eax, [rcx+8]
0x18006b47f  jnz     loc_18006C5F4
0x18006b485  mov     [rcx], r10w
0x18006b489  jmp     loc_18006C5F4
0x18006b48e  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006b496  mov     rax, [rdi+1D0h]
0x18006b49d  mov     [rax], r10w
0x18006b4a1  mov     rax, [rdi+1D8h]
0x18006b4a8  movsx   ecx, byte ptr [rax]
0x18006b4ab  inc     rax
0x18006b4ae  mov     [rdi+1D8h], rax
0x18006b4b5  mov     rax, [rdi+1D0h]
0x18006b4bc  mov     [rax+8], cx
0x18006b4c0  jmp     loc_18006C5F4
0x18006b4c5  add     qword ptr [rdi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18006b4cd  mov     rax, [rdi+1D0h]
0x18006b4d4  mov     word ptr [rax], 8
0x18006b4d9  mov     rax, [rdi+1D8h]
0x18006b4e0  mov     edx, [rax]
0x18006b4e2  add     rax, 4
0x18006b4e6  mov     [rdi+1D8h], rax
0x18006b4ed  mov     rax, [rdi+1D0h]
0x18006b4f4  add     rdx, [rdi+1F0h]
0x18006b4fb  mov     [rax+8], rdx
0x18006b4ff  jmp     loc_18006C5F4
0x18006b504  cmp     ecx, 15h
0x18006b507  ja      loc_18006B617
0x18006b50d  jz      loc_18006B5F3
0x18006b513  sub     ecx, 0Fh
0x18006b516  jz      loc_18006B5DB
0x18006b51c  sub     ecx, 1
0x18006b51f  jz      loc_18006B5B8
0x18006b525  sub     ecx, 1
0x18006b528  jz      short loc_18006B594
0x18006b52a  sub     ecx, 1
0x18006b52d  jz      short loc_18006B57C
0x18006b52f  sub     ecx, 1
0x18006b532  jz      short loc_18006B564
0x18006b534  cmp     ecx, 1
  ... truncated ...
```
