# CScriptRuntime::RunNoEH(VAR *)

- ea: `0x18001f0f0`
- end: `0x180022e94`
- name: `?RunNoEH@CScriptRuntime@@AEAAJPEAVVAR@@@Z`
- size: `15780`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct VAR *)`
- caller_count: `1`
- callee_count: `89`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001ef50`

## callees

- `0x1800014a0`
- `0x1800016c0`
- `0x180001ab8`
- `0x180001c30`
- `0x180002864`
- `0x180002d48`
- `0x180002e60`
- `0x180003f00`
- `0x1800040a0`
- `0x180004400`
- `0x180014d2c`
- `0x180014e50`
- `0x180015e00`
- `0x1800162c0`
- `0x1800166f0`
- `0x180018b50`
- `0x18001a260`
- `0x18001a350`
- `0x18001b5f0`
- `0x18001b9e0`
- `0x18001ed10`
- `0x18001f0f0`
- `0x180022ea0`
- `0x180022ed0`
- `0x180022f50`
- `0x180022fb0`
- `0x1800231a4`
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
- `0x180030790`
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
- `0x180034260`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800208fd`
- `msvcrt!_wcsicmp` at `0x1800208fd`
- `OLEAUT32!__imp_VariantCopy` at `0x1800227da`
- `OLEAUT32!__imp_VariantCopy` at `0x1800227da`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800217b2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800217b2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18002222e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18002222e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180022271`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180022271`

## pseudocode

```c
int __fastcall CScriptRuntime::RunNoEH(_JBTYPE *this, struct VAR *a2)
{
  unsigned __int64 v3; // rax
  int v4; // ecx
  int v5; // eax
  CScriptRuntime *v6; // rsi
  int v7; // r13d
  unsigned __int8 *v8; // rdx
  int v9; // eax
  __int16 *v10; // r9
  __int64 v11; // r14
  const unsigned __int16 *v12; // r14
  unsigned int v13; // edi
  int v14; // ebx
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  VAR *v18; // rcx
  __int64 v19; // rax
  int v20; // ecx
  unsigned __int8 *v21; // rax
  GcContext *v22; // rcx
  unsigned int v23; // ebx
  _WORD *v24; // rcx
  int v25; // edx
  bool v26; // zf
  int v27; // r9d
  char *v28; // rax
  __int16 v29; // cx
  unsigned __int8 v30; // r14
  __int64 v31; // rbx
  const unsigned __int16 *v32; // rbx
  int VarAdr; // edi
  int IsDispmember; // eax
  VAR *v35; // rcx
  __int64 v36; // rdi
  const unsigned __int16 *v37; // rdi
  VARIANTARG *v38; // rbx
  struct SYM *v39; // rax
  unsigned int v40; // ebx
  _WORD *v41; // rcx
  unsigned __int8 v42; // bl
  int v43; // edx
  __int16 *v44; // r8
  __int64 v45; // rax
  struct CEnumArray **v46; // rdi
  __int64 v47; // rcx
  __int64 v48; // r15
  int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // ecx
  __int16 v52; // r8
  __int16 v53; // cx
  struct VAR *v54; // rbx
  struct VAR *v55; // rax
  unsigned int v56; // r9d
  int v57; // eax
  bool v58; // zf
  __int16 v59; // dx
  __int16 v60; // cx
  unsigned int *v61; // rax
  __int64 v62; // rdx
  VARIANTARG *v63; // rbx
  struct VAR *LogicalVal; // rax
  char v65; // cl
  int *v66; // rax
  int v67; // ecx
  __int64 v68; // rcx
  __int64 v69; // rax
  VAR *v70; // rcx
  __int64 v71; // rdx
  VAR *v72; // rbx
  unsigned __int8 v73; // bl
  int v74; // edx
  VAR *v75; // rax
  struct VAR *v76; // rax
  __int16 *v77; // r9
  struct VAR *v78; // r15
  __int64 v79; // rcx
  struct VAR *v80; // rdi
  __int64 v81; // rdx
  struct VAR *v82; // r14
  bool v83; // zf
  int v84; // eax
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rdi
  const unsigned __int16 *v88; // rdi
  __int64 v89; // rbx
  int v90; // r14d
  int v91; // edx
  unsigned __int8 v92; // r12
  __int64 v93; // rbx
  __int64 v94; // rax
  const unsigned __int16 *v95; // rbx
  __int64 v96; // rcx
  VAR *v97; // rbx
  int IsIDispatch; // eax
  VARIANTARG *v100; // rcx
  __int64 v101; // rdx
  int v102; // eax
  __int64 v103; // r12
  __int64 v104; // rcx
  const unsigned __int16 *v105; // r12
  int v106; // r15d
  __int64 v107; // r14
  struct VAR *v108; // rdi
  char v109; // bl
  struct SYM *v110; // rax
  __int64 v111; // r14
  __int64 v112; // rdx
  const unsigned __int16 *v113; // r14
  int v114; // edi
  __int64 v115; // r15
  struct VAR *v116; // rbx
  struct SYM *v117; // rax
  __int64 v118; // rax
  struct VAR *v119; // rax
  __int64 v120; // rbx
  const unsigned __int16 *v121; // rbx
  unsigned __int8 v122; // di
  struct NameTbl *v123; // rcx
  int v124; // eax
  __int64 v125; // r8
  unsigned int *v126; // rdx
  unsigned __int16 *v127; // r8
  __int64 v128; // rcx
  signed int v129; // ebx
  const unsigned __int16 *v130; // r8
  int v131; // r9d
  struct tagSAFEARRAY *v132; // rax
  VAR *v133; // rcx
  LONGLONG v134; // rdx
  unsigned __int16 *v135; // rax
  unsigned int v136; // ecx
  unsigned int v137; // r15d
  struct CEnumArray *v138; // rcx
  struct IDispatch *v139; // rax
  const unsigned __int16 *v140; // rdi
  unsigned __int16 *v141; // rax
  unsigned int v142; // ecx
  __int64 v143; // rbx
  struct VAR *v144; // rax
  unsigned int v145; // r14d
  int v146; // r15d
  unsigned int v147; // r12d
  __int64 v148; // rax
  struct VAR *v149; // rbx
  char v150; // al
  unsigned __int8 v151; // r14
  __int64 v152; // rbx
  __int64 v153; // rax
  const unsigned __int16 *v154; // rbx
  __int64 v155; // rcx
  int v156; // edx
  int v157; // eax
  unsigned __int8 *v158; // rcx
  __int64 v159; // rdx
  __int64 v160; // xmm1_8
  __int64 v161; // rdx
  __int64 v162; // rcx
  int v163; // eax
  __int64 v164; // rcx
  _WORD *v165; // r8
  __int64 v166; // rcx
  __int64 v167; // rbx
  const unsigned __int16 *v168; // rbx
  int v169; // eax
  struct VAR *v170; // rax
  __int64 v171; // r8
  __int64 v172; // rdi
  const unsigned __int16 *v173; // rdi
  unsigned __int8 v174; // bl
  VAR *v175; // rcx
  struct VAR *v176; // rax
  __int64 v177; // rdx
  char v178; // bl
  const unsigned __int16 *v179; // rdx
  struct VAR *v180; // rax
  __int64 v181; // rdi
  signed int v182; // ecx
  const unsigned __int16 *v183; // rdi
  __int64 v184; // r14
  struct tagSAFEARRAY *v185; // rax
  struct tagSAFEARRAY *v186; // rbx
  struct VAR *v187; // rax
  int v188; // eax
  VAR *v189; // rcx
  __int64 v190; // rax
  int v191; // ecx
  GcContext *v192; // rcx
  __int64 v193; // rdx
  const unsigned __int16 *v194; // rdx
  unsigned __int8 v195; // cl
  struct NameTbl *v196; // rax
  __int64 v197; // rdx
  const unsigned __int16 *v198; // rdx
  char v199; // di
  NameTbl *v200; // rbx
  struct VAR *v201; // rax
  struct VAR **v202; // rdx
  __int64 v203; // rcx
  struct VAR *v204; // rax
  int v205; // ecx
  struct VAR *v206; // rax
  __int128 v207; // xmm0
  __int64 v208; // xmm1_8
  __int64 v209; // rax
  __int64 v210; // rdx
  struct VAR *v211; // r8
  __int64 v212; // rdi
  const unsigned __int16 *v213; // rdi
  struct VAR *v214; // r8
  __int64 v215; // rbx
  struct SYM *v216; // rax
  char v217; // r9
  struct VAR *v218; // r8
  __int64 v219; // rdi
  __int64 v220; // rax
  __int64 v221; // rdi
  const unsigned __int16 *v222; // rdi
  __int64 v223; // r14
  const unsigned __int16 *v224; // r14
  unsigned int v225; // edi
  int v226; // ebx
  const unsigned __int16 *v227; // r8
  int v228; // r9d
  LONGLONG llVal; // rcx
  struct tagSAFEARRAY *Array; // rax
  _WORD *v231; // rax
  SAFEARRAY *v232; // rbx
  SAFEARRAY *v233; // rax
  __int64 v234; // rdi
  __int64 v235; // rcx
  SAFEARRAY *v236; // rbx
  _QWORD *v237; // rdx
  int v238; // eax
  __int16 v239; // dx
  int BoolValNull; // eax
  const unsigned __int16 *v241; // rdi
  unsigned __int16 *v242; // rax
  int v243; // ecx
  int v244; // r14d
  __int64 v245; // r15
  __int64 v246; // rdi
  int v247; // ebx
  struct VAR *v248; // rbx
  unsigned int v249; // eax
  int v250; // edx
  struct VAR *v251; // rbx
  char v252; // al
  VAR *v253; // rax
  unsigned __int16 *v254; // rax
  __int64 v255; // rbx
  int v256; // eax
  struct VAR *v257; // rbx
  unsigned int v258; // eax
  __int64 v259; // rdi
  unsigned int v260; // r9d
  __int64 v261; // rdx
  __int64 v262; // rdx
  __int64 v263; // rdx
  HRESULT v264; // ebx
  unsigned __int16 *v265; // rax
  unsigned int v266; // ecx
  struct VAR *v267; // rax
  unsigned int v268; // r14d
  unsigned int v269; // r15d
  __int64 v270; // rdi
  __int64 v271; // rdx
  struct VAR *v272; // r8
  __int64 v273; // rax
  __int64 v274; // r15
  __int64 v275; // rdx
  const unsigned __int16 *v276; // r15
  __int64 v277; // r14
  __int64 v278; // rbx
  __int64 v279; // rax
  __int64 v280; // rdx
  __int64 v281; // rdi
  struct VAR *v282; // rbx
  struct SYM *v283; // rax
  char v284; // r9
  __int64 v285; // rax
  __int64 v286; // rdx
  __int64 v287; // r15
  __int64 v288; // rdx
  __int64 v289; // rbx
  __int64 v290; // rcx
  int v291; // r14d
  __int64 v292; // r15
  struct VAR *v293; // rdi
  struct VAR *v294; // rbx
  char v295; // al
  struct VAR *v296; // rbx
  VAR *v297; // rax
  __int64 v298; // rcx
  __int64 v299; // rcx
  __int64 v300; // rax
  __int64 v301; // rcx
  int v302; // edi
  struct VAR *v303; // rbx
  __int64 v304; // rcx
  int v305; // r14d
  struct VAR *v306; // rdi
  struct VAR *v307; // rbx
  char v308; // al
  struct VAR *v309; // rbx
  __int64 v310; // rcx
  __int64 v311; // rdi
  char v312; // r9
  __int64 v313; // rdx
  struct VAR *v314; // rbx
  struct VAR *v315; // rbx
  unsigned int v316; // r9d
  struct VAR *v317; // rbx
  struct VAR *v318; // rbx
  __int64 v319; // rcx
  VAR *v320; // rbx
  int Adr; // [rsp+40h] [rbp-C0h] BYREF
  VAR *CurrentWithVar; // [rsp+48h] [rbp-B8h] BYREF
  int v323; // [rsp+50h] [rbp-B0h]
  struct IDispatch *v324; // [rsp+58h] [rbp-A8h] BYREF
  struct IEntryPoint *v325; // [rsp+60h] [rbp-A0h] BYREF
  struct CEnumArray *v326; // [rsp+68h] [rbp-98h] BYREF
  struct NameTbl *v327; // [rsp+70h] [rbp-90h] BYREF
  __int128 v328; // [rsp+78h] [rbp-88h] BYREF
  __int64 v329; // [rsp+88h] [rbp-78h]
  unsigned int v330; // [rsp+90h] [rbp-70h] BYREF
  tagBREAKREASON v331; // [rsp+94h] [rbp-6Ch] BYREF
  int v332; // [rsp+98h] [rbp-68h]
  int v333; // [rsp+9Ch] [rbp-64h] BYREF
  int v334; // [rsp+A0h] [rbp-60h] BYREF
  struct IDispatch *v335; // [rsp+A8h] [rbp-58h] BYREF
  SAFEARRAY *psa; // [rsp+B0h] [rbp-50h] BYREF
  VAR *v337; // [rsp+B8h] [rbp-48h]
  struct IRegExp2 *v338; // [rsp+C0h] [rbp-40h] BYREF
  CScriptRuntime *v339; // [rsp+C8h] [rbp-38h] BYREF
  CScriptRuntime *v340; // [rsp+D0h] [rbp-30h]
  __int128 v341; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v342; // [rsp+F0h] [rbp-10h]
  __int128 v343; // [rsp+100h] [rbp+0h]
  __int64 v344; // [rsp+110h] [rbp+10h]
  VARIANTARG pvargDest; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG v346; // [rsp+130h] [rbp+30h] BYREF
  __int128 v347; // [rsp+148h] [rbp+48h] BYREF
  __int64 v348; // [rsp+158h] [rbp+58h]
  __int128 v349; // [rsp+160h] [rbp+60h] BYREF
  __int64 v350; // [rsp+170h] [rbp+70h]
  VARIANTARG v351; // [rsp+178h] [rbp+78h] BYREF
  __int128 v352; // [rsp+190h] [rbp+90h] BYREF
  __int64 v353; // [rsp+1A0h] [rbp+A0h]
  __int128 v354; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v355; // [rsp+1B8h] [rbp+B8h]
  __int128 v356; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v357; // [rsp+1D0h] [rbp+D0h]

  Adr = 0;
  v3 = this[3].Part[0];
  v340 = (CScriptRuntime *)this;
  v337 = a2;
  v333 = 0;
  v4 = *(_DWORD *)(v3 + 24);
  v329 = 0;
  CurrentWithVar = 0;
  v324 = 0;
  v325 = 0;
  v326 = 0;
  v331 = BREAKREASON_STEP;
  v323 = 0;
  v328 = 0;
  v332 = v4;
  memset(&pvargDest, 0, sizeof(pvargDest));
  memset(&v351, 0, sizeof(v351));
  memset(&v346, 0, sizeof(v346));
  this[35].Part[1] = (unsigned __int64)&Adr;
  this[35].Part[0] = (unsigned __int64)&v333;
  v5 = setjmp_0(this + 11);
  v6 = v340;
  if ( v5 )
  {
    Adr = *((_DWORD *)v340 + 40);
    if ( Adr == -2147352318 && (*((_BYTE *)v340 + 504) & 1) == 0 )
      goto LABEL_104;
    if ( !(unsigned int)CSession::IsHalted(*(CSession **)v340) )
    {
      v156 = Adr;
      if ( Adr != -2040119292 && Adr != -2147352318 )
      {
        if ( (*((_BYTE *)v6 + 504) & 3) == 0 )
        {
          v157 = *((_DWORD *)v6 + 37);
          if ( v157 )
          {
            if ( !*((_QWORD *)v6 + 19) )
            {
              *((_QWORD *)v6 + 19) = CScriptRuntime::GetLocalName(v6, v157);
              v156 = Adr;
            }
          }
        }
        Adr = CSession::RecordHr(
                *(CSession **)v6,
                v156,
                *((struct VAR **)v6 + 17),
                *((const unsigned __int16 **)v6 + 19),
                *((_DWORD *)v6 + 36));
      }
      *((_DWORD *)v6 + 40) = 0;
      *((_QWORD *)v6 + 17) = 0;
      *((_QWORD *)v6 + 19) = 0;
      *((_QWORD *)v6 + 18) = 0xFFFFFFFFLL;
      if ( (*((_BYTE *)v6 + 504) & 1) != 0 )
      {
        *((_QWORD *)v6 + 58) = *((_QWORD *)v6 + 54);
        while ( 1 )
        {
          v158 = (unsigned __int8 *)*((_QWORD *)v6 + 59);
          v159 = *v158;
          if ( (unsigned __int8)(v159 - 2) <= 4u )
            break;
          *((_QWORD *)v6 + 59) = &v158[(unsigned __int8)byte_180084A80[4 * v159]];
        }
        Adr = 0;
        goto LABEL_2;
      }
      if ( (int)CSession::CanHandleException(*(CSession **)v6) >= 0 )
      {
        Adr = -2147352318;
        goto LABEL_104;
      }
      if ( (*((_BYTE *)v6 + 504) & 2) == 0
        && Adr != -2147352319
        && (unsigned int)CSession::FReportError(*(CSession **)v6)
        && (unsigned int)CScriptRuntime::FResumeFromRuntimeError(v6, &Adr) )
      {
        goto LABEL_2;
      }
    }
LABEL_103:
    if ( Adr < 0 )
      goto LABEL_424;
LABEL_104:
    CSession::StepOutComplete(*(CSession **)v6, *((_DWORD *)v6 + 6));
    return Adr;
  }
LABEL_2:
  v7 = v323;
  while ( 1 )
  {
    v8 = (unsigned __int8 *)*((_QWORD *)v6 + 59);
    v9 = *v8;
    v10 = (__int16 *)(v8 + 1);
    *((_QWORD *)v6 + 59) = v8 + 1;
    if ( v9 != 25 )
      break;
    v323 = *v10;
    v7 = v323;
    *((_QWORD *)v6 + 59) = v8 + 3;
    CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
    *((_QWORD *)v6 + 58) -= 24LL;
    v18 = CurrentWithVar;
    v19 = *((_QWORD *)v6 + 58);
    if ( *(_WORD *)CurrentWithVar == 16396 )
    {
      *(_OWORD *)v19 = *(_OWORD *)CurrentWithVar;
      *(_QWORD *)(v19 + 16) = *((_QWORD *)v18 + 2);
    }
    else
    {
      *(_WORD *)v19 = 16396;
      *(_QWORD *)(v19 + 8) = v18;
    }
LABEL_19:
    if ( vbs_interpreter_override_bailout )
    {
      Adr = -2147418113;
LABEL_424:
      if ( (*((_BYTE *)v6 + 504) & 2) == 0 )
        Adr = CSession::ReportError(*(CSession **)v6, Adr);
      goto LABEL_104;
    }
  }
  if ( v9 == 3 )
  {
    v20 = *(unsigned __int8 *)v10;
    v21 = v8 + 2;
LABEL_22:
    *((_QWORD *)v6 + 59) = v21;
    *((_DWORD *)v6 + 122) = v20;
    if ( (unsigned int)CSession::FInterrupt(*(CSession **)v6) )
    {
      Adr = CSession::HandleHalt(*(CSession **)v6);
      if ( Adr < 0 )
        goto LABEL_103;
      Adr = CSession::HandleAbort(*(CSession **)v6);
      if ( Adr < 0 )
        goto LABEL_103;
      if ( (unsigned int)CSession::FOneTimeBreak(*(CSession **)v6, *((_DWORD *)v6 + 6), &v331) )
      {
        Adr = CScriptRuntime::Break(v6, v331);
        if ( Adr < 0 )
          goto LABEL_103;
      }
      else if ( (unsigned int)CScriptBody::FBreak(
                                **((CScriptBody ***)v6 + 5),
                                *((_DWORD *)v6 + 122) + *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 5) + 16LL) + 16LL)) )
      {
        Adr = CScriptRuntime::Break(v6, BREAKREASON_BREAKPOINT);
        if ( Adr < 0 )
          goto LABEL_103;
      }
    }
    v22 = (GcContext *)*((_QWORD *)v6 + 6);
    if ( v332 < *((_DWORD *)v22 + 6) )
      GcContext::FreeToMark(v22, v332);
    Adr = CSession::PollHalt(*(CSession **)v6);
    if ( Adr < 0 )
      goto LABEL_103;
    goto LABEL_19;
  }
  switch ( v9 )
  {
    case 0:
    case 2:
      goto LABEL_19;
    case 1:
      v97 = v337;
      if ( !v337 )
        goto LABEL_103;
      goto LABEL_102;
    case 4:
      v20 = (unsigned __int16)*v10;
      v21 = v8 + 3;
      goto LABEL_22;
    case 5:
      v20 = *(_DWORD *)v10;
      v21 = v8 + 5;
      goto LABEL_22;
    case 6:
      v191 = *(_DWORD *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      *((_DWORD *)v6 + 122) = v191;
      Adr = CScriptRuntime::Break(v6, BREAKREASON_BREAKPOINT);
      if ( Adr >= 0 )
      {
        Adr = CSession::HandleHalt(*(CSession **)v6);
        if ( Adr >= 0 )
        {
          v192 = (GcContext *)*((_QWORD *)v6 + 6);
          if ( v332 < *((_DWORD *)v192 + 6) )
            GcContext::FreeToMark(v192, v332);
          Adr = CSession::PollHalt(*(CSession **)v6);
          if ( Adr >= 0 )
            goto LABEL_19;
        }
      }
      goto LABEL_103;
    case 7:
    case 9:
      goto LABEL_135;
    case 8:
    case 10:
      if ( *v8 == 10 )
      {
        v223 = *(unsigned int *)v10;
        *((_QWORD *)v6 + 59) = v8 + 5;
        v224 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v223);
        v225 = *(unsigned __int16 *)(v8 + 5);
        *((_QWORD *)v6 + 59) = v8 + 7;
        v226 = *((_DWORD *)v6 + 126);
        *((_DWORD *)v6 + 126) = v226 | 4;
        CScriptRuntime::GetVarAdr(v6, v224, (struct VAR *)&pvargDest);
        *((_DWORD *)v6 + 126) = ((int)((v226 & 0xFFFFFFFC) << 29) >> 29)
                              ^ (*((_DWORD *)v6 + 126)
                               ^ ((int)((v226 & 0xFFFFFFFC) << 29) >> 29))
                              & 0xFFFFFFFB;
        if ( pvargDest.vt != 16396 )
        {
          Adr = -2146827787;
          CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v224);
        }
        llVal = pvargDest.llVal;
        CurrentWithVar = (VAR *)pvargDest.llVal;
        if ( (*((_BYTE *)v6 + 504) & 0x10) == 0 || *pvargDest.bstrVal )
          goto LABEL_287;
        memset(&v346, 0, sizeof(v346));
        v129 = v225 >> 1;
        Array = MakeArray(v225 >> 1, *((struct VAR **)v6 + 58), v227, v228);
        v133 = CurrentWithVar;
        v134 = (LONGLONG)Array;
        v346.llVal = (LONGLONG)Array;
        if ( *(_WORD *)CurrentWithVar )
        {
          VAR::Clear(CurrentWithVar);
          v134 = v346.llVal;
LABEL_142:
          v133 = CurrentWithVar;
        }
LABEL_143:
        *((_QWORD *)v133 + 1) = (char *)v133 + 16;
        *((_QWORD *)CurrentWithVar + 2) = v134;
        *(_WORD *)CurrentWithVar = 24588;
        *((_QWORD *)v6 + 58) += 24LL * v129;
        goto LABEL_19;
      }
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v224 = 0;
      v231 = (_WORD *)*((_QWORD *)v6 + 59);
      LOWORD(v225) = *v231;
      *((_QWORD *)v6 + 59) = v231 + 1;
      llVal = (LONGLONG)CurrentWithVar;
