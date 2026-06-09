# CScriptRuntime::RunNoEH(VAR *)

- ea: `0x180023ad0`
- end: `0x180027850`
- name: `?RunNoEH@CScriptRuntime@@AEAAJPEAVVAR@@@Z`
- size: `15744`
- prototype: `__int64 __fastcall(CScriptRuntime *__hidden this, struct VAR *)`
- caller_count: `1`
- callee_count: `89`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180023950`

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
- `0x1800060b0`
- `0x180006230`
- `0x180006550`
- `0x180019e78`
- `0x18001a050`
- `0x18001aa50`
- `0x18001b260`
- `0x18001b350`
- `0x18001bd20`
- `0x18001bd44`
- `0x18001c1f0`
- `0x18001c600`
- `0x18001e850`
- `0x180020a50`
- `0x180021160`
- `0x180022b20`
- `0x180023ad0`
- `0x180027860`
- `0x180027890`
- `0x180027900`
- `0x180027960`
- `0x180027b50`
- `0x180027c00`
- `0x180027e00`
- `0x18002c500`
- `0x18002c580`
- `0x18002c6e0`
- `0x18002c990`
- `0x18002c9c0`
- `0x18002cc60`
- `0x18002ce50`
- `0x18002d2d0`
- `0x18002d2f0`
- `0x18002d340`
- `0x18002f4a0`
- `0x18002f550`
- `0x18002f580`
- `0x18002f630`
- `0x180034b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800252d8`
- `msvcrt!_wcsicmp` at `0x1800252d8`
- `OLEAUT32!__imp_VariantCopy` at `0x18002719d`
- `OLEAUT32!__imp_VariantCopy` at `0x18002719d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026187`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026187`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180026bfd`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180026bfd`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180026c3a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180026c3a`

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
  struct VAR *v38; // rbx
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
  VAR *v63; // rbx
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
  unsigned int v109; // ebx
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
  struct tagSAFEARRAY *v130; // rax
  VAR *v131; // rcx
  LONGLONG v132; // rdx
  unsigned __int16 *v133; // rax
  unsigned int v134; // ecx
  unsigned int v135; // r15d
  struct CEnumArray *v136; // rcx
  struct IDispatch *v137; // rax
  const unsigned __int16 *v138; // rdi
  unsigned __int16 *v139; // rax
  unsigned int v140; // ecx
  __int64 v141; // rbx
  struct VAR *v142; // rax
  unsigned int v143; // r14d
  int v144; // r15d
  unsigned int v145; // r12d
  __int64 v146; // rax
  struct VAR *v147; // rbx
  char v148; // al
  unsigned __int8 v149; // r14
  __int64 v150; // rbx
  __int64 v151; // rax
  const unsigned __int16 *v152; // rbx
  __int64 v153; // rcx
  int v154; // edx
  int v155; // eax
  unsigned __int8 *v156; // rcx
  __int64 v157; // rdx
  __int64 v158; // xmm1_8
  __int64 v159; // rdx
  __int64 v160; // rcx
  int v161; // eax
  __int64 v162; // rcx
  _WORD *v163; // r8
  __int64 v164; // rcx
  __int64 v165; // rbx
  const unsigned __int16 *v166; // rbx
  int v167; // eax
  struct VAR *v168; // rax
  __int64 v169; // r8
  __int64 v170; // rdi
  const unsigned __int16 *v171; // rdi
  unsigned __int8 v172; // bl
  VAR *v173; // rcx
  struct VAR *v174; // rax
  __int64 v175; // rdx
  char v176; // bl
  const unsigned __int16 *v177; // rdx
  struct VAR *v178; // rax
  __int64 v179; // rdi
  UINT v180; // ecx
  const unsigned __int16 *v181; // rdi
  __int64 v182; // r14
  struct tagSAFEARRAY *v183; // rax
  struct tagSAFEARRAY *v184; // rbx
  struct VAR *v185; // rax
  int v186; // eax
  VAR *v187; // rcx
  __int64 v188; // rax
  int v189; // ecx
  GcContext *v190; // rcx
  __int64 v191; // rdx
  const unsigned __int16 *v192; // rdx
  unsigned __int8 v193; // cl
  struct NameTbl *v194; // rax
  __int64 v195; // rdx
  const unsigned __int16 *v196; // rdx
  char v197; // di
  NameTbl *v198; // rbx
  struct VAR *v199; // rax
  struct VAR **v200; // rdx
  __int64 v201; // rcx
  struct VAR *v202; // rax
  int v203; // ecx
  struct VAR *v204; // rax
  __int128 v205; // xmm0
  __int64 v206; // xmm1_8
  __int64 v207; // rax
  __int64 v208; // rdx
  struct VAR *v209; // r8
  __int64 v210; // rdi
  const unsigned __int16 *v211; // rdi
  struct VAR *v212; // r8
  __int64 v213; // rbx
  struct SYM *v214; // rax
  unsigned int v215; // r9d
  struct VAR *v216; // r8
  __int64 v217; // rdi
  __int64 v218; // rax
  __int64 v219; // rdi
  const unsigned __int16 *v220; // rdi
  __int64 v221; // r14
  const unsigned __int16 *v222; // r14
  unsigned int v223; // edi
  int v224; // ebx
  LONGLONG llVal; // rcx
  struct tagSAFEARRAY *Array; // rax
  _WORD *v227; // rax
  SAFEARRAY *v228; // rbx
  SAFEARRAY *v229; // rax
  __int64 v230; // rdi
  __int64 v231; // rcx
  SAFEARRAY *v232; // rbx
  _QWORD *v233; // rdx
  int v234; // eax
  __int16 v235; // dx
  int BoolValNull; // eax
  const unsigned __int16 *v237; // rdi
  unsigned __int16 *v238; // rax
  int v239; // ecx
  int v240; // r14d
  __int64 v241; // r15
  __int64 v242; // rdi
  int v243; // ebx
  struct VAR *v244; // rbx
  unsigned int v245; // eax
  int v246; // edx
  struct VAR *v247; // rbx
  char v248; // al
  VAR *v249; // rax
  unsigned __int16 *v250; // rax
  __int64 v251; // rbx
  int v252; // eax
  struct VAR *v253; // rbx
  unsigned int v254; // eax
  __int64 v255; // rdi
  unsigned int v256; // r9d
  __int64 v257; // rdx
  __int64 v258; // rdx
  __int64 v259; // rdx
  HRESULT v260; // ebx
  unsigned __int16 *v261; // rax
  unsigned int v262; // ecx
  struct VAR *v263; // rax
  unsigned int v264; // r14d
  unsigned int v265; // r15d
  __int64 v266; // rdi
  __int64 v267; // rdx
  struct VAR *v268; // r8
  __int64 v269; // rax
  __int64 v270; // r15
  __int64 v271; // rdx
  const unsigned __int16 *v272; // r15
  __int64 v273; // r14
  __int64 v274; // rbx
  __int64 v275; // rax
  __int64 v276; // rdx
  __int64 v277; // rdi
  struct VAR *v278; // rbx
  struct SYM *v279; // rax
  unsigned int v280; // r9d
  __int64 v281; // rax
  __int64 v282; // rdx
  __int64 v283; // r15
  __int64 v284; // rdx
  __int64 v285; // rbx
  __int64 v286; // rcx
  int v287; // r14d
  __int64 v288; // r15
  struct VAR *v289; // rdi
  struct VAR *v290; // rbx
  char v291; // al
  struct VAR *v292; // rbx
  VAR *v293; // rax
  __int64 v294; // rcx
  __int64 v295; // rcx
  __int64 v296; // rax
  __int64 v297; // rcx
  int v298; // edi
  struct VAR *v299; // rbx
  __int64 v300; // rcx
  int v301; // r14d
  struct VAR *v302; // rdi
  struct VAR *v303; // rbx
  char v304; // al
  struct VAR *v305; // rbx
  __int64 v306; // rcx
  __int64 v307; // rdi
  char v308; // r9
  __int64 v309; // rdx
  struct VAR *v310; // rbx
  struct VAR *v311; // rbx
  unsigned int v312; // r9d
  struct VAR *v313; // rbx
  struct VAR *v314; // rbx
  __int64 v315; // rcx
  VAR *v316; // rbx
  int Adr; // [rsp+40h] [rbp-C0h] BYREF
  VAR *CurrentWithVar; // [rsp+48h] [rbp-B8h] BYREF
  int v319; // [rsp+50h] [rbp-B0h]
  struct IDispatch *v320; // [rsp+58h] [rbp-A8h] BYREF
  struct IEntryPoint *v321; // [rsp+60h] [rbp-A0h] BYREF
  struct CEnumArray *v322; // [rsp+68h] [rbp-98h] BYREF
  struct NameTbl *v323; // [rsp+70h] [rbp-90h] BYREF
  __int128 v324; // [rsp+78h] [rbp-88h] BYREF
  __int64 v325; // [rsp+88h] [rbp-78h]
  unsigned int v326; // [rsp+90h] [rbp-70h] BYREF
  tagBREAKREASON v327; // [rsp+94h] [rbp-6Ch] BYREF
  int v328; // [rsp+98h] [rbp-68h]
  int v329; // [rsp+9Ch] [rbp-64h] BYREF
  int v330; // [rsp+A0h] [rbp-60h] BYREF
  struct IDispatch *v331; // [rsp+A8h] [rbp-58h] BYREF
  SAFEARRAY *psa; // [rsp+B0h] [rbp-50h] BYREF
  VAR *v333; // [rsp+B8h] [rbp-48h]
  struct IRegExp2 *v334; // [rsp+C0h] [rbp-40h] BYREF
  CScriptRuntime *v335; // [rsp+C8h] [rbp-38h] BYREF
  CScriptRuntime *v336; // [rsp+D0h] [rbp-30h]
  __int128 v337; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v338; // [rsp+F0h] [rbp-10h]
  __int128 v339; // [rsp+100h] [rbp+0h]
  __int64 v340; // [rsp+110h] [rbp+10h]
  VARIANTARG pvargDest; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG v342; // [rsp+130h] [rbp+30h] BYREF
  __int128 v343; // [rsp+148h] [rbp+48h] BYREF
  __int64 v344; // [rsp+158h] [rbp+58h]
  __int128 v345; // [rsp+160h] [rbp+60h] BYREF
  __int64 v346; // [rsp+170h] [rbp+70h]
  VARIANTARG v347; // [rsp+178h] [rbp+78h] BYREF
  __int128 v348; // [rsp+190h] [rbp+90h] BYREF
  __int64 v349; // [rsp+1A0h] [rbp+A0h]
  __int128 v350; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v351; // [rsp+1B8h] [rbp+B8h]
  __int128 v352; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v353; // [rsp+1D0h] [rbp+D0h]

  Adr = 0;
  v3 = this[3].Part[0];
  v336 = (CScriptRuntime *)this;
  v333 = a2;
  v329 = 0;
  v4 = *(_DWORD *)(v3 + 24);
  v325 = 0;
  CurrentWithVar = 0;
  v320 = 0;
  v321 = 0;
  v322 = 0;
  v327 = BREAKREASON_STEP;
  v319 = 0;
  v324 = 0;
  v328 = v4;
  memset(&pvargDest, 0, sizeof(pvargDest));
  memset(&v347, 0, sizeof(v347));
  memset(&v342, 0, sizeof(v342));
  this[35].Part[1] = (unsigned __int64)&Adr;
  this[35].Part[0] = (unsigned __int64)&v329;
  v5 = setjmp_0(this + 11);
  v6 = v336;
  if ( v5 )
  {
    Adr = *((_DWORD *)v336 + 40);
    if ( Adr == -2147352318 && (*((_BYTE *)v336 + 504) & 1) == 0 )
      goto LABEL_104;
    if ( !(unsigned int)CSession::IsHalted(*(CSession **)v336) )
    {
      v154 = Adr;
      if ( Adr != -2040119292 && Adr != -2147352318 )
      {
        if ( (*((_BYTE *)v6 + 504) & 3) == 0 )
        {
          v155 = *((_DWORD *)v6 + 37);
          if ( v155 )
          {
            if ( !*((_QWORD *)v6 + 19) )
            {
              *((_QWORD *)v6 + 19) = CScriptRuntime::GetLocalName(v6, v155);
              v154 = Adr;
            }
          }
        }
        Adr = CSession::RecordHr(
                *(CSession **)v6,
                v154,
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
          v156 = (unsigned __int8 *)*((_QWORD *)v6 + 59);
          v157 = *v156;
          if ( (unsigned __int8)(v157 - 2) <= 4u )
            break;
          *((_QWORD *)v6 + 59) = &v156[(unsigned __int8)byte_180081A80[4 * v157]];
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
  v7 = v319;
  while ( 1 )
  {
    v8 = (unsigned __int8 *)*((_QWORD *)v6 + 59);
    v9 = *v8;
    v10 = (__int16 *)(v8 + 1);
    *((_QWORD *)v6 + 59) = v8 + 1;
    if ( v9 != 25 )
      break;
    v319 = *v10;
    v7 = v319;
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
      if ( (unsigned int)CSession::FOneTimeBreak(*(CSession **)v6, *((_DWORD *)v6 + 6), &v327) )
      {
        Adr = CScriptRuntime::Break(v6, v327);
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
    if ( v328 < *((_DWORD *)v22 + 6) )
      GcContext::FreeToMark(v22, v328);
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
      v97 = v333;
      if ( !v333 )
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
      v189 = *(_DWORD *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      *((_DWORD *)v6 + 122) = v189;
      Adr = CScriptRuntime::Break(v6, BREAKREASON_BREAKPOINT);
      if ( Adr >= 0 )
      {
        Adr = CSession::HandleHalt(*(CSession **)v6);
        if ( Adr >= 0 )
        {
          v190 = (GcContext *)*((_QWORD *)v6 + 6);
          if ( v328 < *((_DWORD *)v190 + 6) )
            GcContext::FreeToMark(v190, v328);
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
        v221 = *(unsigned int *)v10;
        *((_QWORD *)v6 + 59) = v8 + 5;
        v222 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v221);
        v223 = *(unsigned __int16 *)(v8 + 5);
        *((_QWORD *)v6 + 59) = v8 + 7;
        v224 = *((_DWORD *)v6 + 126);
        *((_DWORD *)v6 + 126) = v224 | 4;
        CScriptRuntime::GetVarAdr(v6, v222, (struct VAR *)&pvargDest);
        *((_DWORD *)v6 + 126) = ((int)((v224 & 0xFFFFFFFC) << 29) >> 29)
                              ^ (*((_DWORD *)v6 + 126)
                               ^ ((int)((v224 & 0xFFFFFFFC) << 29) >> 29))
                              & 0xFFFFFFFB;
        if ( pvargDest.vt != 16396 )
        {
          Adr = -2146827787;
          CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v222);
        }
        llVal = pvargDest.llVal;
        CurrentWithVar = (VAR *)pvargDest.llVal;
        if ( (*((_BYTE *)v6 + 504) & 0x10) == 0 || *pvargDest.bstrVal )
          goto LABEL_287;
        memset(&v342, 0, sizeof(v342));
        v129 = v223 >> 1;
        Array = MakeArray(v223 >> 1, *((struct VAR **)v6 + 58));
        v131 = CurrentWithVar;
        v132 = (LONGLONG)Array;
        v342.llVal = (LONGLONG)Array;
        if ( *(_WORD *)CurrentWithVar )
        {
          VAR::Clear(CurrentWithVar);
          v132 = v342.llVal;
LABEL_142:
          v131 = CurrentWithVar;
        }
LABEL_143:
        *((_QWORD *)v131 + 1) = (char *)v131 + 16;
        *((_QWORD *)CurrentWithVar + 2) = v132;
        *(_WORD *)CurrentWithVar = 24588;
        *((_QWORD *)v6 + 58) += 24LL * v129;
        goto LABEL_19;
      }
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v222 = 0;
      v227 = (_WORD *)*((_QWORD *)v6 + 59);
      LOWORD(v223) = *v227;
      *((_QWORD *)v6 + 59) = v227 + 1;
      llVal = (LONGLONG)CurrentWithVar;
LABEL_287:
      v228 = 0;
      v229 = 0;
      if ( (v223 & 1) == 0 )
        goto LABEL_294;
      if ( *(_WORD *)llVal == 24588 )
      {
        v228 = **(SAFEARRAY ***)(llVal + 8);
      }
      else
      {
        if ( *(_WORD *)llVal != 8204 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrLocal(v6, -2146828275, v222, v7);
          llVal = (LONGLONG)CurrentWithVar;
          v229 = 0;
LABEL_294:
          v230 = (unsigned __int16)v223 >> 1;
          if ( v229 )
          {
            RedimPreserveArray(v228, v230, *((struct VAR **)v6 + 58));
          }
          else if ( *(_WORD *)llVal == 24588 )
          {
            v231 = **(_QWORD **)(llVal + 8);
            if ( v231 && (*(_BYTE *)(v231 + 2) & 0x10) != 0 )
            {
              Adr = -2146828278;
              CScriptRuntime::IfErrorHrLocal(v6, -2146828278, v222, v7);
            }
            v232 = MakeArray(v230, *((struct VAR **)v6 + 58));
            Adr = VAR::Clear(CurrentWithVar);
            if ( Adr < 0 )
            {
              SafeArrayDestroy(v232);
              v233 = (_QWORD *)((char *)CurrentWithVar + 16);
              *((_QWORD *)CurrentWithVar + 1) = (char *)CurrentWithVar + 16;
              *v233 = 0;
              *(_WORD *)CurrentWithVar = 24588;
              CScriptRuntime::RaiseErrorHr(v6, Adr, CurrentWithVar, 0, -1);
            }
            *((_QWORD *)CurrentWithVar + 1) = (char *)CurrentWithVar + 16;
            *((_QWORD *)CurrentWithVar + 2) = v232;
            *(_WORD *)CurrentWithVar = 24588;
          }
          else
          {
            memset(&v342, 0, sizeof(v342));
            v342.llVal = (LONGLONG)MakeArray(v230, *((struct VAR **)v6 + 58));
            v342.vt = 8204;
            if ( (int)VAR::Clear(CurrentWithVar) < 0 && (*(_WORD *)CurrentWithVar & 0x2000) != 0 )
            {
              Adr = -2146828278;
              CScriptRuntime::IfErrorHrLocal(v6, -2146828278, v222, v7);
            }
            v234 = VAR::SafeVariantShallowCopy(CurrentWithVar, (struct VAR *)&v342);
            Adr = v234;
            if ( v234 < 0 )
              CScriptRuntime::RaiseErrorHr(v6, v234, CurrentWithVar, 0, -1);
          }
          *((_QWORD *)v6 + 58) += 24 * v230;
          goto LABEL_19;
        }
        v228 = *(SAFEARRAY **)(llVal + 8);
      }
      v229 = v228;
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
      v200 = (struct VAR **)*((_QWORD *)v6 + 59);
      *((_QWORD *)v6 + 59) = v200 + 1;
      v201 = *((_QWORD *)v6 + 58);
      v202 = *v200;
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
      v323 = 0;
      v330 = 0;
      v120 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v121 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v120);
      v122 = v8[5];
      *((_QWORD *)v6 + 59) = v8 + 6;
      SYM::InitFromSymbol((SYM *)&v324, v121);
      if ( (*((_BYTE *)v6 + 504) & 8) != 0 )
      {
        v123 = (struct NameTbl *)*((_QWORD *)v6 + 11);
        v323 = v123;
        if ( !v123 )
        {
          Adr = NameTbl::Create(&v323, *(struct CSession **)v6);
          CScriptRuntime::IfErrorHr(v6, Adr);
          *((_QWORD *)v6 + 11) = v323;
          v123 = v323;
        }
      }
      else
      {
        v123 = (struct NameTbl *)*((_QWORD *)v6 + 13);
        v323 = v123;
      }
      v124 = (*(__int64 (__fastcall **)(struct NameTbl *, __int128 *, int *))(*(_QWORD *)v123 + 160LL))(
               v123,
               &v324,
               &v330);
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
      Adr = (*(__int64 (__fastcall **)(struct NameTbl *, __int128 *, __int64, _QWORD, _QWORD))(*(_QWORD *)v323 + 120LL))(
              v323,
              &v324,
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
      v187 = CurrentWithVar;
      v188 = *((_QWORD *)v6 + 58);
      if ( *(_WORD *)CurrentWithVar == 16396 )
      {
        *(_OWORD *)v188 = *(_OWORD *)CurrentWithVar;
        *(_QWORD *)(v188 + 16) = *((_QWORD *)v187 + 2);
      }
      else
      {
        *(_WORD *)v188 = 16396;
        *(_QWORD *)(v188 + 8) = v187;
      }
      goto LABEL_19;
    case 24:
      v203 = *v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v7 = v203;
      *((_QWORD *)v6 + 58) -= 24LL;
      v319 = v203;
      v204 = CScriptRuntime::PvarLocal(v6, v203);
      v205 = *(_OWORD *)v204;
      v206 = *((_QWORD *)v204 + 2);
      v207 = *((_QWORD *)v6 + 58);
      *(_OWORD *)v207 = v205;
      *(_QWORD *)(v207 + 16) = v206;
      goto LABEL_387;
    case 26:
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v54 = (struct VAR *)*((_QWORD *)v6 + 58);
      v55 = CScriptRuntime::PvarLocal(v6, v7);
      v56 = 1;
      goto LABEL_65;
    case 27:
      v319 = *v10;
      v7 = v319;
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
      v335 = 0;
      v30 = *v8;
      v31 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v32 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v31);
      *((_QWORD *)v6 + 58) -= 24LL;
      **((_WORD **)v6 + 58) = 0;
      if ( (unsigned int)CScriptRuntime::FUseLocalInEval(v6, v32, &v335) )
      {
        v202 = CScriptRuntime::PvarLocal(v335, 0);
        CurrentWithVar = v202;
        v201 = *((_QWORD *)v6 + 58);
        if ( *(_WORD *)v202 == 16396 )
        {
          *(_OWORD *)v201 = *(_OWORD *)v202;
          *(_QWORD *)(v201 + 16) = *((_QWORD *)v202 + 2);
        }
        else
        {
          *(_WORD *)v201 = 16396;
LABEL_248:
          *(_QWORD *)(v201 + 8) = v202;
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
      if ( (unsigned int)VAR::IsFunction(v35, &v321) || (unsigned int)VAR::IsProperty(*((VAR **)v6 + 58), &v321, 4u) )
      {
        if ( (*(unsigned int (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 16LL))(v321)
          && **((_BYTE **)v6 + 59) != 89 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v32);
        }
        **((_WORD **)v6 + 58) = 0;
        if ( VarAdr )
        {
          v344 = 0;
          v343 = 0;
          VAR::SetIDispatch((VAR *)&v343, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  *((_QWORD *)v6 + 58),
                  0,
                  0,
                  &v343,
                  2);
          VAR::Clear((VAR *)&v343);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v321)(v321);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  *((_QWORD *)v6 + 58),
                  0,
                  0,
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 8LL))(v321);
        }
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v32);
        goto LABEL_19;
      }
      if ( (unsigned int)VAR::IsClass(*((VAR **)v6 + 58), &v321)
        || (unsigned int)VAR::IsProperty(*((VAR **)v6 + 58), &v321, 1u)
        || (unsigned int)VAR::IsProperty(*((VAR **)v6 + 58), &v321, 2u) )
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
      v208 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      CScriptRuntime::SetVar(v6, (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v208), *((struct VAR **)v6 + 58), 1);
      goto LABEL_71;
    case 32:
      *((_QWORD *)v6 + 58) -= 24LL;
      v218 = *((_QWORD *)v6 + 58);
      *(_OWORD *)v218 = *(_OWORD *)((char *)v6 + 440);
      *(_QWORD *)(v218 + 16) = *((_QWORD *)v6 + 57);
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
        v219 = *v126;
        *((_QWORD *)v6 + 59) = v127;
        v220 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v219);
        v129 = *v127;
        *((_QWORD *)v6 + 59) = (char *)v126 + 6;
        CScriptRuntime::GetVarAdr(v6, v220, (struct VAR *)&pvargDest);
        if ( pvargDest.vt != 16396 )
        {
          Adr = -2146827787;
          CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v220);
        }
        CurrentWithVar = (VAR *)pvargDest.llVal;
        if ( *pvargDest.bstrVal )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v220);
        }
      }
      else
      {
        v128 = *(__int16 *)v126;
        *((_QWORD *)v6 + 59) = (char *)v126 + 2;
        v7 = v128;
        v129 = *((unsigned __int16 *)v126 + 1);
        v319 = v128;
        *((_QWORD *)v6 + 59) = v127;
        CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 9) - 24 * v128);
        CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
        if ( *(_WORD *)CurrentWithVar )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrLocal(v6, -2146828275, 0, v7);
        }
      }
      memset(&v342, 0, sizeof(v342));
      v130 = MakeArray(v129, *((struct VAR **)v6 + 58));
      v131 = CurrentWithVar;
      v132 = (LONGLONG)v130;
      v342.llVal = (LONGLONG)v130;
      if ( *(_WORD *)CurrentWithVar )
      {
        VAR::Clear(CurrentWithVar);
        v131 = CurrentWithVar;
        v132 = v342.llVal;
      }
      if ( !v132 )
        goto LABEL_143;
      *(_WORD *)(v132 + 2) |= 0x12u;
      goto LABEL_142;
    case 35:
      v36 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v37 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v36);
      if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v6 + 58), &v320) )
      {
        v209 = (struct VAR *)*((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v209, 0, 0);
      }
      **((_WORD **)v6 + 58) = 0;
      v38 = (struct VAR *)*((_QWORD *)v6 + 58);
      v39 = SYM::InitFromSymbol((SYM *)&v324, v37);
      Adr = InvokeByName(*(struct CSession **)v6, v320, v39, 3u, v38, 0, 0);
      CScriptRuntime::IfErrorHrArg(v6, Adr, v38, v37, 0);
      goto LABEL_19;
    case 36:
      v210 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v211 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v210);
      if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v6 + 58), &v320) )
      {
        v212 = (struct VAR *)*((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v212, 0, 0);
      }
      v213 = *((_QWORD *)v6 + 58);
      v214 = SYM::InitFromSymbol((SYM *)&v324, v211);
      v215 = 4;
      goto LABEL_269;
    case 37:
      v217 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v211 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v217);
      if ( !(unsigned int)VAR::IsIDispatch(*((VAR **)v6 + 58), &v320) )
      {
        v216 = (struct VAR *)*((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v216, 0, 0);
      }
      v213 = *((_QWORD *)v6 + 58);
      v214 = SYM::InitFromSymbol((SYM *)&v324, v211);
      v215 = 8;
LABEL_269:
      Adr = InvokeByName(*(struct CSession **)v6, v320, v214, v215, 0, 1, (struct VAR *)(v213 + 24));
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)v213, v211, 0);
      goto LABEL_270;
    case 38:
      v242 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v241 = *(unsigned __int16 *)(v8 + 5);
      v237 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v242);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v240 = v241;
      v243 = CScriptRuntime::GetVarAdr(v6, v237, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v244 = (struct VAR *)*((_QWORD *)v6 + 58);
        v245 = GrfdispCall(v241);
        Adr = VAR::InvokeByDispID(
                (VAR *)&pvargDest,
                *(struct CSession **)v6,
                0,
                v245,
                (struct VAR *)&pvargDest,
                v241,
                v244);
        v246 = Adr;
LABEL_345:
        CScriptRuntime::IfErrorHrPsz(v6, v246, v237);
        v17 = 3 * v241;
        goto LABEL_15;
      }
      CurrentWithVar = VAR::PvarCutRef((VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsFunction(CurrentWithVar, &v321)
        || (unsigned int)VAR::IsProperty(CurrentWithVar, &v321, 4u) )
      {
        if ( (*(unsigned int (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 16LL))(v321)
          && **((_BYTE **)v6 + 59) != 89 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v237);
        }
        pvargDest.vt = 0;
        if ( v243 )
        {
          v346 = 0;
          v345 = 0;
          VAR::SetIDispatch((VAR *)&v345, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  &pvargDest,
                  (unsigned int)v241,
                  *((_QWORD *)v6 + 58),
                  &v345,
                  2);
          VAR::Clear((VAR *)&v345);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v321)(v321);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  &pvargDest,
                  (unsigned int)v241,
                  *((_QWORD *)v6 + 58),
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 8LL))(v321);
        }
        v246 = Adr;
        goto LABEL_345;
      }
LABEL_335:
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        pvargDest.vt = 0;
        v247 = (struct VAR *)*((_QWORD *)v6 + 58);
        v248 = GrfdispCall(v240);
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, v248, &pvargDest, v240, v247);
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v237, v7);
        v16 = (unsigned int)v241;
        goto LABEL_14;
      }
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v240, *((struct VAR **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrLocal(v6, Adr, v237, v7);
      *((_QWORD *)v6 + 58) += 24LL * (unsigned int)v241 - 24;
LABEL_386:
      v293 = CurrentWithVar;
      v294 = *((_QWORD *)v6 + 58);
      *(_OWORD *)v294 = *(_OWORD *)CurrentWithVar;
      *(_QWORD *)(v294 + 16) = *((_QWORD *)v293 + 2);
LABEL_387:
      v295 = *((_QWORD *)v6 + 58);
      if ( *(_WORD *)v295 == 16396 )
      {
        v296 = *(_QWORD *)(v295 + 8);
        *(_OWORD *)v295 = *(_OWORD *)v296;
        *(_QWORD *)(v295 + 16) = *(_QWORD *)(v296 + 16);
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
        if ( !(unsigned int)VAR::IsFunction(CurrentWithVar, &v321)
          && !(unsigned int)VAR::IsProperty(CurrentWithVar, &v321, 4u) )
        {
          if ( !(unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
          {
            Adr = -2146828275;
            CScriptRuntime::IfErrorHrLocal(v6, -2146828275, v88, v7);
          }
          v347.vt = 0;
          v252 = InvokeDispatch(*(struct CSession **)v6, v320, 0, 1, &v347, v89, *((struct VAR **)v6 + 58));
          CScriptRuntime::IfErrorHrLocal(v6, v252, v88, v7);
          VAR::Clear((VAR *)&v347);
LABEL_97:
          *((_QWORD *)v6 + 58) += 24 * v89;
          goto LABEL_19;
        }
        if ( v90 )
        {
          v348 = 0;
          v349 = 0;
          VAR::SetIDispatch((VAR *)&v348, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  &pvargDest,
                  (unsigned int)v89,
                  *((_QWORD *)v6 + 58),
                  &v348,
                  2);
          VAR::Clear((VAR *)&v348);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v321)(v321);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  &pvargDest,
                  (unsigned int)v89,
                  *((_QWORD *)v6 + 58),
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 8LL))(v321);
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
        v253 = (struct VAR *)*((_QWORD *)v6 + 58);
        v254 = GrfdispCall(v13);
        Adr = VAR::InvokeByDispID(
                (VAR *)&pvargDest,
                *(struct CSession **)v6,
                0,
                v254,
                (struct VAR *)&pvargDest,
                v13,
                v253);
        v15 = Adr;
LABEL_12:
        CScriptRuntime::IfErrorHrPsz(v6, v15, v12);
        goto LABEL_13;
      }
      CurrentWithVar = VAR::PvarCutRef((VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsFunction(CurrentWithVar, &v321)
        || (unsigned int)VAR::IsProperty(CurrentWithVar, &v321, 4u) )
      {
        if ( (*(unsigned int (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 16LL))(v321)
          && **((_BYTE **)v6 + 59) != 89 )
        {
          Adr = -2146828275;
          CScriptRuntime::IfErrorHrPsz(v6, -2146828275, v12);
        }
        pvargDest.vt = 0;
        if ( v14 )
        {
          v351 = 0;
          v350 = 0;
          VAR::SetIDispatch((VAR *)&v350, *((struct IDispatch **)v6 + 12));
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  &pvargDest,
                  v13,
                  *((_QWORD *)v6 + 58),
                  &v350,
                  2);
          VAR::Clear((VAR *)&v350);
        }
        else
        {
          (**(void (__fastcall ***)(struct IEntryPoint *))v321)(v321);
          Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, VARIANTARG *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v321 + 32LL))(
                  v321,
                  &pvargDest,
                  v13,
                  *((_QWORD *)v6 + 58),
                  0,
                  0);
          (*(void (__fastcall **)(struct IEntryPoint *))(*(_QWORD *)v321 + 8LL))(v321);
        }
        v15 = Adr;
        goto LABEL_12;
      }
      v135 = v13;
LABEL_145:
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        pvargDest.vt = 0;
        v147 = (struct VAR *)*((_QWORD *)v6 + 58);
        v148 = GrfdispCall(v13);
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, v148, &pvargDest, v13, v147);
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v12, v7);
        v13 = v135;
      }
      else
      {
        Adr = CScriptRuntime::LockArray(v6, &CurrentWithVar, CurrentWithVar, v13, *((VARIANTARG **)v6 + 58));
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v12, v7);
        v13 = v135;
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
      v255 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v138 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v255);
      v141 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v144 = CScriptRuntime::GetVarAdr(v6, v138, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v256 = 4;
LABEL_361:
        *((_QWORD *)v6 + 58) -= 24LL;
        v257 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v257 = *(_OWORD *)(v257 + 24 * (v141 + 1));
        *(_QWORD *)(v257 + 16) = *(_QWORD *)(v257 + 24 * (v141 + 1) + 16);
        Adr = VAR::InvokeByDispID(
                (VAR *)&pvargDest,
                *(struct CSession **)v6,
                0,
                v256,
                0,
                (int)v141 + 1,
                *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v138);
        v118 = (unsigned int)(v141 + 2);
LABEL_121:
        *((_QWORD *)v6 + 58) += 24 * v118;
        goto LABEL_19;
      }
      v142 = VAR::PvarCutRef((VAR *)&pvargDest);
      CurrentWithVar = v142;
      v143 = v141;
      v145 = v141;
LABEL_153:
      if ( (unsigned int)VAR::IsIDispatch(v142, &v320) )
      {
        *((_QWORD *)v6 + 58) -= 24LL;
        v258 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v258 = *(_OWORD *)(v258 + 24 * (v145 + 1LL));
        *(_QWORD *)(v258 + 16) = *(_QWORD *)(v258 + 24 * (v145 + 1LL) + 16);
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, 4, 0, v143 + 1, *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
      }
      else
      {
        if ( !v144
          || !(unsigned int)VAR::IsProperty((VAR *)&pvargDest, &v321, 2u)
          && !(unsigned int)VAR::IsProperty((VAR *)&pvargDest, &v321, 1u) )
        {
          if ( (unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24LL * v143)) )
          {
            psa = 0;
            Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v141, *((struct VAR **)v6 + 58), &psa);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
            Adr = SafeArrayLock(psa);
            CScriptRuntime::IfErrorHrPsz(v6, Adr, v138);
            Adr = AssignVar(
                    *(struct CSession **)v6,
                    CurrentWithVar,
                    (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * v143),
                    1u);
            v260 = SafeArrayUnlock(psa);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
            CScriptRuntime::IfErrorHrPsz(v6, v260, v138);
          }
          else
          {
            Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v141, *((struct VAR **)v6 + 58), 0);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
            Adr = AssignVar(
                    *(struct CSession **)v6,
                    CurrentWithVar,
                    (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * v143),
                    1u);
            CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
          }
          v146 = v143 + 1;
          goto LABEL_158;
        }
        v352 = 0;
        v353 = 0;
        VAR::SetIDispatch((VAR *)&v352, *((struct IDispatch **)v6 + 12));
        *((_QWORD *)v6 + 58) -= 24LL;
        v259 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v259 = *(_OWORD *)(v259 + 24 * (v145 + 1LL));
        *(_QWORD *)(v259 + 16) = *(_QWORD *)(v259 + 24 * (v145 + 1LL) + 16);
        Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, __int128 *, int))(*(_QWORD *)v321 + 32LL))(
                v321,
                0,
                v143 + 1,
                *((_QWORD *)v6 + 58),
                &v352,
                2);
        VAR::Clear((VAR *)&v352);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v138);
      }
      v146 = v143 + 2;
LABEL_158:
      *((_QWORD *)v6 + 58) += 24 * v146;
      goto LABEL_19;
    case 42:
      v266 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v138 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v266);
      v141 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      CScriptRuntime::GetVarAdr(v6, v138, (struct VAR *)&pvargDest);
      if ( (unsigned int)VAR::IsDispmember((VAR *)&pvargDest) )
      {
        v256 = 8;
        goto LABEL_361;
      }
      v263 = VAR::PvarCutRef((VAR *)&pvargDest);
      CurrentWithVar = v263;
      v264 = v141;
      v265 = v141;
LABEL_373:
      if ( (unsigned int)VAR::IsIDispatch(v263, &v320) )
      {
        *((_QWORD *)v6 + 58) -= 24LL;
        v267 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v267 = *(_OWORD *)(v267 + 24 * (v265 + 1LL));
        *(_QWORD *)(v267 + 16) = *(_QWORD *)(v267 + 24 * (v265 + 1LL) + 16);
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, 8, 0, v264 + 1, *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
        v118 = v264 + 2;
        goto LABEL_121;
      }
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v141, *((struct VAR **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
      Adr = AssignVar(*(struct CSession **)v6, CurrentWithVar, (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * v264), 2u);
      CScriptRuntime::IfErrorHrLocal(v6, Adr, v138, v7);
      *((_QWORD *)v6 + 58) += 24LL * (v264 + 1);
      goto LABEL_19;
    case 43:
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v237 = 0;
      v238 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v239 = *v238;
      *((_QWORD *)v6 + 59) = v238 + 1;
      v240 = v239;
      LODWORD(v241) = v239;
      goto LABEL_335;
    case 44:
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v249 = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(v249);
      v250 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v251 = *v250;
      *((_QWORD *)v6 + 59) = v250 + 1;
      if ( !(unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        Adr = -2146828275;
        CScriptRuntime::IfErrorHrLocal(v6, -2146828275, 0, v7);
      }
      Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, 1, 0, v251, *((struct VAR **)v6 + 58));
      CScriptRuntime::IfErrorHrLocal(v6, Adr, 0, v7);
      *((_QWORD *)v6 + 58) += 24 * v251;
      goto LABEL_19;
    case 45:
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v12 = 0;
      v133 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v134 = *v133;
      *((_QWORD *)v6 + 59) = v133 + 1;
      v13 = v134;
      v135 = v134;
      goto LABEL_145;
    case 46:
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v138 = 0;
      v139 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v140 = *v139;
      *((_QWORD *)v6 + 59) = v139 + 1;
      LODWORD(v141) = v140;
      v142 = CurrentWithVar;
      v143 = v140;
      v144 = 0;
      v145 = v140;
      goto LABEL_153;
    case 47:
      v319 = *v10;
      v7 = v319;
      *((_QWORD *)v6 + 59) = v8 + 3;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v7);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v138 = 0;
      v261 = (unsigned __int16 *)*((_QWORD *)v6 + 59);
      v262 = *v261;
      *((_QWORD *)v6 + 59) = v261 + 1;
      LODWORD(v141) = v262;
      v263 = CurrentWithVar;
      v264 = v262;
      v265 = v262;
      goto LABEL_373;
    case 48:
      v103 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v104 = *(unsigned __int16 *)(v8 + 5);
      v105 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v103);
      v106 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v107 = 24 * v104;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(24 * v104 + *((_QWORD *)v6 + 58)), &v320) )
      {
        v268 = (struct VAR *)(v107 + *((_QWORD *)v6 + 58));
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, v268, 0, v106);
      }
      v108 = (struct VAR *)*((_QWORD *)v6 + 58);
      v109 = GrfdispCall(v106);
      v110 = SYM::InitFromSymbol((SYM *)&v324, v105);
      Adr = InvokeByName(*(struct CSession **)v6, v320, v110, v109, (struct VAR *)&pvargDest, v106, v108);
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
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24 * v112), &v320) )
      {
        v269 = *((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, (struct VAR *)(v269 + 8 * v115), 0, v114);
      }
      v116 = (struct VAR *)*((_QWORD *)v6 + 58);
      v117 = SYM::InitFromSymbol((SYM *)&v324, v113);
      Adr = InvokeByName(*(struct CSession **)v6, v320, v117, 1u, 0, v114, v116);
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)((char *)v116 + 8 * v115), v113, v114);
      v118 = (unsigned int)(v114 + 1);
      goto LABEL_121;
    case 50:
      v270 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v271 = *(unsigned __int16 *)(v8 + 5);
      v272 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v270);
      v273 = (unsigned __int16)v10[2];
      *((_QWORD *)v6 + 59) = v10 + 3;
      v274 = 3 * v271;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24 * v271), &v320) )
      {
        v275 = *((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, (struct VAR *)(v275 + 8 * v274), 0, v273);
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      v276 = *((_QWORD *)v6 + 58);
      v277 = (unsigned int)(v273 + 1);
      *(_OWORD *)v276 = *(_OWORD *)(v276 + 24 * (v273 + 2));
      *(_QWORD *)(v276 + 16) = *(_QWORD *)(v276 + 24 * (v273 + 2) + 16);
      v278 = (struct VAR *)*((_QWORD *)v6 + 58);
      v279 = SYM::InitFromSymbol((SYM *)&v324, v272);
      v280 = 4;
      goto LABEL_380;
    case 51:
      v283 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v284 = *(unsigned __int16 *)(v8 + 5);
      v272 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v283);
      v273 = (unsigned __int16)v10[2];
      *((_QWORD *)v6 + 59) = v10 + 3;
      v285 = 3 * v284;
      if ( !(unsigned int)VAR::IsIDispatch((VAR *)(*((_QWORD *)v6 + 58) + 24 * v284), &v320) )
      {
        v281 = *((_QWORD *)v6 + 58);
        Adr = -2146827864;
        CScriptRuntime::IfErrorHrArg(v6, -2146827864, (struct VAR *)(v281 + 8 * v285), 0, v273);
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      v282 = *((_QWORD *)v6 + 58);
      v277 = (unsigned int)(v273 + 1);
      *(_OWORD *)v282 = *(_OWORD *)(v282 + 24 * (v273 + 2));
      *(_QWORD *)(v282 + 16) = *(_QWORD *)(v282 + 24 * (v273 + 2) + 16);
      v278 = (struct VAR *)*((_QWORD *)v6 + 58);
      v279 = SYM::InitFromSymbol((SYM *)&v324, v272);
      v280 = 8;
LABEL_380:
      Adr = InvokeByName(*(struct CSession **)v6, v320, v279, v280, 0, v277, v278);
      CScriptRuntime::IfErrorHrArg(v6, Adr, (struct VAR *)((char *)v278 + 24 * v277), v272, v277);
      v118 = (unsigned int)(v273 + 3);
      goto LABEL_121;
    case 52:
      v286 = (unsigned __int16)*v10;
      v287 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v288 = 24 * v286;
      CurrentWithVar = (VAR *)(24 * v286 + *((_QWORD *)v6 + 58));
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        v289 = CurrentWithVar;
        pvargDest.vt = 0;
        v290 = (struct VAR *)*((_QWORD *)v6 + 58);
        v291 = GrfdispCall(v287);
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, v291, &pvargDest, v287, v290);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v289, 0, v287);
        *((_QWORD *)v6 + 58) += v288;
        goto LABEL_16;
      }
      v292 = CurrentWithVar;
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v287, *((struct VAR **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrArg(v6, Adr, v292, 0, v287);
      *((_QWORD *)v6 + 58) += v288;
      goto LABEL_386;
    case 53:
      v297 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v298 = v297;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v297);
      if ( !(unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        Adr = -2146828275;
        CScriptRuntime::IfErrorHr(v6, -2146828275);
      }
      v299 = CurrentWithVar;
      Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, 1, 0, v298, *((struct VAR **)v6 + 58));
      CScriptRuntime::IfErrorHrArg(v6, Adr, v299, 0, v298);
      v118 = (unsigned int)(v298 + 1);
      goto LABEL_121;
    case 54:
      v300 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v301 = v300;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v300);
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        v302 = CurrentWithVar;
        pvargDest.vt = 0;
        v303 = (struct VAR *)*((_QWORD *)v6 + 58);
        v304 = GrfdispCall(v301);
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, v304, &pvargDest, v301, v303);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v302, 0, v301);
      }
      else
      {
        v305 = CurrentWithVar;
        Adr = CScriptRuntime::LockArray(v6, &CurrentWithVar, CurrentWithVar, v301, *((VARIANTARG **)v6 + 58));
        CScriptRuntime::IfErrorHrArg(v6, Adr, v305, 0, v301);
        pvargDest.llVal = (LONGLONG)CurrentWithVar;
        pvargDest.vt = 16396;
      }
      *((_QWORD *)v6 + 58) += 24LL * (unsigned int)(v301 + 1) - 24;
      goto LABEL_16;
    case 55:
      v306 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v307 = (unsigned int)v306;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v306);
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        v308 = 4;
        goto LABEL_401;
      }
      v311 = CurrentWithVar;
      Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v307, *((struct VAR **)v6 + 58), 0);
      CScriptRuntime::IfErrorHrArg(v6, Adr, v311, 0, v307);
      v312 = 1;
      goto LABEL_404;
    case 56:
      v315 = (unsigned __int16)*v10;
      *((_QWORD *)v6 + 59) = v8 + 3;
      v307 = (unsigned int)v315;
      CurrentWithVar = (VAR *)(*((_QWORD *)v6 + 58) + 24 * v315);
      if ( (unsigned int)VAR::IsIDispatch(CurrentWithVar, &v320) )
      {
        v308 = 8;
LABEL_401:
        *((_QWORD *)v6 + 58) -= 24LL;
        v309 = *((_QWORD *)v6 + 58);
        *(_OWORD *)v309 = *(_OWORD *)(v309 + 24 * (v307 + 2));
        *(_QWORD *)(v309 + 16) = *(_QWORD *)(v309 + 24 * (v307 + 2) + 16);
        v310 = CurrentWithVar;
        Adr = InvokeDispatch(*(struct CSession **)v6, v320, 0, v308, 0, (int)v307 + 1, *((struct VAR **)v6 + 58));
        CScriptRuntime::IfErrorHrArg(v6, Adr, v310, 0, v307);
        v118 = (unsigned int)(v307 + 3);
      }
      else
      {
        v313 = CurrentWithVar;
        Adr = AccessArray(&CurrentWithVar, CurrentWithVar, v307, *((struct VAR **)v6 + 58), 0);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v313, 0, v307);
        v312 = 2;
LABEL_404:
        v314 = CurrentWithVar;
        Adr = AssignVar(
                *(struct CSession **)v6,
                CurrentWithVar,
                (struct VAR *)(*((_QWORD *)v6 + 58) + 24LL * (unsigned int)(v307 + 1)),
                v312);
        CScriptRuntime::IfErrorHrArg(v6, Adr, v314, 0, v307);
        v118 = (unsigned int)(v307 + 2);
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
        BoolValNull = GetBoolValNull(v41, v8, 0x8000, v10);
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
        v102 = GetBoolValNull(v24, v8, 0x8000, v10);
        v25 = 0;
        v26 = v102 == 0;
      }
      LOBYTE(v25) = v26;
      goto LABEL_30;
    case 61:
      VbsVarNeg(*((struct VAR **)v6 + 58));
      goto LABEL_19;
    case 62:
      VbsVarOr((struct VAR *)(*((_QWORD *)v6 + 58) + 24LL), *((struct VAR **)v6 + 58));
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
      v63 = (VAR *)*((_QWORD *)v6 + 58);
      LogicalVal = VAR::PvarGetLogicalVal(v63);
      *(_WORD *)v63 = *(_WORD *)LogicalVal;
      *((_DWORD *)v63 + 2) = ~*((_DWORD *)LogicalVal + 2);
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
      v235 = -1;
      if ( v50 > 2 )
        v235 = 0;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 32LL) = v235;
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
      v191 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v7 = *((_DWORD *)v10 + 1);
      v192 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v191);
      *((_QWORD *)v6 + 59) = v10 + 4;
      v193 = *((_BYTE *)v10 + 8);
      *((_QWORD *)v6 + 59) = (char *)v10 + 9;
      v194 = (struct NameTbl *)*((_QWORD *)v6 + 11);
      v319 = v7;
      if ( !v194 )
        v194 = (struct NameTbl *)*((_QWORD *)v6 + 13);
      Adr = CScriptRuntime::BindFunction(v6, v192, v7, v193, v194);
      CScriptRuntime::IfErrorHr(v6, Adr);
      COleScript::IncGeneration(*((COleScript **)v6 + 1));
      goto LABEL_19;
    case 86:
      v326 = 0;
      v195 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v7 = v10[2];
      v196 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v195);
      *((_QWORD *)v6 + 59) = v10 + 3;
      v197 = *((_BYTE *)v10 + 6);
      v319 = v7;
      *((_QWORD *)v6 + 59) = (char *)v10 + 7;
      SYM::InitFromSymbol((SYM *)&v324, v196);
      v198 = (NameTbl *)*((_QWORD *)v6 + 11);
      if ( !v198 )
        v198 = (NameTbl *)*((_QWORD *)v6 + 13);
      Adr = (*(__int64 (__fastcall **)(NameTbl *, __int128 *, unsigned int *))(*(_QWORD *)v198 + 152LL))(
              v198,
              &v324,
              &v326);
      CScriptRuntime::IfErrorHr(v6, Adr);
      if ( Adr || (v326 & 3) != 0 || (v197 != 0) != ((v326 >> 2) & 1) )
      {
        Adr = (*(__int64 (__fastcall **)(NameTbl *, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v198 + 120LL))(
                v198,
                &v324,
                v197 != 0 ? 4 : 0,
                0,
                0);
        CScriptRuntime::IfErrorHr(v6, Adr);
      }
      if ( v7 )
      {
        v199 = CScriptRuntime::PvarLocal(v6, v7);
        Adr = NameTbl::GetAdr(v198, (struct SYM *)&v324, v199);
        CScriptRuntime::IfErrorHr(v6, Adr);
      }
      goto LABEL_19;
    case 87:
      v97 = v333;
      if ( !v333 )
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
      v316 = v333;
      if ( v333 )
      {
        Adr = AssignVar(*(struct CSession **)v6, v333, *((struct VAR **)v6 + 58), 0);
        CScriptRuntime::IfErrorHr(v6, Adr);
        if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v316) )
        {
          GcContext::FreeToMark(*((GcContext **)v6 + 6), *((_DWORD *)v6 + 14));
          Adr = VAR::MoveToHeap(v316, *((struct GcContext **)v6 + 6));
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
      v165 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v166 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v165);
      if ( _wcsicmp(L"regexp", v166) )
      {
        pvargDest.vt = 0;
        CScriptRuntime::GetVarAdr(v6, v166, (struct VAR *)&pvargDest);
        if ( !(unsigned int)VAR::IsClass((VAR *)&pvargDest, &v321) )
        {
          Adr = -2146827782;
          CScriptRuntime::IfErrorHrPsz(v6, -2146827782, v166);
        }
        *((_QWORD *)v6 + 58) -= 24LL;
        **((_WORD **)v6 + 58) = 0;
        Adr = (*(__int64 (__fastcall **)(struct IEntryPoint *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v321 + 32LL))(
                v321,
                *((_QWORD *)v6 + 58),
                0,
                0,
                0,
                0);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v166);
        v168 = VAR::PvarCutAll(*((VAR **)v6 + 58));
        VBScriptClass::InitializeClass(*((VBScriptClass **)v168 + 1));
      }
      else
      {
        v334 = 0;
        Adr = CRegExp::Create(&v334);
        CScriptRuntime::IfErrorHrPsz(v6, Adr, v166);
        pvargDest.vt = 9;
        pvargDest.llVal = (LONGLONG)v334;
        *((_QWORD *)v6 + 58) -= 24LL;
        *(VARIANTARG *)*((_QWORD *)v6 + 58) = pvargDest;
        v167 = VAR::MoveToHeap((VAR *)&pvargDest);
        Adr = v167;
        if ( v167 < 0 )
          CScriptRuntime::IfErrorHrPsz(v6, v167, v166);
      }
      goto LABEL_19;
    case 91:
      v331 = 0;
      v169 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      Adr = VBScriptClass::Create(
              (struct VBScriptClass **)&v331,
              *(struct CSession **)v6,
              (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v169));
      CScriptRuntime::IfErrorHr(v6, Adr);
      *((_QWORD *)v6 + 58) -= 24LL;
      Adr = VAR::SetHeapIDispatch(*((VAR **)v6 + 58), v331);
      ((void (__fastcall *)(struct IDispatch *))v331->lpVtbl->Release)(v331);
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_19;
    case 92:
      v170 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v7 = *(_DWORD *)(v8 + 5);
      v171 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v170);
      *((_QWORD *)v6 + 59) = v8 + 9;
      v172 = v8[9];
      *((_QWORD *)v6 + 59) = v8 + 10;
      v173 = (VAR *)*((_QWORD *)v6 + 58);
      v319 = v7;
      v174 = VAR::PvarCutAll(v173);
      Adr = CScriptRuntime::BindFunction(v6, v171, v7, v172, *((struct NameTbl **)v174 + 1));
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_19;
    case 93:
      v175 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v176 = *((_BYTE *)v10 + 4);
      v177 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v175);
      *((_QWORD *)v6 + 59) = (char *)v10 + 5;
      SYM::InitFromSymbol((SYM *)&v324, v177);
      v178 = VAR::PvarCutAll(*((VAR **)v6 + 58));
      Adr = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v178 + 1) + 120LL))(
              *((_QWORD *)v178 + 1),
              &v324,
              v176 != 0 ? 0xC : 0,
              0,
              0);
      CScriptRuntime::IfErrorHr(v6, Adr);
      goto LABEL_19;
    case 94:
      v179 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v180 = *(unsigned __int16 *)(v8 + 5);
      v181 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v179);
      v182 = *(unsigned __int16 *)(v8 + 5);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v183 = MakeArray(v180, *((struct VAR **)v6 + 58));
      v184 = v183;
      if ( v183 )
        v183->fFeatures |= 0x12u;
      *((_QWORD *)v6 + 58) += 24 * v182;
      SYM::InitFromSymbol((SYM *)&v324, v181);
      v185 = VAR::PvarCutAll(*((VAR **)v6 + 58));
      Adr = NameTbl::GetAdr(*((NameTbl **)v185 + 1), (struct SYM *)&v324, (struct VAR *)&pvargDest);
      CurrentWithVar = (VAR *)pvargDest.llVal;
      if ( pvargDest.llVal )
      {
        *(_QWORD *)(pvargDest.llVal + 8) = pvargDest.llVal + 16;
        *((_QWORD *)CurrentWithVar + 2) = v184;
        *(_WORD *)CurrentWithVar = 24588;
      }
      goto LABEL_19;
    case 95:
      v186 = CScriptRuntime::WithPush(v6, *((struct VAR **)v6 + 58));
      CScriptRuntime::IfErrorHr(v6, v186);
      goto LABEL_71;
    case 96:
    case 97:
      VAR::Clear((VAR *)(*((_QWORD *)v6 + 8) + 24LL * (int)--*((_DWORD *)v6 + 15)));
      goto LABEL_19;
    case 98:
    case 99:
      v73 = *v8;
      v74 = *v10;
      v319 = v74;
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
      v319 = v7;
      if ( v7 == 17 )
      {
        ForLoopInit(v80, v82, *((struct VAR **)v6 + 58), v78);
        *((_QWORD *)v6 + 58) += 72LL;
      }
      *((_QWORD *)v6 + 58) -= 24LL;
      memset(&v342, 0, sizeof(v342));
      v342 = *(VARIANTARG *)v78;
      **((_WORD **)v6 + 58) = 11;
      *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = ExNextVar((VARIANTARG *)v80, (VARIANTARG *)v82, &v342, v7);
      v84 = VAR::SafeVariantShallowCopy(v78, (struct VAR *)&v342);
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
      v319 = v43;
      *((_QWORD *)v6 + 59) = v10 + 1;
      CurrentWithVar = CScriptRuntime::PvarLocal(v6, v43);
      CurrentWithVar = VAR::PvarCutRef(CurrentWithVar);
      v44 = (__int16 *)*((_QWORD *)v6 + 59);
      v45 = *v44;
      *((_QWORD *)v6 + 59) = v44 + 1;
      v46 = (struct CEnumArray **)(*((_QWORD *)v6 + 9) - 24 * v45);
      v47 = v44[1];
      v7 = v44[1];
      v319 = v7;
      *((_QWORD *)v6 + 59) = v44 + 2;
      v48 = *((_QWORD *)v6 + 9) - 24 * v47;
      if ( v42 == 106 )
        goto LABEL_50;
      goto LABEL_105;
    case 107:
    case 108:
      v149 = *v8;
      v150 = *(unsigned int *)v10;
      *((_QWORD *)v6 + 59) = v8 + 5;
      v151 = *(__int16 *)(v8 + 5);
      v152 = (const unsigned __int16 *)(*((_QWORD *)v6 + 62) + v150);
      *((_QWORD *)v6 + 59) = v8 + 7;
      v46 = (struct CEnumArray **)(*((_QWORD *)v6 + 9) - 24 * v151);
      v153 = *(__int16 *)(v8 + 7);
      v7 = *(__int16 *)(v8 + 7);
      v319 = v7;
      *((_QWORD *)v6 + 59) = v8 + 9;
      v48 = *((_QWORD *)v6 + 9) - 24 * v153;
      CScriptRuntime::GetVarAdr(v6, v152, (struct VAR *)&pvargDest);
      if ( pvargDest.vt != 16396 )
      {
        Adr = -2146827787;
        CScriptRuntime::IfErrorHrPsz(v6, -2146827787, v152);
      }
      CurrentWithVar = (VAR *)pvargDest.llVal;
      if ( *pvargDest.bstrVal != 24588 )
      {
        if ( v149 == 107 )
        {
LABEL_105:
          IsIDispatch = VAR::IsIDispatch(*((VAR **)v6 + 58), &v320);
          v100 = (VARIANTARG *)*((_QWORD *)v6 + 58);
          if ( IsIDispatch )
          {
            Adr = InvokeDispatch(*(struct CSession **)v6, v320, -4, 3, v100, 0, 0);
            CScriptRuntime::IfErrorHr(v6, Adr);
            Adr = AssignVar(*(struct CSession **)v6, (struct VAR *)v46, *((struct VAR **)v6 + 58), 0);
            CScriptRuntime::IfErrorHr(v6, Adr);
            if ( ((*(_WORD *)v46 - 9) & 0xFFFB) != 0
              || (v136 = v46[1]) == 0
              || (**(int (__fastcall ***)(struct CEnumArray *, GUID *, struct CEnumArray **))v136)(
                   v136,
                   &IID_IEnumVARIANT,
                   &v322) < 0 )
            {
              Adr = -2146827837;
              CScriptRuntime::IfErrorHr(v6, -2146827837);
            }
            (*(void (__fastcall **)(struct CEnumArray *))(*(_QWORD *)v46[1] + 16LL))(v46[1]);
            v46[1] = v322;
            *(_WORD *)v46 = 77;
            v137 = v320;
            *(_QWORD *)(v48 + 8) = v320;
            *(_WORD *)v48 = 9;
            ((void (__fastcall *)(struct IDispatch *))v137->lpVtbl->AddRef)(v137);
          }
          else if ( (unsigned int)VAR::IsArray((VAR *)v100) )
          {
            Adr = CEnumArray::Create(*((struct VAR **)v6 + 58), &v322);
            CScriptRuntime::IfErrorHr(v6, Adr);
            v46[1] = v322;
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
          v322 = v46[1];
          *((_QWORD *)v6 + 58) -= 24LL;
        }
        **((_WORD **)v6 + 58) = 11;
        *(_WORD *)(*((_QWORD *)v6 + 58) + 8LL) = 0;
        pvargDest.vt = 0;
        Adr = VAR::Clear(CurrentWithVar);
        CScriptRuntime::IfErrorHr(v6, Adr);
        Adr = (*(__int64 (__fastcall **)(struct CEnumArray *, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)v322 + 24LL))(
                v322,
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
      v319 = v7;
      *((_QWORD *)v6 + 59) = v10 + 2;
      v72 = (VAR *)(*((_QWORD *)v6 + 9) - 24 * v71);
      VAR::Clear(v70);
      VAR::Clear(v72);
      goto LABEL_19;
    case 110:
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL) )
        CScriptRuntime::IfErrorHr(v6, -2146828281);
      CurrentWithVar = VAR::PvarCutAll(*((VAR **)v6 + 58));
      v158 = *((_QWORD *)CurrentWithVar + 2);
      v159 = *(_QWORD *)(*(_QWORD *)v6 + 32LL);
      v339 = *(_OWORD *)CurrentWithVar;
      v340 = v158;
      v160 = *(_QWORD *)(v159 + 136);
      v337 = v339;
      v338 = v158;
      v161 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v160 + 208LL))(v160, &v337);
      goto LABEL_191;
    case 111:
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL) )
        CScriptRuntime::IfErrorHr(v6, -2146828281);
      v163 = (_WORD *)*((_QWORD *)v6 + 58);
      if ( *v163 == 2 )
      {
        v164 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL);
        v161 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v164 + 216LL))(v164, (unsigned __int16)v163[4]);
      }
      else
      {
        CurrentWithVar = VAR::PvarGetTypeVal(*((VARIANTARG **)v6 + 58), 2u);
        v162 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 32LL) + 136LL);
        v161 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v162 + 216LL))(
                 v162,
                 *((unsigned __int16 *)CurrentWithVar + 4));
      }
LABEL_191:
      CScriptRuntime::IfResponseError(v6, v161);
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
0x180023ad0  mov     [rsp-8+arg_10], rbx
0x180023ad5  push    rbp
0x180023ad6  push    rsi
0x180023ad7  push    rdi
0x180023ad8  push    r12
0x180023ada  push    r13
0x180023adc  push    r14
0x180023ade  push    r15
0x180023ae0  lea     rbp, [rsp-0E0h]
0x180023ae8  sub     rsp, 1E0h
0x180023aef  mov     rax, cs:__security_cookie
0x180023af6  xor     rax, rsp
0x180023af9  mov     [rbp+110h+var_38], rax
0x180023b00  mov     [rsp+210h+var_1D0], 0
0x180023b08  mov     r8, rcx
0x180023b0b  mov     rax, [rcx+30h]
0x180023b0f  xorps   xmm0, xmm0
0x180023b12  mov     [rbp+110h+var_140], rcx
0x180023b16  xorps   xmm1, xmm1
0x180023b19  mov     [rbp+110h+var_158], rdx
0x180023b1d  mov     rdx, rsp
0x180023b20  mov     [rbp+110h+var_174], 0
0x180023b27  mov     ecx, [rax+18h]
0x180023b2a  xor     eax, eax
0x180023b2c  mov     [rbp+110h+var_188], rax
0x180023b30  mov     [rsp+210h+var_1C8], rax
0x180023b35  mov     [rsp+210h+var_1B8], rax
0x180023b3a  mov     [rsp+210h+var_1B0], rax
0x180023b3f  mov     qword ptr [rbp+110h+pvargDest+10h], rax
0x180023b43  mov     [rsp+210h+var_1A8], rax
0x180023b48  mov     [rbp+110h+var_88], rax
0x180023b4f  mov     qword ptr [rbp+110h+var_E0+10h], rax
0x180023b53  mov     [rbp+110h+var_17C], eax
0x180023b56  mov     [rsp+210h+var_1C0], eax
0x180023b5a  lea     rax, [rsp+210h+var_1D0]
0x180023b5f  movups  [rsp+210h+var_198], xmm0
0x180023b64  mov     [rbp+110h+var_178], ecx
0x180023b67  lea     rcx, [r8+0B0h]; Buf
0x180023b6e  movups  xmmword ptr [rbp+110h+pvargDest], xmm0
0x180023b72  movups  [rbp+110h+var_98], xmm0
0x180023b76  movups  xmmword ptr [rbp+110h+var_E0], xmm1
0x180023b7a  mov     [r8+238h], rax
0x180023b81  lea     rax, [rbp+110h+var_174]
0x180023b85  mov     [r8+230h], rax
0x180023b8c  call    _setjmp_0
0x180023b91  mov     rsi, [rbp+110h+var_140]
0x180023b95  lea     rbx, __ImageBase
0x180023b9c  mov     r10d, 0FFFFFFFFh
0x180023ba2  test    eax, eax
0x180023ba4  jnz     loc_180025049
0x180023baa  mov     r13d, [rsp+210h+var_1C0]
0x180023baf  mov     r8d, 8000h
0x180023bb5  mov     r11d, 8
0x180023bbb  mov     r14d, 0Bh
0x180023bc1  mov     r12d, 1
0x180023bc7  mov     r15d, 400Ch
0x180023bcd  mov     edi, 2
0x180023bd2  mov     rdx, [rsi+1D8h]
0x180023bd9  movzx   eax, byte ptr [rdx]
0x180023bdc  lea     r9, [rdx+1]
0x180023be0  mov     [rsi+1D8h], r9
0x180023be7  cmp     eax, 19h
0x180023bea  jz      loc_180023D2C
0x180023bf0  cmp     eax, 3
0x180023bf3  jz      loc_180023DA2
0x180023bf9  cmp     eax, 6Fh; switch 112 cases
0x180023bfc  ja      def_180023C0C; jumptable 0000000180023C0C default case, cases 3,25
0x180023c02  mov     ecx, ds:(jpt_180023C0C - 180000000h)[rbx+rax*4]
0x180023c09  add     rcx, rbx
0x180023c0c  jmp     rcx; switch jump
0x180023c0e  mov     r14d, [r9]; jumptable 0000000180023C0C case 40
0x180023c11  lea     rcx, [r9+4]
0x180023c15  mov     [rsi+1D8h], rcx
0x180023c1c  lea     rax, [r9+6]
0x180023c20  add     r14, [rsi+1F0h]
0x180023c27  lea     r8, [rbp+110h+pvargDest]; struct VAR *
0x180023c2b  movzx   edi, word ptr [rcx]
0x180023c2e  mov     rdx, r14; unsigned __int16 *
0x180023c31  mov     rcx, rsi; this
0x180023c34  mov     [rsi+1D8h], rax
0x180023c3b  call    ?GetVarAdr@CScriptRuntime@@AEAAHPEBGPEAVVAR@@@Z; CScriptRuntime::GetVarAdr(ushort const *,VAR *)
0x180023c40  lea     rcx, [rbp+110h+pvargDest]; this
0x180023c44  mov     ebx, eax
0x180023c46  call    ?IsDispmember@VAR@@QEAAHXZ; VAR::IsDispmember(void)
0x180023c4b  test    eax, eax
0x180023c4d  jnz     loc_1800268CB
0x180023c53  lea     rcx, [rbp+110h+pvargDest]; this
0x180023c57  call    ?PvarCutRef@VAR@@QEAAPEAV1@XZ; VAR::PvarCutRef(void)
0x180023c5c  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x180023c61  mov     [rsp+210h+var_1C8], rax
0x180023c66  mov     rcx, rax; this
0x180023c69  call    ?IsFunction@VAR@@QEAAHPEAPEAVIEntryPoint@@@Z; VAR::IsFunction(IEntryPoint * *)
0x180023c6e  test    eax, eax
0x180023c70  jz      loc_180026908
0x180023c76  mov     rcx, [rsp+210h+var_1B0]
0x180023c7b  mov     rax, [rcx]
0x180023c7e  mov     rax, [rax+10h]
0x180023c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c87  test    eax, eax
0x180023c89  jnz     loc_1800247A4
0x180023c8f  xor     eax, eax
0x180023c91  mov     word ptr [rbp+110h+pvargDest], ax
0x180023c95  test    ebx, ebx
0x180023c97  jnz     loc_18002692D
0x180023c9d  mov     rcx, [rsp+210h+var_1B0]
0x180023ca2  mov     rax, [rcx]
0x180023ca5  mov     rax, [rax]
0x180023ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cad  mov     rcx, [rsp+210h+var_1B0]
0x180023cb2  lea     rdx, [rbp+110h+pvargDest]
0x180023cb6  mov     r9, [rsi+1D0h]
0x180023cbd  mov     r8d, edi
0x180023cc0  mov     [rsp+210h+var_1E8], ebx
0x180023cc4  mov     [rsp+210h+pvarSrc], 0
0x180023ccd  mov     rax, [rcx]
0x180023cd0  mov     rax, [rax+20h]
0x180023cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd9  mov     rcx, [rsp+210h+var_1B0]
0x180023cde  mov     [rsp+210h+var_1D0], eax
0x180023ce2  mov     rax, [rcx]
0x180023ce5  mov     rax, [rax+8]
0x180023ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cee  mov     edx, [rsp+210h+var_1D0]; int
0x180023cf2  mov     r8, r14; unsigned __int16 *
0x180023cf5  mov     rcx, rsi; this
0x180023cf8  call    ?IfErrorHrPsz@CScriptRuntime@@AEAAXJPEBG@Z; CScriptRuntime::IfErrorHrPsz(long,ushort const *)
0x180023cfd  mov     eax, edi
0x180023cff  lea     rcx, [rax+rax*2]
0x180023d03  lea     rcx, ds:0FFFFFFFFFFFFFFE8h[rcx*8]
0x180023d0b  add     [rsi+1D0h], rcx
0x180023d12  mov     rax, [rsi+1D0h]
0x180023d19  movups  xmm0, xmmword ptr [rbp+110h+pvargDest]
0x180023d1d  movups  xmmword ptr [rax], xmm0
0x180023d20  movsd   xmm1, qword ptr [rbp+110h+pvargDest+10h]
0x180023d25  movsd   qword ptr [rax+10h], xmm1
0x180023d2a  jmp     short loc_180023D77
0x180023d2c  movsx   ecx, word ptr [r9]
0x180023d30  lea     rax, [r9+2]
0x180023d34  mov     r13d, ecx
0x180023d37  mov     [rsp+210h+var_1C0], ecx
0x180023d3b  mov     edx, ecx; int
0x180023d3d  mov     [rsi+1D8h], rax
0x180023d44  mov     rcx, rsi; this
0x180023d47  call    ?PvarLocal@CScriptRuntime@@AEAAPEAVVAR@@H@Z; CScriptRuntime::PvarLocal(int)
0x180023d4c  mov     [rsp+210h+var_1C8], rax
0x180023d51  add     qword ptr [rsi+1D0h], 0FFFFFFFFFFFFFFE8h
0x180023d59  mov     rcx, [rsp+210h+var_1C8]
0x180023d5e  mov     rax, [rsi+1D0h]
0x180023d65  cmp     [rcx], r15w
0x180023d69  jz      loc_180024052
0x180023d6f  mov     [rax], r15w
0x180023d73  mov     [rax+8], rcx
0x180023d77  mov     r10d, 0FFFFFFFFh
0x180023d7d  mov     r8d, 8000h
0x180023d83  mov     r11d, 8
0x180023d89  cmp     cs:?vbs_interpreter_override_bailout@@3_NA, 0; jumptable 0000000180023C0C cases 0,2
0x180023d90  jnz     loc_180027666
0x180023d96  lea     rbx, __ImageBase
0x180023d9d  jmp     loc_180023BBB
0x180023da2  movzx   ecx, byte ptr [r9]
0x180023da6  lea     rax, [r9+1]
0x180023daa  mov     [rsi+1D8h], rax
0x180023db1  mov     [rsi+1E8h], ecx
0x180023db7  mov     rcx, [rsi]; this
0x180023dba  call    ?FInterrupt@CSession@@QEAAHXZ; CSession::FInterrupt(void)
0x180023dbf  test    eax, eax
0x180023dc1  jnz     loc_180027563
0x180023dc7  mov     rcx, [rsi+30h]; this
0x180023dcb  mov     eax, [rbp+110h+var_178]
0x180023dce  cmp     eax, [rcx+18h]
0x180023dd1  jl      short loc_180023E23
0x180023dd3  mov     rcx, [rsi]; this
0x180023dd6  call    ?PollHalt@CSession@@QEAAJXZ; CSession::PollHalt(void)
0x180023ddb  mov     [rsp+210h+var_1D0], eax
0x180023ddf  test    eax, eax
0x180023de1  jns     short loc_180023D77
0x180023de3  jmp     loc_1800246E4
0x180023de8  mov     ebx, [r9]; jumptable 0000000180023C0C case 60
0x180023deb  lea     rax, [r9+4]
0x180023def  mov     [rsi+1D8h], rax
0x180023df6  mov     rcx, [rsi+1D0h]
0x180023dfd  cmp     word ptr [rcx], 0Bh
0x180023e01  jnz     loc_180024823
0x180023e07  xor     edx, edx
0x180023e09  cmp     [rcx+8], dx
0x180023e0d  setz    dl; int
0x180023e10  mov     r9d, r12d; int
0x180023e13  mov     r8d, ebx; unsigned int
0x180023e16  mov     rcx, rsi; this
0x180023e19  call    ?Branch@CScriptRuntime@@AEAAXHIH@Z; CScriptRuntime::Branch(int,uint,int)
0x180023e1e  jmp     loc_180023D77
0x180023e23  mov     edx, eax; int
0x180023e25  call    ?FreeToMark@GcContext@@QEAAXJ@Z; GcContext::FreeToMark(long)
0x180023e2a  jmp     short loc_180023DD3
0x180023e2c  add     qword ptr [rsi+1D0h], 0FFFFFFFFFFFFFFE8h; jumptable 0000000180023C0C case 11
0x180023e34  mov     rax, [rsi+1D0h]
0x180023e3b  mov     [rax], di
0x180023e3e  mov     rax, [rsi+1D8h]
0x180023e45  movsx   ecx, byte ptr [rax]
0x180023e48  inc     rax
0x180023e4b  mov     [rsi+1D8h], rax
0x180023e52  mov     rax, [rsi+1D0h]
0x180023e59  mov     [rax+8], cx
0x180023e5d  jmp     loc_180023D89; jumptable 0000000180023C0C cases 0,2
0x180023e62  mov     [rbp+110h+var_148], 0; jumptable 0000000180023C0C cases 28,29
0x180023e6a  lea     rax, [r9+4]
0x180023e6e  movzx   r14d, byte ptr [rdx]
0x180023e72  lea     r8, [rbp+110h+var_148]; struct CScriptRuntime **
0x180023e76  mov     ebx, [r9]
0x180023e79  mov     [rsi+1D8h], rax
0x180023e80  xor     eax, eax
0x180023e82  add     rbx, [rsi+1F0h]
0x180023e89  add     qword ptr [rsi+1D0h], 0FFFFFFFFFFFFFFE8h
0x180023e91  mov     rdx, rbx; unsigned __int16 *
0x180023e94  mov     rcx, [rsi+1D0h]
0x180023e9b  mov     [rcx], ax
0x180023e9e  mov     rcx, rsi; this
0x180023ea1  call    ?FUseLocalInEval@CScriptRuntime@@AEAAHPEBGPEAPEAV1@@Z; CScriptRuntime::FUseLocalInEval(ushort const *,CScriptRuntime * *)
0x180023ea6  test    eax, eax
0x180023ea8  jnz     loc_180025B3C
0x180023eae  mov     r8, [rsi+1D0h]; struct VAR *
0x180023eb5  mov     rdx, rbx; unsigned __int16 *
0x180023eb8  mov     rcx, rsi; this
0x180023ebb  call    ?GetVarAdr@CScriptRuntime@@AEAAHPEBGPEAVVAR@@@Z; CScriptRuntime::GetVarAdr(ushort const *,VAR *)
0x180023ec0  mov     rcx, [rsi+1D0h]; this
0x180023ec7  mov     edi, eax
0x180023ec9  call    ?IsDispmember@VAR@@QEAAHXZ; VAR::IsDispmember(void)
0x180023ece  mov     rcx, [rsi+1D0h]; this
0x180023ed5  test    eax, eax
0x180023ed7  jnz     loc_180025B84
0x180023edd  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x180023ee2  call    ?IsFunction@VAR@@QEAAHPEAPEAVIEntryPoint@@@Z; VAR::IsFunction(IEntryPoint * *)
0x180023ee7  test    eax, eax
0x180023ee9  jnz     loc_180025BDE
0x180023eef  mov     rcx, [rsi+1D0h]; this
0x180023ef6  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x180023efb  mov     r8d, 4; unsigned __int16
0x180023f01  call    ?IsProperty@VAR@@QEAAHPEAPEAVIEntryPoint@@G@Z; VAR::IsProperty(IEntryPoint * *,ushort)
0x180023f06  test    eax, eax
0x180023f08  jnz     loc_180025BDE
0x180023f0e  mov     rcx, [rsi+1D0h]; this
0x180023f15  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x180023f1a  call    ?IsClass@VAR@@QEAAHPEAPEAVIEntryPoint@@@Z; VAR::IsClass(IEntryPoint * *)
0x180023f1f  test    eax, eax
0x180023f21  jnz     loc_180025BC1
0x180023f27  mov     rcx, [rsi+1D0h]; this
0x180023f2e  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x180023f33  mov     r8d, r12d; unsigned __int16
0x180023f36  call    ?IsProperty@VAR@@QEAAHPEAPEAVIEntryPoint@@G@Z; VAR::IsProperty(IEntryPoint * *,ushort)
0x180023f3b  test    eax, eax
0x180023f3d  jnz     loc_180025BC1
0x180023f43  mov     rcx, [rsi+1D0h]; this
0x180023f4a  lea     rdx, [rsp+210h+var_1B0]; struct IEntryPoint **
0x180023f4f  mov     r8d, 2; unsigned __int16
0x180023f55  call    ?IsProperty@VAR@@QEAAHPEAPEAVIEntryPoint@@G@Z; VAR::IsProperty(IEntryPoint * *,ushort)
0x180023f5a  test    eax, eax
0x180023f5c  jnz     loc_180025BC1
0x180023f62  cmp     r14b, 1Ch
0x180023f66  jnz     loc_180023D77
0x180023f6c  jmp     loc_18002713F
0x180023f71  mov     rax, [rsi+1D0h]; jumptable 0000000180023C0C case 84
0x180023f78  or      [rax], r8w
0x180023f7c  jmp     loc_180023D89; jumptable 0000000180023C0C cases 0,2
0x180023f81  mov     edi, [r9]; jumptable 0000000180023C0C case 35
0x180023f84  lea     rax, [r9+4]
0x180023f88  mov     [rsi+1D8h], rax
0x180023f8f  lea     rdx, [rsp+210h+var_1B8]; struct IDispatch **
0x180023f94  mov     rcx, [rsi+1D0h]; this
0x180023f9b  add     rdi, [rsi+1F0h]
0x180023fa2  call    ?IsIDispatch@VAR@@QEAAHPEAPEAUIDispatch@@@Z; VAR::IsIDispatch(IDispatch * *)
0x180023fa7  test    eax, eax
0x180023fa9  jz      loc_180025D23
0x180023faf  mov     rcx, [rsi+1D0h]
0x180023fb6  xor     eax, eax
0x180023fb8  mov     rdx, rdi; unsigned __int16 *
0x180023fbb  mov     [rcx], ax
0x180023fbe  lea     rcx, [rsp+210h+var_198]; this
0x180023fc3  mov     rbx, [rsi+1D0h]
0x180023fca  call    ?InitFromSymbol@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromSymbol(ushort const *)
0x180023fcf  mov     rdx, [rsp+210h+var_1B8]; struct IDispatch *
0x180023fd4  mov     r9d, 3; unsigned int
0x180023fda  mov     rcx, [rsi]; struct CSession *
0x180023fdd  mov     r8, rax; struct SYM *
0x180023fe0  mov     [rsp+210h+var_1E0], 0; struct VAR *
0x180023fe9  mov     [rsp+210h+var_1E8], 0; int
0x180023ff1  mov     [rsp+210h+pvarSrc], rbx; struct VAR *
0x180023ff6  call    ?InvokeByName@@YAJPEAVCSession@@PEAUIDispatch@@PEAUSYM@@KPEAVVAR@@H3@Z; InvokeByName(CSession *,IDispatch *,SYM *,ulong,VAR *,int,VAR *)
0x180023ffb  mov     r9, rdi; unsigned __int16 *
0x180023ffe  mov     [rsp+210h+var_1D0], eax
0x180024002  mov     r8, rbx; struct VAR *
0x180024005  mov     dword ptr [rsp+210h+pvarSrc], 0; int
0x18002400d  mov     edx, eax; int
0x18002400f  mov     rcx, rsi; this
0x180024012  call    ?IfErrorHrArg@CScriptRuntime@@AEAAXJPEAVVAR@@PEBGH@Z; CScriptRuntime::IfErrorHrArg(long,VAR *,ushort const *,int)
0x180024017  jmp     loc_180023D77
0x18002401c  mov     ebx, [r9]; jumptable 0000000180023C0C case 59
0x18002401f  lea     rax, [r9+4]
0x180024023  mov     [rsi+1D8h], rax
0x18002402a  mov     rcx, [rsi+1D0h]
0x180024031  cmp     word ptr [rcx], 0Bh
  ... truncated ...
```
