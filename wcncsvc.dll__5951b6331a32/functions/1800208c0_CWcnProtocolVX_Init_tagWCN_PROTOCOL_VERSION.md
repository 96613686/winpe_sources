# CWcnProtocolVX::Init(tagWCN_PROTOCOL_VERSION)

- ea: `0x1800208c0`
- end: `0x180025cde`
- name: `?Init@CWcnProtocolVX@@QEAAJW4tagWCN_PROTOCOL_VERSION@@@Z`
- size: `21534`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180003dec`

## callees

- `0x180001404`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x1800196cc`
- `0x18001e828`
- `0x18001fa44`
- `0x18001fa5c`
- `0x18001fa90`
- `0x18001fab0`
- `0x18001fae4`
- `0x18001fdf0`
- `0x18001fe8c`
- `0x1800208c0`
- `0x180026a3c`
- `0x180028514`
- `0x180028798`
- `0x180053004`
- `0x180055cbc`
- `0x180055cd8`
- `0x180055f00`

## string_xrefs

- `0x18002421f`: `Final : Discovery complete (Proxy) [VX]`
- `0x180024511`: `Final : Discovery complete (NackNack) [VX]`
- `0x180024754`: `Final : Discovery complete (ACK) [VX]`
- `0x180024835`: `Final : Discovery complete (No M2D) [VX]`
- `0x180025281`: `Final : Finished full protocol (skip M8) [VX]`
- `0x1800254bd`: `Final : Finished full protocol (no DONE) [VX]`
- `0x180025778`: `ACK : Process final ack for full protocol [VX]`
- `0x180025866`: `Final : Finished full protocol (with ACK) [VX]`
- `0x180025944`: `Final : Finished full protocol (no ACK) [VX]`

## pseudocode