LABEL_287:
      v232 = 0;
      v233 = 0;
      if ( (v225 & 1) == 0 )
        goto LABEL_294;
      if ( *(_WORD *)llVal == 24588 )
      {
        v232 = **(SAFEARRAY ***)(llVal + 8);
      }
      else
      {
        if ( *(_WORD *)llVal != 8204 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrLocal(v6, -2146828275, v224, v7);
          llVal = (LONGLONG)CurrentWithVar;
          v233 = 0;
LABEL_294:
          v234 = (unsigned __int16)v225 >> 1;
          if ( v233 )
          {
            RedimPreserveArray(v232, v234, *((struct VAR **)v6 + 58), v228);
          }
          else if ( *(_WORD *)llVal == 24588 )
          {
            v235 = **(_QWORD **)(llVal + 8);
            if ( v235 && (*(_BYTE *)(v235 + 2) & 0x10) != 0 )
            {
              Adr = -2146828278;
              CScriptRuntime::IfErrorHrLocal(v6, -2146828278, v224, v7);
            }
            v236 = MakeArray(v234, *((struct VAR **)v6 + 58), v227, v228);
            Adr = VAR::Clear(CurrentWithVar);
            if ( Adr < 0 )
            {
              SafeArrayDestroy(v236);
              v237 = (_QWORD *)((char *)CurrentWithVar + 16);
              *((_QWORD *)CurrentWithVar + 1) = (char *)CurrentWithVar + 16;
              *v237 = 0;
              *(_WORD *)CurrentWithVar = 24588;
              CScriptRuntime::RaiseErrorHr(v6, Adr, CurrentWithVar, 0, -1);
            }
            *((_QWORD *)CurrentWithVar + 1) = (char *)CurrentWithVar + 16;
            *((_QWORD *)CurrentWithVar + 2) = v236;
            *(_WORD *)CurrentWithVar = 24588;
          }
          else
          {
            memset(&v346, 0, sizeof(v346));
            v346.llVal = (LONGLONG)MakeArray(v234, *((struct VAR **)v6 + 58), v227, v228);
            v346.vt = 8204;
            if ( (int)VAR::Clear(CurrentWithVar) < 0 && (*(_WORD *)CurrentWithVar & 0x2000) != 0 )
            {
              Adr = -2146828278;
              CScriptRuntime::IfErrorHrLocal(v6, -2146828278, v224, v7);
            }
            v238 = VAR::SafeVariantShallowCopy(CurrentWithVar, (struct VAR *)&v346);
            Adr = v238;
            if ( v238 < 0 )
              CScriptRuntime::RaiseErrorHr(v6, v238, CurrentWithVar, 0, -1);
          }
          *((_QWORD *)v6 + 58) += 24 * v234;
          goto LABEL_19;
        }
        v232 = *(SAFEARRAY **)(llVal + 8);
      }
      v233 = v232;
      goto LABEL_294;
    case 11:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 2;
      v28 = (char *)*((_QWORD *)v6 + 59);
      v29 = *v28;
      *((_QWORD *)v6 + 59) = v28 + 1;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = v29;
      goto LABEL_19;
    case 12:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 3;
      v66 = (int *)*((_QWORD *)v6 + 59);
      v67 = *v66;
      *((_QWORD *)v6 + 59) = v66 + 1;
      *(_DWORD *)(*((_QWORD *)v6 + 58) + 8LL) = v67;
      v68 = *((_QWORD *)v6 + 58);
      if ( (unsigned int)(*(_DWORD *)(v68 + 8) + 0x7FFF) <= 0xFFFE )
        *(_WORD *)v68 = 2;
      goto LABEL_19;
    case 13:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 5;
      goto LABEL_246;
    case 14:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 8;
      v61 = (unsigned int *)*((_QWORD *)v6 + 59);
      v62 = *v61;
      *((_QWORD *)v6 + 59) = v61 + 1;
      *(_QWORD *)(*((_QWORD *)v6 + 58) + 8LL) = *((_QWORD *)v6 + 62) + v62;
      goto LABEL_19;
    case 15:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 7;
LABEL_246:
      v202 = (struct VAR **)*((_QWORD *)v6 + 59);
      *((_QWORD *)v6 + 59) = v202 + 1;
      v203 = *((_QWORD *)v6 + 58);
      v204 = *v202;
      goto LABEL_248;
    case 16:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 11;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = 0;
      goto LABEL_19;
    case 17:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 11;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = -1;
      goto LABEL_19;
    case 18:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 1;
      goto LABEL_19;
    case 19:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 0;
      goto LABEL_19;
    case 20:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 10;
      *(_DWORD *)(*((_QWORD *)v6 + 58) + 8LL) = -2147352572;
      goto LABEL_19;
    case 21:
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 9;
      *(_QWORD *)(*((_QWORD *)v6 + 58) + 8LL) = 0;
      goto LABEL_19;
    case 22:
      v327 = 0;
      v334 = 0;
      v120 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v121 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v120);
      v122 = v8[5];
      *((_QWORD *)v6 + 59) = v8 + 6;
      SYM::InitFromSymbol((SYM *)&v328, v121);
      if ( (*((_BYTE *)v6 + 504) & 8) != 0 )
      {
        v123 = (struct NameTbl *)*((_QWORD *)v6 + 11);
        v327 = v123;
        if ( !v123 )
        {
          Adr = NameTbl::Create(&v327, *(struct CSession **)v6);
          CScriptRuntime::IfErrorHr(v6, Adr);
          *((_QWORD *)v6 + 11) = v327;
          v123 = v327;
        }
      }
      else
      {
        v123 = (struct NameTbl *)*((_QWORD *)v6 + 13);
        v327 = v123;
      }
      v124 = (*(__int64 (__fastcall **)(struct NameTbl *, __int128 *, int *))(*(_QWORD *)v123 + 160LL))(
               v123,
               &v328,
               &v334);
      Adr = v124;
      if ( !v124 )
      {
        Adr = -2146827247;
        CScriptRuntime::IfErrorHrPsz(v6, -2146827247, v121);
        v124 = Adr;
      }
      CScriptRuntime::IfErrorHrPsz(v6, v124, v121);
      v125 = 6;
      if ( !v122 )
        v125 = 2;
      Adr = (*(__int64 (__fastcall **)(struct NameTbl *, __int128 *, __int64, _QWORD, _QWORD))(*(_QWORD *)v327 + 120LL))(
              v327,
              &v328,
              v125,
              *((_QWORD *)v6 + 58),
              0);
      CScriptRuntime::IfErrorHrPsz(v6, Adr, v121);
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 23:
      CurrentWithVar = CScriptRuntime::PvarGetCurrentWithVar(v6);
      if ( !CurrentWithVar )
      {
        Adr = -2146827783;
        CScriptRuntime::IfErrorHr(v6, -2146827783);
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      v189 = CurrentWithVar;
      v190 = *((_QWORD *)v6 + 58);
      if ( *(_WORD *)CurrentWithVar == 16396 )
      {
        *(_OWORD *)v190 = *(_OWORD *)CurrentWithVar;
        *(_QWORD *)(v190 + 16) = *((_QWORD *)v189 + 2);
      }
      else
      {
        *(_WORD *)v190 = 16396;
        *(_QWORD *)(v190 + 8) = v189;
      }
      goto LABEL_19;
    case 24:
      v205 = *v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v7 = v205;
      *((_QWORD *)v6 + 58) -= 24LL;
      v323 = v205;
      v206 = CScriptRuntime::PvarLocal(v6, v205);
      v207 = *(_OWORD *)v206;
      v208 = *((_QWORD *)v206 + 2);
      v209 = *((_QWORD *)v6 + 58);
      *(_OWORD *)v209 = v207;
      *(_QWORD *)(v209 + 16) = v208;
      goto LABEL_387;
    case 26:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v54 = (struct VAR *)*((_QWORD *)v6 + 58);
      v55 = CScriptRuntime::PvarLocal(v6, v7);
      v56 = 1;
      goto LABEL_65;
    case 27:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v54 = (struct VAR *)*((_QWORD *)v6 + 58);
      v55 = CScriptRuntime::PvarLocal(v6, v7);
      v56 = 2;
LABEL_65:
      Adr = AssignVar(*(struct CSession **)v6, v55, v54, v56);
      CScriptRuntime::IfErrorHr(v6, Adr);
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 28:
    case 29:
      v339 = 0;
      v30 = *v8;
      v31 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v32 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v31);
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 0;
      if ( (unsigned int)CScriptRuntime::FUseLocalInEval(v6, v32, &v339) )
      {
        v204 = CScriptRuntime::PvarLocal(v339, 0);
        CurrentWithVar = v204;
        v203 = *((_QWORD *)v6 + 58);
        if ( *(_WORD *)v204 == 16396 )
        {
          *(_OWORD *)v203 = *(_OWORD *)v204;
          *(_QWORD *)(v203 + 16) = *((_QWORD *)v204 + 2);
        }
        else
        {
          *(_WORD *)v203 = 16396;
LABEL_248:
          *(_QWORD *)(v203 + 8) = v204;
        }
        goto LABEL_19;
      }
      VarAdr = CScriptRuntime::GetVarAdr(v6, v32, *((struct VAR **)v6 + 58));
      IsDispmember = VAR::IsDispmember(*((VAR **)v6 + 58));
      v35 = (VAR *)*((_QWORD *)v6 + 58);
      if ( IsDispmember )
      {
        Adr = VAR::InvokeByDispID(v35, *(struct CSession **)v6, 0, 3u, v35, 0, 0);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v32);
        goto LABEL_19;
      }
      if ( (unsigned int)VAR::IsFunction(v35, &v325) || (unsigned int)VAR::IsProperty(*((VAR **)v6 + 58), &v325, 4u) )
      {
        if ( (*(unsigned int (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 16LL))(v325)
          && **((_BYTE **)v6 + 59) != 89 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v32);
        }
        **((_WORD **)v6 + 58) = 0;
        if ( VarAdr )
        {
          v348 = 0;
          v347 = 0;
          VAR::SetIDispatch((VAR *)&v347, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  *((_QWORD *)v6 + 58),
                  0,
                  0,
                  &v347,
                  2);
          VAR::Clear((VAR *)&v347);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v325)(v325);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  *((_QWORD *)v6 + 58),
                  0,
                  0,
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 8LL))(v325);
        }
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v32);
        goto LABEL_19;
      }
      if ( (unsigned int)VAR::IsClass(*((VAR **)v6 + 58), &v325)
        || (unsigned int)VAR::IsProperty(*((VAR **)v6 + 58), &v325, 1u)
        || (unsigned int)VAR::IsProperty(*((VAR **)v6 + 58), &v325, 2u) )
      {
        Adr = -2146827788;
        CScriptRuntime::IfErrorHrPsz(v6, -2146827788, v32);
        goto LABEL_19;
      }
      if ( v30 != 28 )
        goto LABEL_19;
      goto LABEL_387;
    case 30:
      v101 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      CScriptRuntime::SetVar(v6, (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v101), *((struct VAR **)v6 + 58), 0);
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 31:
      v210 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      CScriptRuntime::SetVar(v6, (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v210), *((struct VAR **)v6 + 58), 1);
      goto LABEL_71;
    case 32:
      *((_QWORD *)v6 + 58) -= 24LL;
      v220 = *((_QWORD *)v6 + 58);
      *(_OWORD *)v220 = *(_OWORD *)((char *)v6 + 440);
      *(_QWORD *)(v220 + 16) = *((_QWORD *)v6 + 57);
      goto LABEL_19;
    case 33:
    case 34:
      Adr = -2146827787;
      CScriptRuntime::IfErrorHrPsz(v6, -2146827787, L"Me");
LABEL_135:
      v126 = (unsigned int *)*((_QWORD *)v6 + 59);
      v127 = (unsigned __int16 *)(v126 + 1);
      if ( *((_BYTE *)v126 - 1) == 9 )
      {
        v221 = *v126;
        *((_QWORD *)v6 + 59) = v127;
        v222 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v221);
        v129 = *v127;
        *((_QWORD *)v6 + 59) = (char *)v126 + 6;
        CScriptRuntime::GetVarAdr(v6, v222, (struct VAR *)&pvargDest);
        if ( pvargDest.vt != 16396 )
        {
          Adr = -2146827787;
          CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v222);
        }
        CurrentWithVar = (VAR *)pvargDest.llVal;
        if ( *pvargDest.bstrVal )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v222);
        }
      }
      else
      {
        v128 = *(__int16 *)v126;
        *((_QWORD *)v6 + 59) = (char *)v126 + 2;
        v7 = v128;
        v129 = *((unsigned __int16 *)v126 + 1);
        v323 = v128;
        *((_QWORD *)v6 + 59) = v127;
        CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 9) - 24 * v128);
        CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
        if ( *(_WORD *)CurrentWithVar )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrLocal(v6, -2146828275, 0, v7);
        }
      }
      memset(&v346, 0, sizeof(v346));
      v132 = MakeArray(v129, *((struct VAR **)v6 + 58), v130, v131);
      v133 = CurrentWithVar;
      v134 = (LONGLONG)v132;
      v346.llVal = (LONGLONG)v132;
      if ( *(_WORD *)CurrentWithVar )
      {
        VAR::Clear(CurrentWithVar);
        v133 = CurrentWithVar;
        v134 = v346.llVal;
      }
      if ( !v134 )
        goto LABEL_143;
      *(_WORD *)(v134 + 2) |= 0x12u;
      goto LABEL_142;
    case 35:
      v36 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v37 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v36);
      if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v6 + 58), &v324) )
      {
        v211 = (struct VAR *)*((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v211, 0, 0);
      }
      **((_WORD **)v6 + 58) = 0;
      v38 = (VARIANTARG *)*((_QWORD *)v6 + 58);
      v39 = SYM::InitFromSymbol((SYM *)&v328, v37);
      Adr = InvokeByName(*(struct CSession **)v6, v324, v39, 3, v38, 0, 0);
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)v38, v37, 0);
      goto LABEL_19;
    case 36:
      v212 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v213 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v212);
      if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v6 + 58), &v324) )
      {
        v214 = (struct VAR *)*((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v214, 0, 0);
      }
      v215 = *((_QWORD *)v6 + 58);
      v216 = SYM::InitFromSymbol((SYM *)&v328, v213);
      v217 = 4;
      goto LABEL_269;
    case 37:
      v219 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v213 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v219);
      if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v6 + 58), &v324) )
      {
        v218 = (struct VAR *)*((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v218, 0, 0);
      }
      v215 = *((_QWORD *)v6 + 58);
      v216 = SYM::InitFromSymbol((SYM *)&v328, v213);
      v217 = 8;
LABEL_269:
      Adr = InvokeByName(*(struct CSession **)v6, v324, v216, v217, 0, 1, (struct VAR *)(v215 + 24));
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)v215, v213, 0);
      goto LABEL_270;
    case 38:
      v246 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v245 = *(unsigned __int16 *)(v8 + 5);
      v241 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v246);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v244 = v245;
      v247 = CScriptRuntime::GetVarAdr(v6, v241, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v248 = (struct VAR *)*((_QWORD *)v6 + 58);
        v249 = GrfdispCall(v245);
        Adr = VAR::InvokeByDispID(
                (VAR *)&pvargDest,
                *(struct CSession **)v6,
                0,
                v249,
                (struct VAR *)&pvargDest,
                v245,
                v248);
        v250 = Adr;
LABEL_345:
        CScriptRuntime::IfErrorHrPsz(v6, v250, v241);
        v17 = 3 * v245;
        goto LABEL_15;
      }
      CurrentWithVar = VAR::PvarCutRef((VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsFunction(CurrentWithVar, &v325)
        || (unsigned int)VAR::IsProperty(CurrentWithVar, &v325, 4u) )
      {
        if ( (*(unsigned int (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 16LL))(v325)
          && **((_BYTE **)v6 + 59) != 89 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v241);
        }
        pvargDest.vt = 0;
        if ( v247 )
        {
          v350 = 0;
          v349 = 0;
          VAR::SetIDispatch((VAR *)&v349, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  &pvargDest,
                  (unsigned int)v245,
                  *((_QWORD *)v6 + 58),
                  &v349,
                  2);
          VAR::Clear((VAR *)&v349);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v325)(v325);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  &pvargDest,
                  (unsigned int)v245,
                  *((_QWORD *)v6 + 58),
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 8LL))(v325);
        }
        v250 = Adr;
        goto LABEL_345;
      }