```c
__int64 __fastcall CWcnProtocolVX::Init(__int64 a1, int a2)
{
  const char *Indent; // rax
  const char *v5; // rax
  __int64 *v6; // rax
  __int64 *v7; // rdi
  __int64 ***v8; // r12
  int v9; // edi
  const wchar_t *v10; // rcx
  __int64 v11; // r9
  __int64 *v12; // r8
  int v13; // eax
  __int64 *v14; // rax
  __int64 *v15; // rdi
  const wchar_t *v16; // rcx
  __int64 *v17; // r8
  __int64 v18; // r9
  int v19; // eax
  __int64 *v20; // rax
  __int64 *v21; // rdi
  __int64 *v22; // rax
  __int64 *v23; // rdi
  const wchar_t *v24; // rcx
  __int64 *v25; // r8
  __int64 v26; // r9
  int v27; // eax
  __int64 *v28; // rax
  __int64 *v29; // rdi
  const wchar_t *v30; // rcx
  __int64 *v31; // r8
  int v32; // eax
  __int64 *v33; // rax
  __int64 *v34; // rdi
  const wchar_t *v35; // rcx
  __int64 *v36; // r8
  __int64 v37; // r9
  int v38; // eax
  __int64 *v39; // rax
  __int64 *v40; // rdi
  const wchar_t *v41; // rcx
  __int64 *v42; // r8
  __int64 v43; // r9
  int v44; // eax
  __int64 *v45; // rax
  __int64 *v46; // rdi
  const wchar_t *v47; // rcx
  __int64 *v48; // r8
  __int64 v49; // r9
  int v50; // eax
  __int64 *v51; // rax
  __int64 *v52; // rdi
  const wchar_t *v53; // rcx
  __int64 *v54; // r8
  __int64 v55; // r9
  int v56; // eax
  __int64 *v57; // rax
  __int64 *v58; // rdi
  const wchar_t *v59; // rcx
  __int64 *v60; // r8
  __int64 v61; // r9
  int v62; // eax
  __int64 *v63; // rax
  __int64 *v64; // rdi
  const wchar_t *v65; // rcx
  __int64 *v66; // r8
  __int64 v67; // r9
  int v68; // eax
  __int64 *v69; // rax
  __int64 *v70; // rdi
  const wchar_t *v71; // rcx
  __int64 *v72; // r8
  __int64 v73; // r9
  int v74; // eax
  __int64 *v75; // rax
  __int64 *v76; // rdi
  const wchar_t *v77; // rcx
  __int64 *v78; // r8
  __int64 v79; // r9
  int v80; // eax
  __int64 *v81; // rax
  __int64 *v82; // rdi
  __int64 *v83; // rax
  __int64 *v84; // rdi
  const wchar_t *v85; // rax
  __int64 *v86; // r8
  int v87; // eax
  __int64 *v88; // rax
  __int64 *v89; // rdi
  const wchar_t *v90; // rax
  __int64 *v91; // r8
  int v92; // eax
  __int64 *v93; // rax
  __int64 *v94; // rdi
  const wchar_t *v95; // rax
  __int64 *v96; // r8
  int v97; // eax
  __int64 *v98; // rax
  __int64 v99; // r13
  const wchar_t *v100; // rax
  __int64 *v101; // r8
  int v102; // eax
  __int64 *v103; // rax
  __int64 v104; // r15
  const wchar_t *v105; // rax
  __int64 *v106; // r8
  int v107; // eax
  __int64 *v108; // rax
  __int64 v109; // r14
  const wchar_t *v110; // rax
  __int64 *v111; // r8
  int v112; // eax
  __int64 *v113; // rax
  __int64 v114; // rsi
  const wchar_t *v115; // rax
  __int64 *v116; // r8
  int v117; // eax
  __int64 *v118; // rax
  __int64 *v119; // rdi
  unsigned __int8 v120; // r12
  const wchar_t *v121; // rcx
  __int64 *v122; // r8
  __int64 v123; // r9
  int v124; // eax
  __int64 *v125; // rax
  __int64 *v126; // rdi
  int v127; // eax
  __int64 *v128; // rax
  __int64 *v129; // rdi
  int v130; // eax
  __int64 *v131; // rax
  __int64 *v132; // rdi
  int v133; // eax
  __int64 *v134; // rax
  __int64 *v135; // rdi
  int v136; // eax
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 *v143; // rax
  struct CWcnProtocolVX *v144; // r15
  __int64 ***v145; // rsi
  int v146; // edi
  const wchar_t **v147; // rax
  const wchar_t *v148; // rcx
  const wchar_t *v149; // rcx
  const wchar_t **v150; // rax
  const wchar_t *v151; // rcx
  const wchar_t **v152; // rax
  const wchar_t *v153; // rcx
  const wchar_t **v154; // rax
  const wchar_t *v155; // rcx
  const wchar_t **v156; // rax
  const wchar_t *v157; // rcx
  const wchar_t **v158; // rax
  const wchar_t *v159; // rcx
  const wchar_t **v160; // rax
  const wchar_t *v161; // rcx
  const wchar_t **v162; // rax
  const wchar_t *v163; // rcx
  const wchar_t **v164; // rax
  const wchar_t *v165; // rcx
  const wchar_t **v166; // rax
  const wchar_t *v167; // rcx
  const wchar_t **v168; // rax
  const wchar_t *v169; // rcx
  const wchar_t **v170; // rax
  const wchar_t *v171; // rcx
  const wchar_t **v172; // rax
  const wchar_t *v173; // rcx
  const wchar_t **v174; // rax
  const wchar_t *v175; // rcx
  const wchar_t **v176; // rax
  const wchar_t *v177; // rcx
  const wchar_t **v178; // rax
  const wchar_t *v179; // rcx
  CSmState *v180; // rax
  struct CSmState *v181; // rax
  CSmState *v182; // rax
  CSmState *v183; // rax
  CSmState *v184; // rax
  CSmState *v185; // rax
  CSmState *v186; // rdi
  CSmState *v187; // rax
  CSmState *v188; // rax
  CSmState *v189; // rax
  CSmState *v190; // rax
  CSmState *v191; // rax
  CSmState *v192; // rax
  CSmState *v193; // rax
  struct CSmState *v194; // rax
  CSmState *v195; // rax
  CSmState *v196; // rax
  CSmState *v197; // rax
  CSmState *v198; // rax
  int v199; // edi
  int v200; // edi
  int v201; // edi
  CSmState *v202; // rax
  struct CSmState *v203; // rax
  CSmState *v204; // rax
  CSmState *v205; // rax
  CSmState *v206; // rax
  struct CWcnProtocolVX *v207; // rsi
  CWcnProtocolVX::CVXNackCheck *v208; // rax
  struct CSmTransition *v209; // rdi
  char *v210; // r14
  CWcnProtocolVX::CVXResendCheck *v211; // rax
  struct CSmTransition *v212; // rdi
  __int64 *v213; // rax
  __int64 v214; // rdi
  CWcnProtocolVX::CVXM2DiscoveryCheck *v215; // rax
  struct CSmTransition *v216; // rdi
  CWcnProtocolVX::CVXResendCheck *v217; // rax
  struct CSmTransition *v218; // rdi
  __int64 *v219; // rax
  __int64 v220; // rdi
  CWcnProtocolVX::CVXNackCheck *v221; // rax
  struct CSmTransition *v222; // rdi
  CWcnProtocolVX::CVXResendCheck *v223; // rax
  struct CSmTransition *v224; // rdi
  __int64 *v225; // rax
  __int64 v226; // rdi
  CWcnProtocolVX::CVXNackCheck *v227; // rax
  struct CSmTransition *v228; // rdi
  __int64 *v229; // rax
  __int64 v230; // rdi
  CWcnProtocolVX::CVXNackCheck *v231; // rax
  struct CSmTransition *v232; // rdi
  __int64 *v233; // rax
  __int64 v234; // rdi
  CWcnProtocolVX::CVXNackCheck *v235; // rax
  struct CSmTransition *v236; // rdi
  __int64 *v237; // rax
  __int64 v238; // rdi
  CWcnProtocolVX::CVXNackCheck *v239; // rax
  struct CSmTransition *v240; // rdi
  __int64 *v241; // rax
  __int64 v242; // rdi
  CWcnProtocolVX::CVXNackCheck *v243; // rax
  struct CSmTransition *v244; // rdi
  __int64 *v245; // rax
  __int64 v246; // rdi
  CWcnProtocolVX::CVXResendCheck *v247; // rax
  struct CSmTransition *v248; // rdi
  __int64 *v249; // rax
  __int64 v250; // rdi
  CWcnProtocolVX::CVXResendCheck *v251; // rax
  struct CSmTransition *v252; // rdi
  __int64 *v253; // rax
  __int64 v254; // rdi
  CWcnProtocolVX::CVXNackCheck *v255; // rax
  struct CSmTransition *v256; // rdi
  __int64 *v257; // rax
  __int64 v258; // rdi
  CWcnProtocolVX::CVXNackCheck *v259; // rax
  struct CSmTransition *v260; // rdi
  CWcnProtocolVX::CVXResendCheck *v261; // rax
  struct CSmTransition *v262; // rdi
  __int64 *v263; // rax
  __int64 v264; // rdi
  CWcnProtocolVX::CVXNackCheck *v265; // rax
  struct CSmTransition *v266; // rdi
  __int64 *v267; // rax
  __int64 v268; // rdi
  CWcnProtocolVX::CVXNackCheck *v269; // rax
  struct CSmTransition *v270; // rdi
  __int64 *v271; // rax
  __int64 v272; // rdi
  CWcnProtocolVX::CVXNackCheck *v273; // rax
  struct CSmTransition *v274; // rdi
  CWcnProtocolVX::CVXResendCheck *v275; // rax
  struct CSmTransition *v276; // rdi
  __int64 *v277; // rax
  __int64 v278; // rdi
  CWcnProtocolVX::CVXNackCheck *v279; // rax
  struct CSmTransition *v280; // rdi
  CWcnProtocolVX::CVXResendCheck *v281; // rax
  struct CSmTransition *v282; // rdi
  __int64 *v283; // rax
  __int64 v284; // rdi
  CWcnProtocolVX::CVXNackCheck *v285; // rax
  struct CSmTransition *v286; // rdi
  CWcnProtocolVX::CVXResendCheck *v287; // rax
  struct CSmTransition *v288; // rdi
  __int64 *v289; // rax
  __int64 v290; // rdi
  CWcnProtocolVX::CVXNackCheck *v291; // rax
  struct CSmTransition *v292; // rdi
  CWcnProtocolVX::CVXResendCheck *v293; // rax
  struct CSmTransition *v294; // rdi
  __int64 *v295; // rax
  __int64 v296; // rdi
  CWcnProtocolVX::CVXNackCheck *v297; // rax
  struct CSmTransition *v298; // rdi
  CWcnProtocolVX::CVXResendCheck *v299; // rax
  struct CSmTransition *v300; // rdi
  __int64 *v301; // rax
  __int64 v302; // rdi
  CWcnProtocolVX::CVXNackCheck *v303; // rax
  struct CSmTransition *v304; // rdi
  CWcnProtocolVX::CVXResendCheck *v305; // rax
  struct CSmTransition *v306; // rdi
  __int64 *v307; // rax
  __int64 v308; // rdi
  CWcnProtocolVX::CVXResendCheck *v309; // rax
  struct CSmTransition *v310; // rdi
  __int64 *v311; // rax
  __int64 v312; // rdi
  CWcnProtocolVX::CVXNackCheck *v313; // rax
  struct CSmTransition *v314; // rdi
  __int64 *v315; // rax
  __int64 v316; // rdi
  CWcnProtocolVX::CVXNackCheck *v317; // rax
  struct CSmTransition *v318; // rdi
  CWcnProtocolVX::CVXResendCheck *v319; // rax
  struct CSmTransition *v320; // rdi
  __int64 *v321; // rax
  __int64 v322; // rdi
  CWcnProtocolVX::CVXNackCheck *v323; // rax
  struct CSmTransition *v324; // rdi
  __int64 *v325; // rax
  __int64 v326; // rdi
  CWcnProtocolVX::CVXNackCheck *v327; // rax
  struct CSmTransition *v328; // rdi
  CWcnProtocolVX::CVXResendCheck *v329; // rax
  struct CSmTransition *v330; // rdi
  __int64 *v331; // rax
  __int64 v332; // rdi
  CWcnProtocolVX::CVXNackCheck *v333; // rax
  struct CSmTransition *v334; // rdi
  CWcnProtocolVX::CVXResendCheck *v335; // rax
  struct CWcnProtocolVX *v336; // r15
  struct CSmTransition *v337; // rdi
  __int64 *v338; // rax
  __int64 v339; // rdi
  CWcnProtocolVX::CVXNackCheck *v340; // rax
  struct CSmTransition *v341; // rdi
  __int64 *v342; // rax
  __int64 v343; // rdi
  CWcnProtocolVX::CVXNackCheck *v344; // rax
  struct CSmTransition *v345; // rdi
  __int64 *v346; // rax
  __int64 v347; // rdi
  CWcnProtocolVX::CVXNackCheck *v348; // rax
  struct CSmTransition *v349; // rdi
  CWcnProtocolVX::CVXResendCheck *v350; // rax
  struct CWcnProtocolVX *v351; // rsi
  struct CSmTransition *v352; // rdi
  struct CWcnProtocolVX *v353; // rax
  __int64 v354; // rdi
  struct CWcnProtocolVX *v355; // rax
  struct CSmTransition *v356; // rdi
  struct CWcnProtocolVX *v357; // rax
  __int64 v358; // rdi
  CSmState *v359; // rcx
  _QWORD *v360; // rax
  __int64 v361; // rdx
  unsigned int v362; // eax
  struct CSmState *v364; // [rsp+30h] [rbp-158h] BYREF
  struct CSmState *v365; // [rsp+38h] [rbp-150h] BYREF
  struct CSmState *v366; // [rsp+40h] [rbp-148h] BYREF
  CSmState *v367; // [rsp+48h] [rbp-140h] BYREF
  struct CSmState *v368; // [rsp+50h] [rbp-138h] BYREF
  struct CSmState *v369; // [rsp+58h] [rbp-130h] BYREF
  __int64 *v370; // [rsp+60h] [rbp-128h] BYREF
  __int64 *v371; // [rsp+68h] [rbp-120h] BYREF
  struct CSmState *v372; // [rsp+70h] [rbp-118h] BYREF
  __int64 *v373; // [rsp+78h] [rbp-110h] BYREF
  __int64 *v374; // [rsp+80h] [rbp-108h] BYREF
  __int64 *v375; // [rsp+88h] [rbp-100h] BYREF
  struct CSmState *v376; // [rsp+90h] [rbp-F8h] BYREF
  __int64 *v377; // [rsp+98h] [rbp-F0h] BYREF
  __int64 *v378; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 *v379; // [rsp+A8h] [rbp-E0h] BYREF
  struct CSmState *v380; // [rsp+B0h] [rbp-D8h] BYREF
  struct CSmState *v381; // [rsp+B8h] [rbp-D0h] BYREF
  struct CSmState *v382; // [rsp+C0h] [rbp-C8h] BYREF
  struct CSmState *v383; // [rsp+C8h] [rbp-C0h] BYREF
  struct CSmState *v384; // [rsp+D0h] [rbp-B8h] BYREF
  __int64 *v385; // [rsp+D8h] [rbp-B0h] BYREF
  __int64 *v386; // [rsp+E0h] [rbp-A8h] BYREF
  __int64 *v387; // [rsp+E8h] [rbp-A0h] BYREF
  __int64 *v388; // [rsp+F0h] [rbp-98h] BYREF
  struct CSmState *v389; // [rsp+F8h] [rbp-90h] BYREF
  _QWORD *v390; // [rsp+100h] [rbp-88h] BYREF
  struct CSmState *v391; // [rsp+108h] [rbp-80h] BYREF
  CSmState *v392; // [rsp+110h] [rbp-78h] BYREF
  CSmState *v393; // [rsp+118h] [rbp-70h] BYREF
  CSmState *v394; // [rsp+120h] [rbp-68h] BYREF
  __int64 *v395; // [rsp+128h] [rbp-60h] BYREF
  const wchar_t **v396; // [rsp+130h] [rbp-58h] BYREF
  __int64 *v397; // [rsp+138h] [rbp-50h]
  struct CWcnProtocolVX *v398; // [rsp+190h] [rbp+8h] BYREF
  int v399; // [rsp+198h] [rbp+10h]
  __int64 *v400; // [rsp+1A0h] [rbp+18h] BYREF
  struct CSmState *v401; // [rsp+1A8h] [rbp+20h] BYREF

  v399 = a2;
  v398 = (struct CWcnProtocolVX *)a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids, Indent);
  }
  v377 = 0;
  v378 = 0;
  v379 = 0;
  v385 = 0;
  v373 = 0;
  v374 = 0;
  v375 = 0;
  v370 = 0;
  v371 = 0;
  v386 = 0;
  v387 = 0;
  v388 = 0;
  v390 = 0;
  v395 = 0;
  *(_DWORD *)(a1 + 152) = a2;
  if ( (*(_BYTE *)(a1 + 157) || *(_BYTE *)(a1 + 156))
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = GetIndent(0);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids, v5);
  }
  v6 = (__int64 *)operator new(0x38u);
  v7 = v6;
  v400 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 4) = 8;
    v6[3] = 0;
    *((_BYTE *)v6 + 36) = 0;
    v6[5] = 0;
    v6[6] = 0;
    *v6 = 0;
  }
  else
  {
    v7 = 0;
  }
  v377 = v7;
  v8 = (__int64 ***)(a1 + 24);
  LODWORD(v400) = 0;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](
     (__int64 ***)(a1 + 24),
     (int *)&v400) = v7;
  if ( a2 == 16 )
  {
    *v377 = (__int64)L"M1 [VX-v1]";
    v13 = CWcnMessage::Init((__int64)v377, 5, (__int64)qword_1800665C0, 23);
    v9 = v13;
  }
  else if ( a2 == 32 )
  {
    *v377 = (__int64)L"M1 [VX-v2]";
    v13 = CWcnMessage::Init((__int64)v377, 5, (__int64)qword_180066020, 24);
    v9 = v13;
  }
  else
  {
    if ( a2 == 272 )
    {
      v10 = L"M1 [VX-v1-WFD]";
      v11 = 23;
      v12 = qword_180065350;
    }
    else
    {
      if ( a2 != 288 )
      {
        v9 = -2147467259;
        goto LABEL_959;
      }
      v10 = L"M1 [VX-v2-WFD]";
      v11 = 24;
      v12 = qword_180065940;
    }
    *v377 = (__int64)v10;
    v13 = CWcnMessage::Init((__int64)v377, 5, (__int64)v12, v11);
    v9 = v13;
  }
  if ( v13 < 0 )
    goto LABEL_959;
  if ( !v13 )
    *((_DWORD *)v377 + 5) = 4;
  v14 = (__int64 *)operator new(0x38u);
  v15 = v14;
  v400 = v14;
  if ( v14 )
  {
    *((_DWORD *)v14 + 4) = 8;
    v14[3] = 0;
    *((_BYTE *)v14 + 36) = 0;
    v14[5] = 0;
    v14[6] = 0;
    *v14 = 0;
  }
  else
  {
    v15 = 0;
  }
  v378 = v15;
  LODWORD(v400) = 1;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v15;
  if ( a2 == 16 )
  {
    *v378 = (__int64)L"M2 [VX-v1]";
    v19 = CWcnMessage::Init((__int64)v378, 6, (__int64)qword_180066220, 23);
    v9 = v19;
    goto LABEL_37;
  }
  if ( a2 == 32 )
  {
    v16 = L"M2 [VX-v2]";
    v17 = qword_180065B40;
    goto LABEL_34;
  }
  if ( a2 != 272 )
  {
    v16 = L"M2 [VX-v2-WFD]";
    v17 = qword_180065530;
LABEL_34:
    v18 = 24;
    goto LABEL_35;
  }
  v16 = L"M2 [VX-v1-WFD]";
  v18 = 23;
  v17 = qword_180064FB0;
LABEL_35:
  *v378 = (__int64)v16;
  v19 = CWcnMessage::Init((__int64)v378, 6, (__int64)v17, v18);
  v9 = v19;
LABEL_37:
  if ( v19 < 0 )
    goto LABEL_959;
  if ( !v19 )
    *((_DWORD *)v378 + 5) = 5;
  v20 = (__int64 *)operator new(0x38u);
  v21 = v20;
  v400 = v20;
  if ( v20 )
  {
    *((_DWORD *)v20 + 4) = 8;
    v20[3] = 0;
    *((_BYTE *)v20 + 36) = 0;
    v20[5] = 0;
    v20[6] = 0;
    *v20 = 0;
  }
  else
  {
    v21 = 0;
  }
  v395 = v21;
  LODWORD(v400) = 2;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v21;
  if ( a2 == 32 )
  {
    *v395 = (__int64)L"M2_NFC_CH [VX-v2]";
    v9 = CWcnMessage::Init((__int64)v395, 6, (__int64)qword_180065C40, 25);
    if ( v9 < 0 )
      goto LABEL_959;
  }
  *((_DWORD *)v395 + 5) = 5;
  v22 = (__int64 *)operator new(0x38u);
  v23 = v22;
  v400 = v22;
  if ( v22 )
  {
    *((_DWORD *)v22 + 4) = 8;
    v22[3] = 0;
    *((_BYTE *)v22 + 36) = 0;
    v22[5] = 0;
    v22[6] = 0;
    *v22 = 0;
  }
  else
  {
    v23 = 0;
  }
  v379 = v23;
  LODWORD(v400) = 3;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v23;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v24 = L"M2D [VX-v2]";
      v25 = qword_180065DB0;
    }
    else
    {
      if ( a2 == 272 )
      {
        v24 = L"M2D [VX-v1-WFD]";
        v26 = 20;
        v25 = qword_180065130;
LABEL_55:
        *v379 = (__int64)v24;
        v27 = CWcnMessage::Init((__int64)v379, 6, (__int64)v25, v26);
        v9 = v27;
        goto LABEL_57;
      }
      v24 = L"M2D [VX-v2-WFD]";
      v25 = qword_1800656D0;
    }
    v26 = 21;
    goto LABEL_55;
  }
  *v379 = (__int64)L"M2D [VX-v1]";
  v27 = CWcnMessage::Init((__int64)v379, 6, (__int64)qword_1800663A0, 20);
  v9 = v27;
LABEL_57:
  if ( v27 < 0 )
    goto LABEL_959;
  if ( !v27 )
    *((_DWORD *)v379 + 5) = 6;
  v28 = (__int64 *)operator new(0x38u);
  v29 = v28;
  v400 = v28;
  if ( v28 )
  {
    *((_DWORD *)v28 + 4) = 8;
    v28[3] = 0;
    *((_BYTE *)v28 + 36) = 0;
    v28[5] = 0;
    v28[6] = 0;
    *v28 = 0;
  }
  else
  {
    v29 = 0;
  }
  v385 = v29;
  LODWORD(v400) = 4;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v29;
  if ( a2 == 16 )
  {
    *v385 = (__int64)L"M3 [VX-v1]";
    v32 = CWcnMessage::Init((__int64)v385, 6, (__int64)qword_180066550, 7);
    v9 = v32;
  }
  else
  {
    if ( a2 == 32 )
    {
      v30 = L"M3 [VX-v2]";
      v31 = qword_180065F90;
    }
    else
    {
      if ( a2 == 272 )
      {
        *v385 = (__int64)L"M3 [VX-v1-WFD]";
        v32 = CWcnMessage::Init((__int64)v385, 6, (__int64)qword_1800652E0, 7);
        v9 = v32;
        goto LABEL_71;
      }
      v30 = L"M3 [VX-v2-WFD]";
      v31 = qword_1800658B0;
    }
    *v385 = (__int64)v30;
    v32 = CWcnMessage::Init((__int64)v385, 6, (__int64)v31, 8);
    v9 = v32;
  }
LABEL_71:
  if ( v32 < 0 )
    goto LABEL_959;
  if ( !v32 )
    *((_DWORD *)v385 + 5) = 7;
  v33 = (__int64 *)operator new(0x38u);
  v34 = v33;
  v400 = v33;
  if ( v33 )
  {
    *((_DWORD *)v33 + 4) = 8;
    v33[3] = 0;
    *((_BYTE *)v33 + 36) = 0;
    v33[5] = 0;
    v33[6] = 0;
    *v33 = 0;
  }
  else
  {
    v34 = 0;
  }
  v373 = v34;
  LODWORD(v400) = 5;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v34;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v35 = L"M4 [VX-v2]";
      v36 = qword_180066130;
    }
    else
    {
      if ( a2 == 272 )
      {
        v35 = L"M4 [VX-v1-WFD]";
        v37 = 8;
        v36 = qword_180065440;
LABEL_84:
        *v373 = (__int64)v35;
        v38 = CWcnMessage::Init((__int64)v373, 6, (__int64)v36, v37);
        v9 = v38;
        goto LABEL_86;
      }
      v35 = L"M4 [VX-v2-WFD]";
      v36 = qword_180065A40;
    }
    v37 = 9;
    goto LABEL_84;
  }
  *v373 = (__int64)L"M4 [VX-v1]";
  v38 = CWcnMessage::Init((__int64)v373, 6, (__int64)qword_1800666B0, 8);
  v9 = v38;
LABEL_86:
  if ( v38 < 0 )
    goto LABEL_959;
  if ( !v38 )
    *((_DWORD *)v373 + 5) = 8;
  v39 = (__int64 *)operator new(0x38u);
  v40 = v39;
  v400 = v39;
  if ( v39 )
  {
    *((_DWORD *)v39 + 4) = 8;
    v39[3] = 0;
    *((_BYTE *)v39 + 36) = 0;
    v39[5] = 0;
    v39[6] = 0;
    *v39 = 0;
  }
  else
  {
    v40 = 0;
  }
  v374 = v40;
  LODWORD(v400) = 6;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v40;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v41 = L"M5 [VX-v2]";
      v42 = qword_180065C00;
    }
    else
    {
      if ( a2 == 272 )
      {
        *v374 = (__int64)L"M5 [VX-v1-WFD]";
        v43 = 6;
        v42 = qword_180065068;
LABEL_99:
        v44 = CWcnMessage::Init((__int64)v374, 6, (__int64)v42, v43);
        v9 = v44;
        goto LABEL_101;
      }
      v41 = L"M5 [VX-v2-WFD]";
      v42 = qword_1800655F0;
    }
    v43 = 7;
    *v374 = (__int64)v41;
    goto LABEL_99;
  }
  *v374 = (__int64)L"M5 [VX-v1]";
  v44 = CWcnMessage::Init((__int64)v374, 6, (__int64)qword_1800662D8, 6);
  v9 = v44;
LABEL_101:
  if ( v44 < 0 )
    goto LABEL_959;
  if ( !v44 )
    *((_DWORD *)v374 + 5) = 9;
  v45 = (__int64 *)operator new(0x38u);
  v46 = v45;
  v400 = v45;
  if ( v45 )
  {
    *((_DWORD *)v45 + 4) = 8;
    v45[3] = 0;
    *((_BYTE *)v45 + 36) = 0;
    v45[5] = 0;
    v45[6] = 0;
    *v45 = 0;
  }
  else
  {
    v46 = 0;
  }
  v375 = v46;
  LODWORD(v400) = 7;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v46;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v47 = L"M6 [VX-v2]";
      v48 = qword_180065D08;
    }
    else
    {
      if ( a2 == 272 )
      {
        *v375 = (__int64)L"M6 [VX-v1-WFD]";
        v49 = 6;
        v48 = qword_180065098;
LABEL_114:
        v50 = CWcnMessage::Init((__int64)v375, 6, (__int64)v48, v49);
        v9 = v50;
        goto LABEL_116;
      }
      v47 = L"M6 [VX-v2-WFD]";
      v48 = qword_180065628;
    }
    v49 = 7;
    *v375 = (__int64)v47;
    goto LABEL_114;
  }
  *v375 = (__int64)L"M6 [VX-v1]";
  v50 = CWcnMessage::Init((__int64)v375, 6, (__int64)qword_180066308, 6);
  v9 = v50;
LABEL_116:
  if ( v50 < 0 )
    goto LABEL_959;
  if ( !v50 )
    *((_DWORD *)v375 + 5) = 10;
  v51 = (__int64 *)operator new(0x38u);
  v52 = v51;
  v400 = v51;
  if ( v51 )
  {
    *((_DWORD *)v51 + 4) = 8;
    v51[3] = 0;
    *((_BYTE *)v51 + 36) = 0;
    v51[5] = 0;
    v51[6] = 0;
    *v51 = 0;
  }
  else
  {
    v52 = 0;
  }
  v370 = v52;
  LODWORD(v400) = 8;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v52;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v53 = L"M7 [VX-v2]";
      v54 = qword_180065AE8;
    }
    else
    {
      if ( a2 == 272 )
      {
        *v370 = (__int64)L"M7 [VX-v1-WFD]";
        v55 = 6;
        v54 = qword_180064F60;
LABEL_129:
        v56 = CWcnMessage::Init((__int64)v370, 6, (__int64)v54, v55);
        v9 = v56;
        goto LABEL_131;
      }
      v53 = L"M7 [VX-v2-WFD]";
      v54 = qword_1800654D8;
    }
    v55 = 7;
    *v370 = (__int64)v53;
    goto LABEL_129;
  }
  *v370 = (__int64)L"M7 [VX-v1]";
  v56 = CWcnMessage::Init((__int64)v370, 6, (__int64)qword_1800661D8, 6);
  v9 = v56;
LABEL_131:
  if ( v56 < 0 )
    goto LABEL_959;
  if ( !v56 )
    *((_DWORD *)v370 + 5) = 11;
  v57 = (__int64 *)operator new(0x38u);
  v58 = v57;
  v400 = v57;
  if ( v57 )
  {
    *((_DWORD *)v57 + 4) = 8;
    v57[3] = 0;
    *((_BYTE *)v57 + 36) = 0;
    v57[5] = 0;
    v57[6] = 0;
    *v57 = 0;
  }
  else
  {
    v58 = 0;
  }
  v371 = v58;
  LODWORD(v400) = 9;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v58;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v59 = L"M8 [VX-v2]";
      v60 = qword_180065E58;
    }
    else
    {
      if ( a2 == 272 )
      {
        *v371 = (__int64)L"M8 [VX-v1-WFD]";
        v61 = 6;
        v60 = qword_1800651D0;
LABEL_144:
        v62 = CWcnMessage::Init((__int64)v371, 6, (__int64)v60, v61);
        v9 = v62;
        goto LABEL_146;
      }
      v59 = L"M8 [VX-v2-WFD]";
      v60 = qword_180065778;
    }
    v61 = 7;
    *v371 = (__int64)v59;
    goto LABEL_144;
  }
  *v371 = (__int64)L"M8 [VX-v1]";
  v62 = CWcnMessage::Init((__int64)v371, 6, (__int64)qword_180066440, 6);
  v9 = v62;
LABEL_146:
  if ( v62 < 0 )
    goto LABEL_959;
  if ( !v62 )
    *((_DWORD *)v371 + 5) = 12;
  v63 = (__int64 *)operator new(0x38u);
  v64 = v63;
  v400 = v63;
  if ( v63 )
  {
    *((_DWORD *)v63 + 4) = 8;
    v63[3] = 0;
    *((_BYTE *)v63 + 36) = 0;
    v63[5] = 0;
    v63[6] = 0;
    *v63 = 0;
  }
  else
  {
    v64 = 0;
  }
  v386 = v64;
  LODWORD(v400) = 23;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v64;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v65 = L"ACK [VX-v2]";
      v66 = qword_180066178;
    }
    else
    {
      if ( a2 == 272 )
      {
        v65 = L"ACK [VX-v1-WFD]";
        v67 = 5;
        v66 = qword_180065480;
LABEL_159:
        *v386 = (__int64)v65;
        v68 = CWcnMessage::Init((__int64)v386, 2, (__int64)v66, v67);
        v9 = v68;
        goto LABEL_161;
      }
      v65 = L"ACK [VX-v2-WFD]";
      v66 = qword_180065A88;
    }
    v67 = 6;
    goto LABEL_159;
  }
  *v386 = (__int64)L"ACK [VX-v1]";
  v68 = CWcnMessage::Init((__int64)v386, 2, (__int64)qword_1800666F0, 5);
  v9 = v68;
LABEL_161:
  if ( v68 < 0 )
    goto LABEL_959;
  if ( !v68 )
    *((_DWORD *)v386 + 5) = 13;
  v69 = (__int64 *)operator new(0x38u);
  v70 = v69;
  v400 = v69;
  if ( v69 )
  {
    *((_DWORD *)v69 + 4) = 8;
    v69[3] = 0;
    *((_BYTE *)v69 + 36) = 0;
    v69[5] = 0;
    v69[6] = 0;
    *v69 = 0;
  }
  else
  {
    v70 = 0;
  }
  v387 = v70;
  LODWORD(v400) = 24;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v70;
  if ( a2 != 16 )
  {
    if ( a2 == 32 )
    {
      v71 = L"NACK [VX-v2]";
      v72 = qword_1800660F8;
    }
    else
    {
      if ( a2 == 272 )
      {
        v71 = L"NACK [VX-v1-WFD]";
        v73 = 6;
        v72 = qword_180065408;
LABEL_174:
        *v387 = (__int64)v71;
        v74 = CWcnMessage::Init((__int64)v387, 3, (__int64)v72, v73);
        v9 = v74;
        goto LABEL_176;
      }
      v71 = L"NACK [VX-v2-WFD]";
      v72 = qword_180065A00;
    }
    v73 = 7;
    goto LABEL_174;
  }
  *v387 = (__int64)L"NACK [VX-v1]";
  v74 = CWcnMessage::Init((__int64)v387, 3, (__int64)qword_180066678, 6);
  v9 = v74;
LABEL_176:
  if ( v74 < 0 )
    goto LABEL_959;
  if ( !v74 )
    *((_DWORD *)v387 + 5) = 14;
  v75 = (__int64 *)operator new(0x38u);
  v76 = v75;
  v400 = v75;
  if ( v75 )
  {
    *((_DWORD *)v75 + 4) = 8;
    v75[3] = 0;
    *((_BYTE *)v75 + 36) = 0;
    v75[5] = 0;
    v75[6] = 0;
    *v75 = 0;
  }
  else
  {
    v76 = 0;
  }
  v388 = v76;
  LODWORD(v400) = 25;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v76;
  if ( a2 == 16 )
  {
    *v388 = (__int64)L"DONE [VX-v1]";
    v80 = CWcnMessage::Init((__int64)v388, 1, (__int64)qword_180066470, 5);
    v9 = v80;
    goto LABEL_191;
  }
  if ( a2 == 32 )
  {
    v77 = L"DONE [VX-v2]";
    v78 = qword_180065E90;
    goto LABEL_188;
  }
  if ( a2 != 272 )
  {
    v77 = L"DONE [VX-v2-WFD]";
    v78 = qword_1800657B0;
LABEL_188:
    v79 = 6;
    goto LABEL_189;
  }
  v77 = L"DONE [VX-v1-WFD]";
  v79 = 5;
  v78 = qword_180065200;
LABEL_189:
  *v388 = (__int64)v77;
  v80 = CWcnMessage::Init((__int64)v388, 1, (__int64)v78, v79);
  v9 = v80;
LABEL_191:
  if ( v80 < 0 )
    goto LABEL_959;
  if ( !v80 )
    *((_DWORD *)v388 + 5) = 15;
  v81 = (__int64 *)operator new(0x38u);
  v82 = v81;
  v397 = v81;
  v400 = v81;
  if ( v81 )
  {
    *((_DWORD *)v81 + 4) = 8;
    v81[3] = 0;
    *((_BYTE *)v81 + 36) = 0;
    v81[5] = 0;
    v81[6] = 0;
    *v81 = 0;
  }
  else
  {
    v82 = 0;
    v397 = 0;
  }
  LODWORD(v400) = 10;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v82;
  if ( a2 == 32 )
  {
    *v82 = (__int64)L"ESM2E_NFC_CH [VX-v2]";
    v9 = CWcnMessage::Init((__int64)v82, 7, (__int64)qword_1800660E0, 3);
    if ( v9 < 0 )
      goto LABEL_959;
  }
  v83 = (__int64 *)operator new(0x38u);
  v84 = v83;
  v400 = v83;
  if ( v83 )
  {
    *((_DWORD *)v83 + 4) = 8;
    v83[3] = 0;
    *((_BYTE *)v83 + 36) = 0;
    v83[5] = 0;
    v83[6] = 0;
    *v83 = 0;
  }
  else
  {
    v84 = 0;
  }
  LODWORD(v400) = 11;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v84;
  if ( a2 == 16 )
  {
    *v84 = (__int64)L"ESM4 [VX-v1]";
    v87 = CWcnMessage::Init((__int64)v84, 7, (__int64)qword_180066208, 3);
    v9 = v87;
  }
  else
  {
    if ( a2 == 32 )
    {
      v85 = L"ESM4 [VX-v2]";
      v86 = qword_180065B20;
    }
    else if ( a2 == 272 )
    {
      v85 = L"ESM4 [VX-v1-WFD]";
      v86 = qword_180064F90;
    }
    else
    {
      v85 = L"ESM4 [VX-v2-WFD]";
      v86 = qword_180065510;
    }
    *v84 = (__int64)v85;
    v87 = CWcnMessage::Init((__int64)v84, 7, (__int64)v86, 3);
    v9 = v87;
  }
  if ( v87 < 0 )
    goto LABEL_959;
  v88 = (__int64 *)operator new(0x38u);
  v89 = v88;
  v400 = v88;
  if ( v88 )
  {
    *((_DWORD *)v88 + 4) = 8;
    v88[3] = 0;
    *((_BYTE *)v88 + 36) = 0;
    v88[5] = 0;
    v88[6] = 0;
    *v88 = 0;
  }
  else
  {
    v89 = 0;
  }
  LODWORD(v400) = 12;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v89;
  if ( a2 == 16 )
  {
    *v89 = (__int64)L"ESM5 [VX-v1]";
    v92 = CWcnMessage::Init((__int64)v89, 7, (__int64)qword_180066718, 3);
    v9 = v92;
  }
  else
  {
    if ( a2 == 32 )
    {
      v90 = L"ESM5 [VX-v2]";
      v91 = qword_1800661A8;
    }
    else if ( a2 == 272 )
    {
      v90 = L"ESM5 [VX-v1-WFD]";
      v91 = qword_1800654A8;
    }
    else
    {
      v90 = L"ESM5 [VX-v2-WFD]";
      v91 = qword_180065AB8;
    }
    *v89 = (__int64)v90;
    v92 = CWcnMessage::Init((__int64)v89, 7, (__int64)v91, 3);
    v9 = v92;
  }
  if ( v92 < 0 )
    goto LABEL_959;
  v93 = (__int64 *)operator new(0x38u);
  v94 = v93;
  v400 = v93;
  if ( v93 )
  {
    *((_DWORD *)v93 + 4) = 8;
    v93[3] = 0;
    *((_BYTE *)v93 + 36) = 0;
    v93[5] = 0;
    v93[6] = 0;
    *v93 = 0;
  }
  else
  {
    v94 = 0;
  }
  LODWORD(v400) = 13;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v94;
  if ( a2 == 16 )
  {
    *v94 = (__int64)L"ESM6 [VX-v1]";
    v97 = CWcnMessage::Init((__int64)v94, 7, (__int64)qword_1800661C0, 3);
    v9 = v97;
  }
  else
  {
    if ( a2 == 32 )
    {
      v95 = L"ESM6 [VX-v2]";
      v96 = qword_180065AD0;
    }
    else if ( a2 == 272 )
    {
      v95 = L"ESM6 [VX-v1-WFD]";
      v96 = qword_180064F48;
    }
    else
    {
      v95 = L"ESM6 [VX-v2-WFD]";
      v96 = qword_1800654C0;
    }
    *v94 = (__int64)v95;
    v97 = CWcnMessage::Init((__int64)v94, 7, (__int64)v96, 3);
    v9 = v97;
  }
  if ( v97 < 0 )
    goto LABEL_959;
  v98 = (__int64 *)operator new(0x38u);
  v99 = (__int64)v98;
  v400 = v98;
  if ( v98 )
  {
    *((_DWORD *)v98 + 4) = 8;
    v98[3] = 0;
    *((_BYTE *)v98 + 36) = 0;
    v98[5] = 0;
    v98[6] = 0;
    *v98 = 0;
  }
  else
  {
    v99 = 0;
  }
  LODWORD(v400) = 14;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = (__int64 *)v99;
  if ( a2 == 16 )
  {
    *(_QWORD *)v99 = L"ESM7A [VX-v1]";
    v102 = CWcnMessage::Init(v99, 7, (__int64)qword_1800664A0, 9);
    v9 = v102;
  }
  else
  {
    if ( a2 == 32 )
    {
      v100 = L"ESM7A [VX-v2]";
      v101 = qword_180065ED0;
    }
    else if ( a2 == 272 )
    {
      v100 = L"ESM7A [VX-v1-WFD]";
      v101 = qword_180065230;
    }
    else
    {
      v100 = L"ESM7A [VX-v2-WFD]";
      v101 = qword_1800657F0;
    }
    *(_QWORD *)v99 = v100;
    v102 = CWcnMessage::Init(v99, 7, (__int64)v101, 9);
    v9 = v102;
  }
  if ( v102 < 0 )
    goto LABEL_959;
  v103 = (__int64 *)operator new(0x38u);
  v104 = (__int64)v103;
  v400 = v103;
  if ( v103 )
  {
    *((_DWORD *)v103 + 4) = 8;
    v103[3] = 0;
    *((_BYTE *)v103 + 36) = 0;
    v103[5] = 0;
    v103[6] = 0;
    *v103 = 0;
  }
  else
  {
    v104 = 0;
  }
  LODWORD(v400) = 15;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = (__int64 *)v104;
  if ( a2 == 16 )
  {
    *(_QWORD *)v104 = L"ESM7E [VX-v1]";
    v107 = CWcnMessage::Init(v104, 7, (__int64)qword_180066588, 4);
    v9 = v107;
  }
  else
  {
    if ( a2 == 32 )
    {
      v105 = L"ESM7E [VX-v2]";
      v106 = qword_180065FD0;
    }
    else if ( a2 == 272 )
    {
      v105 = L"ESM7E [VX-v1-WFD]";
      v106 = qword_180065318;
    }
    else
    {
      v105 = L"ESM7E [VX-v2-WFD]";
      v106 = qword_1800658F0;
    }
    *(_QWORD *)v104 = v105;
    v107 = CWcnMessage::Init(v104, 7, (__int64)v106, 4);
    v9 = v107;
  }
  if ( v107 < 0 )
    goto LABEL_959;
  v108 = (__int64 *)operator new(0x38u);
  v109 = (__int64)v108;
  v400 = v108;
  if ( v108 )
  {
    *((_DWORD *)v108 + 4) = 8;
    v108[3] = 0;
    *((_BYTE *)v108 + 36) = 0;
    v108[5] = 0;
    v108[6] = 0;
    *v108 = 0;
  }
  else
  {
    v109 = 0;
  }
  LODWORD(v400) = 16;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = (__int64 *)v109;
  if ( a2 == 16 )
  {
    *(_QWORD *)v109 = L"ESM8A [VX-v1]";
    v112 = CWcnMessage::Init(v109, 7, (__int64)qword_180066340, 11);
    v9 = v112;
  }
  else
  {
    if ( a2 == 32 )
    {
      v110 = L"ESM8A [VX-v2]";
      v111 = qword_180065D40;
    }
    else if ( a2 == 272 )
    {
      v110 = L"ESM8A [VX-v1-WFD]";
      v111 = qword_1800650D0;
    }
    else
    {
      v110 = L"ESM8A [VX-v2-WFD]";
      v111 = qword_180065660;
    }
    *(_QWORD *)v109 = v110;
    v112 = CWcnMessage::Init(v109, 7, (__int64)v111, 11);
    v9 = v112;
  }
  if ( v112 < 0 )
    goto LABEL_959;
  v113 = (__int64 *)operator new(0x38u);
  v114 = (__int64)v113;
  v400 = v113;
  if ( v113 )
  {
    *((_DWORD *)v113 + 4) = 8;
    v113[3] = 0;
    *((_BYTE *)v113 + 36) = 0;
    v113[5] = 0;
    v113[6] = 0;
    *v113 = 0;
  }
  else
  {
    v114 = 0;
  }
  LODWORD(v400) = 17;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = (__int64 *)v114;
  if ( v399 == 16 )
  {
    *(_QWORD *)v114 = L"ESM8E [VX-v1]";
    v117 = CWcnMessage::Init(v114, 7, (__int64)qword_1800665A8, 3);
    v9 = v117;
  }
  else
  {
    switch ( v399 )
    {
      case 32:
        v115 = L"ESM8E [VX-v2]";
        v116 = qword_180065FF0;
        break;
      case 272:
        v115 = L"ESM8E [VX-v1-WFD]";
        v116 = qword_180065338;
        break;
      case 288:
        v115 = L"ESM8E [VX-v2-WFD]";
        v116 = qword_180065910;
        break;
      default:
        v9 = -2147467259;
        goto LABEL_959;
    }
    *(_QWORD *)v114 = v115;
    v117 = CWcnMessage::Init(v114, 7, (__int64)v116, 3);
    v9 = v117;
  }
  if ( v117 < 0 )
    goto LABEL_959;
  v118 = (__int64 *)operator new(0x38u);
  v119 = v118;
  v400 = v118;
  if ( v118 )
  {
    *((_DWORD *)v118 + 4) = 8;
    v118[3] = 0;
    *((_BYTE *)v118 + 36) = 0;
    v118[5] = 0;
    v118[6] = 0;
    *v118 = 0;
  }
  else
  {
    v119 = 0;
  }
  v390 = v119;
  LODWORD(v400) = 18;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](v8, (int *)&v400) = v119;
  v120 = v399;
  if ( v399 != 16 )
  {
    switch ( v399 )
    {
      case 32:
        v121 = L"CREDENTIAL [VX-v2]";
        v122 = qword_180065F20;
        break;
      case 272:
        v121 = L"CREDENTIAL [VX-v1-WFD]";
        v123 = 12;
        v122 = qword_180065280;
LABEL_297:
        *v390 = v121;
        v124 = CWcnMessage::Init((__int64)v390, 7, (__int64)v122, v123);
        v9 = v124;
        goto LABEL_299;
      case 288:
        v121 = L"CREDENTIAL [VX-v2-WFD]";
        v122 = qword_180065840;
        break;
      default:
        v9 = -2147467259;
        goto LABEL_959;
    }
    v123 = 13;
    goto LABEL_297;
  }
  *v390 = L"CREDENTIAL [VX-v1]";
  v124 = CWcnMessage::Init((__int64)v390, 7, (__int64)qword_1800664F0, 12);
  v9 = v124;
LABEL_299:
  if ( v124 < 0 )
    goto LABEL_959;
  if ( v120 < 0x20u )
    goto LABEL_345;
  v125 = (__int64 *)operator new(0x38u);
  v126 = v125;
  v400 = v125;
  if ( v125 )
  {
    *((_DWORD *)v125 + 4) = 8;
    v125[3] = 0;
    *((_BYTE *)v125 + 36) = 0;
    v125[5] = 0;
    v125[6] = 0;
    *v125 = 0;
  }
  else
  {
    v126 = 0;
  }
  LODWORD(v400) = 21;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](
     (__int64 ***)v398 + 3,
     (int *)&v400) = v126;
  if ( v399 != 16 )
  {
    switch ( v399 )
    {
      case 32:
        *v126 = (__int64)L"WFA_VE_MX [VX-v2]";
        v127 = CWcnMessage::Init((__int64)v126, 9, (__int64)qword_180065EC0, 1);
        v9 = v127;
        break;
      case 272:
        goto LABEL_312;
      case 288:
        *v126 = (__int64)L"WFA_VE_MX [VX-v2-WFD]";
        v127 = CWcnMessage::Init((__int64)v126, 9, (__int64)qword_1800657E0, 1);
        v9 = v127;
        break;
      default:
        v9 = -2147467259;
        goto LABEL_959;
    }
    if ( v127 < 0 )
      goto LABEL_959;
  }
LABEL_312:
  v128 = (__int64 *)operator new(0x38u);
  v129 = v128;
  v400 = v128;
  if ( v128 )
  {
    *((_DWORD *)v128 + 4) = 8;
    v128[3] = 0;
    *((_BYTE *)v128 + 36) = 0;
    v128[5] = 0;
    v128[6] = 0;
    *v128 = 0;
  }
  else
  {
    v129 = 0;
  }
  LODWORD(v400) = 19;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](
     (__int64 ***)v398 + 3,
     (int *)&v400) = v129;
  if ( v399 != 16 )
  {
    switch ( v399 )
    {
      case 32:
        *v129 = (__int64)L"WFA_VE_M1 [VX-v2]";
        v130 = CWcnMessage::Init((__int64)v129, 9, (__int64)qword_180066008, 2);
        v9 = v130;
        break;
      case 272:
        goto LABEL_323;
      case 288:
        *v129 = (__int64)L"WFA_VE_M1 [VX-v2-WFD]";
        v130 = CWcnMessage::Init((__int64)v129, 9, (__int64)qword_180065928, 2);
        v9 = v130;
        break;
      default:
        v9 = -2147467259;
        goto LABEL_959;
    }
    if ( v130 < 0 )
      goto LABEL_959;
  }
LABEL_323:
  v131 = (__int64 *)operator new(0x38u);
  v132 = v131;
  v400 = v131;
  if ( v131 )
  {
    *((_DWORD *)v131 + 4) = 8;
    v131[3] = 0;
    *((_BYTE *)v131 + 36) = 0;
    v131[5] = 0;
    v131[6] = 0;
    *v131 = 0;
  }
  else
  {
    v132 = 0;
  }
  LODWORD(v400) = 20;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](
     (__int64 ***)v398 + 3,
     (int *)&v400) = v132;
  if ( v399 != 16 )
  {
    switch ( v399 )
    {
      case 32:
        *v132 = (__int64)L"WFA_VE_M7 [VX-v2]";
        v133 = CWcnMessage::Init((__int64)v132, 9, (__int64)qword_180065D98, 2);
        v9 = v133;
        break;
      case 272:
        goto LABEL_334;
      case 288:
        *v132 = (__int64)L"WFA_VE_M7 [VX-v2-WFD]";
        v133 = CWcnMessage::Init((__int64)v132, 9, (__int64)qword_1800656B8, 2);
        v9 = v133;
        break;
      default:
        v9 = -2147467259;
        goto LABEL_959;
    }
    if ( v133 < 0 )
      goto LABEL_959;
  }
LABEL_334:
  v134 = (__int64 *)operator new(0x38u);
  v135 = v134;
  v400 = v134;
  if ( v134 )
  {
    *((_DWORD *)v134 + 4) = 8;
    v134[3] = 0;
    *((_BYTE *)v134 + 36) = 0;
    v134[5] = 0;
    v134[6] = 0;
    *v134 = 0;
  }
  else
  {
    v135 = 0;
  }
  LODWORD(v400) = 22;
  *std::map<enum CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](
     (__int64 ***)v398 + 3,
     (int *)&v400) = v135;
  if ( v399 != 16 )
  {
    switch ( v399 )
    {
      case 32:
        *v135 = (__int64)L"WFA_VE_CREDENTIAL [VX-v2]";
        v136 = CWcnMessage::Init((__int64)v135, 9, (__int64)&qword_180065DA8, 1);
        v9 = v136;
        break;
      case 272:
        goto LABEL_345;
      case 288:
        *v135 = (__int64)L"WFA_VE_CREDENTIAL [VX-v2-WFD]";
        v136 = CWcnMessage::Init((__int64)v135, 9, (__int64)&qword_1800656C8, 1);
        v9 = v136;
        break;
      default:
        v9 = -2147467259;
        goto LABEL_959;
    }
    if ( v136 < 0 )
      goto LABEL_959;
  }
LABEL_345:
  v137 = (__int64)v377;
  *((_BYTE *)v377 + 36) = 1;
  *(_DWORD *)(v137 + 32) = 0;
  v138 = (__int64)v378;
  *((_BYTE *)v378 + 36) = 1;
  *(_DWORD *)(v138 + 32) = 0;
  v139 = (__int64)v395;
  *((_BYTE *)v395 + 36) = 1;
  *(_DWORD *)(v139 + 32) = 0;
  v140 = (__int64)v379;
  *((_BYTE *)v379 + 36) = 1;
  *(_DWORD *)(v140 + 32) = 0;
  v141 = (__int64)v370;
  *((_BYTE *)v370 + 36) = 1;
  *(_DWORD *)(v141 + 32) = 1;
  v142 = (__int64)v371;
  *((_BYTE *)v371 + 36) = 1;
  *(_DWORD *)(v142 + 32) = 1;
  v143 = v397;
  *((_BYTE *)v397 + 36) = 1;
  *((_DWORD *)v143 + 8) = 2;
  *(_BYTE *)(v99 + 36) = 1;
  *(_DWORD *)(v99 + 32) = 2;
  *(_BYTE *)(v104 + 36) = 1;
  *(_DWORD *)(v104 + 32) = 2;
  *(_BYTE *)(v109 + 36) = 1;
  *(_DWORD *)(v109 + 32) = 2;
  *(_BYTE *)(v114 + 36) = 1;
  *(_DWORD *)(v114 + 32) = 2;
  v144 = v398;
  v145 = (__int64 ***)((char *)v398 + 104);
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               (__int64 ***)v398 + 13,
               (__int64 *)&v395) = 10;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               v145,
               (__int64 *)&v373) = 11;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               (__int64 ***)v144 + 15,
               (__int64 *)&v373) = 11;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               v145,
               (__int64 *)&v374) = 12;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               (__int64 ***)v144 + 15,
               (__int64 *)&v374) = 12;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               v145,
               (__int64 *)&v375) = 13;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               (__int64 ***)v144 + 15,
               (__int64 *)&v375) = 13;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               v145,
               (__int64 *)&v370) = 15;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               (__int64 ***)v144 + 15,
               (__int64 *)&v370) = 14;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               v145,
               (__int64 *)&v371) = 17;
  *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
               (__int64 ***)v144 + 15,
               (__int64 *)&v371) = 16;
  if ( v120 >= 0x20u )
  {
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v377) = 19;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v370) = 20;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v390) = 22;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v378) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v395) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v379) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v385) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v373) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v374) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v375) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v371) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v386) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v387) = 21;
    *(_DWORD *)std::map<CWcnMessage const *,enum CWcnProtocolVX::tagWcnProtocolVXMessageType>::operator[](
                 (__int64 ***)v144 + 17,
                 (__int64 *)&v388) = 21;
  }
  v389 = 0;
  v146 = v399;
  switch ( v399 )
  {
    case 16:
      v147 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v147;
      if ( v147 )
      {
        v149 = L"Initial [VX-v1]";
        goto LABEL_363;
      }
LABEL_364:
      v147 = 0;
      goto LABEL_365;
    case 32:
      v147 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v147;
      if ( v147 )
      {
        v149 = L"Initial [VX-v2]";
LABEL_363:
        v147[4] = 0;
        v147[3] = 0;
        v147[2] = 0;
        *v147 = v149;
        goto LABEL_365;
      }
      goto LABEL_364;
    case 272:
      v147 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v147;
      if ( v147 )
      {
        v148 = L"Initial [VX-v1-WFD]";
        goto LABEL_353;
      }
      break;
    case 288:
      v147 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v147;
      if ( v147 )
      {
        v148 = L"Initial [VX-v2-WFD]";
        goto LABEL_353;
      }
      break;
    default:
      v147 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v147;
      if ( v147 )
      {
        v148 = L"Initial [VX-v?]";
LABEL_353:
        v147[4] = 0;
        v147[3] = 0;
        v147[2] = 0;
        *v147 = v148;
        goto LABEL_365;
      }
      break;
  }
  v147 = 0;
LABEL_365:
  v389 = (struct CSmState *)v147;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v389);
  v365 = 0;
  switch ( v146 )
  {
    case 16:
      v150 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v150;
      if ( v150 )
      {
        v151 = L"DidM1 [VX-v1]";
        goto LABEL_379;
      }
      break;
    case 32:
      v150 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v150;
      if ( v150 )
      {
        v151 = L"DidM1 [VX-v2]";
        goto LABEL_379;
      }
      break;
    case 272:
      v150 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v150;
      if ( v150 )
      {
        v151 = L"DidM1 [VX-v1-WFD]";
        goto LABEL_379;
      }
      break;
    case 288:
      v150 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v150;
      if ( v150 )
      {
        v151 = L"DidM1 [VX-v2-WFD]";
        goto LABEL_379;
      }
      break;
    default:
      v150 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v150;
      if ( v150 )
      {
        v151 = L"DidM1 [VX-v?]";
LABEL_379:
        v150[4] = 0;
        v150[3] = 0;
        v150[2] = 0;
        *v150 = v151;
        goto LABEL_381;
      }
      break;
  }
  v150 = 0;
LABEL_381:
  v365 = (struct CSmState *)v150;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v365);
  v391 = 0;
  switch ( v146 )
  {
    case 16:
      v152 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v152;
      if ( v152 )
      {
        v153 = L"DidM2Nack [VX-v1]";
        goto LABEL_395;
      }
      break;
    case 32:
      v152 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v152;
      if ( v152 )
      {
        v153 = L"DidM2Nack [VX-v2]";
        goto LABEL_395;
      }
      break;
    case 272:
      v152 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v152;
      if ( v152 )
      {
        v153 = L"DidM2Nack [VX-v1-WFD]";
        goto LABEL_395;
      }
      break;
    case 288:
      v152 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v152;
      if ( v152 )
      {
        v153 = L"DidM2Nack [VX-v2-WFD]";
        goto LABEL_395;
      }
      break;
    default:
      v152 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v152;
      if ( v152 )
      {
        v153 = L"DidM2Nack [VX-v?]";
LABEL_395:
        v152[4] = 0;
        v152[3] = 0;
        v152[2] = 0;
        *v152 = v153;
        goto LABEL_397;
      }
      break;
  }
  v152 = 0;
LABEL_397:
  v391 = (struct CSmState *)v152;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v391);
  v366 = 0;
  switch ( v146 )
  {
    case 16:
      v154 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v154;
      if ( v154 )
      {
        v155 = L"DidM2 [VX-v1]";
        goto LABEL_411;
      }
      break;
    case 32:
      v154 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v154;
      if ( v154 )
      {
        v155 = L"DidM2 [VX-v2]";
        goto LABEL_411;
      }
      break;
    case 272:
      v154 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v154;
      if ( v154 )
      {
        v155 = L"DidM2 [VX-v1-WFD]";
        goto LABEL_411;
      }
      break;
    case 288:
      v154 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v154;
      if ( v154 )
      {
        v155 = L"DidM2 [VX-v2-WFD]";
        goto LABEL_411;
      }
      break;
    default:
      v154 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v154;
      if ( v154 )
      {
        v155 = L"DidM2 [VX-v?]";
LABEL_411:
        v154[4] = 0;
        v154[3] = 0;
        v154[2] = 0;
        *v154 = v155;
        goto LABEL_413;
      }
      break;
  }
  v154 = 0;
LABEL_413:
  v366 = (struct CSmState *)v154;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v366);
  v380 = 0;
  switch ( v146 )
  {
    case 16:
      v156 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v156;
      if ( v156 )
      {
        v157 = L"DidM3 [VX-v1]";
        goto LABEL_427;
      }
      break;
    case 32:
      v156 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v156;
      if ( v156 )
      {
        v157 = L"DidM3 [VX-v2]";
        goto LABEL_427;
      }
      break;
    case 272:
      v156 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v156;
      if ( v156 )
      {
        v157 = L"DidM3 [VX-v1-WFD]";
        goto LABEL_427;
      }
      break;
    case 288:
      v156 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v156;
      if ( v156 )
      {
        v157 = L"DidM3 [VX-v2-WFD]";
        goto LABEL_427;
      }
      break;
    default:
      v156 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v156;
      if ( v156 )
      {
        v157 = L"DidM3 [VX-v?]";
LABEL_427:
        v156[4] = 0;
        v156[3] = 0;
        v156[2] = 0;
        *v156 = v157;
        goto LABEL_429;
      }
      break;
  }
  v156 = 0;
LABEL_429:
  v380 = (struct CSmState *)v156;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v380);
  v381 = 0;
  switch ( v146 )
  {
    case 16:
      v158 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v158;
      if ( v158 )
      {
        v159 = L"DidM4 [VX-v1]";
        goto LABEL_443;
      }
      break;
    case 32:
      v158 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v158;
      if ( v158 )
      {
        v159 = L"DidM4 [VX-v2]";
        goto LABEL_443;
      }
      break;
    case 272:
      v158 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v158;
      if ( v158 )
      {
        v159 = L"DidM4 [VX-v1-WFD]";
        goto LABEL_443;
      }
      break;
    case 288:
      v158 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v158;
      if ( v158 )
      {
        v159 = L"DidM4 [VX-v2-WFD]";
        goto LABEL_443;
      }
      break;
    default:
      v158 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v158;
      if ( v158 )
      {
        v159 = L"DidM4 [VX-v?]";
LABEL_443:
        v158[4] = 0;
        v158[3] = 0;
        v158[2] = 0;
        *v158 = v159;
        goto LABEL_445;
      }
      break;
  }
  v158 = 0;
LABEL_445:
  v381 = (struct CSmState *)v158;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v381);
  v382 = 0;
  switch ( v146 )
  {
    case 16:
      v160 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v160;
      if ( v160 )
      {
        v161 = L"DidM5 [VX-v1]";
        goto LABEL_459;
      }
      break;
    case 32:
      v160 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v160;
      if ( v160 )
      {
        v161 = L"DidM5 [VX-v2]";
        goto LABEL_459;
      }
      break;
    case 272:
      v160 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v160;
      if ( v160 )
      {
        v161 = L"DidM5 [VX-v1-WFD]";
        goto LABEL_459;
      }
      break;
    case 288:
      v160 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v160;
      if ( v160 )
      {
        v161 = L"DidM5 [VX-v2-WFD]";
        goto LABEL_459;
      }
      break;
    default:
      v160 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v160;
      if ( v160 )
      {
        v161 = L"DidM5 [VX-v?]";
LABEL_459:
        v160[4] = 0;
        v160[3] = 0;
        v160[2] = 0;
        *v160 = v161;
        goto LABEL_461;
      }
      break;
  }
  v160 = 0;
LABEL_461:
  v382 = (struct CSmState *)v160;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v382);
  v383 = 0;
  switch ( v146 )
  {
    case 16:
      v162 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v162;
      if ( v162 )
      {
        v163 = L"DidM6 [VX-v1]";
        goto LABEL_475;
      }
      break;
    case 32:
      v162 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v162;
      if ( v162 )
      {
        v163 = L"DidM6 [VX-v2]";
        goto LABEL_475;
      }
      break;
    case 272:
      v162 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v162;
      if ( v162 )
      {
        v163 = L"DidM6 [VX-v1-WFD]";
        goto LABEL_475;
      }
      break;
    case 288:
      v162 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v162;
      if ( v162 )
      {
        v163 = L"DidM6 [VX-v2-WFD]";
        goto LABEL_475;
      }
      break;
    default:
      v162 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v162;
      if ( v162 )
      {
        v163 = L"DidM6 [VX-v?]";
LABEL_475:
        v162[4] = 0;
        v162[3] = 0;
        v162[2] = 0;
        *v162 = v163;
        goto LABEL_477;
      }
      break;
  }
  v162 = 0;
LABEL_477:
  v383 = (struct CSmState *)v162;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v383);
  v369 = 0;
  switch ( v146 )
  {
    case 16:
      v164 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v164;
      if ( v164 )
      {
        v165 = L"DidM7 [VX-v1]";
        goto LABEL_491;
      }
      break;
    case 32:
      v164 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v164;
      if ( v164 )
      {
        v165 = L"DidM7 [VX-v2]";
        goto LABEL_491;
      }
      break;
    case 272:
      v164 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v164;
      if ( v164 )
      {
        v165 = L"DidM7 [VX-v1-WFD]";
        goto LABEL_491;
      }
      break;
    case 288:
      v164 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v164;
      if ( v164 )
      {
        v165 = L"DidM7 [VX-v2-WFD]";
        goto LABEL_491;
      }
      break;
    default:
      v164 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v164;
      if ( v164 )
      {
        v165 = L"DidM7 [VX-v?]";
LABEL_491:
        v164[4] = 0;
        v164[3] = 0;
        v164[2] = 0;
        *v164 = v165;
        goto LABEL_493;
      }
      break;
  }
  v164 = 0;
LABEL_493:
  v369 = (struct CSmState *)v164;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v369);
  v372 = 0;
  switch ( v146 )
  {
    case 16:
      v166 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v166;
      if ( v166 )
      {
        v167 = L"DidM8 [VX-v1]";
        goto LABEL_507;
      }
      break;
    case 32:
      v166 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v166;
      if ( v166 )
      {
        v167 = L"DidM8 [VX-v2]";
        goto LABEL_507;
      }
      break;
    case 272:
      v166 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v166;
      if ( v166 )
      {
        v167 = L"DidM8 [VX-v1-WFD]";
        goto LABEL_507;
      }
      break;
    case 288:
      v166 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v166;
      if ( v166 )
      {
        v167 = L"DidM8 [VX-v2-WFD]";
        goto LABEL_507;
      }
      break;
    default:
      v166 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v166;
      if ( v166 )
      {
        v167 = L"DidM8 [VX-v?]";
LABEL_507:
        v166[4] = 0;
        v166[3] = 0;
        v166[2] = 0;
        *v166 = v167;
        goto LABEL_509;
      }
      break;
  }
  v166 = 0;
LABEL_509:
  v372 = (struct CSmState *)v166;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v372);
  v368 = 0;
  switch ( v146 )
  {
    case 16:
      v168 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v168;
      if ( v168 )
      {
        v169 = L"DidDone [VX-v1]";
        goto LABEL_523;
      }
      break;
    case 32:
      v168 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v168;
      if ( v168 )
      {
        v169 = L"DidDone [VX-v2]";
        goto LABEL_523;
      }
      break;
    case 272:
      v168 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v168;
      if ( v168 )
      {
        v169 = L"DidDone [VX-v1-WFD]";
        goto LABEL_523;
      }
      break;
    case 288:
      v168 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v168;
      if ( v168 )
      {
        v169 = L"DidDone [VX-v2-WFD]";
        goto LABEL_523;
      }
      break;
    default:
      v168 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v168;
      if ( v168 )
      {
        v169 = L"DidDone [VX-v?]";
LABEL_523:
        v168[4] = 0;
        v168[3] = 0;
        v168[2] = 0;
        *v168 = v169;
        goto LABEL_525;
      }
      break;
  }
  v168 = 0;
LABEL_525:
  v368 = (struct CSmState *)v168;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v368);
  v394 = 0;
  switch ( v146 )
  {
    case 16:
      v170 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v170;
      if ( v170 )
      {
        v171 = L"DidFullAck [VX-v1]";
        goto LABEL_539;
      }
      break;
    case 32:
      v170 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v170;
      if ( v170 )
      {
        v171 = L"DidFullAck [VX-v2]";
        goto LABEL_539;
      }
      break;
    case 272:
      v170 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v170;
      if ( v170 )
      {
        v171 = L"DidFullAck [VX-v1-WFD]";
        goto LABEL_539;
      }
      break;
    case 288:
      v170 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v170;
      if ( v170 )
      {
        v171 = L"DidFullAck [VX-v2-WFD]";
        goto LABEL_539;
      }
      break;
    default:
      v170 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v170;
      if ( v170 )
      {
        v171 = L"DidFullAck [VX-v?]";
LABEL_539:
        v170[4] = 0;
        v170[3] = 0;
        v170[2] = 0;
        *v170 = v171;
        goto LABEL_541;
      }
      break;
  }
  v170 = 0;
LABEL_541:
  v394 = (CSmState *)v170;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v394);
  v393 = 0;
  switch ( v146 )
  {
    case 16:
      v172 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v172;
      if ( v172 )
      {
        v173 = L"DidM7Nack [VX-v1]";
        goto LABEL_555;
      }
      break;
    case 32:
      v172 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v172;
      if ( v172 )
      {
        v173 = L"DidM7Nack [VX-v2]";
        goto LABEL_555;
      }
      break;
    case 272:
      v172 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v172;
      if ( v172 )
      {
        v173 = L"DidM7Nack [VX-v1-WFD]";
        goto LABEL_555;
      }
      break;
    case 288:
      v172 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v172;
      if ( v172 )
      {
        v173 = L"DidM7Nack [VX-v2-WFD]";
        goto LABEL_555;
      }
      break;
    default:
      v172 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v172;
      if ( v172 )
      {
        v173 = L"DidM7Nack [VX-v?]";
LABEL_555:
        v172[4] = 0;
        v172[3] = 0;
        v172[2] = 0;
        *v172 = v173;
        goto LABEL_557;
      }
      break;
  }
  v172 = 0;
LABEL_557:
  v393 = (CSmState *)v172;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v393);
  v364 = 0;
  switch ( v146 )
  {
    case 16:
      v174 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v174;
      if ( v174 )
      {
        v175 = L"DidM2d [VX-v1]";
        goto LABEL_571;
      }
      break;
    case 32:
      v174 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v174;
      if ( v174 )
      {
        v175 = L"DidM2d [VX-v2]";
        goto LABEL_571;
      }
      break;
    case 272:
      v174 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v174;
      if ( v174 )
      {
        v175 = L"DidM2d [VX-v1-WFD]";
        goto LABEL_571;
      }
      break;
    case 288:
      v174 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v174;
      if ( v174 )
      {
        v175 = L"DidM2d [VX-v2-WFD]";
        goto LABEL_571;
      }
      break;
    default:
      v174 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v174;
      if ( v174 )
      {
        v175 = L"DidM2d [VX-v?]";
LABEL_571:
        v174[4] = 0;
        v174[3] = 0;
        v174[2] = 0;
        *v174 = v175;
        goto LABEL_573;
      }
      break;
  }
  v174 = 0;
LABEL_573:
  v364 = (struct CSmState *)v174;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v364);
  v367 = 0;
  switch ( v146 )
  {
    case 16:
      v176 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v176;
      if ( v176 )
      {
        v177 = L"DidDiscoAck [VX-v1]";
        goto LABEL_587;
      }
      break;
    case 32:
      v176 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v176;
      if ( v176 )
      {
        v177 = L"DidDiscoAck [VX-v2]";
        goto LABEL_587;
      }
      break;
    case 272:
      v176 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v176;
      if ( v176 )
      {
        v177 = L"DidDiscoAck [VX-v1-WFD]";
        goto LABEL_587;
      }
      break;
    case 288:
      v176 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v176;
      if ( v176 )
      {
        v177 = L"DidDiscoAck [VX-v2-WFD]";
        goto LABEL_587;
      }
      break;
    default:
      v176 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v176;
      if ( v176 )
      {
        v177 = L"DidDiscoAck [VX-v?]";
LABEL_587:
        v176[4] = 0;
        v176[3] = 0;
        v176[2] = 0;
        *v176 = v177;
        goto LABEL_589;
      }
      break;
  }
  v176 = 0;
LABEL_589:
  v367 = (CSmState *)v176;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v367);
  v396 = 0;
  switch ( v146 )
  {
    case 16:
      v178 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v178;
      if ( v178 )
      {
        v179 = L"DidExtraM2d [VX-v1]";
        goto LABEL_603;
      }
      break;
    case 32:
      v178 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v178;
      if ( v178 )
      {
        v179 = L"DidExtraM2d [VX-v2]";
        goto LABEL_603;
      }
      break;
    case 272:
      v178 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v178;
      if ( v178 )
      {
        v179 = L"DidExtraM2d [VX-v1-WFD]";
        goto LABEL_603;
      }
      break;
    case 288:
      v178 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v178;
      if ( v178 )
      {
        v179 = L"DidExtraM2d [VX-v2-WFD]";
        goto LABEL_603;
      }
      break;
    default:
      v178 = (const wchar_t **)operator new(0x28u);
      v400 = (__int64 *)v178;
      if ( v178 )
      {
        v179 = L"DidExtraM2d [VX-v?]";
LABEL_603:
        v178[4] = 0;
        v178[3] = 0;
        v178[2] = 0;
        *v178 = v179;
        goto LABEL_605;
      }
      break;
  }
  v178 = 0;
LABEL_605:
  v396 = v178;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v396);
  v376 = 0;
  if ( v146 == 16 )
  {
    v185 = (CSmState *)operator new(0x28u);
    v186 = v185;
    v400 = (__int64 *)v185;
    if ( v185 )
    {
      std::_Vector_val<std::_Simple_types<CSmTransition *>>::_Vector_val<std::_Simple_types<CSmTransition *>>((char *)v185 + 16);
      CSmState::SetDebugName(v186, L"DidNack1 [VX-v1]");
    }
    else
    {
      v186 = 0;
    }
    v376 = v186;
    v146 = v399;
  }
  else
  {
    switch ( v146 )
    {
      case 32:
        v184 = (CSmState *)operator new(0x28u);
        v400 = (__int64 *)v184;
        if ( v184 )
          v181 = CSmState::CSmState(v184, L"DidNack1 [VX-v2]");
        else
          v181 = 0;
        break;
      case 272:
        v183 = (CSmState *)operator new(0x28u);
        v400 = (__int64 *)v183;
        if ( v183 )
          v181 = CSmState::CSmState(v183, L"DidNack1 [VX-v1-WFD]");
        else
          v181 = 0;
        break;
      case 288:
        v182 = (CSmState *)operator new(0x28u);
        v400 = (__int64 *)v182;
        if ( v182 )
          v181 = CSmState::CSmState(v182, L"DidNack1 [VX-v2-WFD]");
        else
          v181 = 0;
        break;
      default:
        v180 = (CSmState *)operator new(0x28u);
        v400 = (__int64 *)v180;
        if ( v180 )
          v181 = CSmState::CSmState(v180, L"DidNack1 [VX-v?]");
        else
          v181 = 0;
        break;
    }
    v376 = v181;
  }
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v376);
  v392 = 0;
  switch ( v146 )
  {
    case 16:
      v192 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v192;
      if ( v192 )
        v188 = CSmState::CSmState(v192, L"DidNack2 [VX-v1]");
      else
        v188 = 0;
      break;
    case 32:
      v191 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v191;
      if ( v191 )
        v188 = CSmState::CSmState(v191, L"DidNack2 [VX-v2]");
      else
        v188 = 0;
      break;
    case 272:
      v190 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v190;
      if ( v190 )
        v188 = CSmState::CSmState(v190, L"DidNack2 [VX-v1-WFD]");
      else
        v188 = 0;
      break;
    case 288:
      v189 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v189;
      if ( v189 )
        v188 = CSmState::CSmState(v189, L"DidNack2 [VX-v2-WFD]");
      else
        v188 = 0;
      break;
    default:
      v187 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v187;
      if ( v187 )
        v188 = CSmState::CSmState(v187, L"DidNack2 [VX-v?]");
      else
        v188 = 0;
      break;
  }
  v392 = v188;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v392);
  v384 = 0;
  switch ( v146 )
  {
    case 16:
      v198 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v198;
      if ( v198 )
        v194 = CSmState::CSmState(v198, L"Error [VX-v1]");
      else
        v194 = 0;
      break;
    case 32:
      v197 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v197;
      if ( v197 )
        v194 = CSmState::CSmState(v197, L"Error [VX-v2]");
      else
        v194 = 0;
      break;
    case 272:
      v196 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v196;
      if ( v196 )
        v194 = CSmState::CSmState(v196, L"Error [VX-v1-WFD]");
      else
        v194 = 0;
      break;
    case 288:
      v195 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v195;
      if ( v195 )
        v194 = CSmState::CSmState(v195, L"Error [VX-v2-WFD]");
      else
        v194 = 0;
      break;
    default:
      v193 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v193;
      if ( v193 )
        v194 = CSmState::CSmState(v193, L"Error [VX-v?]");
      else
        v194 = 0;
      break;
  }
  v384 = v194;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v384);
  v401 = 0;
  v199 = v146 - 16;
  if ( v199 )
  {
    v200 = v199 - 16;
    if ( v200 )
    {
      v201 = v200 - 240;
      if ( v201 )
      {
        v202 = (CSmState *)operator new(0x28u);
        if ( v201 == 16 )
        {
          v400 = (__int64 *)v202;
          if ( v202 )
            v203 = CSmState::CSmState(v202, L"Final [VX-v2-WFD]");
          else
            v203 = 0;
        }
        else
        {
          v400 = (__int64 *)v202;
          if ( v202 )
            v203 = CSmState::CSmState(v202, L"Final [VX-v?]");
          else
            v203 = 0;
        }
      }
      else
      {
        v204 = (CSmState *)operator new(0x28u);
        v400 = (__int64 *)v204;
        if ( v204 )
          v203 = CSmState::CSmState(v204, L"Final [VX-v1-WFD]");
        else
          v203 = 0;
      }
    }
    else
    {
      v205 = (CSmState *)operator new(0x28u);
      v400 = (__int64 *)v205;
      if ( v205 )
        v203 = CSmState::CSmState(v205, L"Final [VX-v2]");
      else
        v203 = 0;
    }
  }
  else
  {
    v206 = (CSmState *)operator new(0x28u);
    v400 = (__int64 *)v206;
    if ( v206 )
      v203 = CSmState::CSmState(v206, L"Final [VX-v1]");
    else
      v203 = 0;
  }
  v401 = v203;
  std::vector<CSmState *>::push_back((char *)v144 + 40, &v401);
  v207 = v398;
  *((_QWORD *)v398 + 11) = v389;
  *((_QWORD *)v207 + 12) = v384;
  v208 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v208;
  if ( v208 )
    v209 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v208, v401, 0x8000000, L"M1 : Check for terminated session [VX]");
  else
    v209 = 0;
  CSmState::AddTransition(v389, v209);
  v210 = (char *)v207 + 64;
  v400 = (__int64 *)v209;
  std::vector<CSmTransition *>::push_back((char *)v207 + 64, &v400);
  v211 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v211;
  if ( v211 )
    v212 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v211,
             WCN_VALUE_MT_M1,
             v389,
             0x8000000,
             v207,
             L"M1 : Check message type [VX]");
  else
    v212 = 0;
  CSmState::AddTransition(v389, v212);
  v400 = (__int64 *)v212;
  std::vector<CSmTransition *>::push_back((char *)v207 + 64, &v400);
  v213 = (__int64 *)operator new(0x30u);
  v400 = v213;
  if ( v213 )
    v214 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v213,
             0,
             (__int64)v365,
             0x8000000,
             (__int64)v207,
             (__int64)L"M1 : Process M1 [VX]");
  else
    v214 = 0;
  if ( v365 == v401 )
    *(_DWORD *)(v214 + 32) |= 0x1000000u;
  CSmState::AddTransition(v389, (struct CSmTransition *)v214);
  v400 = (__int64 *)v214;
  std::vector<CSmTransition *>::push_back((char *)v207 + 64, &v400);
  v215 = (CWcnProtocolVX::CVXM2DiscoveryCheck *)operator new(0x28u);
  v400 = (__int64 *)v215;
  if ( v215 )
    v216 = CWcnProtocolVX::CVXM2DiscoveryCheck::CVXM2DiscoveryCheck(v215, WCN_VALUE_MT_M2, v391);
  else
    v216 = 0;
  CSmState::AddTransition(v365, v216);
  v400 = (__int64 *)v216;
  std::vector<CSmTransition *>::push_back((char *)v207 + 64, &v400);
  v217 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v217;
  if ( v217 )
  {
    v207 = v398;
    v218 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v217,
             WCN_VALUE_MT_NACK,
             v391,
             8,
             v398,
             L"NACK : Check message type [VX]");
  }
  else
  {
    v218 = 0;
  }
  CSmState::AddTransition(v391, v218);
  v400 = (__int64 *)v218;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v219 = (__int64 *)operator new(0x30u);
  v400 = v219;
  if ( v219 )
    v220 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v219,
             24,
             (__int64)v376,
             8,
             (__int64)v207,
             (__int64)L"NACK : Process Wrong M2 NACK [VX]");
  else
    v220 = 0;
  if ( v376 == v401 )
    *(_DWORD *)(v220 + 32) |= 0x1000000u;
  *(_DWORD *)(v220 + 32) |= 0x2000000u;
  CSmState::AddTransition(v391, (struct CSmTransition *)v220);
  v400 = (__int64 *)v220;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v221 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v221;
  if ( v221 )
    v222 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v221, v401, 1, L"M2D : Check for terminated session [VX]");
  else
    v222 = 0;
  CSmState::AddTransition(v365, v222);
  v400 = (__int64 *)v222;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v223 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v223;
  if ( v223 )
    v224 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v223,
             WCN_VALUE_MT_M2D,
             v365,
             1,
             v207,
             L"M2D : Check message type [VX]");
  else
    v224 = 0;
  CSmState::AddTransition(v365, v224);
  v400 = (__int64 *)v224;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v225 = (__int64 *)operator new(0x30u);
  v400 = v225;
  if ( v225 )
    v226 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v225,
             3,
             (__int64)v364,
             1,
             (__int64)v207,
             (__int64)L"M2D : Process M2D [VX]");
  else
    v226 = 0;
  if ( v364 == v401 )
    *(_DWORD *)(v226 + 32) |= 0x1000000u;
  *(_DWORD *)(v226 + 32) |= 0x2000000u;
  CSmState::AddTransition(v365, (struct CSmTransition *)v226);
  v400 = (__int64 *)v226;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v227 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v227;
  if ( v227 )
    v228 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v227, v401, 32, L"M2D : Check for terminated session [VX]");
  else
    v228 = 0;
  CSmState::AddTransition(v365, v228);
  v400 = (__int64 *)v228;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v229 = (__int64 *)operator new(0x30u);
  v400 = v229;
  if ( v229 )
    v230 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v229,
             3,
             (__int64)v364,
             32,
             (__int64)v207,
             (__int64)L"M2D : Process M2D - keep going [VX]");
  else
    v230 = 0;
  if ( v364 == v401 )
    *(_DWORD *)(v230 + 32) |= 0x1000000u;
  CSmState::AddTransition(v365, (struct CSmTransition *)v230);
  v400 = (__int64 *)v230;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v231 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v231;
  if ( v231 )
    v232 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v231, v401, 32, L"ACK : Check for terminated session [VX]");
  else
    v232 = 0;
  CSmState::AddTransition(v364, v232);
  v400 = (__int64 *)v232;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v233 = (__int64 *)operator new(0x30u);
  v400 = v233;
  if ( v233 )
    v234 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v233,
             23,
             (__int64)v367,
             32,
             (__int64)v207,
             (__int64)L"ACK : Process M2D ACK - keep going [VX]");
  else
    v234 = 0;
  if ( v367 == v401 )
    *(_DWORD *)(v234 + 32) |= 0x1000000u;
  CSmState::AddTransition(v364, (struct CSmTransition *)v234);
  v400 = (__int64 *)v234;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v235 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v235;
  if ( v235 )
    v236 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v235, v401, 32, L"M2D : Check for terminated session [VX]");
  else
    v236 = 0;
  CSmState::AddTransition(v367, v236);
  v400 = (__int64 *)v236;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v237 = (__int64 *)operator new(0x30u);
  v400 = v237;
  if ( v237 )
    v238 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v237,
             3,
             (__int64)v364,
             32,
             (__int64)v207,
             (__int64)L"M2D : Process another M2D - keep going [VX]");
  else
    v238 = 0;
  if ( v364 == v401 )
    *(_DWORD *)(v238 + 32) |= 0x1000000u;
  CSmState::AddTransition(v367, (struct CSmTransition *)v238);
  v400 = (__int64 *)v238;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v239 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v239;
  if ( v239 )
    v240 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v239, v401, 32, L"M2 : Check for terminated session [VX]");
  else
    v240 = 0;
  CSmState::AddTransition(v367, v240);
  v400 = (__int64 *)v240;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v241 = (__int64 *)operator new(0x30u);
  v400 = v241;
  if ( v241 )
    v242 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v241,
             1,
             (__int64)v366,
             32,
             (__int64)v398,
             (__int64)L"M2 : Process M2 [VX]");
  else
    v242 = 0;
  if ( v366 == v401 )
    *(_DWORD *)(v242 + 32) |= 0x1000000u;
  CSmState::AddTransition(v367, (struct CSmTransition *)v242);
  v400 = (__int64 *)v242;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v243 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v243;
  if ( v243 )
    v244 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v243, v401, 4, L"Final : Check for terminated session [VX]");
  else
    v244 = 0;
  CSmState::AddTransition(v364, v244);
  v400 = (__int64 *)v244;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v245 = (__int64 *)operator new(0x30u);
  v400 = v245;
  if ( v245 )
    v246 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v245,
             30,
             (__int64)v401,
             4,
             (__int64)v398,
             (__int64)L"Final : Discovery complete (Proxy) [VX]");
  else
    v246 = 0;
  *(_DWORD *)(v246 + 32) |= 0x3000000u;
  CSmState::AddTransition(v364, (struct CSmTransition *)v246);
  v400 = (__int64 *)v246;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v247 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v247;
  if ( v247 )
    v248 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v247,
             WCN_VALUE_MT_NACK,
             v364,
             8,
             v398,
             L"NACK : Check message type [VX]");
  else
    v248 = 0;
  CSmState::AddTransition(v364, v248);
  v400 = (__int64 *)v248;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v249 = (__int64 *)operator new(0x30u);
  v400 = v249;
  if ( v249 )
    v250 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v249,
             24,
             (__int64)v376,
             8,
             (__int64)v398,
             (__int64)L"NACK : Process first NACK for discovery [VX]");
  else
    v250 = 0;
  if ( v376 == v401 )
    *(_DWORD *)(v250 + 32) |= 0x1000000u;
  *(_DWORD *)(v250 + 32) |= 0x2000000u;
  CSmState::AddTransition(v364, (struct CSmTransition *)v250);
  v400 = (__int64 *)v250;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v251 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v251;
  if ( v251 )
    v252 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v251,
             WCN_VALUE_MT_NACK,
             v376,
             0x8000000,
             v398,
             L"NACK : Check message type [VX]");
  else
    v252 = 0;
  CSmState::AddTransition(v376, v252);
  v400 = (__int64 *)v252;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v253 = (__int64 *)operator new(0x30u);
  v400 = v253;
  if ( v253 )
    v254 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v253,
             24,
             (__int64)v392,
             0x8000000,
             (__int64)v398,
             (__int64)L"NACK : Process second NACK for discovery [VX]");
  else
    v254 = 0;
  if ( v392 == v401 )
    *(_DWORD *)(v254 + 32) |= 0x1000000u;
  *(_DWORD *)(v254 + 32) |= 0x2000000u;
  CSmState::AddTransition(v376, (struct CSmTransition *)v254);
  v400 = (__int64 *)v254;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v255 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v255;
  if ( v255 )
    v256 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v255,
             v401,
             0x8000000,
             L"Final : Check for terminated session [VX]");
  else
    v256 = 0;
  CSmState::AddTransition(v392, v256);
  v400 = (__int64 *)v256;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v257 = (__int64 *)operator new(0x30u);
  v400 = v257;
  if ( v257 )
    v258 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v257,
             30,
             (__int64)v401,
             0x8000000,
             (__int64)v398,
             (__int64)L"Final : Discovery complete (NackNack) [VX]");
  else
    v258 = 0;
  *(_DWORD *)(v258 + 32) |= 0x3000000u;
  CSmState::AddTransition(v392, (struct CSmTransition *)v258);
  v400 = (__int64 *)v258;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v259 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v259;
  if ( v259 )
    v260 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v259, v401, 16, L"ACK : Check for terminated session [VX]");
  else
    v260 = 0;
  CSmState::AddTransition(v364, v260);
  v400 = (__int64 *)v260;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v261 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v261;
  if ( v261 )
    v262 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v261,
             WCN_VALUE_MT_ACK,
             v364,
             16,
             v398,
             L"ACK : Check message type [VX]");
  else
    v262 = 0;
  CSmState::AddTransition(v364, v262);
  v400 = (__int64 *)v262;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v263 = (__int64 *)operator new(0x30u);
  v400 = v263;
  if ( v263 )
    v264 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v263,
             23,
             (__int64)v367,
             16,
             (__int64)v398,
             (__int64)L"ACK : Process ACK for discovery [VX]");
  else
    v264 = 0;
  if ( v367 == v401 )
    *(_DWORD *)(v264 + 32) |= 0x1000000u;
  *(_DWORD *)(v264 + 32) |= 0x2000000u;
  CSmState::AddTransition(v364, (struct CSmTransition *)v264);
  v400 = (__int64 *)v264;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v265 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v265;
  if ( v265 )
    v266 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v265,
             v401,
             0x8000000,
             L"Final : Check for terminated session [VX]");
  else
    v266 = 0;
  CSmState::AddTransition(v367, v266);
  v400 = (__int64 *)v266;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v267 = (__int64 *)operator new(0x30u);
  v400 = v267;
  if ( v267 )
    v268 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v267,
             30,
             (__int64)v401,
             0x8000000,
             (__int64)v398,
             (__int64)L"Final : Discovery complete (ACK) [VX]");
  else
    v268 = 0;
  *(_DWORD *)(v268 + 32) |= 0x3000000u;
  CSmState::AddTransition(v367, (struct CSmTransition *)v268);
  v400 = (__int64 *)v268;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v269 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v269;
  if ( v269 )
    v270 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v269, v401, 2, L"Final : Check for terminated session [VX]");
  else
    v270 = 0;
  CSmState::AddTransition(v365, v270);
  v400 = (__int64 *)v270;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v271 = (__int64 *)operator new(0x30u);
  v400 = v271;
  if ( v271 )
    v272 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v271,
             30,
             (__int64)v401,
             2,
             (__int64)v398,
             (__int64)L"Final : Discovery complete (No M2D) [VX]");
  else
    v272 = 0;
  *(_DWORD *)(v272 + 32) |= 0x3000000u;
  CSmState::AddTransition(v365, (struct CSmTransition *)v272);
  v400 = (__int64 *)v272;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v273 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v273;
  if ( v273 )
    v274 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v273, v401, 0x8000000, L"M2 : Check for terminated session [VX]");
  else
    v274 = 0;
  CSmState::AddTransition(v365, v274);
  v400 = (__int64 *)v274;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v275 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v275;
  if ( v275 )
    v276 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v275,
             WCN_VALUE_MT_M2,
             v365,
             0x8000000,
             v398,
             L"M2 : Check message type [VX]");
  else
    v276 = 0;
  CSmState::AddTransition(v365, v276);
  v400 = (__int64 *)v276;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v277 = (__int64 *)operator new(0x30u);
  v400 = v277;
  if ( v277 )
    v278 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v277,
             1,
             (__int64)v366,
             0x8000000,
             (__int64)v398,
             (__int64)L"M2 : Process M2 [VX]");
  else
    v278 = 0;
  if ( v366 == v401 )
    *(_DWORD *)(v278 + 32) |= 0x1000000u;
  *(_DWORD *)(v278 + 32) |= 0x4000000u;
  CSmState::AddTransition(v365, (struct CSmTransition *)v278);
  v400 = (__int64 *)v278;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v279 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v279;
  if ( v279 )
    v280 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v279, v401, 0x8000000, L"M3 : Check for terminated session [VX]");
  else
    v280 = 0;
  CSmState::AddTransition(v366, v280);
  v400 = (__int64 *)v280;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v281 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v281;
  if ( v281 )
    v282 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v281,
             WCN_VALUE_MT_M3,
             v366,
             0x8000000,
             v398,
             L"M3 : Check message type [VX]");
  else
    v282 = 0;
  CSmState::AddTransition(v366, v282);
  v400 = (__int64 *)v282;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v283 = (__int64 *)operator new(0x30u);
  v400 = v283;
  if ( v283 )
    v284 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v283,
             4,
             (__int64)v380,
             0x8000000,
             (__int64)v398,
             (__int64)L"M3 : Process M3 [VX]");
  else
    v284 = 0;
  if ( v380 == v401 )
    *(_DWORD *)(v284 + 32) |= 0x1000000u;
  CSmState::AddTransition(v366, (struct CSmTransition *)v284);
  v400 = (__int64 *)v284;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v285 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v285;
  if ( v285 )
    v286 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v285, v401, 0x8000000, L"M4 : Check for terminated session [VX]");
  else
    v286 = 0;
  CSmState::AddTransition(v380, v286);
  v400 = (__int64 *)v286;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v287 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v287;
  if ( v287 )
    v288 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v287,
             WCN_VALUE_MT_M4,
             v380,
             0x8000000,
             v398,
             L"M4 : Check message type [VX]");
  else
    v288 = 0;
  CSmState::AddTransition(v380, v288);
  v400 = (__int64 *)v288;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v289 = (__int64 *)operator new(0x30u);
  v400 = v289;
  if ( v289 )
    v290 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v289,
             5,
             (__int64)v381,
             0x8000000,
             (__int64)v398,
             (__int64)L"M4 : Process M4 [VX]");
  else
    v290 = 0;
  if ( v381 == v401 )
    *(_DWORD *)(v290 + 32) |= 0x1000000u;
  *(_DWORD *)(v290 + 32) |= 0x4000000u;
  CSmState::AddTransition(v380, (struct CSmTransition *)v290);
  v400 = (__int64 *)v290;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v291 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v291;
  if ( v291 )
    v292 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v291, v401, 0x8000000, L"M5 : Check for terminated session [VX]");
  else
    v292 = 0;
  CSmState::AddTransition(v381, v292);
  v400 = (__int64 *)v292;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v293 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v293;
  if ( v293 )
    v294 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v293,
             WCN_VALUE_MT_M5,
             v381,
             0x8000000,
             v398,
             L"M5 : Check message type [VX]");
  else
    v294 = 0;
  CSmState::AddTransition(v381, v294);
  v400 = (__int64 *)v294;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v295 = (__int64 *)operator new(0x30u);
  v400 = v295;
  if ( v295 )
    v296 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v295,
             6,
             (__int64)v382,
             0x8000000,
             (__int64)v398,
             (__int64)L"M5 : Process M5 [VX]");
  else
    v296 = 0;
  if ( v382 == v401 )
    *(_DWORD *)(v296 + 32) |= 0x1000000u;
  CSmState::AddTransition(v381, (struct CSmTransition *)v296);
  v400 = (__int64 *)v296;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v297 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v297;
  if ( v297 )
    v298 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v297, v401, 0x8000000, L"M6 : Check for terminated session [VX]");
  else
    v298 = 0;
  CSmState::AddTransition(v382, v298);
  v400 = (__int64 *)v298;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v299 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v299;
  if ( v299 )
    v300 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v299,
             WCN_VALUE_MT_M6,
             v382,
             0x8000000,
             v398,
             L"M6 : Check message type [VX]");
  else
    v300 = 0;
  CSmState::AddTransition(v382, v300);
  v400 = (__int64 *)v300;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v301 = (__int64 *)operator new(0x30u);
  v400 = v301;
  if ( v301 )
    v302 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v301,
             7,
             (__int64)v383,
             0x8000000,
             (__int64)v398,
             (__int64)L"M6 : Process M6 [VX]");
  else
    v302 = 0;
  if ( v383 == v401 )
    *(_DWORD *)(v302 + 32) |= 0x1000000u;
  *(_DWORD *)(v302 + 32) |= 0x4000000u;
  CSmState::AddTransition(v382, (struct CSmTransition *)v302);
  v400 = (__int64 *)v302;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v303 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v303;
  if ( v303 )
    v304 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v303, v401, 0x8000000, L"M7 : Check for terminated session [VX]");
  else
    v304 = 0;
  CSmState::AddTransition(v383, v304);
  v400 = (__int64 *)v304;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v305 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v305;
  if ( v305 )
    v306 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v305,
             WCN_VALUE_MT_M7,
             v383,
             0x8000000,
             v398,
             L"M7 : Check message type [VX]");
  else
    v306 = 0;
  CSmState::AddTransition(v383, v306);
  v400 = (__int64 *)v306;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v307 = (__int64 *)operator new(0x30u);
  v400 = v307;
  if ( v307 )
    v308 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v307,
             8,
             (__int64)v369,
             0x8000000,
             (__int64)v398,
             (__int64)L"M7 : Process M7 [VX]");
  else
    v308 = 0;
  if ( v369 == v401 )
    *(_DWORD *)(v308 + 32) |= 0x1000000u;
  CSmState::AddTransition(v383, (struct CSmTransition *)v308);
  v400 = (__int64 *)v308;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v309 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v309;
  if ( v309 )
    v310 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v309,
             WCN_VALUE_MT_NACK,
             v369,
             128,
             v398,
             L"NACK : Check message type [VX]");
  else
    v310 = 0;
  CSmState::AddTransition(v369, v310);
  v400 = (__int64 *)v310;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v311 = (__int64 *)operator new(0x30u);
  v400 = v311;
  if ( v311 )
    v312 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v311,
             24,
             (__int64)v393,
             128,
             (__int64)v398,
             (__int64)L"NACK : Process NACK instead of M8 [VX]");
  else
    v312 = 0;
  if ( v393 == v401 )
    *(_DWORD *)(v312 + 32) |= 0x1000000u;
  *(_DWORD *)(v312 + 32) |= 0x2000000u;
  CSmState::AddTransition(v369, (struct CSmTransition *)v312);
  v400 = (__int64 *)v312;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v313 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v313;
  if ( v313 )
    v314 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v313,
             v401,
             0x8000000,
             L"Final : Check for terminated session [VX]");
  else
    v314 = 0;
  CSmState::AddTransition(v393, v314);
  v400 = (__int64 *)v314;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v315 = (__int64 *)operator new(0x30u);
  v400 = v315;
  if ( v315 )
    v316 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v315,
             30,
             (__int64)v401,
             0x8000000,
             (__int64)v398,
             (__int64)L"Final : Finished full protocol (skip M8) [VX]");
  else
    v316 = 0;
  *(_DWORD *)(v316 + 32) |= 0x3000000u;
  CSmState::AddTransition(v393, (struct CSmTransition *)v316);
  v400 = (__int64 *)v316;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v317 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v317;
  if ( v317 )
    v318 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v317, v401, 0x8000000, L"M8 : Check for terminated session [VX]");
  else
    v318 = 0;
  CSmState::AddTransition(v369, v318);
  v400 = (__int64 *)v318;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v319 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v319;
  if ( v319 )
    v320 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v319,
             WCN_VALUE_MT_M8,
             v369,
             0x8000000,
             v398,
             L"M8 : Check message type [VX]");
  else
    v320 = 0;
  CSmState::AddTransition(v369, v320);
  v400 = (__int64 *)v320;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v321 = (__int64 *)operator new(0x30u);
  v400 = v321;
  if ( v321 )
    v322 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v321,
             9,
             (__int64)v372,
             0x8000000,
             (__int64)v398,
             (__int64)L"M8 : Process M8 [VX]");
  else
    v322 = 0;
  if ( v372 == v401 )
    *(_DWORD *)(v322 + 32) |= 0x1000000u;
  *(_DWORD *)(v322 + 32) |= 0x4000000u;
  CSmState::AddTransition(v369, (struct CSmTransition *)v322);
  v400 = (__int64 *)v322;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v323 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v323;
  if ( v323 )
    v324 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v323, v401, 256, L"Final : Check for terminated session [VX]");
  else
    v324 = 0;
  CSmState::AddTransition(v372, v324);
  v400 = (__int64 *)v324;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v325 = (__int64 *)operator new(0x30u);
  v400 = v325;
  if ( v325 )
    v326 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v325,
             30,
             (__int64)v401,
             256,
             (__int64)v398,
             (__int64)L"Final : Finished full protocol (no DONE) [VX]");
  else
    v326 = 0;
  *(_DWORD *)(v326 + 32) |= 0x3000000u;
  CSmState::AddTransition(v372, (struct CSmTransition *)v326);
  v400 = (__int64 *)v326;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v327 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v327;
  if ( v327 )
    v328 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v327,
             v401,
             0x8000000,
             L"DONE : Check for terminated session [VX]");
  else
    v328 = 0;
  CSmState::AddTransition(v372, v328);
  v400 = (__int64 *)v328;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v329 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v329;
  if ( v329 )
    v330 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v329,
             WCN_VALUE_MT_DONE,
             v372,
             0x8000000,
             v398,
             L"DONE : Check message type [VX]");
  else
    v330 = 0;
  CSmState::AddTransition(v372, v330);
  v400 = (__int64 *)v330;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v331 = (__int64 *)operator new(0x30u);
  v400 = v331;
  if ( v331 )
    v332 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v331,
             25,
             (__int64)v368,
             0x8000000,
             (__int64)v398,
             (__int64)L"DONE : Process DONE [VX]");
  else
    v332 = 0;
  if ( v368 == v401 )
    *(_DWORD *)(v332 + 32) |= 0x1000000u;
  *(_DWORD *)(v332 + 32) |= 0x2000000u;
  CSmState::AddTransition(v372, (struct CSmTransition *)v332);
  v400 = (__int64 *)v332;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v333 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v333;
  if ( v333 )
    v334 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(v333, v401, 64, L"ACK : Check for terminated session [VX]");
  else
    v334 = 0;
  CSmState::AddTransition(v368, v334);
  v400 = (__int64 *)v334;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v335 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v335;
  if ( v335 )
  {
    v336 = v398;
    v337 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v335,
             WCN_VALUE_MT_ACK,
             v368,
             64,
             v398,
             L"ACK : Check message type [VX]");
  }
  else
  {
    v337 = 0;
    v336 = v398;
  }
  CSmState::AddTransition(v368, v337);
  v400 = (__int64 *)v337;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v338 = (__int64 *)operator new(0x30u);
  v400 = v338;
  if ( v338 )
    v339 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v338,
             23,
             (__int64)v394,
             64,
             (__int64)v336,
             (__int64)L"ACK : Process final ack for full protocol [VX]");
  else
    v339 = 0;
  if ( v394 == v401 )
    *(_DWORD *)(v339 + 32) |= 0x1000000u;
  *(_DWORD *)(v339 + 32) |= 0x2000000u;
  CSmState::AddTransition(v368, (struct CSmTransition *)v339);
  v400 = (__int64 *)v339;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v340 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v340;
  if ( v340 )
    v341 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v340,
             v401,
             0x8000000,
             L"Final : Check for terminated session [VX]");
  else
    v341 = 0;
  CSmState::AddTransition(v394, v341);
  v400 = (__int64 *)v341;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v342 = (__int64 *)operator new(0x30u);
  v400 = v342;
  if ( v342 )
    v343 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v342,
             30,
             (__int64)v401,
             0x8000000,
             (__int64)v398,
             (__int64)L"Final : Finished full protocol (with ACK) [VX]");
  else
    v343 = 0;
  *(_DWORD *)(v343 + 32) |= 0x3000000u;
  CSmState::AddTransition(v394, (struct CSmTransition *)v343);
  v400 = (__int64 *)v343;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v344 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v344;
  if ( v344 )
    v345 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v344,
             v401,
             0x8000000,
             L"Final : Check for terminated session [VX]");
  else
    v345 = 0;
  CSmState::AddTransition(v368, v345);
  v400 = (__int64 *)v345;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v346 = (__int64 *)operator new(0x30u);
  v400 = v346;
  if ( v346 )
    v347 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v346,
             30,
             (__int64)v401,
             0x8000000,
             (__int64)v398,
             (__int64)L"Final : Finished full protocol (no ACK) [VX]");
  else
    v347 = 0;
  *(_DWORD *)(v347 + 32) |= 0x3000000u;
  CSmState::AddTransition(v368, (struct CSmTransition *)v347);
  v400 = (__int64 *)v347;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v348 = (CWcnProtocolVX::CVXNackCheck *)operator new(0x28u);
  v400 = (__int64 *)v348;
  if ( v348 )
    v349 = CWcnProtocolVX::CVXNackCheck::CVXNackCheck(
             v348,
             v401,
             0x8000000,
             L"DONE : Check for terminated session [VX]");
  else
    v349 = 0;
  CSmState::AddTransition(v366, v349);
  v400 = (__int64 *)v349;
  std::vector<CSmTransition *>::push_back(v210, &v400);
  v350 = (CWcnProtocolVX::CVXResendCheck *)operator new(0x30u);
  v400 = (__int64 *)v350;
  if ( v350 )
  {
    v351 = v398;
    v352 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v350,
             WCN_VALUE_MT_DONE,
             v366,
             0x8000000,
             v398,
             L"DONE : Check message type [VX]");
  }
  else
  {
    v352 = 0;
    v351 = v398;
  }
  CSmState::AddTransition(v366, v352);
  v398 = v352;
  std::vector<CSmTransition *>::push_back(v210, &v398);
  v353 = (struct CWcnProtocolVX *)operator new(0x30u);
  v398 = v353;
  if ( v353 )
    v354 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v353,
             25,
             (__int64)v368,
             0x8000000,
             (__int64)v351,
             (__int64)L"DONE : Process DONE after M2 [VX]");
  else
    v354 = 0;
  if ( v368 == v401 )
    *(_DWORD *)(v354 + 32) |= 0x1000000u;
  *(_DWORD *)(v354 + 32) |= 0x2000000u;
  CSmState::AddTransition(v366, (struct CSmTransition *)v354);
  v398 = (struct CWcnProtocolVX *)v354;
  std::vector<CSmTransition *>::push_back(v210, &v398);
  v355 = (struct CWcnProtocolVX *)operator new(0x30u);
  v398 = v355;
  if ( v355 )
    v356 = CWcnProtocolVX::CVXResendCheck::CVXResendCheck(
             v355,
             WCN_VALUE_MT_NACK,
             v384,
             0x8000000,
             v351,
             L"NACK : Check message type [VX]");
  else
    v356 = 0;
  CSmState::AddTransition(v384, v356);
  v398 = v356;
  std::vector<CSmTransition *>::push_back(v210, &v398);
  v357 = (struct CWcnProtocolVX *)operator new(0x30u);
  v398 = v357;
  if ( v357 )
    v358 = CWcnProtocolVX::CVXTransition::CVXTransition(
             (__int64)v357,
             24,
             (__int64)v384,
             0x8000000,
             (__int64)v351,
             (__int64)L"NACK : Stuck in error state. [VX]");
  else
    v358 = 0;
  v359 = v384;
  if ( v384 == v401 )
  {
    *(_DWORD *)(v358 + 32) |= 0x1000000u;
    v359 = v384;
  }
  CSmState::AddTransition(v359, (struct CSmTransition *)v358);
  v398 = (struct CWcnProtocolVX *)v358;
  std::vector<CSmTransition *>::push_back(v210, &v398);
  v9 = CWcnParserVX::Init();
  if ( v9 >= 0 )
  {
    *((_BYTE *)v351 + 156) = 1;
    v9 = CWcnGeneratorVX::Init();
    if ( v9 >= 0 )
    {
      *((_BYTE *)v351 + 157) = 1;
      goto LABEL_959;
    }
    v360 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_959;
    v361 = 16;
    goto LABEL_953;
  }
  v360 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v9;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v361 = 15;
LABEL_953:
    WPP_SF_d(v360[2], v361, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids, (unsigned int)v9);
  }
LABEL_959:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v362 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids,
      v362,
      v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800208c0  mov     [rsp+arg_8], edx
0x1800208c4  mov     [rsp+arg_0], rcx
0x1800208c9  push    rbx
0x1800208ca  push    rsi
0x1800208cb  push    rdi
0x1800208cc  push    r12
0x1800208ce  push    r13
0x1800208d0  push    r14
0x1800208d2  push    r15
0x1800208d4  sub     rsp, 150h
0x1800208db  mov     esi, edx
0x1800208dd  mov     r14, rcx
0x1800208e0  lea     rcx, WPP_GLOBAL_Control
0x1800208e7  mov     rax, cs:WPP_GLOBAL_Control
0x1800208ee  mov     r15d, 6
0x1800208f4  cmp     rax, rcx
0x1800208f7  jz      short loc_18002092D
0x1800208f9  cmp     [rax+19h], r15b
0x1800208fd  jb      short loc_18002092D
0x1800208ff  lea     ecx, [r15-5]; int
0x180020903  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180020908  lea     edx, [r15+6]
0x18002090c  mov     r9, rax
0x18002090f  lea     r8, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids
0x180020916  mov     rcx, cs:WPP_GLOBAL_Control
0x18002091d  mov     rcx, [rcx+10h]
0x180020921  call    WPP_SF_s
0x180020926  lea     rcx, WPP_GLOBAL_Control
0x18002092d  xor     ebx, ebx
0x18002092f  mov     [rsp+188h+var_F0], rbx
0x180020937  mov     [rsp+188h+var_E8], rbx
0x18002093f  mov     [rsp+188h+var_E0], rbx
0x180020947  mov     [rsp+188h+var_B0], rbx
0x18002094f  mov     [rsp+188h+var_110], rbx
0x180020954  mov     [rsp+188h+var_108], rbx
0x18002095c  mov     [rsp+188h+var_100], rbx
0x180020964  mov     [rsp+188h+var_128], rbx
0x180020969  mov     [rsp+188h+var_120], rbx
0x18002096e  mov     [rsp+188h+var_A8], rbx
0x180020976  mov     [rsp+188h+var_A0], rbx
0x18002097e  mov     [rsp+188h+var_98], rbx
0x180020986  mov     [rsp+188h+var_88], rbx
0x18002098e  mov     [rsp+188h+var_60], rbx
0x180020996  mov     [r14+98h], esi
0x18002099d  cmp     [r14+9Dh], bl
0x1800209a4  jnz     short loc_1800209AF
0x1800209a6  cmp     [r14+9Ch], bl
0x1800209ad  jz      short loc_1800209E8
0x1800209af  mov     rax, cs:WPP_GLOBAL_Control
0x1800209b6  cmp     rax, rcx
0x1800209b9  jz      short loc_1800209E8
0x1800209bb  cmp     byte ptr [rax+19h], 2
0x1800209bf  jb      short loc_1800209E8
0x1800209c1  xor     ecx, ecx; int
0x1800209c3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800209c8  mov     edx, 0Dh
0x1800209cd  mov     r9, rax
0x1800209d0  lea     r8, WPP_4f48bed5e19434a0ae8963251cb823a4_Traceguids
0x1800209d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209de  mov     rcx, [rcx+10h]
0x1800209e2  call    WPP_SF_s
0x1800209e7  nop
0x1800209e8  mov     ecx, 38h ; '8'; Size
0x1800209ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800209f2  mov     rdi, rax
0x1800209f5  mov     [rsp+188h+arg_10], rax
0x1800209fd  mov     r13d, 8
0x180020a03  test    rax, rax
0x180020a06  jz      short loc_180020A20
0x180020a08  mov     [rax+10h], r13d
0x180020a0c  mov     [rax+18h], rbx
0x180020a10  mov     [rax+24h], bl
0x180020a13  mov     [rax+28h], rbx
0x180020a17  mov     [rax+30h], rbx
0x180020a1b  mov     [rax], rbx
0x180020a1e  jmp     short loc_180020A23
0x180020a20  mov     rdi, rbx
0x180020a23  mov     [rsp+188h+var_F0], rdi
0x180020a2b  lea     r12, [r14+18h]
0x180020a2f  mov     dword ptr [rsp+188h+arg_10], ebx
0x180020a36  lea     rdx, [rsp+188h+arg_10]
0x180020a3e  mov     rcx, r12
0x180020a41  call    ??A?$map@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@U?$less@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@std@@V?$allocator@U?$pair@$$CBW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@@std@@@5@@std@@QEAAAEAPEAVCWcnMessage@@$$QEAW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@Z; std::map<CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](CWcnProtocolVX::tagWcnProtocolVXMessageType &&)
0x180020a46  mov     [rax], rdi
0x180020a49  mov     ecx, esi
0x180020a4b  sub     ecx, 10h
0x180020a4e  jz      loc_180020AF2
0x180020a54  sub     ecx, 10h
0x180020a57  jz      short loc_180020ABE
0x180020a59  mov     r14d, 0F0h
0x180020a5f  sub     ecx, r14d
0x180020a62  jz      short loc_180020A89
0x180020a64  cmp     ecx, 10h
0x180020a67  jz      short loc_180020A73
0x180020a69  mov     edi, 80004005h
0x180020a6e  jmp     loc_180020B2E
0x180020a73  lea     rcx, aM1VxV2Wfd; "M1 [VX-v2-WFD]"
0x180020a7a  mov     r9d, 18h
0x180020a80  lea     r8, qword_180065940
0x180020a87  jmp     short loc_180020A9D
0x180020a89  lea     rcx, aM1VxV1Wfd; "M1 [VX-v1-WFD]"
0x180020a90  mov     r9d, 17h
0x180020a96  lea     r8, qword_180065350
0x180020a9d  mov     rax, [rsp+188h+var_F0]
0x180020aa5  mov     [rax], rcx
0x180020aa8  mov     edx, 5
0x180020aad  mov     rcx, [rsp+188h+var_F0]
0x180020ab5  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020aba  mov     edi, eax
0x180020abc  jmp     short loc_180020B2A
0x180020abe  lea     rcx, aM1VxV2; "M1 [VX-v2]"
0x180020ac5  mov     rax, [rsp+188h+var_F0]
0x180020acd  mov     [rax], rcx
0x180020ad0  mov     r9d, 18h
0x180020ad6  lea     r8, qword_180066020
0x180020add  lea     edx, [r9-13h]
0x180020ae1  mov     rcx, [rsp+188h+var_F0]
0x180020ae9  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020aee  mov     edi, eax
0x180020af0  jmp     short loc_180020B24
0x180020af2  lea     rcx, aM1VxV1; "M1 [VX-v1]"
0x180020af9  mov     rax, [rsp+188h+var_F0]
0x180020b01  mov     [rax], rcx
0x180020b04  mov     r9d, 17h
0x180020b0a  lea     r8, qword_1800665C0
0x180020b11  lea     edx, [r9-12h]
0x180020b15  mov     rcx, [rsp+188h+var_F0]
0x180020b1d  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020b22  mov     edi, eax
0x180020b24  mov     r14d, 0F0h
0x180020b2a  test    eax, eax
0x180020b2c  jns     short loc_180020B3A
0x180020b2e  lea     rsi, WPP_GLOBAL_Control
0x180020b35  jmp     loc_180025C85
0x180020b3a  jnz     short loc_180020B4B
0x180020b3c  mov     rax, [rsp+188h+var_F0]
0x180020b44  mov     dword ptr [rax+14h], 4
0x180020b4b  mov     ecx, 38h ; '8'; Size
0x180020b50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020b55  mov     rdi, rax
0x180020b58  mov     [rsp+188h+arg_10], rax
0x180020b60  test    rax, rax
0x180020b63  jz      short loc_180020B7D
0x180020b65  mov     [rax+10h], r13d
0x180020b69  mov     [rax+18h], rbx
0x180020b6d  mov     [rax+24h], bl
0x180020b70  mov     [rax+28h], rbx
0x180020b74  mov     [rax+30h], rbx
0x180020b78  mov     [rax], rbx
0x180020b7b  jmp     short loc_180020B80
0x180020b7d  mov     rdi, rbx
0x180020b80  mov     [rsp+188h+var_E8], rdi
0x180020b88  mov     dword ptr [rsp+188h+arg_10], 1
0x180020b93  lea     rdx, [rsp+188h+arg_10]
0x180020b9b  mov     rcx, r12
0x180020b9e  call    ??A?$map@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@U?$less@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@std@@V?$allocator@U?$pair@$$CBW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@@std@@@5@@std@@QEAAAEAPEAVCWcnMessage@@$$QEAW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@Z; std::map<CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](CWcnProtocolVX::tagWcnProtocolVXMessageType &&)
0x180020ba3  mov     [rax], rdi
0x180020ba6  mov     ecx, esi
0x180020ba8  sub     ecx, 10h
0x180020bab  jz      short loc_180020C1F
0x180020bad  sub     ecx, 10h
0x180020bb0  jz      short loc_180020BEC
0x180020bb2  sub     ecx, r14d
0x180020bb5  jz      short loc_180020BD6
0x180020bb7  cmp     ecx, 10h
0x180020bba  jz      short loc_180020BC6
0x180020bbc  mov     edi, 80004005h
0x180020bc1  jmp     loc_180020C54
0x180020bc6  lea     rcx, aM2VxV2Wfd; "M2 [VX-v2-WFD]"
0x180020bcd  lea     r8, qword_180065530
0x180020bd4  jmp     short loc_180020BFA
0x180020bd6  lea     rcx, aM2VxV1Wfd; "M2 [VX-v1-WFD]"
0x180020bdd  mov     r9d, 17h
0x180020be3  lea     r8, qword_180064FB0
0x180020bea  jmp     short loc_180020C00
0x180020bec  lea     rcx, aM2VxV2; "M2 [VX-v2]"
0x180020bf3  lea     r8, qword_180065B40
0x180020bfa  mov     r9d, 18h
0x180020c00  mov     rax, [rsp+188h+var_E8]
0x180020c08  mov     [rax], rcx
0x180020c0b  mov     edx, r15d
0x180020c0e  mov     rcx, [rsp+188h+var_E8]
0x180020c16  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020c1b  mov     edi, eax
0x180020c1d  jmp     short loc_180020C50
0x180020c1f  lea     rcx, aM2VxV1; "M2 [VX-v1]"
0x180020c26  mov     rax, [rsp+188h+var_E8]
0x180020c2e  mov     [rax], rcx
0x180020c31  mov     r9d, 17h
0x180020c37  lea     r8, qword_180066220
0x180020c3e  mov     edx, r15d
0x180020c41  mov     rcx, [rsp+188h+var_E8]
0x180020c49  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020c4e  mov     edi, eax
0x180020c50  test    eax, eax
0x180020c52  jns     short loc_180020C60
0x180020c54  lea     rsi, WPP_GLOBAL_Control
0x180020c5b  jmp     loc_180025C85
0x180020c60  jnz     short loc_180020C71
0x180020c62  mov     rax, [rsp+188h+var_E8]
0x180020c6a  mov     dword ptr [rax+14h], 5
0x180020c71  mov     ecx, 38h ; '8'; Size
0x180020c76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020c7b  mov     rdi, rax
0x180020c7e  mov     [rsp+188h+arg_10], rax
0x180020c86  test    rax, rax
0x180020c89  jz      short loc_180020CA3
0x180020c8b  mov     [rax+10h], r13d
0x180020c8f  mov     [rax+18h], rbx
0x180020c93  mov     [rax+24h], bl
0x180020c96  mov     [rax+28h], rbx
0x180020c9a  mov     [rax+30h], rbx
0x180020c9e  mov     [rax], rbx
0x180020ca1  jmp     short loc_180020CA6
0x180020ca3  mov     rdi, rbx
0x180020ca6  mov     [rsp+188h+var_60], rdi
0x180020cae  mov     dword ptr [rsp+188h+arg_10], 2
0x180020cb9  lea     rdx, [rsp+188h+arg_10]
0x180020cc1  mov     rcx, r12
0x180020cc4  call    ??A?$map@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@U?$less@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@std@@V?$allocator@U?$pair@$$CBW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@@std@@@5@@std@@QEAAAEAPEAVCWcnMessage@@$$QEAW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@Z; std::map<CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](CWcnProtocolVX::tagWcnProtocolVXMessageType &&)
0x180020cc9  mov     [rax], rdi
0x180020ccc  mov     ecx, esi
0x180020cce  sub     ecx, 10h
0x180020cd1  jz      short loc_180020D2A
0x180020cd3  sub     ecx, 10h
0x180020cd6  jz      short loc_180020CE9
0x180020cd8  sub     ecx, r14d
0x180020cdb  jz      short loc_180020D2A
0x180020cdd  cmp     ecx, 10h
0x180020ce0  jz      short loc_180020D2A
0x180020ce2  mov     edi, 80004005h
0x180020ce7  jmp     short loc_180020D1E
0x180020ce9  lea     rcx, aM2NfcChVxV2; "M2_NFC_CH [VX-v2]"
0x180020cf0  mov     rax, [rsp+188h+var_60]
0x180020cf8  mov     [rax], rcx
0x180020cfb  mov     r9d, 19h
0x180020d01  lea     r8, qword_180065C40
0x180020d08  mov     edx, r15d
0x180020d0b  mov     rcx, [rsp+188h+var_60]
0x180020d13  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020d18  mov     edi, eax
0x180020d1a  test    eax, eax
0x180020d1c  jns     short loc_180020D2A
0x180020d1e  lea     rsi, WPP_GLOBAL_Control
0x180020d25  jmp     loc_180025C85
0x180020d2a  mov     rax, [rsp+188h+var_60]
0x180020d32  mov     dword ptr [rax+14h], 5
0x180020d39  mov     ecx, 38h ; '8'; Size
0x180020d3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020d43  mov     rdi, rax
0x180020d46  mov     [rsp+188h+arg_10], rax
0x180020d4e  test    rax, rax
0x180020d51  jz      short loc_180020D6B
0x180020d53  mov     [rax+10h], r13d
0x180020d57  mov     [rax+18h], rbx
0x180020d5b  mov     [rax+24h], bl
0x180020d5e  mov     [rax+28h], rbx
0x180020d62  mov     [rax+30h], rbx
0x180020d66  mov     [rax], rbx
0x180020d69  jmp     short loc_180020D6E
0x180020d6b  mov     rdi, rbx
0x180020d6e  mov     [rsp+188h+var_E0], rdi
0x180020d76  mov     dword ptr [rsp+188h+arg_10], 3
0x180020d81  lea     rdx, [rsp+188h+arg_10]
0x180020d89  mov     rcx, r12
0x180020d8c  call    ??A?$map@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@U?$less@W4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@std@@V?$allocator@U?$pair@$$CBW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@PEAVCWcnMessage@@@std@@@5@@std@@QEAAAEAPEAVCWcnMessage@@$$QEAW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@Z; std::map<CWcnProtocolVX::tagWcnProtocolVXMessageType,CWcnMessage *>::operator[](CWcnProtocolVX::tagWcnProtocolVXMessageType &&)
0x180020d91  mov     [rax], rdi
0x180020d94  mov     ecx, esi
0x180020d96  sub     ecx, 10h
0x180020d99  jz      short loc_180020E0D
0x180020d9b  sub     ecx, 10h
0x180020d9e  jz      short loc_180020DDA
0x180020da0  sub     ecx, r14d
0x180020da3  jz      short loc_180020DC4
0x180020da5  cmp     ecx, 10h
0x180020da8  jz      short loc_180020DB4
0x180020daa  mov     edi, 80004005h
0x180020daf  jmp     loc_180020E42
0x180020db4  lea     rcx, aM2dVxV2Wfd; "M2D [VX-v2-WFD]"
0x180020dbb  lea     r8, qword_1800656D0
0x180020dc2  jmp     short loc_180020DE8
0x180020dc4  lea     rcx, aM2dVxV1Wfd; "M2D [VX-v1-WFD]"
0x180020dcb  mov     r9d, 14h
0x180020dd1  lea     r8, qword_180065130
0x180020dd8  jmp     short loc_180020DEE
0x180020dda  lea     rcx, aM2dVxV2; "M2D [VX-v2]"
0x180020de1  lea     r8, qword_180065DB0
0x180020de8  mov     r9d, 15h
0x180020dee  mov     rax, [rsp+188h+var_E0]
0x180020df6  mov     [rax], rcx
0x180020df9  mov     edx, r15d
0x180020dfc  mov     rcx, [rsp+188h+var_E0]
0x180020e04  call    ?Init@CWcnMessage@@QEAAJW4tagWCN_MESSAGE_TYPE@@PEBUtagWCN_MESSAGE_RULE@@_K@Z; CWcnMessage::Init(tagWCN_MESSAGE_TYPE,tagWCN_MESSAGE_RULE const *,unsigned __int64)
0x180020e09  mov     edi, eax
0x180020e0b  jmp     short loc_180020E3E
0x180020e0d  lea     rcx, aM2dVxV1; "M2D [VX-v1]"
0x180020e14  mov     rax, [rsp+188h+var_E0]
0x180020e1c  mov     [rax], rcx
0x180020e1f  mov     r9d, 14h
0x180020e25  lea     r8, qword_1800663A0
  ... truncated ...
```