LABEL_335:
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        pvargDest.vt = 0;
        v251 = (struct VAR *)*((_QWORD *)v6 + 58);
        v252 = GrfdispCall(v244);
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, v252, &pvargDest, v244, v251);
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v241, v7);
        v16 = (unsigned int)v245;
        goto LABEL_14;
      }
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v244, *((VARIANTARG **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrLocal(v6, Adr, v241, v7);
      *((_QWORD *)v6 + 58) += 24LL * (unsigned int)v245 - 24;
LABEL_386:
      v297 = CurrentWithVar;
      v298 = *((_QWORD *)v6 + 58);
      *(_OWORD *)v298 = *(_OWORD *)CurrentWithVar;
      *(_QWORD *)(v298 + 16) = *((_QWORD *)v297 + 2);
LABEL_387:
      v299 = *((_QWORD *)v6 + 58);
      if ( *(_WORD *)v299 == 16396 )
      {
        v300 = *(_QWORD *)(v299 + 8);
        *(_OWORD *)v299 = *(_OWORD *)v300;
        *(_QWORD *)(v299 + 16) = *(_QWORD *)(v300 + 16);
      }
      if ( (unsigned int)VAR::IsSimpleType(**((unsigned __int16 **)v6 + 58)) || **((_WORD **)v6 + 58) == 74 )
        goto LABEL_19;
      pvargDest.vt = 0;
      Adr = VariantCopy(&pvargDest, *((const VARIANTARG **)v6 + 58));
      CScriptRuntime::IfErrorHr(v6, Adr);
      Adr = VAR::MoveToHeap((VAR *)&pvargDest, *((struct GcContext **)v6 + 6));
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_16;
    case 39:
      v87 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v88 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v87);
      v89 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v90 = CScriptRuntime::GetVarAdr(v6, v88, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        Adr = VAR::InvokeByDispID((VAR *)&pvargDest, *(struct CSession **)v6, 0, 1u, 0, v89, *((struct VAR **)v6 + 58));
        v91 = Adr;
      }
      else
      {
        CurrentWithVar = VAR::PvarCutRef((VAR *)&pvargDest);
        if ( !(unsigned int)VAR::IsFunction(CurrentWithVar, &v325)
          && !(unsigned int)VAR::IsProperty(CurrentWithVar, &v325, 4u) )
        {
          if ( !(unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
          {
            Adr = -2146828275;
            CScriptRuntime::IfErrorHrLocal(v6, -2146828275, v88, v7);
          }
          v351.vt = 0;
          v256 = InvokeDispatch(*(struct CSession **)v6, v324, 0, 1, &v351, v89, *((struct VAR **)v6 + 58));
          CScriptRuntime::IfErrorHrLocal(v6, v256, v88, v7);
          VAR::Clear((VAR *)&v351);
LABEL_97:
          *((_QWORD *)v6 + 58) += 24 * v89;
          goto LABEL_19;
        }
        if ( v90 )
        {
          v352 = 0;
          v353 = 0;
          VAR::SetIDispatch((VAR *)&v352, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  &pvargDest,
                  (unsigned int)v89,
                  *((_QWORD *)v6 + 58),
                  &v352,
                  2);
          VAR::Clear((VAR *)&v352);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v325)(v325);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  &pvargDest,
                  (unsigned int)v89,
                  *((_QWORD *)v6 + 58),
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 8LL))(v325);
        }
        v91 = Adr;
      }
      CScriptRuntime::IfErrorHrPsz(v6, v91, v88);
      goto LABEL_97;
    case 40:
      v11 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v12 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v11);
      v13 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v14 = CScriptRuntime::GetVarAdr(v6, v12, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v257 = (struct VAR *)*((_QWORD *)v6 + 58);
        v258 = GrfdispCall(v13);
        Adr = VAR::InvokeByDispID(
                (VAR *)&pvargDest,
                *(struct CSession **)v6,
                0,
                v258,
                (struct VAR *)&pvargDest,
                v13,
                v257);
        v15 = Adr;
LABEL_12:
        CScriptRuntime::IfErrorHrPsz(v6, v15, v12);
        goto LABEL_13;
      }
      CurrentWithVar = VAR::PvarCutRef((VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsFunction(CurrentWithVar, &v325)
        || (unsigned int)VAR::IsProperty(CurrentWithVar, &v325, 4u) )
      {
        if ( (*(unsigned int (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 16LL))(v325)
          && **((_BYTE **)v6 + 59) != 89 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v12);
        }
        pvargDest.vt = 0;
        if ( v14 )
        {
          v355 = 0;
          v354 = 0;
          VAR::SetIDispatch((VAR *)&v354, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  &pvargDest,
                  v13,
                  *((_QWORD *)v6 + 58),
                  &v354,
                  2);
          VAR::Clear((VAR *)&v354);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v325)(v325);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v325 + 32LL))(
                  v325,
                  &pvargDest,
                  v13,
                  *((_QWORD *)v6 + 58),
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v325 + 8LL))(v325);
        }
        v15 = Adr;
        goto LABEL_12;
      }
      v137 = v13;
LABEL_145:
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        pvargDest.vt = 0;
        v149 = (struct VAR *)*((_QWORD *)v6 + 58);
        v150 = GrfdispCall(v13);
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, v150, &pvargDest, v13, v149);
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v12, v7);
        v13 = v137;
      }
      else
      {
        Adr = CScriptRuntime::LockArray(v6, &CurrentWithVar, CurrentWithVar, v13, *((VARIANTARG **)v6 + 58));
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v12, v7);
        v13 = v137;
        pvargDest.vt = 16396;
        pvargDest.llVal = (LONGLONG)CurrentWithVar;
      }
LABEL_13:
      v16 = v13;
LABEL_14:
      v17 = 3 * v16;
LABEL_15:
      *((_QWORD *)v6 + 58) += 8 * v17 - 24;
LABEL_16:
      *(VARIANTARG *)*((_QWORD *)v6 + 58) = pvargDest;
      goto LABEL_19;
    case 41:
      v259 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v140 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v259);
      v143 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v146 = CScriptRuntime::GetVarAdr(v6, v140, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v260 = 4;
LABEL_361:
        *((_QWORD *)v6 + 58) -= 24LL;
        v261 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v261 = *(_OWORD *)(v261 + 24 * (v143 + 1));
        *(_QWORD *)(v261 + 16) = *(_QWORD *)(v261 + 24 * (v143 + 1) + 16);
        Adr = VAR::InvokeByDispID(
                (VAR *)&pvargDest,
                *(struct CSession **)v6,
                0,
                v260,
                0,
                (int)v143 + 1,
                *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v140);
        v118 = (unsigned int)(v143 + 2);
LABEL_121:
        *((_QWORD *)v6 + 58) += 24 * v118;
        goto LABEL_19;
      }
      v144 = VAR::PvarCutRef((VAR *)&pvargDest);
      CurrentWithVar = v144;
      v145 = v143;
      v147 = v143;
LABEL_153:
      if ( (unsigned int)VAR::IsIDispatch(v144, &v324) )
      {
        *((_QWORD *)v6 + 58) -= 24LL;
        v262 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v262 = *(_OWORD *)(v262 + 24 * (v147 + 1LL));
        *(_QWORD *)(v262 + 16) = *(_QWORD *)(v262 + 24 * (v147 + 1LL) + 16);
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, 4, 0, v145 + 1, *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
      }
      else
      {
        if ( !v146
          || !(unsigned int)VAR::IsProperty((VAR *)&pvargDest, &v325, 2u)
          && !(unsigned int)VAR::IsProperty((VAR *)&pvargDest, &v325, 1u) )
        {
          if ( (unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24LL * v145)) )
          {
            psa = 0;
            Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v143, *((VARIANTARG **)v6 + 58), &psa);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
            Adr = SafeArrayLock(psa);
            CScriptRuntime::IfErrorHrPsz(v6, Adr, v140);
            Adr = AssignVar(
                    *(struct CSession **)v6,
                    CurrentWithVar,
                    (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * v145),
                    1u);
            v264 = SafeArrayUnlock(psa);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
            CScriptRuntime::IfErrorHrPsz(v6, v264, v140);
          }
          else
          {
            Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v143, *((VARIANTARG **)v6 + 58), 0);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
            Adr = AssignVar(
                    *(struct CSession **)v6,
                    CurrentWithVar,
                    (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * v145),
                    1u);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
          }
          v148 = v145 + 1;
          goto LABEL_158;
        }
        v356 = 0;
        v357 = 0;
        VAR::SetIDispatch((VAR *)&v356, *((struct IDispatch **)v6 + 12));
        *((_QWORD *)v6 + 58) -= 24LL;
        v263 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v263 = *(_OWORD *)(v263 + 24 * (v147 + 1LL));
        *(_QWORD *)(v263 + 16) = *(_QWORD *)(v263 + 24 * (v147 + 1LL) + 16);
        Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v325 + 32LL))(
                v325,
                0,
                v145 + 1,
                *((_QWORD *)v6 + 58),
                &v356,
                2);
        VAR::Clear((VAR *)&v356);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v140);
      }
      v148 = v145 + 2;
LABEL_158:
      *((_QWORD *)v6 + 58) += 24 * v148;
      goto LABEL_19;
    case 42:
      v270 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v140 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v270);
      v143 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      CScriptRuntime::GetVarAdr(v6, v140, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v260 = 8;
        goto LABEL_361;
      }
      v267 = VAR::PvarCutRef((VAR *)&pvargDest);
      CurrentWithVar = v267;
      v268 = v143;
      v269 = v143;
LABEL_373:
      if ( (unsigned int)VAR::IsIDispatch(v267, &v324) )
      {
        *((_QWORD *)v6 + 58) -= 24LL;
        v271 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v271 = *(_OWORD *)(v271 + 24 * (v269 + 1LL));
        *(_QWORD *)(v271 + 16) = *(_QWORD *)(v271 + 24 * (v269 + 1LL) + 16);
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, 8, 0, v268 + 1, *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
        v118 = v268 + 2;
        goto LABEL_121;
      }
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v143, *((VARIANTARG **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
      Adr = AssignVar(*(struct CSession **)v6, CurrentWithVar, (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * v268), 2u);
      CScriptRuntime::IfErrorHrLocal(v6, Adr, v140, v7);
      *((_QWORD *)v6 + 58) += 24LL * (v268 + 1);
      goto LABEL_19;
    case 43:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v241 = 0;
      v242 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v243 = *v242;
      *((_QWORD *)v6 + 59) = v242 + 1;
      v244 = v243;
      LODWORD(v245) = v243;
      goto LABEL_335;
    case 44:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v253 = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(v253);
      v254 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v255 = *v254;
      *((_QWORD *)v6 + 59) = v254 + 1;
      if ( !(unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        Adr = -2146828275;
        CScriptRuntime::IfErrorHrLocal(v6, -2146828275, 0, v7);
      }
      Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, 1, 0, v255, *((struct VAR **)v6 + 58));
      CScriptRuntime::IfErrorHrLocal(v6, Adr, 0, v7);
      *((_QWORD *)v6 + 58) += 24 * v255;
      goto LABEL_19;
    case 45:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v12 = 0;
      v135 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v136 = *v135;
      *((_QWORD *)v6 + 59) = v135 + 1;
      v13 = v136;
      v137 = v136;
      goto LABEL_145;
    case 46:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v140 = 0;
      v141 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v142 = *v141;
      *((_QWORD *)v6 + 59) = v141 + 1;
      LODWORD(v143) = v142;
      v144 = CurrentWithVar;
      v145 = v142;
      v146 = 0;
      v147 = v142;
      goto LABEL_153;
    case 47:
      v323 = *v10;
      v7 = v323;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v140 = 0;
      v265 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v266 = *v265;
      *((_QWORD *)v6 + 59) = v265 + 1;
      LODWORD(v143) = v266;
      v267 = CurrentWithVar;
      v268 = v266;
      v269 = v266;
      goto LABEL_373;
    case 48:
      v103 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v104 = *(unsigned __int16 *)(v8 + 5);
      v105 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v103);
      v106 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v107 = 24 * v104;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(24 * v104 + *((_QWORD *)v6 + 58)), &v324) )
      {
        v272 = (struct VAR *)(v107 + *((_QWORD *)v6 + 58));
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v272, 0, v106);
      }
      v108 = (struct VAR *)*((_QWORD *)v6 + 58);
      v109 = GrfdispCall(v106);
      v110 = SYM::InitFromSymbol((SYM *)&v328, v105);
      Adr = InvokeByName(*(struct CSession **)v6, v324, v110, v109, &pvargDest, v106, v108);
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)((char *)v108 + v107), v105, v106);
      *((_QWORD *)v6 + 58) += v107;
      goto LABEL_16;
    case 49:
      v111 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v112 = *(unsigned __int16 *)(v8 + 5);
      v113 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v111);
      v114 = (unsigned __int16)v10[2];
      *((_QWORD *)v6 + 59) = v10 + 3;
      v115 = 3 * v112;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24 * v112), &v324) )
      {
        v273 = *((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, (struct VAR *)(v273 + 8 * v115), 0, v114);
      }
      v116 = (struct VAR *)*((_QWORD *)v6 + 58);
      v117 = SYM::InitFromSymbol((SYM *)&v328, v113);
      Adr = InvokeByName(*(struct CSession **)v6, v324, v117, 1, 0, v114, v116);
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)((char *)v116 + 8 * v115), v113, v114);
      v118 = (unsigned int)(v114 + 1);
      goto LABEL_121;
    case 50:
      v274 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v275 = *(unsigned __int16 *)(v8 + 5);
      v276 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v274);
      v277 = (unsigned __int16)v10[2];
      *((_QWORD *)v6 + 59) = v10 + 3;
      v278 = 3 * v275;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24 * v275), &v324) )
      {
        v279 = *((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, (struct VAR *)(v279 + 8 * v278), 0, v277);
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      v280 = *((_QWORD *)v6 + 58);
      v281 = (unsigned int)(v277 + 1);
      *(_OWORD *)v280 = *(_OWORD *)(v280 + 24 * (v277 + 2));
      *(_QWORD *)(v280 + 16) = *(_QWORD *)(v280 + 24 * (v277 + 2) + 16);
      v282 = (struct VAR *)*((_QWORD *)v6 + 58);
      v283 = SYM::InitFromSymbol((SYM *)&v328, v276);
      v284 = 4;
      goto LABEL_380;
    case 51:
      v287 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v288 = *(unsigned __int16 *)(v8 + 5);
      v276 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v287);
      v277 = (unsigned __int16)v10[2];
      *((_QWORD *)v6 + 59) = v10 + 3;
      v289 = 3 * v288;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24 * v288), &v324) )
      {
        v285 = *((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, (struct VAR *)(v285 + 8 * v289), 0, v277);
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      v286 = *((_QWORD *)v6 + 58);
      v281 = (unsigned int)(v277 + 1);
      *(_OWORD *)v286 = *(_OWORD *)(v286 + 24 * (v277 + 2));
      *(_QWORD *)(v286 + 16) = *(_QWORD *)(v286 + 24 * (v277 + 2) + 16);
      v282 = (struct VAR *)*((_QWORD *)v6 + 58);
      v283 = SYM::InitFromSymbol((SYM *)&v328, v276);
      v284 = 8;
LABEL_380:
      Adr = InvokeByName(*(struct CSession **)v6, v324, v283, v284, 0, v281, v282);
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)((char *)v282 + 24 * v281), v276, v281);
      v118 = (unsigned int)(v277 + 3);
      goto LABEL_121;
    case 52:
      v290 = (unsigned __int16)*v10;
      v291 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v292 = 24 * v290;
      CurrentWithVar = (VAR *)(24 * v290 + *((_QWORD *)v6 + 58));
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        v293 = CurrentWithVar;
        pvargDest.vt = 0;
        v294 = (struct VAR *)*((_QWORD *)v6 + 58);
        v295 = GrfdispCall(v291);
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, v295, &pvargDest, v291, v294);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v293, 0, v291);
        *((_QWORD *)v6 + 58) += v292;
        goto LABEL_16;
      }
      v296 = CurrentWithVar;
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v291, *((VARIANTARG **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrArg(v6, Adr, v296, 0, v291);
      *((_QWORD *)v6 + 58) += v292;
      goto LABEL_386;
    case 53:
      v301 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v302 = v301;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v301);
      if ( !(unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        Adr = -2146828275;
        CScriptRuntime::IfErrorHr(v6, -2146828275);
      }
      v303 = CurrentWithVar;
      Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, 1, 0, v302, *((struct VAR **)v6 + 58));
      CScriptRuntime::IfErrorHrArg(v6, Adr, v303, 0, v302);
      v118 = (unsigned int)(v302 + 1);
      goto LABEL_121;
    case 54:
      v304 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v305 = v304;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v304);
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        v306 = CurrentWithVar;
        pvargDest.vt = 0;
        v307 = (struct VAR *)*((_QWORD *)v6 + 58);
        v308 = GrfdispCall(v305);
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, v308, &pvargDest, v305, v307);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v306, 0, v305);
      }
      else
      {
        v309 = CurrentWithVar;
        Adr = CScriptRuntime::LockArray(v6, &CurrentWithVar, CurrentWithVar, v305, *((VARIANTARG **)v6 + 58));
        CScriptRuntime::IfErrorHrArg(v6, Adr, v309, 0, v305);
        pvargDest.llVal = (LONGLONG)CurrentWithVar;
        pvargDest.vt = 16396;
      }
      *((_QWORD *)v6 + 58) += 24LL * (unsigned int)(v305 + 1) - 24;
      goto LABEL_16;
    case 55:
      v310 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v311 = (unsigned int)v310;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v310);
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        v312 = 4;
        goto LABEL_401;
      }
      v315 = CurrentWithVar;
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v311, *((VARIANTARG **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrArg(v6, Adr, v315, 0, v311);
      v316 = 1;
      goto LABEL_404;
    case 56:
      v319 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v311 = (unsigned int)v319;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v319);
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v324) )
      {
        v312 = 8;
LABEL_401:
        *((_QWORD *)v6 + 58) -= 24LL;
        v313 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v313 = *(_OWORD *)(v313 + 24 * (v311 + 2));
        *(_QWORD *)(v313 + 16) = *(_QWORD *)(v313 + 24 * (v311 + 2) + 16);
        v314 = CurrentWithVar;
        Adr = InvokeDispatch(*(struct CSession **)v6, v324, 0, v312, 0, (int)v311 + 1, *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrArg(v6, Adr, v314, 0, v311);
        v118 = (unsigned int)(v311 + 3);
      }
      else
      {
        v317 = CurrentWithVar;
        Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v311, *((VARIANTARG **)v6 + 58), 0);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v317, 0, v311);
        v316 = 2;
LABEL_404:
        v318 = CurrentWithVar;
        Adr = AssignVar(
                *(struct CSession **)v6,
                CurrentWithVar,
                (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * (unsigned int)(v311 + 1)),
                v316);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v318, 0, v311);
        v118 = (unsigned int)(v311 + 2);
      }
      goto LABEL_121;
    case 57:
      Adr = -2146827787;
      CScriptRuntime::IfErrorHr(v6, -2146827787);
      goto LABEL_19;
    case 58:
      v85 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      *((_QWORD *)v6 + 16) = *((_QWORD *)v6 + 58);
      v86 = v85 + *((_QWORD *)v6 + 60);
      *((_QWORD *)v6 + 59) = v86;
      *((_QWORD *)v6 + 15) = v86;
      goto LABEL_19;
    case 59:
      v40 = *(_DWORD *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v41 = (_WORD *)*((_QWORD *)v6 + 58);
      if ( *v41 == 11 )
      {
        CScriptRuntime::Branch(v6, (__int16)v41[4], v40, 1);
      }
      else
      {
        BoolValNull = GetBoolValNull(v41, v8, 0x8000);
        CScriptRuntime::Branch(v6, BoolValNull, v40, 1);
      }
      goto LABEL_19;
    case 60:
      v23 = *(_DWORD *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v24 = (_WORD *)*((_QWORD *)v6 + 58);
      if ( *v24 == 11 )
      {
        v25 = 0;
        v26 = v24[4] == 0;
      }
      else
      {
        v102 = GetBoolValNull(v24, v8, 0x8000);
        v25 = 0;
        v26 = v102 == 0;
      }
      LOBYTE(v25) = v26;
      goto LABEL_30;
    case 61:
      VbsVarNeg(*((struct VAR **)v6 + 58));
      goto LABEL_19;
    case 62:
      VbsVarOr((VARIANTARG *)(*((_QWORD *)v6 + 58) + 24LL), *((VARIANTARG **)v6 + 58));
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 63:
      VbsVarXor((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 64:
      VbsVarAnd((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 65:
      v63 = (VARIANTARG *)*((_QWORD *)v6 + 58);
      LogicalVal = VAR::PvarGetLogicalVal(v63);
      v63->vt = *(_WORD *)LogicalVal;
      v63->lVal = ~*((_DWORD *)LogicalVal + 2);
      goto LABEL_19;
    case 66:
      v57 = VbsVarRel(*((_QWORD *)v6 + 58) + 24LL);
      v58 = v57 == 0;
      goto LABEL_67;
    case 67:
      v57 = VbsVarRel(*((_QWORD *)v6 + 58) + 24LL);
      v59 = -(v57 != 0);
      goto LABEL_68;
    case 68:
      v57 = VbsVarRel(*((_QWORD *)v6 + 58) + 24LL);
      v58 = v57 == -1;
LABEL_67:
      v59 = !v58 - 1;
LABEL_68:
      *(_WORD *)(*((_QWORD *)v6 + 58) + 32LL) = v59;
      v60 = 1;
      if ( v57 != -2 )
        v60 = 11;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 24LL) = v60;
      goto LABEL_71;
    case 69:
      v50 = VbsVarRel(*((_QWORD *)v6 + 58) + 24LL);
      v51 = v50 + 1;
      goto LABEL_58;
    case 70:
      v50 = VbsVarRel(*((_QWORD *)v6 + 58) + 24LL);
      v51 = v50 - 1;
LABEL_58:
      v52 = -1;
      if ( v51 > 1 )
        v52 = 0;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 32LL) = v52;
      goto LABEL_61;
    case 71:
      v50 = VbsVarRel(*((_QWORD *)v6 + 58) + 24LL);
      v239 = -1;
      if ( v50 > 2 )
        v239 = 0;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 32LL) = v239;
LABEL_61:
      v53 = 1;
      if ( v50 != -2 )
        v53 = 11;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 24LL) = v53;
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 72:
      VbsVarAdd((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 73:
      VbsVarSub((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 74:
      VbsVarMul((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 75:
      VbsVarDiv((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 76:
      VbsVarMod((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 77:
      VbsVarEqv((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 78:
      VbsVarPow((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 79:
      VbsVarImp((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
      goto LABEL_71;
    case 80:
      *(_WORD *)(*((_QWORD *)v6 + 58) + 32LL) = VbsVarIs(
                                                  (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL),
                                                  *((struct VAR **)v6 + 58));
      *(_WORD *)(*((_QWORD *)v6 + 58) + 24LL) = 11;
      goto LABEL_71;
    case 81:
      Adr = -2146828253;
      CScriptRuntime::IfErrorHr(v6, -2146828253);
      goto LABEL_19;
    case 82:
      VbsVarConcat((VARIANTARG *)(*((_QWORD *)v6 + 58) + 24LL));
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 83:
      VbsVarIdiv((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL));
      goto LABEL_71;
    case 84:
      **((_WORD **)v6 + 58) |= 0x8000u;
      goto LABEL_19;
    case 85:
      v193 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v7 = *((_DWORD *)v10 + 1);
      v194 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v193);
      *((_QWORD *)v6 + 59) = v10 + 4;
      v195 = *((_BYTE *)v10 + 8);
      *((_QWORD *)v6 + 59) = (char *)v10 + 9;
      v196 = (struct NameTbl *)*((_QWORD *)v6 + 11);
      v323 = v7;
      if ( !v196 )
        v196 = (struct NameTbl *)*((_QWORD *)v6 + 13);
      Adr = CScriptRuntime::BindFunction(v6, v194, v7, v195, v196);
      CScriptRuntime::IfErrorHr(v6, Adr);
      COleScript::IncGeneration(*((COleScript **)v6 + 1));
      goto LABEL_19;
    case 86:
      v330 = 0;
      v197 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v7 = v10[2];
      v198 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v197);
      *((_QWORD *)v6 + 59) = v10 + 3;
      v199 = *((_BYTE *)v10 + 6);
      v323 = v7;
      *((_QWORD *)v6 + 59) = (char *)v10 + 7;
      SYM::InitFromSymbol((SYM *)&v328, v198);
      v200 = (NameTbl *)*((_QWORD *)v6 + 11);
      if ( !v200 )
        v200 = (NameTbl *)*((_QWORD *)v6 + 13);
      Adr = (*(__int64 (__fastcall **)(NameTbl *, __int128 *, unsigned int *))(*(_QWORD *)v200 + 152LL))(
              v200,
              &v328,
              &v330);
      CScriptRuntime::IfErrorHr(v6, Adr);
      if ( Adr || (v330 & 3) != 0 || (v199 != 0) != ((v330 >> 2) & 1) )
      {
        Adr = (*(__int64 (__fastcall **)(NameTbl *, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v200 + 120LL))(
                v200,
                &v328,
                v199 != 0 ? 4 : 0,
                0,
                0);
        CScriptRuntime::IfErrorHr(v6, Adr);
      }
      if ( v7 )
      {
        v201 = CScriptRuntime::PvarLocal(v6, v7);
        Adr = NameTbl::GetAdr(v200, (struct SYM *)&v328, v201);
        CScriptRuntime::IfErrorHr(v6, Adr);
      }
      goto LABEL_19;
    case 87:
      v97 = v337;
      if ( !v337 )
        goto LABEL_103;
      v119 = CScriptRuntime::PvarLocal(v6, 0);
      CurrentWithVar = v119;
      if ( *(_WORD *)v119 == 16396 )
      {
LABEL_102:
        *(_WORD *)v97 = 0;
      }
      else
      {
        *(_OWORD *)v97 = *(_OWORD *)v119;
        *((_QWORD *)v97 + 2) = *((_QWORD *)v119 + 2);
        *(_WORD *)CurrentWithVar = 0;
        if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v97) )
        {
          GcContext::FreeToMark(*((GcContext **)v6 + 6), *((_DWORD *)v6 + 14));
          Adr = VAR::MoveToHeap(v97, *((struct GcContext **)v6 + 6));
          if ( Adr >= 0 )
            *((_DWORD *)v6 + 14) = *(_DWORD *)(*((_QWORD *)v6 + 6) + 24LL);
        }
      }
      goto LABEL_103;
    case 88:
      v320 = v337;
      if ( v337 )
      {
        Adr = AssignVar(*(struct CSession **)v6, v337, *((struct VAR **)v6 + 58), 0);
        CScriptRuntime::IfErrorHr(v6, Adr);
        if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v320) )
        {
          GcContext::FreeToMark(*((GcContext **)v6 + 6), *((_DWORD *)v6 + 14));
          Adr = VAR::MoveToHeap(v320, *((struct GcContext **)v6 + 6));
          if ( Adr >= 0 )
            *((_DWORD *)v6 + 14) = *(_DWORD *)(*((_QWORD *)v6 + 6) + 24LL);
        }
      }
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_103;
    case 89:
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    case 90:
      v167 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v168 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v167);
      if ( _wcsicmp(L"regexp", v168) )
      {
        pvargDest.vt = 0;
        CScriptRuntime::GetVarAdr(v6, v168, (struct VAR *)&pvargDest);
        if ( !(unsigned int)VAR::IsClass((VAR *)&pvargDest, &v325) )
        {
          Adr = -2146827782;
          CScriptRuntime::IfErrorHrPsz(v6, -2146827782, v168);
        }
        *((_QWORD *)v6 + 58) -= 24LL;
        **((_WORD **)v6 + 58) = 0;
        Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v325 + 32LL))(
                v325,
                *((_QWORD *)v6 + 58),
                0,
                0,
                0,
                0);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v168);
        v170 = VAR::PvarCutAll(*((VAR **)v6 + 58));
        VBScriptClass::InitializeClass(*((VBScriptClass **)v170 + 1));
      }
      else
      {
        v338 = 0;
        Adr = CRegExp::Create(&v338);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v168);
        pvargDest.vt = 9;
        pvargDest.llVal = (LONGLONG)v338;
        *((_QWORD *)v6 + 58) -= 24LL;
        *(VARIANTARG *)*((_QWORD *)v6 + 58) = pvargDest;
        v169 = VAR::MoveToHeap((VAR *)&pvargDest);
        Adr = v169;
        if ( v169 < 0 )
          CScriptRuntime::IfErrorHrPsz(v6, v169, v168);
      }
      goto LABEL_19;
    case 91:
      v335 = 0;
      v171 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      Adr = VBScriptClass::Create(
              (struct VBScriptClass **)&v335,
              *(struct CSession **)v6,
              (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v171));
      CScriptRuntime::IfErrorHr(v6, Adr);
      *((_QWORD *)v6 + 58) -= 24LL;
      Adr = VAR::SetHeapIDispatch(*((VAR **)v6 + 58), v335);
      ((void (__fastcall *)(struct IDispatch *))v335->lpVtbl->Release)(v335);
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_19;
    case 92:
      v172 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v7 = *(_DWORD *)(v8 + 5);
      v173 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v172);
      *((_QWORD *)v6 + 59) = v8 + 9;
      v174 = v8[9];
      *((_QWORD *)v6 + 59) = v8 + 10;
      v175 = (VAR *)*((_QWORD *)v6 + 58);
      v323 = v7;
      v176 = VAR::PvarCutAll(v175);
      Adr = CScriptRuntime::BindFunction(v6, v173, v7, v174, *((struct NameTbl **)v176 + 1));
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_19;
    case 93:
      v177 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v178 = *((_BYTE *)v10 + 4);
      v179 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v177);
      *((_QWORD *)v6 + 59) = (char *)v10 + 5;
      SYM::InitFromSymbol((SYM *)&v328, v179);
      v180 = VAR::PvarCutAll(*((VAR **)v6 + 58));
      Adr = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v180 + 1) + 120LL))(
              *((_QWORD *)v180 + 1),
              &v328,
              v178 != 0 ? 0xC : 0,
              0,
              0);
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_19;
    case 94:
      v181 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v182 = *(unsigned __int16 *)(v8 + 5);
      v183 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v181);
      v184 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v185 = MakeArray(v182, *((struct VAR **)v6 + 58), (const unsigned __int16 *)0x8000, (int)v10);
      v186 = v185;
      if ( v185 )
        v185->fFeatures |= 0x12u;
      *((_QWORD *)v6 + 58) += 24 * v184;
      SYM::InitFromSymbol((SYM *)&v328, v183);
      v187 = VAR::PvarCutAll(*((VAR **)v6 + 58));
      Adr = NameTbl::GetAdr(*((NameTbl **)v187 + 1), (struct SYM *)&v328, (struct VAR *)&pvargDest);
      CurrentWithVar = (VAR *)pvargDest.llVal;
      if ( pvargDest.llVal )
      {
        *(_QWORD *)(pvargDest.llVal + 8) = pvargDest.llVal + 16;
        *((_QWORD *)CurrentWithVar + 2) = v186;
        *(_WORD *)CurrentWithVar = 24588;
      }
      goto LABEL_19;
    case 95:
      v188 = CScriptRuntime::WithPush(v6, *((struct VAR **)v6 + 58));
      CScriptRuntime::IfErrorHr(v6, v188);
      goto LABEL_71;
    case 96:
    case 97:
      VAR::Clear((VAR *)(*((_QWORD *)v6 + 8) + 24LL * (int)--*((_DWORD *)v6 + 15)));
      goto LABEL_19;
    case 98:
    case 99:
      v73 = *v8;
      v74 = *v10;
      v323 = v74;
      *((_QWORD *)v6 + 59) = v10 + 1;
      v75 = CScriptRuntime::PvarLocal(v6, v74);
      v76 = VAR::PvarCutRef(v75);
      v77 = (__int16 *)*((_QWORD *)v6 + 59);
      v78 = v76;
      v79 = *v77;
      *((_QWORD *)v6 + 59) = v77 + 1;
      v80 = (struct VAR *)(*((_QWORD *)v6 + 9) - 24 * v79);
      v81 = v77[1];
      *((_QWORD *)v6 + 59) = v77 + 2;
      v82 = (struct VAR *)(*((_QWORD *)v6 + 9) - 24 * v81);
      v83 = v73 == 98;
      goto LABEL_84;
    case 100:
    case 101:
      v92 = *v8;
      v93 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v94 = *(__int16 *)(v8 + 5);
      v95 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v93);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v80 = (struct VAR *)(*((_QWORD *)v6 + 9) - 24 * v94);
      v96 = *(__int16 *)(v8 + 7);
      *((_QWORD *)v6 + 59) = v8 + 9;
      v82 = (struct VAR *)(*((_QWORD *)v6 + 9) - 24 * v96);
      CScriptRuntime::GetVarAdr(v6, v95, (struct VAR *)&pvargDest);
      if ( pvargDest.vt != 16396 )
      {
        Adr = -2146827787;
        CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v95);
      }
      v78 = (struct VAR *)pvargDest.llVal;
      v83 = v92 == 100;
LABEL_84:
      v7 = 17;
      if ( !v83 )
        v7 = 0;
      v323 = v7;
      if ( v7 == 17 )
      {
        ForLoopInit(v80, v82, *((struct VAR **)v6 + 58), v78);
        *((_QWORD *)v6 + 58) += 72LL;
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      memset(&v346, 0, sizeof(v346));
      v346 = *(VARIANTARG *)v78;
      **((_WORD **)v6 + 58) = 11;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = ExNextVar((VARIANTARG *)v80, (VARIANTARG *)v82, &v346, v7);
      v84 = VAR::SafeVariantShallowCopy(v78, (struct VAR *)&v346);
      Adr = v84;
      if ( v84 < 0 )
        CScriptRuntime::RaiseErrorHr(v6, v84, v78, 0, -1);
      goto LABEL_19;
    case 102:
      v65 = *(_BYTE *)v10;
      *((_QWORD *)v6 + 59) = v8 + 2;
      if ( v65 )
        *((_DWORD *)v6 + 126) |= 1u;
      else
        *((_DWORD *)v6 + 126) &= ~1u;
      CSession::FreeError(*(CSession **)v6);
      goto LABEL_19;
    case 103:
      v23 = *(_DWORD *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      if ( (unsigned int)VbsVarRel(*((_QWORD *)v6 + 58) + 24LL) )
        goto LABEL_71;
      v27 = 2;
      v25 = 1;
      goto LABEL_31;
    case 104:
      v23 = *(_DWORD *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      if ( (unsigned int)VbsVarRel(*((_QWORD *)v6 + 58) + 24LL) )
      {
        v25 = 1;
LABEL_30:
        v27 = 1;
LABEL_31:
        CScriptRuntime::Branch(v6, v25, v23, v27);
      }
      else
      {
LABEL_270:
        *((_QWORD *)v6 + 58) += 48LL;
      }
      goto LABEL_19;
    case 105:
    case 106:
      v42 = *v8;
      v43 = *v10;
      v323 = v43;
      *((_QWORD *)v6 + 59) = v10 + 1;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v43);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v44 = (__int16 *)*((_QWORD *)v6 + 59);
      v45 = *v44;
      *((_QWORD *)v6 + 59) = v44 + 1;
      v46 = (struct CEnumArray **)(*((_QWORD *)v6 + 9) - 24 * v45);
      v47 = v44[1];
      v7 = v44[1];
      v323 = v7;
      *((_QWORD *)v6 + 59) = v44 + 2;
      v48 = *((_QWORD *)v6 + 9) - 24 * v47;
      if ( v42 == 106 )
        goto LABEL_50;
      goto LABEL_105;
    case 107:
    case 108:
      v151 = *v8;
      v152 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v153 = *(__int16 *)(v8 + 5);
      v154 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v152);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v46 = (struct CEnumArray **)(*((_QWORD *)v6 + 9) - 24 * v153);
      v155 = *(__int16 *)(v8 + 7);
      v7 = *(__int16 *)(v8 + 7);
      v323 = v7;
      *((_QWORD *)v6 + 59) = v8 + 9;
      v48 = *((_QWORD *)v6 + 9) - 24 * v155;
      CScriptRuntime::GetVarAdr(v6, v154, (struct VAR *)&pvargDest);
      if ( pvargDest.vt != 16396 )
      {
        Adr = -2146827787;
        CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v154);
      }
      CurrentWithVar = (VAR *)pvargDest.llVal;
      if ( *pvargDest.bstrVal != 24588 )
      {
        if ( v151 == 107 )
        {
LABEL_105:
          IsIDispatch = VAR::IsIDispatch(*((VAR **)v6 + 58), &v324);
          v100 = (VARIANTARG *)*((_QWORD *)v6 + 58);
          if ( IsIDispatch )
          {
            Adr = InvokeDispatch(*(struct CSession **)v6, v324, -4, 3, v100, 0, 0);
            CScriptRuntime::IfErrorHr(v6, Adr);
            Adr = AssignVar(*(struct CSession **)v6, (struct VAR *)v46, *((struct VAR **)v6 + 58), 0);
            CScriptRuntime::IfErrorHr(v6, Adr);
            if ( ((*(_WORD *)v46 - 9) & 0xFFFB) != 0
              || (v138 = v46[1]) == 0
              || (**(int (__fastcall ***)(struct CEnumArray *, GUID *, struct CEnumArray **))v138)(
                   v138,
                   &IID_IEnumVARIANT,
                   &v326) < 0 )
            {
              Adr = -2146827837;
              CScriptRuntime::IfErrorHr(v6, -2146827837);
            }
            (*(void (__fastcall **)(struct CEnumArray *))(*(_QWORD *)v46[1] + 16LL))(v46[1]);
            v46[1] = v326;
            *(_WORD *)v46 = 77;
            v139 = v324;
            *(_QWORD *)(v48 + 8) = v324;
            *(_WORD *)v48 = 9;
            ((void (__fastcall *)(struct IDispatch *))v139->lpVtbl->AddRef)(v139);
          }
          else if ( (unsigned int)VAR::IsArray((VAR *)v100) )
          {
            Adr = CEnumArray::Create(*((struct VAR **)v6 + 58), &v326);
            CScriptRuntime::IfErrorHr(v6, Adr);
            v46[1] = v326;
            *(_WORD *)v46 = 77;
          }
          else
          {
            Adr = -2146827837;
            CScriptRuntime::IfErrorHr(v6, -2146827837);
          }
        }
        else
        {
LABEL_50:
          if ( *(_WORD *)v46 != 77 )
          {
            Adr = -2146827837;
            CScriptRuntime::IfErrorHr(v6, -2146827837);
          }
          v326 = v46[1];
          *((_QWORD *)v6 + 58) -= 24LL;
        }
        **((_WORD **)v6 + 58) = 11;
        *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = 0;
        pvargDest.vt = 0;
        Adr = VAR::Clear(CurrentWithVar);
        CScriptRuntime::IfErrorHr(v6, Adr);
        Adr = (*(__int64 (__fastcall **)(struct CEnumArray *, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)v326 + 24LL))(
                v326,
                1,
                &pvargDest,
                0);
        CScriptRuntime::IfErrorHr(v6, Adr);
        if ( !Adr )
          *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = -1;
        v49 = VAR::SafeVariantShallowCopy(CurrentWithVar, (struct VAR *)&pvargDest);
        Adr = v49;
        if ( v49 < 0 )
          CScriptRuntime::RaiseErrorHr(v6, v49, CurrentWithVar, 0, -1);
        goto LABEL_19;
      }
      return CSession::RecordHr(*(CSession **)v6, -2147352571, (struct VAR *)pvargDest.llVal, 0, -1);
    case 109:
      v69 = *v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v70 = (VAR *)(*((_QWORD *)v6 + 9) - 24 * v69);
      v71 = *(__int16 *)(v8 + 3);
      v7 = v10[1];
      v323 = v7;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v72 = (VAR *)(*((_QWORD *)v6 + 9) - 24 * v71);
      VAR::Clear(v70);
      VAR::Clear(v72);
      goto LABEL_19;
    case 110:
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL) )
        CScriptRuntime::IfErrorHr(v6, -2146828281);
      CurrentWithVar = VAR::PvarCutAll(*((VAR **)v6 + 58));
      v160 = *((_QWORD *)CurrentWithVar + 2);
      v161 = *(_QWORD *)(*(_QWORD *)v6 + 32LL);
      v343 = *(_OWORD *)CurrentWithVar;
      v344 = v160;
      v162 = *(_QWORD *)(v161 + 136);
      v341 = v343;
      v342 = v160;
      v163 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v162 + 208LL))(v162, &v341);
      goto LABEL_191;
    case 111:
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL) )
        CScriptRuntime::IfErrorHr(v6, -2146828281);
      v165 = (_WORD *)*((_QWORD *)v6 + 58);
      if ( *v165 == 2 )
      {
        v166 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL);
        v163 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v166 + 216LL))(v166, (unsigned __int16)v165[4]);
      }
      else
      {
        CurrentWithVar = VAR::PvarGetTypeVal(*((VARIANTARG **)v6 + 58), 2u);
        v164 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL);
        v163 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v164 + 216LL))(
                 v164,
                 *((unsigned __int16 *)CurrentWithVar + 4));
      }
LABEL_191:
      CScriptRuntime::IfResponseError(v6, v163);
LABEL_71:
      *((_QWORD *)v6 + 58) += 24LL;
      goto LABEL_19;
    default:
      Adr = -2146828237;
      CScriptRuntime::IfErrorHr(v6, -2146828237);
      goto LABEL_19;
  }
}

```

## disassembly

```asm
0x18001f0f0  mov     [rsp-8+arg_10], rbx
0x18001f0f5  push    rbp
0x18001f0f6  push    rsi
0x18001f0f7  push    rdi
0x18001f0f8  push    r12
0x18001f0fa  push    r13
0x18001f0fc  push    r14
0x18001f0fe  push    r15
0x18001f100  lea     rbp, [rsp-0E0h]
0x18001f108  sub     rsp, 1E0h
0x18001f10f  mov     rax, cs:__security_cookie
0x18001f116  xor     rax, rsp
0x18001f119  mov     [rbp+110h+var_38], rax
0x18001f120  mov     [rsp+210h+var_1D0], 0
0x18001f128  mov     r8, rcx
0x18001f12b  mov     rax, [rcx+30h]
0x18001f12f  xorps   xmm0, xmm0
0x18001f132  mov     [rbp+110h+var_140], rcx
0x18001f136  xorps   xmm1, xmm1
0x18001f139  mov     [rbp+110h+var_158], rdx
0x18001f13d  mov     rdx, rsp
0x18001f140  mov     [rbp+110h+var_174], 0
0x18001f147  mov     ecx, [rax+18h]
0x18001f14a  xor     eax, eax
0x18001f14c  mov     [rbp+110h+var_188], rax
0x18001f150  mov     [rsp+210h+var_1C8], rax
0x18001f155  mov     [rsp+210h+var_1B8], rax
0x18001f15a  mov     [rsp+210h+var_1B0], rax
0x18001f15f  mov     qword ptr [rbp+110h+pvargDest+10h], rax
0x18001f163  mov     [rsp+210h+var_1A8], rax
0x18001f168  mov     [rbp+110h+var_88], rax
0x18001f16f  mov     qword ptr [rbp+110h+var_E0+10h], rax
0x18001f173  mov     [rbp+110h+var_17C], eax
0x18001f176  mov     [rsp+210h+var_1C0], eax
0x18001f17a  lea     rax, [rsp+210h+var_1D0]
0x18001f17f  movups  [rsp+210h+var_198], xmm0
0x18001f184  mov     [rbp+110h+var_178], ecx
0x18001f187  lea     rcx, [r8+0B0h]; Buf
0x18001f18e  movups  xmmword ptr [rbp+110h+pvargDest], xmm0
0x18001f192  movups  [rbp+110h+var_98], xmm0
0x18001f196  movups  xmmword ptr [rbp+110h+var_E0], xmm1
0x18001f19a  mov     [r8+238h], rax
0x18001f1a1  lea     rax, [rbp+110h+var_174]
0x18001f1a5  mov     [r8+230h], rax
0x18001f1ac  call    _setjmp_0
0x18001f1b1  mov     rsi, [rbp+110h+var_140]
0x18001f1b5  lea     rbx, __ImageBase
0x18001f1bc  mov     r10d, 0FFFFFFFFh
0x18001f1c2  test    eax, eax
0x18001f1c4  jnz     loc_18002066E
0x18001f1ca  mov     r13d, [rsp+210h+var_1C0]
0x18001f1cf  mov     r8d, 8000h
0x18001f1d5  mov     r11d, 8
0x18001f1db  mov     r14d, 0Bh
0x18001f1e1  mov     r12d, 1
0x18001f1e7  mov     r15d, 400Ch
0x18001f1ed  mov     edi, 2
0x18001f1f2  mov     rdx, [rsi+1D8h]
0x18001f1f9  movzx   eax, byte ptr [rdx]
0x18001f1fc  lea     r9, [rdx+1]
0x18001f200  mov     [rsi+1D8h], r9
0x18001f207  cmp     eax, 19h
0x18001f20a  jz      loc_18001F350
0x18001f210  cmp     eax, 3
0x18001f213  jz      loc_18001F3C6
0x18001f219  cmp     eax, 6Fh; switch 112 cases
0x18001f21c  ja      def_18001F22C; jumptable 000000018001F22C default case, cases 3,25
0x18001f222  mov     ecx, ds:(jpt_18001F22C - 180000000h)[rbx+rax*4]
0x18001f229  add     rcx, rbx
0x18001f22c  jmp     rcx; switch jump
0x18001f232  mov     r14d, [r9]; jumptable 000000018001F22C case 40
0x18001f235  lea     rcx, [r9+4]
0x18001f239  mov     [rsi+1D8h], rcx
0x18001f240  lea     rax, [r9+6]
0x18001f244  add     r14, [rsi+1F0h]
0x18001f24b  lea     r8, [rbp+110h+pvargDest]; struct VAR *
0x18001f24f  movzx   edi, word ptr [rcx]
0x18001f252  mov     rdx, r14; unsigned __int16 *
0x18001f255  mov     rcx, rsi; this
0x18001f258  mov     [rsi+1D8h], rax
0x18001f25f  call    ?GetVarAdr@CScriptRuntime@@AEAAHPEBGPEAVVAR@@@Z; CScriptRuntime::GetVarAdr(ushort const *,VAR *)
0x18001f264  lea     rcx, [rbp+110h+pvargDest]; this
0x18001f268  mov     ebx, eax
0x18001f26a  call    ?IsDispmember@VAR@@QEAAHXZ; VAR::IsDispmember(void)
0x18001f26f  test    eax, eax
0x18001f271  jnz     loc_180021EFC
0x18001f277  lea     rcx, [rbp+110h+pvargDest]; this
0x18001f27b  call    ?PvarCutRef@VAR@@QEAAPEAV1@XZ; VAR::PvarCutRef(void)
0x18001f280  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x18001f285  mov     [rsp+210h+var_1C8], rax
0x18001f28a  mov     rcx, rax; this
0x18001f28d  call    ?IsFunction@VAR@@QEAAHPEAPEAVIEntryPoint@@@Z; VAR::IsFunction(IEntryPoint * *)
0x18001f292  test    eax, eax
0x18001f294  jz      loc_180021F39
0x18001f29a  mov     rcx, [rsp+210h+var_1B0]
0x18001f29f  mov     rax, [rcx]
0x18001f2a2  mov     rax, [rax+10h]
0x18001f2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ab  test    eax, eax
0x18001f2ad  jnz     loc_18001FDC9
0x18001f2b3  xor     eax, eax
0x18001f2b5  mov     word ptr [rbp+110h+pvargDest], ax
0x18001f2b9  test    ebx, ebx
0x18001f2bb  jnz     loc_180021F5E
0x18001f2c1  mov     rcx, [rsp+210h+var_1B0]
0x18001f2c6  mov     rax, [rcx]
0x18001f2c9  mov     rax, [rax]
0x18001f2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2d1  mov     rcx, [rsp+210h+var_1B0]
0x18001f2d6  lea     rdx, [rbp+110h+pvargDest]
0x18001f2da  mov     r9, [rsi+1D0h]
0x18001f2e1  mov     r8d, edi
0x18001f2e4  mov     [rsp+210h+var_1E8], ebx
0x18001f2e8  mov     [rsp+210h+pvarSrc], 0
0x18001f2f1  mov     rax, [rcx]
0x18001f2f4  mov     rax, [rax+20h]
0x18001f2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2fd  mov     rcx, [rsp+210h+var_1B0]
0x18001f302  mov     [rsp+210h+var_1D0], eax
0x18001f306  mov     rax, [rcx]
0x18001f309  mov     rax, [rax+8]
0x18001f30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f312  mov     edx, [rsp+210h+var_1D0]; int
0x18001f316  mov     r8, r14; unsigned __int16 *
0x18001f319  mov     rcx, rsi; this
0x18001f31c  call    ?IfErrorHrPsz@CScriptRuntime@@AEAAXJPEBG@Z; CScriptRuntime::IfErrorHrPsz(long,ushort const *)
0x18001f321  mov     eax, edi
0x18001f323  lea     rcx, [rax+rax*2]
0x18001f327  lea     rcx, ds:0FFFFFFFFFFFFFFE8h[rcx*8]
0x18001f32f  add     [rsi+1D0h], rcx
0x18001f336  mov     rax, [rsi+1D0h]
0x18001f33d  movups  xmm0, xmmword ptr [rbp+110h+pvargDest]
0x18001f341  movups  xmmword ptr [rax], xmm0
0x18001f344  movsd   xmm1, qword ptr [rbp+110h+pvargDest+10h]
0x18001f349  movsd   qword ptr [rax+10h], xmm1
0x18001f34e  jmp     short loc_18001F39B
0x18001f350  movsx   ecx, word ptr [r9]
0x18001f354  lea     rax, [r9+2]
0x18001f358  mov     r13d, ecx
0x18001f35b  mov     [rsp+210h+var_1C0], ecx
0x18001f35f  mov     edx, ecx; int
0x18001f361  mov     [rsi+1D8h], rax
0x18001f368  mov     rcx, rsi; this
0x18001f36b  call    ?PvarLocal@CScriptRuntime@@AEAAPEAVVAR@@H@Z; CScriptRuntime::PvarLocal(int)
0x18001f370  mov     [rsp+210h+var_1C8], rax
0x18001f375  add     qword ptr [rsi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18001f37d  mov     rcx, [rsp+210h+var_1C8]
0x18001f382  mov     rax, [rsi+1D0h]
0x18001f389  cmp     [rcx], r15w
0x18001f38d  jz      loc_18001F676
0x18001f393  mov     [rax], r15w
0x18001f397  mov     [rax+8], rcx
0x18001f39b  mov     r10d, 0FFFFFFFFh
0x18001f3a1  mov     r8d, 8000h
0x18001f3a7  mov     r11d, 8
0x18001f3ad  cmp     cs:?vbs_interpreter_override_bailout@@3_NA, 0; jumptable 000000018001F22C cases 0,2
0x18001f3b4  jnz     loc_180022CA9
0x18001f3ba  lea     rbx, __ImageBase
0x18001f3c1  jmp     loc_18001F1DB
0x18001f3c6  movzx   ecx, byte ptr [r9]
0x18001f3ca  lea     rax, [r9+1]
0x18001f3ce  mov     [rsi+1D8h], rax
0x18001f3d5  mov     [rsi+1E8h], ecx
0x18001f3db  mov     rcx, [rsi]; this
0x18001f3de  call    ?FInterrupt@CSession@@QEAAHXZ; CSession::FInterrupt(void)
0x18001f3e3  test    eax, eax
0x18001f3e5  jnz     loc_180022BA6
0x18001f3eb  mov     rcx, [rsi+30h]; this
0x18001f3ef  mov     eax, [rbp+110h+var_178]
0x18001f3f2  cmp     eax, [rcx+18h]
0x18001f3f5  jl      short loc_18001F447
0x18001f3f7  mov     rcx, [rsi]; this
0x18001f3fa  call    ?PollHalt@CSession@@QEAAJXZ; CSession::PollHalt(void)
0x18001f3ff  mov     [rsp+210h+var_1D0], eax
0x18001f403  test    eax, eax
0x18001f405  jns     short loc_18001F39B
0x18001f407  jmp     loc_18001FD08
0x18001f40c  mov     ebx, [r9]; jumptable 000000018001F22C case 60
0x18001f40f  lea     rax, [r9+4]
0x18001f413  mov     [rsi+1D8h], rax
0x18001f41a  mov     rcx, [rsi+1D0h]
0x18001f421  cmp     word ptr [rcx], 0Bh
0x18001f425  jnz     loc_18001FE48
0x18001f42b  xor     edx, edx
0x18001f42d  cmp     [rcx+8], dx
0x18001f431  setz    dl; int
0x18001f434  mov     r9d, r12d; int
0x18001f437  mov     r8d, ebx; unsigned int
0x18001f43a  mov     rcx, rsi; this
0x18001f43d  call    ?Branch@CScriptRuntime@@AEAAXHIH@Z; CScriptRuntime::Branch(int,uint,int)
0x18001f442  jmp     loc_18001F39B
0x18001f447  mov     edx, eax; int
0x18001f449  call    ?FreeToMark@GcContext@@QEAAXJ@Z; GcContext::FreeToMark(long)
0x18001f44e  jmp     short loc_18001F3F7
0x18001f450  add     qword ptr [rsi+1D0h], 0FFFFFFFFFFFFFFE8h; jumptable 000000018001F22C case 11
0x18001f458  mov     rax, [rsi+1D0h]
0x18001f45f  mov     [rax], di
0x18001f462  mov     rax, [rsi+1D8h]
0x18001f469  movsx   ecx, byte ptr [rax]
0x18001f46c  inc     rax
0x18001f46f  mov     [rsi+1D8h], rax
0x18001f476  mov     rax, [rsi+1D0h]
0x18001f47d  mov     [rax+8], cx
0x18001f481  jmp     loc_18001F3AD; jumptable 000000018001F22C cases 0,2
0x18001f486  mov     [rbp+110h+var_148], 0; jumptable 000000018001F22C cases 28,29
0x18001f48e  lea     rax, [r9+4]
0x18001f492  movzx   r14d, byte ptr [rdx]
0x18001f496  lea     r8, [rbp+110h+var_148]; struct CScriptRuntime **
0x18001f49a  mov     ebx, [r9]
0x18001f49d  mov     [rsi+1D8h], rax
0x18001f4a4  xor     eax, eax
0x18001f4a6  add     rbx, [rsi+1F0h]
0x18001f4ad  add     qword ptr [rsi+1D0h], 0FFFFFFFFFFFFFFE8h
0x18001f4b5  mov     rdx, rbx; unsigned __int16 *
0x18001f4b8  mov     rcx, [rsi+1D0h]
0x18001f4bf  mov     [rcx], ax
0x18001f4c2  mov     rcx, rsi; this
0x18001f4c5  call    ?FUseLocalInEval@CScriptRuntime@@AEAAHPEBGPEAPEAV1@@Z; CScriptRuntime::FUseLocalInEval(ushort const *,CScriptRuntime * *)
0x18001f4ca  test    eax, eax
0x18001f4cc  jnz     loc_180021167
0x18001f4d2  mov     r8, [rsi+1D0h]; struct VAR *
0x18001f4d9  mov     rdx, rbx; unsigned __int16 *
0x18001f4dc  mov     rcx, rsi; this
0x18001f4df  call    ?GetVarAdr@CScriptRuntime@@AEAAHPEBGPEAVVAR@@@Z; CScriptRuntime::GetVarAdr(ushort const *,VAR *)
0x18001f4e4  mov     rcx, [rsi+1D0h]; this
0x18001f4eb  mov     edi, eax
0x18001f4ed  call    ?IsDispmember@VAR@@QEAAHXZ; VAR::IsDispmember(void)
0x18001f4f2  mov     rcx, [rsi+1D0h]; this
0x18001f4f9  test    eax, eax
0x18001f4fb  jnz     loc_1800211AF
0x18001f501  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x18001f506  call    ?IsFunction@VAR@@QEAAHPEAPEAVIEntryPoint@@@Z; VAR::IsFunction(IEntryPoint * *)
0x18001f50b  test    eax, eax
0x18001f50d  jnz     loc_180021209
0x18001f513  mov     rcx, [rsi+1D0h]; this
0x18001f51a  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x18001f51f  mov     r8d, 4; unsigned __int16
0x18001f525  call    ?IsProperty@VAR@@QEAAHPEAPEAVIEntryPoint@@G@Z; VAR::IsProperty(IEntryPoint * *,ushort)
0x18001f52a  test    eax, eax
0x18001f52c  jnz     loc_180021209
0x18001f532  mov     rcx, [rsi+1D0h]; this
0x18001f539  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x18001f53e  call    ?IsClass@VAR@@QEAAHPEAPEAVIEntryPoint@@@Z; VAR::IsClass(IEntryPoint * *)
0x18001f543  test    eax, eax
0x18001f545  jnz     loc_1800211EC
0x18001f54b  mov     rcx, [rsi+1D0h]; this
0x18001f552  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x18001f557  mov     r8d, r12d; unsigned __int16
0x18001f55a  call    ?IsProperty@VAR@@QEAAHPEAPEAVIEntryPoint@@G@Z; VAR::IsProperty(IEntryPoint * *,ushort)
0x18001f55f  test    eax, eax
0x18001f561  jnz     loc_1800211EC
0x18001f567  mov     rcx, [rsi+1D0h]; this
0x18001f56e  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x18001f573  mov     r8d, 2; unsigned __int16
0x18001f579  call    ?IsProperty@VAR@@QEAAHPEAPEAVIEntryPoint@@G@Z; VAR::IsProperty(IEntryPoint * *,ushort)
0x18001f57e  test    eax, eax
0x18001f580  jnz     loc_1800211EC
0x18001f586  cmp     r14b, 1Ch
0x18001f58a  jnz     loc_18001F39B
0x18001f590  jmp     loc_18002277C
0x18001f595  mov     rax, [rsi+1D0h]; jumptable 000000018001F22C case 84
0x18001f59c  or      [rax], r8w
0x18001f5a0  jmp     loc_18001F3AD; jumptable 000000018001F22C cases 0,2
0x18001f5a5  mov     edi, [r9]; jumptable 000000018001F22C case 35
0x18001f5a8  lea     rax, [r9+4]
0x18001f5ac  mov     [rsi+1D8h], rax
0x18001f5b3  lea     rdx, [rsp+210h+var_1B8]; struct IDispatch **
0x18001f5b8  mov     rcx, [rsi+1D0h]; this
0x18001f5bf  add     rdi, [rsi+1F0h]
0x18001f5c6  call    ?IsIDispatch@VAR@@QEAAHPEAPEAUIDispatch@@@Z; VAR::IsIDispatch(IDispatch * *)
0x18001f5cb  test    eax, eax
0x18001f5cd  jz      loc_18002134E
0x18001f5d3  mov     rcx, [rsi+1D0h]
0x18001f5da  xor     eax, eax
0x18001f5dc  mov     rdx, rdi; unsigned __int16 *
0x18001f5df  mov     [rcx], ax
0x18001f5e2  lea     rcx, [rsp+210h+var_198]; this
0x18001f5e7  mov     rbx, [rsi+1D0h]
0x18001f5ee  call    ?InitFromSymbol@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromSymbol(ushort const *)
0x18001f5f3  mov     rdx, [rsp+210h+var_1B8]; struct IDispatch *
0x18001f5f8  mov     r9d, 3; unsigned int
0x18001f5fe  mov     rcx, [rsi]; struct CSession *
0x18001f601  mov     r8, rax; struct SYM *
0x18001f604  mov     [rsp+210h+var_1E0], 0; struct VAR *
0x18001f60d  mov     [rsp+210h+var_1E8], 0; int
0x18001f615  mov     [rsp+210h+pvarSrc], rbx; struct VAR *
0x18001f61a  call    ?InvokeByName@@YAJPEAVCSession@@PEAUIDispatch@@PEAUSYM@@KPEAVVAR@@H3@Z; InvokeByName(CSession *,IDispatch *,SYM *,ulong,VAR *,int,VAR *)
0x18001f61f  mov     r9, rdi; unsigned __int16 *
0x18001f622  mov     [rsp+210h+var_1D0], eax
0x18001f626  mov     r8, rbx; struct VAR *
0x18001f629  mov     dword ptr [rsp+210h+pvarSrc], 0; int
0x18001f631  mov     edx, eax; int
0x18001f633  mov     rcx, rsi; this
0x18001f636  call    ?IfErrorHrArg@CScriptRuntime@@AEAAXJPEAVVAR@@PEBGH@Z; CScriptRuntime::IfErrorHrArg(long,VAR *,ushort const *,int)
0x18001f63b  jmp     loc_18001F39B
0x18001f640  mov     ebx, [r9]; jumptable 000000018001F22C case 59
0x18001f643  lea     rax, [r9+4]
0x18001f647  mov     [rsi+1D8h], rax
0x18001f64e  mov     rcx, [rsi+1D0h]
0x18001f655  cmp     word ptr [rcx], 0Bh
  ... truncated ...
```
