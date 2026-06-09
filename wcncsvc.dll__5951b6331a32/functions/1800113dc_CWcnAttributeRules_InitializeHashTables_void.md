# CWcnAttributeRules::InitializeHashTables(void)

- ea: `0x1800113dc`
- end: `0x180014523`
- name: `?InitializeHashTables@CWcnAttributeRules@@CAJXZ`
- size: `12615`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003dec`

## callees

- `0x180001404`
- `0x180010e5c`
- `0x180010efc`
- `0x180010f9c`
- `0x1800113dc`
- `0x1800148d8`

## string_xrefs

- `0x1800120b7`: `WCN_TYPE_CONFIG_METHODS`
- `0x180012118`: `WCN_TYPE_CONFIGURATION_ERROR`
- `0x1800135bf`: `WCN_TYPE_SSID`
- `0x180013754`: `WCN_TYPE_VENDOR_EXTENSION`
- `0x180013aea`: `WCN_TYPE_PERMITTED_CONFIG_METHODS`
- `0x180013b50`: `WCN_TYPE_SELECTED_REGISTRAR_CONFIG_METHODS`
- `0x180013d47`: `WCN_TYPE_APPLICATION_EXTENSION`
- `0x180014128`: `WCN_TYPE_CURRENT_SSID`
- `0x180014173`: `WCN_TYPE_BSSID`
- `0x18001420f`: `WCN_TYPE_VENDOR_EXTENSION_WFA`

## pseudocode

```c
__int64 CWcnAttributeRules::InitializeHashTables(void)
{
  _QWORD *v1; // rax
  __int64 v2; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rbx
  _DWORD *v7; // rax
  __int64 v8; // rcx
  _DWORD *v9; // rbx
  _DWORD *v10; // rax
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  _DWORD *v13; // rax
  __int64 v14; // rcx
  _DWORD *v15; // rdi
  _DWORD *v16; // rax
  __int64 v17; // rcx
  _DWORD *v18; // rdi
  _DWORD *v19; // rax
  __int64 v20; // rcx
  _DWORD *v21; // rdi
  _DWORD *v22; // rax
  __int64 v23; // rcx
  _DWORD *v24; // rdi
  char *v25; // rax
  __int64 v26; // rcx
  char *v27; // rdi
  _DWORD *v28; // rax
  __int64 v29; // rcx
  _DWORD *v30; // rdi
  _DWORD *v31; // rax
  __int64 v32; // rcx
  _DWORD *v33; // rdi
  _DWORD *v34; // rax
  __int64 v35; // rcx
  _DWORD *v36; // rdi
  _DWORD *v37; // rax
  __int64 v38; // rcx
  _DWORD *v39; // rdi
  char *v40; // rax
  __int64 v41; // rcx
  char *v42; // rdi
  _DWORD *v43; // rax
  __int64 v44; // rcx
  _DWORD *v45; // rdi
  _DWORD *v46; // rax
  __int64 v47; // rcx
  _DWORD *v48; // rdi
  __int64 v49; // rcx
  char *v50; // rdi
  _DWORD *v51; // rax
  __int64 v52; // rcx
  _DWORD *v53; // rdi
  _DWORD *v54; // rax
  __int64 v55; // rcx
  _DWORD *v56; // rdi
  _DWORD *v57; // rax
  __int64 v58; // rcx
  _DWORD *v59; // rdi
  _DWORD *v60; // rax
  __int64 v61; // rcx
  _DWORD *v62; // rdi
  __int64 v63; // rcx
  _DWORD *v64; // rdi
  _DWORD *v65; // rax
  __int64 v66; // rcx
  _DWORD *v67; // rdi
  __int64 v68; // rcx
  _DWORD *v69; // rdi
  __int64 v70; // rcx
  _DWORD *v71; // rdi
  _DWORD *v72; // rax
  __int64 v73; // rcx
  _DWORD *v74; // rdi
  _DWORD *v75; // rax
  __int64 v76; // rcx
  _DWORD *v77; // rdi
  __int64 v78; // rcx
  _DWORD *v79; // rdi
  _DWORD *v80; // rax
  __int64 v81; // rcx
  _DWORD *v82; // rdi
  __int64 v83; // rcx
  _DWORD *v84; // rdi
  __int64 v85; // rcx
  _DWORD *v86; // rdi
  __int64 v87; // rcx
  _DWORD *v88; // rdi
  __int64 v89; // rcx
  _DWORD *v90; // rdi
  _DWORD *v91; // rax
  __int64 v92; // rcx
  _DWORD *v93; // rdi
  __int64 v94; // rcx
  _DWORD *v95; // rdi
  __int64 v96; // rcx
  _DWORD *v97; // rdi
  _DWORD *v98; // rax
  __int64 v99; // rcx
  _DWORD *v100; // rdi
  __int64 v101; // rcx
  _DWORD *v102; // rdi
  __int64 v103; // rcx
  char *v104; // rdi
  __int64 v105; // rcx
  char *v106; // rdi
  _DWORD *v107; // rax
  __int64 v108; // rcx
  _DWORD *v109; // rdi
  _DWORD *v110; // rax
  _DWORD *v111; // rdi
  __int64 v112; // rcx
  _DWORD *v113; // rax
  __int64 v114; // rcx
  _DWORD *v115; // rdi
  __int64 v116; // rcx
  _DWORD *v117; // rax
  __int64 v118; // rcx
  _DWORD *v119; // rdi
  __int64 v120; // rcx
  _DWORD *v121; // rax
  __int64 v122; // rcx
  _DWORD *v123; // rdi
  __int64 v124; // rcx
  _DWORD *v125; // rax
  __int64 v126; // rcx
  _DWORD *v127; // rdi
  __int64 v128; // rcx
  _DWORD *v129; // rax
  __int64 v130; // rcx
  _DWORD *v131; // rdi
  __int64 v132; // rcx
  _DWORD *v133; // rax
  __int64 v134; // rcx
  _DWORD *v135; // rdi
  __int64 v136; // rcx
  _DWORD *v137; // rax
  __int64 v138; // rcx
  _DWORD *v139; // rdi
  __int64 v140; // rcx
  _DWORD *v141; // rax
  __int64 v142; // rcx
  _DWORD *v143; // rdi
  __int64 v144; // rcx
  _DWORD *v145; // rax
  __int64 v146; // rcx
  _DWORD *v147; // rdi
  __int64 v148; // rcx
  _DWORD *v149; // rax
  __int64 v150; // rcx
  _DWORD *v151; // rdi
  __int64 v152; // rcx
  _DWORD *v153; // rax
  __int64 v154; // rcx
  _DWORD *v155; // rdi
  __int64 v156; // rcx
  _QWORD *v157; // rax
  __int64 v158; // rcx
  _QWORD *v159; // rdi
  __int64 v160; // rcx
  _DWORD *v161; // rax
  __int64 v162; // rcx
  _DWORD *v163; // rdi
  __int64 v164; // rcx
  _DWORD *v165; // rax
  __int64 v166; // rcx
  _DWORD *v167; // rdi
  __int64 v168; // rcx
  _DWORD *v169; // rax
  __int64 v170; // rcx
  _DWORD *v171; // rdi
  __int64 v172; // rcx
  _DWORD *v173; // rax
  __int64 v174; // rcx
  _DWORD *v175; // rdi
  __int64 v176; // rcx
  _DWORD *v177; // rax
  __int64 v178; // rcx
  _DWORD *v179; // rdi
  __int64 v180; // rcx
  _DWORD *v181; // rax
  __int64 v182; // rcx
  _DWORD *v183; // rdi
  __int64 v184; // rcx
  _DWORD *v185; // rax
  __int64 v186; // rcx
  _DWORD *v187; // rdi
  __int64 v188; // rcx
  _DWORD *v189; // rax
  __int64 v190; // rcx
  _DWORD *v191; // rdi
  __int64 v192; // rcx
  _DWORD *v193; // rax
  __int64 v194; // rcx
  _DWORD *v195; // rdi
  __int64 v196; // rcx
  _DWORD *v197; // rax
  __int64 v198; // rcx
  _DWORD *v199; // rdi
  __int64 v200; // rcx
  _DWORD *v201; // rax
  __int64 v202; // rcx
  _DWORD *v203; // rdi
  __int64 v204; // rcx
  _DWORD *v205; // rax
  __int64 v206; // rcx
  _DWORD *v207; // rdi
  __int64 v208; // rcx
  _DWORD *v209; // rax
  __int64 v210; // rcx
  _DWORD *v211; // rdi
  __int64 v212; // rcx
  _DWORD *v213; // rax
  __int64 v214; // rcx
  _DWORD *v215; // rdi
  __int64 v216; // rcx
  _DWORD *v217; // rax
  __int64 v218; // rcx
  _DWORD *v219; // rdi
  __int64 v220; // rcx
  _DWORD *v221; // rax
  __int64 v222; // rcx
  _DWORD *v223; // rdi
  __int64 v224; // rcx
  _DWORD *v225; // rax
  __int64 v226; // rcx
  _DWORD *v227; // rdi
  __int64 v228; // rcx
  _QWORD *v229; // rax
  __int64 v230; // rcx
  _QWORD *v231; // rdi
  __int64 v232; // rcx
  _QWORD *v233; // rax
  __int64 v234; // rcx
  _QWORD *v235; // rdi
  __int64 v236; // rcx
  _DWORD *v237; // rax
  __int64 v238; // rcx
  _DWORD *v239; // rdi
  __int64 v240; // rcx
  _DWORD *v241; // rax
  __int64 v242; // rcx
  _DWORD *v243; // rdi
  __int64 v244; // rcx
  _DWORD *v245; // rax
  __int64 v246; // rcx
  _DWORD *v247; // rdi
  __int64 v248; // rcx
  _QWORD *v249; // rax
  __int64 v250; // rcx
  _QWORD *v251; // rdi
  __int64 v252; // rcx
  _DWORD *v253; // rax
  __int64 v254; // rcx
  _DWORD *v255; // rdi
  __int64 v256; // rcx
  _DWORD *v257; // rax
  __int64 v258; // rcx
  _DWORD *v259; // rdi
  __int64 v260; // rcx
  _DWORD *v261; // rax
  __int64 v262; // rcx
  _DWORD *v263; // rdi
  __int64 v264; // rcx
  _DWORD *v265; // rax
  __int64 v266; // rcx
  _DWORD *v267; // rdi
  __int64 v268; // rcx
  _DWORD *v269; // rax
  __int64 v270; // rcx
  _DWORD *v271; // rdi
  __int64 v272; // rcx
  _DWORD *v273; // rax
  __int64 v274; // rcx
  _DWORD *v275; // rdi
  __int64 v276; // rcx
  _DWORD *v277; // rax
  __int64 v278; // rcx
  _DWORD *v279; // rdi
  __int64 v280; // rcx
  _DWORD *v281; // rax
  __int64 v282; // rcx
  _DWORD *v283; // rdi
  __int64 v284; // rcx
  _DWORD *v285; // rax
  __int64 v286; // rcx
  _DWORD *v287; // rdi
  __int64 v288; // rcx
  _DWORD *v289; // rax
  __int64 v290; // rcx
  _DWORD *v291; // rdi
  __int64 v292; // rcx
  _DWORD *v293; // rax
  __int64 v294; // rcx
  _DWORD *v295; // rdi
  __int64 v296; // rcx
  _DWORD *v297; // rax
  __int64 v298; // rcx
  _DWORD *v299; // rdi
  __int64 v300; // rcx
  _DWORD *v301; // rax
  __int64 v302; // rcx
  _DWORD *v303; // rdi
  __int64 v304; // rcx
  _DWORD *v305; // rax
  __int64 v306; // rcx
  _DWORD *v307; // rdi
  __int64 v308; // rcx
  _DWORD *v309; // rax
  __int64 v310; // rcx
  _DWORD *v311; // rdi
  __int64 v312; // rcx
  _DWORD *v313; // rax
  __int64 v314; // rcx
  _DWORD *v315; // rdi
  __int64 v316; // rcx
  _DWORD *v317; // rax
  __int64 v318; // rcx
  _DWORD *v319; // rdi
  __int64 v320; // rcx
  _DWORD *v321; // rax
  __int64 v322; // rcx
  _DWORD *v323; // rdi
  __int64 v324; // rcx
  _DWORD *v325; // rax
  __int64 v326; // rcx
  _DWORD *v327; // rdi
  __int64 v328; // rcx
  _DWORD *v329; // rax
  __int64 v330; // rcx
  _DWORD *v331; // rdi
  __int64 v332; // rcx
  _DWORD *v333; // rax
  __int64 v334; // rcx
  _DWORD *v335; // rdi
  __int64 v336; // rcx
  _DWORD *v337; // rax
  __int64 v338; // rcx
  _DWORD *v339; // rdi
  __int64 v340; // rcx
  _QWORD *v341; // rax
  __int64 v342; // rcx
  _QWORD *v343; // rdi
  __int64 v344; // rcx
  _DWORD *v345; // rax
  __int64 v346; // rcx
  _DWORD *v347; // rdi
  __int64 v348; // rcx
  _DWORD *v349; // rax
  __int64 v350; // rcx
  _DWORD *v351; // rdi
  __int64 v352; // rcx
  _DWORD *v353; // rax
  __int64 v354; // rcx
  _DWORD *v355; // rdi
  __int64 v356; // rcx
  _DWORD *v357; // rax
  __int64 v358; // rcx
  _DWORD *v359; // rdi
  __int64 v360; // rcx
  _DWORD *v361; // rax
  __int64 v362; // rcx
  _DWORD *v363; // rdi
  __int64 v364; // rcx
  _DWORD *v365; // rax
  __int64 v366; // rcx
  _DWORD *v367; // rdi
  __int64 v368; // rcx
  _DWORD *v369; // rax
  __int64 v370; // rcx
  _DWORD *v371; // rdi
  __int64 v372; // rcx
  _DWORD *v373; // rax
  __int64 v374; // rcx
  _DWORD *v375; // rdi
  __int64 v376; // rcx
  _DWORD *v377; // rax
  __int64 v378; // rcx
  _DWORD *v379; // rdi
  __int64 v380; // rcx
  _DWORD *v381; // rax
  __int64 v382; // rcx
  _DWORD *v383; // rdi
  __int64 v384; // rcx
  _DWORD *v385; // rax
  __int64 v386; // rcx
  _DWORD *v387; // rdi
  __int64 v388; // rcx
  _DWORD *v389; // rax
  __int64 v390; // rcx
  _DWORD *v391; // rdi
  __int64 v392; // rcx
  _DWORD *v393; // rax
  __int64 v394; // rcx
  _DWORD *v395; // rdi
  __int64 v396; // rcx
  _DWORD *v397; // rax
  __int64 v398; // rcx
  _DWORD *v399; // rdi
  __int64 v400; // rcx
  _DWORD *v401; // rax
  __int64 v402; // rcx
  _DWORD *v403; // rdi
  __int64 v404; // rcx
  _DWORD *v405; // rax
  __int64 v406; // rcx
  _DWORD *v407; // rdi
  __int64 v408; // rcx
  _DWORD *v409; // rax
  __int64 v410; // rcx
  _DWORD *v411; // rdi
  __int64 v412; // rcx
  _DWORD *v413; // rax
  __int64 v414; // rcx
  _DWORD *v415; // rdi
  __int64 v416; // rcx
  _DWORD *v417; // rax
  __int64 v418; // rcx
  _DWORD *v419; // rdi
  __int64 v420; // rcx
  _DWORD *v421; // rax
  __int64 v422; // rcx
  _DWORD *v423; // rdi
  __int64 v424; // rcx
  _DWORD *v425; // rax
  __int64 v426; // rcx
  _DWORD *v427; // rdi
  __int64 v428; // rcx
  _DWORD *v429; // rax
  __int64 v430; // rcx
  _DWORD *v431; // rdi
  __int64 v432; // rcx
  _DWORD *v433; // rax
  __int64 v434; // rcx
  _DWORD *v435; // rdi
  __int64 v436; // rcx
  _DWORD *v437; // rax
  __int64 v438; // rcx
  _DWORD *v439; // rdi
  __int64 v440; // rcx
  _DWORD *v441; // rax
  __int64 v442; // rcx
  _DWORD *v443; // rdi
  __int64 v444; // rcx
  _DWORD *v445; // rax
  __int64 v446; // rcx
  _DWORD *v447; // rdi
  __int64 v448; // rcx
  _DWORD *v449; // rax
  __int64 v450; // rcx
  _DWORD *v451; // rdi
  __int64 v452; // rcx
  _DWORD *v453; // rax
  __int64 v454; // rcx
  _DWORD *v455; // rdi
  _DWORD *v456; // rax
  __int64 v457; // rcx
  _DWORD *v458; // rdi
  _DWORD *v459; // rax
  __int64 v460; // rcx
  _DWORD *v461; // rdi
  _DWORD *v462; // rax
  __int64 v463; // rcx
  _DWORD *v464; // rdi
  _DWORD *v465; // rax
  __int64 v466; // rcx
  _DWORD *v467; // rdi
  _DWORD *v468; // rax
  __int64 v469; // rcx
  _DWORD *v470; // rdi
  _DWORD *v471; // rax
  __int64 v472; // rcx
  _DWORD *v473; // rdi
  _DWORD *v474; // rax
  __int64 v475; // rcx
  _DWORD *v476; // rdi
  __int64 v477; // rcx
  _DWORD *v478; // rsi
  __int64 v479; // rcx
  _DWORD *v480; // rsi
  __int64 v481; // rcx
  _DWORD *v482; // rsi
  __int64 v483; // rcx
  _DWORD *v484; // rsi
  __int64 v485; // rcx
  _DWORD *v486; // rsi
  _DWORD *v487; // rax
  __int64 v488; // rcx
  _DWORD *v489; // rdi
  __int64 v490; // rcx
  _QWORD *v491; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v492; // [rsp+58h] [rbp+10h]

  v492 = 0;
  if ( CWcnAttributeRules::m_fInitialized )
    return 2147942583LL;
  CWcnAttributeRules::m_fInitialized = 1;
  try
  {
    v1 = operator new(0x10u);
    v2 = (__int64)v1;
    v491 = v1;
    if ( v1 )
    {
      *v1 = 0;
      v1[1] = 0;
      *v1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>::_Buyheadnode();
    }
    else
    {
      v2 = 0;
    }
    CWcnAttributeRules::m_pDataTypeRules = v2;
    v3 = operator new(0x10u);
    v4 = (__int64)v3;
    v491 = v3;
    if ( v3 )
    {
      *v3 = 0;
      v3[1] = 0;
      *v3 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>::_Buyheadnode();
    }
    else
    {
      v4 = 0;
    }
    CWcnAttributeRules::m_pAttributeRules = v4;
    v5 = operator new(0x10u);
    v6 = (__int64)v5;
    v491 = v5;
    if ( v5 )
    {
      *v5 = 0;
      v5[1] = 0;
      *v5 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>::_Buyheadnode();
    }
    else
    {
      v6 = 0;
    }
    CWcnAttributeRules::m_pAttributeIds = v6;
    v7 = operator new(0x14u);
    v9 = v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = 1;
      v7[2] = 32;
      *((_WORD *)v7 + 6) = 0;
      v7[4] = 39;
    }
    else
    {
      v9 = 0;
    }
    LODWORD(v491) = 0;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v8, &v491) = v9;
    v10 = operator new(0x14u);
    v12 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 1;
      v10[2] = 64;
      *((_WORD *)v10 + 6) = 0;
      v10[4] = 39;
    }
    else
    {
      v12 = 0;
    }
    LODWORD(v491) = 1;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v11, &v491) = v12;
    v13 = operator new(0x14u);
    v15 = v13;
    if ( v13 )
    {
      *(_QWORD *)v13 = 2;
      v13[2] = 512;
      *((_WORD *)v13 + 6) = 0;
      v13[4] = 39;
    }
    else
    {
      v15 = 0;
    }
    LODWORD(v491) = 2;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v14, &v491) = v15;
    v16 = operator new(0x14u);
    v18 = v16;
    if ( v16 )
    {
      *(_QWORD *)v16 = 2;
      v16[2] = 128;
      *((_WORD *)v16 + 6) = 0;
      v16[4] = 39;
    }
    else
    {
      v18 = 0;
    }
    LODWORD(v491) = 3;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v17, &v491) = v18;
    v19 = operator new(0x14u);
    v21 = v19;
    if ( v19 )
    {
      *v19 = 2;
      v19[1] = 1;
      v19[2] = 8;
      *((_WORD *)v19 + 6) = 1;
      v19[4] = 39;
    }
    else
    {
      v21 = 0;
    }
    LODWORD(v491) = 4;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v20, &v491) = v21;
    v22 = operator new(0x14u);
    v24 = v22;
    if ( v22 )
    {
      *v22 = 0;
      v22[1] = 1;
      v22[2] = 1;
      *((_WORD *)v22 + 6) = 0;
      v22[4] = 39;
    }
    else
    {
      v24 = 0;
    }
    LODWORD(v491) = 5;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v23, &v491) = v24;
    v25 = (char *)operator new(0x14u);
    v27 = v25;
    if ( v25 )
    {
      *(_DWORD *)v25 = 2;
      *(_QWORD *)(v25 + 4) = 2;
      *((_WORD *)v25 + 6) = 0;
      *((_DWORD *)v25 + 4) = 39;
    }
    else
    {
      v27 = 0;
    }
    LODWORD(v491) = 6;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v26, &v491) = v27;
    v28 = operator new(0x14u);
    v30 = v28;
    if ( v28 )
    {
      *v28 = 2;
      v28[1] = 1;
      v28[2] = 8;
      *((_WORD *)v28 + 6) = 0;
      v28[4] = 39;
    }
    else
    {
      v30 = 0;
    }
    LODWORD(v491) = 7;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v29, &v491) = v30;
    v31 = operator new(0x14u);
    v33 = v31;
    if ( v31 )
    {
      *(_QWORD *)v31 = 2;
      v31[2] = 128;
      *((_WORD *)v31 + 6) = 256;
      v31[4] = 7;
    }
    else
    {
      v33 = 0;
    }
    LODWORD(v491) = 8;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v32, &v491) = v33;
    v34 = operator new(0x14u);
    v36 = v34;
    if ( v34 )
    {
      *(_QWORD *)v34 = 2;
      v34[2] = 64;
      *((_WORD *)v34 + 6) = 0;
      v34[4] = 39;
    }
    else
    {
      v36 = 0;
    }
    LODWORD(v491) = 9;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v35, &v491) = v36;
    v37 = operator new(0x14u);
    v39 = v37;
    if ( v37 )
    {
      *(_QWORD *)v37 = 2;
      v37[2] = 8;
      *((_WORD *)v37 + 6) = 0;
      v37[4] = 39;
    }
    else
    {
      v39 = 0;
    }
    LODWORD(v491) = 10;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v38, &v491) = v39;
    v40 = (char *)operator new(0x14u);
    v42 = v40;
    if ( v40 )
    {
      *(_DWORD *)v40 = 2;
      *(_QWORD *)(v40 + 4) = 2;
      *((_WORD *)v40 + 6) = 0;
      *((_DWORD *)v40 + 4) = 39;
    }
    else
    {
      v42 = 0;
    }
    LODWORD(v491) = 11;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v41, &v491) = v42;
    v43 = operator new(0x14u);
    v45 = v43;
    if ( v43 )
    {
      *v43 = 2;
      v43[1] = 1;
      v43[2] = 32;
      *((_WORD *)v43 + 6) = 0;
      v43[4] = 39;
    }
    else
    {
      v45 = 0;
    }
    LODWORD(v491) = 12;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v44, &v491) = v45;
    v46 = operator new(0x14u);
    v48 = v46;
    if ( v46 )
    {
      *(_QWORD *)v46 = 2;
      v46[2] = 80;
      *((_WORD *)v46 + 6) = 0;
      v46[4] = 39;
    }
    else
    {
      v48 = 0;
    }
    LODWORD(v491) = 13;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v47, &v491) = v48;
    v50 = (char *)operator new(0x14u);
    if ( v50 )
    {
      *(_DWORD *)v50 = 2;
      *(_QWORD *)(v50 + 4) = 2;
      *((_WORD *)v50 + 6) = 0;
      *((_DWORD *)v50 + 4) = 39;
    }
    else
    {
      v50 = 0;
    }
    LODWORD(v491) = 14;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v49, &v491) = v50;
    v51 = operator new(0x14u);
    v53 = v51;
    if ( v51 )
    {
      *v51 = 2;
      v51[1] = 1;
      v51[2] = 80;
      *((_WORD *)v51 + 6) = 0;
      v51[4] = 39;
    }
    else
    {
      v53 = 0;
    }
    LODWORD(v491) = 15;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v52, &v491) = v53;
    v54 = operator new(0x14u);
    v56 = v54;
    if ( v54 )
    {
      *v54 = 2;
      v54[1] = 1;
      v54[2] = 16;
      *((_WORD *)v54 + 6) = 0;
      v54[4] = 39;
    }
    else
    {
      v56 = 0;
    }
    LODWORD(v491) = 16;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v55, &v491) = v56;
    v57 = operator new(0x14u);
    v59 = v57;
    if ( v57 )
    {
      *v57 = 2;
      v57[1] = 1;
      v57[2] = 8;
      *((_WORD *)v57 + 6) = 1;
      v57[4] = 39;
    }
    else
    {
      v59 = 0;
    }
    LODWORD(v491) = 17;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v58, &v491) = v59;
    v60 = operator new(0x14u);
    v62 = v60;
    if ( v60 )
    {
      *v60 = 2;
      v60[1] = 1;
      v60[2] = 6;
      *((_WORD *)v60 + 6) = 0;
      v60[4] = 39;
    }
    else
    {
      v62 = 0;
    }
    LODWORD(v491) = 18;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v61, &v491) = v62;
    v64 = operator new(0x14u);
    if ( v64 )
    {
      *(_QWORD *)v64 = 2;
      v64[2] = 64;
      *((_WORD *)v64 + 6) = 0;
      v64[4] = 39;
    }
    else
    {
      v64 = 0;
    }
    LODWORD(v491) = 19;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v63, &v491) = v64;
    v65 = operator new(0x14u);
    v67 = v65;
    if ( v65 )
    {
      *v65 = 2;
      v65[1] = 1;
      v65[2] = 16;
      *((_WORD *)v65 + 6) = 0;
      v65[4] = 39;
    }
    else
    {
      v67 = 0;
    }
    LODWORD(v491) = 20;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v66, &v491) = v67;
    v69 = operator new(0x14u);
    if ( v69 )
    {
      *(_QWORD *)v69 = 2;
      v69[2] = 58;
      *((_WORD *)v69 + 6) = 0;
      v69[4] = 39;
    }
    else
    {
      v69 = 0;
    }
    LODWORD(v491) = 21;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v68, &v491) = v69;
    v71 = operator new(0x14u);
    if ( v71 )
    {
      *(_QWORD *)v71 = 2;
      v71[2] = 64;
      *((_WORD *)v71 + 6) = 0;
      v71[4] = 39;
    }
    else
    {
      v71 = 0;
    }
    LODWORD(v491) = 22;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v70, &v491) = v71;
    v72 = operator new(0x14u);
    v74 = v72;
    if ( v72 )
    {
      *v72 = 2;
      v72[1] = 1;
      v72[2] = 192;
      *((_WORD *)v72 + 6) = 0;
      v72[4] = 39;
    }
    else
    {
      v74 = 0;
    }
    LODWORD(v491) = 23;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v73, &v491) = v74;
    v75 = operator new(0x14u);
    v77 = v75;
    if ( v75 )
    {
      *v75 = 2;
      v75[1] = 1;
      v75[2] = 20;
      *((_WORD *)v75 + 6) = 0;
      v75[4] = 39;
    }
    else
    {
      v77 = 0;
    }
    LODWORD(v491) = 24;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v76, &v491) = v77;
    v79 = operator new(0x14u);
    if ( v79 )
    {
      *(_QWORD *)v79 = 2;
      v79[2] = 512;
      *((_WORD *)v79 + 6) = 0;
      v79[4] = 39;
    }
    else
    {
      v79 = 0;
    }
    LODWORD(v491) = 25;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v78, &v491) = v79;
    v80 = operator new(0x14u);
    v82 = v80;
    if ( v80 )
    {
      *v80 = 2;
      v80[1] = 1;
      v80[2] = 32;
      *((_WORD *)v80 + 6) = 0;
      v80[4] = 39;
    }
    else
    {
      v82 = 0;
    }
    LODWORD(v491) = 26;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v81, &v491) = v82;
    v84 = operator new(0x14u);
    if ( v84 )
    {
      *(_QWORD *)v84 = 2;
      v84[2] = 32;
      *((_WORD *)v84 + 6) = 0;
      v84[4] = 39;
    }
    else
    {
      v84 = 0;
    }
    LODWORD(v491) = 27;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v83, &v491) = v84;
    v86 = operator new(0x14u);
    if ( v86 )
    {
      *v86 = 0;
      v85 = 1;
      v86[1] = 1;
      v86[2] = 1;
      *((_WORD *)v86 + 6) = 0;
      v86[4] = 39;
    }
    else
    {
      v86 = 0;
    }
    LODWORD(v491) = 28;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v85, &v491) = v86;
    v88 = operator new(0x14u);
    if ( v88 )
    {
      *v88 = 0;
      v88[1] = 1;
      v88[2] = 2;
      *((_WORD *)v88 + 6) = 0;
      v88[4] = 39;
    }
    else
    {
      v88 = 0;
    }
    LODWORD(v491) = 29;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v87, &v491) = v88;
    v90 = operator new(0x14u);
    if ( v90 )
    {
      *v90 = 0;
      v90[1] = 1;
      v90[2] = 4;
      *((_WORD *)v90 + 6) = 0;
      v90[4] = 39;
    }
    else
    {
      v90 = 0;
    }
    LODWORD(v491) = 30;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v89, &v491) = v90;
    v91 = operator new(0x14u);
    v93 = v91;
    if ( v91 )
    {
      *v91 = 2;
      v91[1] = 1;
      v91[2] = 8;
      *((_WORD *)v91 + 6) = 0;
      v91[4] = 39;
    }
    else
    {
      v93 = 0;
    }
    LODWORD(v491) = 31;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v92, &v491) = v93;
    v95 = operator new(0x14u);
    if ( v95 )
    {
      *(_QWORD *)v95 = 1;
      v95[2] = 64;
      *((_WORD *)v95 + 6) = 0;
      v95[4] = 39;
    }
    else
    {
      v95 = 0;
    }
    LODWORD(v491) = 32;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v94, &v491) = v95;
    v97 = operator new(0x14u);
    if ( v97 )
    {
      *(_QWORD *)v97 = 1;
      v97[2] = 76;
      *((_WORD *)v97 + 6) = 0;
      v97[4] = 39;
    }
    else
    {
      v97 = 0;
    }
    LODWORD(v491) = 33;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v96, &v491) = v97;
    v98 = operator new(0x14u);
    v100 = v98;
    if ( v98 )
    {
      *v98 = 2;
      v98[1] = 1;
      v98[2] = 16;
      *((_WORD *)v98 + 6) = 0;
      v98[4] = 39;
    }
    else
    {
      v100 = 0;
    }
    LODWORD(v491) = 34;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v99, &v491) = v100;
    v102 = operator new(0x14u);
    if ( v102 )
    {
      *(_QWORD *)v102 = 2;
      v102[2] = 1024;
      *((_WORD *)v102 + 6) = 0;
      v102[4] = 39;
    }
    else
    {
      v102 = 0;
    }
    LODWORD(v491) = 35;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v101, &v491) = v102;
    v104 = (char *)operator new(0x14u);
    if ( v104 )
    {
      *(_DWORD *)v104 = 2;
      *(_QWORD *)(v104 + 4) = 2;
      *((_WORD *)v104 + 6) = 0;
      *((_DWORD *)v104 + 4) = 39;
    }
    else
    {
      v104 = 0;
    }
    LODWORD(v491) = 36;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v103, &v491) = v104;
    v106 = (char *)operator new(0x14u);
    if ( v106 )
    {
      *(_DWORD *)v106 = 2;
      *(_QWORD *)(v106 + 4) = 2;
      *((_WORD *)v106 + 6) = 0;
      *((_DWORD *)v106 + 4) = 39;
    }
    else
    {
      v106 = 0;
    }
    LODWORD(v491) = 37;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v105, &v491) = v106;
    v107 = operator new(0x14u);
    v109 = v107;
    if ( v107 )
    {
      *(_QWORD *)v107 = 2;
      v107[2] = 30;
      *((_WORD *)v107 + 6) = 256;
      v107[4] = 18;
    }
    else
    {
      v109 = 0;
    }
    LODWORD(v491) = 38;
    *(_QWORD *)std::map<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](v108, &v491) = v109;
    v110 = operator new(0x20u);
    v111 = v110;
    if ( v110 )
    {
      *v110 = 0;
      v110[1] = 4097;
      v110[2] = 29;
      *((_QWORD *)v110 + 2) = L"WCN_TYPE_AP_CHANNEL";
      *((_QWORD *)v110 + 3) = 131074;
    }
    else
    {
      v111 = 0;
    }
    LODWORD(v491) = 0;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 0,
                 &v491) = v111;
    LODWORD(v491) = 4097;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v112, &v491) = v111;
    v113 = operator new(0x20u);
    v115 = v113;
    if ( v113 )
    {
      *v113 = 1;
      v113[1] = 4098;
      v113[2] = 29;
      *((_QWORD *)v113 + 2) = L"WCN_TYPE_ASSOCIATION_STATE";
      *((_QWORD *)v113 + 3) = 131074;
    }
    LODWORD(v491) = 1;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v114,
                 &v491) = v113;
    LODWORD(v491) = 4098;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v116, &v491) = v115;
    v117 = operator new(0x20u);
    v119 = v117;
    if ( v117 )
    {
      *v117 = 2;
      v117[1] = 4099;
      v117[2] = 29;
      *((_QWORD *)v117 + 2) = L"WCN_TYPE_AUTHENTICATION_TYPE";
      *((_QWORD *)v117 + 3) = 131074;
    }
    LODWORD(v491) = 2;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v118,
                 &v491) = v117;
    LODWORD(v491) = 4099;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v120, &v491) = v119;
    v121 = operator new(0x20u);
    v123 = v121;
    if ( v121 )
    {
      *v121 = 3;
      v121[1] = 4100;
      v121[2] = 29;
      *((_QWORD *)v121 + 2) = L"WCN_TYPE_AUTHENTICATION_TYPE_FLAGS";
      *((_QWORD *)v121 + 3) = 131074;
    }
    LODWORD(v491) = 3;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v122,
                 &v491) = v121;
    LODWORD(v491) = 4100;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v124, &v491) = v123;
    v125 = operator new(0x20u);
    v127 = v125;
    if ( v125 )
    {
      *v125 = 4;
      v125[1] = 4101;
      v125[2] = 4;
      *((_QWORD *)v125 + 2) = L"WCN_TYPE_AUTHENTICATOR";
      *((_QWORD *)v125 + 3) = 131074;
    }
    LODWORD(v491) = 4;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v126,
                 &v491) = v125;
    LODWORD(v491) = 4101;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v128, &v491) = v127;
    v129 = operator new(0x20u);
    v131 = v129;
    if ( v129 )
    {
      *v129 = 5;
      v129[1] = 4104;
      v129[2] = 29;
      *((_QWORD *)v129 + 2) = L"WCN_TYPE_CONFIG_METHODS";
      *((_QWORD *)v129 + 3) = 131074;
    }
    LODWORD(v491) = 5;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v130,
                 &v491) = v129;
    LODWORD(v491) = 4104;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v132, &v491) = v131;
    v133 = operator new(0x20u);
    v135 = v133;
    if ( v133 )
    {
      *v133 = 6;
      v133[1] = 4105;
      v133[2] = 29;
      *((_QWORD *)v133 + 2) = L"WCN_TYPE_CONFIGURATION_ERROR";
      *((_QWORD *)v133 + 3) = 131074;
    }
    LODWORD(v491) = 6;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v134,
                 &v491) = v133;
    LODWORD(v491) = 4105;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v136, &v491) = v135;
    v137 = operator new(0x20u);
    v139 = v137;
    if ( v137 )
    {
      *v137 = 7;
      v137[1] = 4106;
      v137[2] = 32;
      *((_QWORD *)v137 + 2) = L"WCN_TYPE_CONFIRMATION_URL4";
      *((_QWORD *)v137 + 3) = 131074;
    }
    LODWORD(v491) = 7;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v138,
                 &v491) = v137;
    LODWORD(v491) = 4106;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v140, &v491) = v139;
    v141 = operator new(0x20u);
    v143 = v141;
    if ( v141 )
    {
      *v141 = 8;
      v141[1] = 4107;
      v141[2] = 33;
      *((_QWORD *)v141 + 2) = L"WCN_TYPE_CONFIRMATION_URL6";
      *((_QWORD *)v141 + 3) = 131074;
    }
    LODWORD(v491) = 8;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v142,
                 &v491) = v141;
    LODWORD(v491) = 4107;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v144, &v491) = v143;
    v145 = operator new(0x20u);
    v147 = v145;
    if ( v145 )
    {
      *v145 = 9;
      v145[1] = 4108;
      v145[2] = 28;
      *((_QWORD *)v145 + 2) = L"WCN_TYPE_CONNECTION_TYPE";
      *((_QWORD *)v145 + 3) = 131074;
    }
    LODWORD(v491) = 9;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v146,
                 &v491) = v145;
    LODWORD(v491) = 4108;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v148, &v491) = v147;
    v149 = operator new(0x20u);
    v151 = v149;
    if ( v149 )
    {
      *v149 = 10;
      v149[1] = 4109;
      v149[2] = 28;
      *((_QWORD *)v149 + 2) = L"WCN_TYPE_CONNECTION_TYPE_FLAGS";
      *((_QWORD *)v149 + 3) = 131074;
    }
    LODWORD(v491) = 10;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v150,
                 &v491) = v149;
    LODWORD(v491) = 4109;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v152, &v491) = v151;
    v153 = operator new(0x20u);
    v155 = v153;
    if ( v153 )
    {
      *v153 = 11;
      v153[1] = 4110;
      v153[2] = 6;
      *((_QWORD *)v153 + 2) = L"WCN_TYPE_CREDENTIAL";
      *((_QWORD *)v153 + 3) = 131074;
    }
    LODWORD(v491) = 11;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v154,
                 &v491) = v153;
    LODWORD(v491) = 4110;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v156, &v491) = v155;
    v157 = operator new(0x20u);
    v159 = v157;
    if ( v157 )
    {
      *(_DWORD *)v157 = 12;
      *(_QWORD *)((char *)v157 + 4) = 4113;
      v157[2] = L"WCN_TYPE_DEVICE_NAME";
      v157[3] = 131074;
    }
    LODWORD(v491) = 12;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v158,
                 &v491) = v157;
    LODWORD(v491) = 4113;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v160, &v491) = v159;
    v161 = operator new(0x20u);
    v163 = v161;
    if ( v161 )
    {
      *v161 = 13;
      v161[1] = 4114;
      v161[2] = 29;
      *((_QWORD *)v161 + 2) = L"WCN_TYPE_DEVICE_PASSWORD_ID";
      *((_QWORD *)v161 + 3) = 131074;
    }
    LODWORD(v491) = 13;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v162,
                 &v491) = v161;
    LODWORD(v491) = 4114;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v164, &v491) = v163;
    v165 = operator new(0x20u);
    v167 = v165;
    if ( v165 )
    {
      *v165 = 14;
      v165[1] = 4116;
      v165[2] = 12;
      *((_QWORD *)v165 + 2) = L"WCN_TYPE_E_HASH1";
      *((_QWORD *)v165 + 3) = 131074;
    }
    LODWORD(v491) = 14;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v166,
                 &v491) = v165;
    LODWORD(v491) = 4116;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v168, &v491) = v167;
    v169 = operator new(0x20u);
    v171 = v169;
    if ( v169 )
    {
      *v169 = 15;
      v169[1] = 4117;
      v169[2] = 12;
      *((_QWORD *)v169 + 2) = L"WCN_TYPE_E_HASH2";
      *((_QWORD *)v169 + 3) = 131074;
    }
    LODWORD(v491) = 15;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v170,
                 &v491) = v169;
    LODWORD(v491) = 4117;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v172, &v491) = v171;
    v173 = operator new(0x20u);
    v175 = v173;
    if ( v173 )
    {
      *v173 = 16;
      v173[1] = 4118;
      v173[2] = 20;
      *((_QWORD *)v173 + 2) = L"WCN_TYPE_E_SNONCE1";
      *((_QWORD *)v173 + 3) = 131074;
    }
    LODWORD(v491) = 16;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v174,
                 &v491) = v173;
    LODWORD(v491) = 4118;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v176, &v491) = v175;
    v177 = operator new(0x20u);
    v179 = v177;
    if ( v177 )
    {
      *v177 = 17;
      v177[1] = 4119;
      v177[2] = 20;
      *((_QWORD *)v177 + 2) = L"WCN_TYPE_E_SNONCE2";
      *((_QWORD *)v177 + 3) = 131074;
    }
    LODWORD(v491) = 17;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v178,
                 &v491) = v177;
    LODWORD(v491) = 4119;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v180, &v491) = v179;
    v181 = operator new(0x20u);
    v183 = v181;
    if ( v181 )
    {
      *v181 = 18;
      v181[1] = 4120;
      v181[2] = 11;
      *((_QWORD *)v181 + 2) = L"WCN_TYPE_ENCRYPTED_SETTINGS";
      *((_QWORD *)v181 + 3) = 131074;
    }
    LODWORD(v491) = 18;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v182,
                 &v491) = v181;
    LODWORD(v491) = 4120;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v184, &v491) = v183;
    v185 = operator new(0x20u);
    v187 = v185;
    if ( v185 )
    {
      *v185 = 19;
      v185[1] = 4111;
      v185[2] = 29;
      *((_QWORD *)v185 + 2) = L"WCN_TYPE_ENCRYPTION_TYPE";
      *((_QWORD *)v185 + 3) = 131074;
    }
    LODWORD(v491) = 19;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v186,
                 &v491) = v185;
    LODWORD(v491) = 4111;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v188, &v491) = v187;
    v189 = operator new(0x20u);
    v191 = v189;
    if ( v189 )
    {
      *v189 = 20;
      v189[1] = 4112;
      v189[2] = 29;
      *((_QWORD *)v189 + 2) = L"WCN_TYPE_ENCRYPTION_TYPE_FLAGS";
      *((_QWORD *)v189 + 3) = 131074;
    }
    LODWORD(v491) = 20;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v190,
                 &v491) = v189;
    LODWORD(v491) = 4112;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v192, &v491) = v191;
    v193 = operator new(0x20u);
    v195 = v193;
    if ( v193 )
    {
      *v193 = 21;
      v193[1] = 4122;
      v193[2] = 20;
      *((_QWORD *)v193 + 2) = L"WCN_TYPE_ENROLLEE_NONCE";
      *((_QWORD *)v193 + 3) = 131074;
    }
    LODWORD(v491) = 21;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v194,
                 &v491) = v193;
    LODWORD(v491) = 4122;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v196, &v491) = v195;
    v197 = operator new(0x20u);
    v199 = v197;
    if ( v197 )
    {
      *v197 = 22;
      v197[1] = 4123;
      v197[2] = 30;
      *((_QWORD *)v197 + 2) = L"WCN_TYPE_FEATURE_ID";
      *((_QWORD *)v197 + 3) = 131074;
    }
    LODWORD(v491) = 22;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v198,
                 &v491) = v197;
    LODWORD(v491) = 4123;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v200, &v491) = v199;
    v201 = operator new(0x20u);
    v203 = v201;
    if ( v201 )
    {
      *v201 = 23;
      v201[1] = 4124;
      v201[2] = 13;
      *((_QWORD *)v201 + 2) = L"WCN_TYPE_IDENTITY";
      *((_QWORD *)v201 + 3) = 131074;
    }
    LODWORD(v491) = 23;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v202,
                 &v491) = v201;
    LODWORD(v491) = 4124;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v204, &v491) = v203;
    v205 = operator new(0x20u);
    v207 = v205;
    if ( v205 )
    {
      *v205 = 24;
      v205[1] = 4125;
      v205[2] = 14;
      *((_QWORD *)v205 + 2) = L"WCN_TYPE_IDENTITY_PROOF";
      *((_QWORD *)v205 + 3) = 131074;
    }
    LODWORD(v491) = 24;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v206,
                 &v491) = v205;
    LODWORD(v491) = 4125;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v208, &v491) = v207;
    v209 = operator new(0x20u);
    v211 = v209;
    if ( v209 )
    {
      *v209 = 25;
      v209[1] = 4126;
      v209[2] = 17;
      *((_QWORD *)v209 + 2) = L"WCN_TYPE_KEY_WRAP_AUTHENTICATOR";
      *((_QWORD *)v209 + 3) = 131074;
    }
    LODWORD(v491) = 25;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v210,
                 &v491) = v209;
    LODWORD(v491) = 4126;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v212, &v491) = v211;
    v213 = operator new(0x20u);
    v215 = v213;
    if ( v213 )
    {
      *v213 = 26;
      v213[1] = 4127;
      v213[2] = 16;
      *((_QWORD *)v213 + 2) = L"WCN_TYPE_KEY_IDENTIFIER";
      *((_QWORD *)v213 + 3) = 131074;
    }
    LODWORD(v491) = 26;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v214,
                 &v491) = v213;
    LODWORD(v491) = 4127;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v216, &v491) = v215;
    v217 = operator new(0x20u);
    v219 = v217;
    if ( v217 )
    {
      *v217 = 27;
      v217[1] = 4128;
      v217[2] = 18;
      *((_QWORD *)v217 + 2) = L"WCN_TYPE_MAC_ADDRESS";
      *((_QWORD *)v217 + 3) = 131074;
    }
    LODWORD(v491) = 27;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v218,
                 &v491) = v217;
    LODWORD(v491) = 4128;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v220, &v491) = v219;
    v221 = operator new(0x20u);
    v223 = v221;
    if ( v221 )
    {
      *v221 = 28;
      v221[1] = 4129;
      v221[2] = 1;
      *((_QWORD *)v221 + 2) = L"WCN_TYPE_MANUFACTURER";
      *((_QWORD *)v221 + 3) = 131074;
    }
    LODWORD(v491) = 28;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v222,
                 &v491) = v221;
    LODWORD(v491) = 4129;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v224, &v491) = v223;
    v225 = operator new(0x20u);
    v227 = v225;
    if ( v225 )
    {
      *v225 = 29;
      v225[1] = 4130;
      v225[2] = 28;
      *((_QWORD *)v225 + 2) = L"WCN_TYPE_MESSAGE_TYPE";
      *((_QWORD *)v225 + 3) = 131074;
    }
    LODWORD(v491) = 29;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v226,
                 &v491) = v225;
    LODWORD(v491) = 4130;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v228, &v491) = v227;
    v229 = operator new(0x20u);
    v231 = v229;
    if ( v229 )
    {
      *(_DWORD *)v229 = 30;
      *(_QWORD *)((char *)v229 + 4) = 4131;
      v229[2] = L"WCN_TYPE_MODEL_NAME";
      v229[3] = 131074;
    }
    LODWORD(v491) = 30;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v230,
                 &v491) = v229;
    LODWORD(v491) = 4131;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v232, &v491) = v231;
    v233 = operator new(0x20u);
    v235 = v233;
    if ( v233 )
    {
      *(_DWORD *)v233 = 31;
      *(_QWORD *)((char *)v233 + 4) = 4132;
      v233[2] = L"WCN_TYPE_MODEL_NUMBER";
      v233[3] = 131074;
    }
    LODWORD(v491) = 31;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v234,
                 &v491) = v233;
    LODWORD(v491) = 4132;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v236, &v491) = v235;
    v237 = operator new(0x20u);
    v239 = v237;
    if ( v237 )
    {
      *v237 = 32;
      v237[1] = 4134;
      v237[2] = 28;
      *((_QWORD *)v237 + 2) = L"WCN_TYPE_NETWORK_INDEX";
      *((_QWORD *)v237 + 3) = 131074;
    }
    LODWORD(v491) = 32;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v238,
                 &v491) = v237;
    LODWORD(v491) = 4134;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v240, &v491) = v239;
    v241 = operator new(0x20u);
    v243 = v241;
    if ( v241 )
    {
      *v241 = 33;
      v241[1] = 4135;
      v241[2] = 19;
      *((_QWORD *)v241 + 2) = L"WCN_TYPE_NETWORK_KEY";
      *((_QWORD *)v241 + 3) = 131074;
    }
    LODWORD(v491) = 33;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v242,
                 &v491) = v241;
    LODWORD(v491) = 4135;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v244, &v491) = v243;
    v245 = operator new(0x20u);
    v247 = v245;
    if ( v245 )
    {
      *v245 = 34;
      v245[1] = 4136;
      v245[2] = 28;
      *((_QWORD *)v245 + 2) = L"WCN_TYPE_NETWORK_KEY_INDEX";
      *((_QWORD *)v245 + 3) = 131074;
    }
    LODWORD(v491) = 34;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v246,
                 &v491) = v245;
    LODWORD(v491) = 4136;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v248, &v491) = v247;
    v249 = operator new(0x20u);
    v251 = v249;
    if ( v249 )
    {
      *(_DWORD *)v249 = 35;
      *(_QWORD *)((char *)v249 + 4) = 4137;
      v249[2] = L"WCN_TYPE_NEW_DEVICE_NAME";
      v249[3] = 131074;
    }
    LODWORD(v491) = 35;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v250,
                 &v491) = v249;
    LODWORD(v491) = 4137;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v252, &v491) = v251;
    v253 = operator new(0x20u);
    v255 = v253;
    if ( v253 )
    {
      *v253 = 36;
      v253[1] = 4138;
      v253[2] = 22;
      *((_QWORD *)v253 + 2) = L"WCN_TYPE_NEW_PASSWORD";
      *((_QWORD *)v253 + 3) = 131074;
    }
    LODWORD(v491) = 36;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v254,
                 &v491) = v253;
    LODWORD(v491) = 4138;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v256, &v491) = v255;
    v257 = operator new(0x20u);
    v259 = v257;
    if ( v257 )
    {
      *v257 = 37;
      v257[1] = 4140;
      v257[2] = 21;
      *((_QWORD *)v257 + 2) = L"WCN_TYPE_OOB_DEVICE_PASSWORD";
      *((_QWORD *)v257 + 3) = 131074;
    }
    LODWORD(v491) = 37;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v258,
                 &v491) = v257;
    LODWORD(v491) = 4140;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v260, &v491) = v259;
    v261 = operator new(0x20u);
    v263 = v261;
    if ( v261 )
    {
      *v261 = 38;
      v261[1] = 4141;
      v261[2] = 30;
      *((_QWORD *)v261 + 2) = L"WCN_TYPE_OS_VERSION";
      *((_QWORD *)v261 + 3) = 131074;
    }
    LODWORD(v491) = 38;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v262,
                 &v491) = v261;
    LODWORD(v491) = 4141;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v264, &v491) = v263;
    v265 = operator new(0x20u);
    v267 = v265;
    if ( v265 )
    {
      *v265 = 39;
      v265[1] = 4143;
      v265[2] = 28;
      *((_QWORD *)v265 + 2) = L"WCN_TYPE_POWER_LEVEL";
      *((_QWORD *)v265 + 3) = 131074;
    }
    LODWORD(v491) = 39;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v266,
                 &v491) = v265;
    LODWORD(v491) = 4143;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v268, &v491) = v267;
    v269 = operator new(0x20u);
    v271 = v269;
    if ( v269 )
    {
      *v269 = 40;
      v269[1] = 4144;
      v269[2] = 28;
      *((_QWORD *)v269 + 2) = L"WCN_TYPE_PSK_CURRENT";
      *((_QWORD *)v269 + 3) = 131074;
    }
    else
    {
      v271 = 0;
    }
    LODWORD(v491) = 40;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v270,
                 &v491) = v271;
    LODWORD(v491) = 4144;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v272, &v491) = v271;
    v273 = operator new(0x20u);
    v275 = v273;
    if ( v273 )
    {
      *v273 = 41;
      v273[1] = 4145;
      v273[2] = 28;
      *((_QWORD *)v273 + 2) = L"WCN_TYPE_PSK_MAX";
      *((_QWORD *)v273 + 3) = 131074;
    }
    else
    {
      v275 = 0;
    }
    LODWORD(v491) = 41;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v274,
                 &v491) = v275;
    LODWORD(v491) = 4145;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v276, &v491) = v275;
    v277 = operator new(0x20u);
    v279 = v277;
    if ( v277 )
    {
      *v277 = 42;
      v277[1] = 4146;
      v277[2] = 23;
      *((_QWORD *)v277 + 2) = L"WCN_TYPE_PUBLIC_KEY";
      *((_QWORD *)v277 + 3) = 131074;
    }
    else
    {
      v279 = 0;
    }
    LODWORD(v491) = 42;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v278,
                 &v491) = v279;
    LODWORD(v491) = 4146;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v280, &v491) = v279;
    v281 = operator new(0x20u);
    v283 = v281;
    if ( v281 )
    {
      *v281 = 43;
      v281[1] = 4147;
      v281[2] = 5;
      *((_QWORD *)v281 + 2) = L"WCN_TYPE_RADIO_ENABLED";
      *((_QWORD *)v281 + 3) = 131074;
    }
    else
    {
      v283 = 0;
    }
    LODWORD(v491) = 43;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v282,
                 &v491) = v283;
    LODWORD(v491) = 4147;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v284, &v491) = v283;
    v285 = operator new(0x20u);
    v287 = v285;
    if ( v285 )
    {
      *v285 = 44;
      v285[1] = 4148;
      v285[2] = 5;
      *((_QWORD *)v285 + 2) = L"WCN_TYPE_REBOOT";
      *((_QWORD *)v285 + 3) = 131074;
    }
    else
    {
      v287 = 0;
    }
    LODWORD(v491) = 44;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v286,
                 &v491) = v287;
    LODWORD(v491) = 4148;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v288, &v491) = v287;
    v289 = operator new(0x20u);
    v291 = v289;
    if ( v289 )
    {
      *v289 = 45;
      v289[1] = 4149;
      v289[2] = 28;
      *((_QWORD *)v289 + 2) = L"WCN_TYPE_REGISTRAR_CURRENT";
      *((_QWORD *)v289 + 3) = 131074;
    }
    else
    {
      v291 = 0;
    }
    LODWORD(v491) = 45;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v290,
                 &v491) = v291;
    LODWORD(v491) = 4149;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v292, &v491) = v291;
    v293 = operator new(0x20u);
    v295 = v293;
    if ( v293 )
    {
      *v293 = 46;
      v293[1] = 4150;
      v293[2] = 5;
      *((_QWORD *)v293 + 2) = L"WCN_TYPE_REGISTRAR_ESTABLISHED";
      *((_QWORD *)v293 + 3) = 131074;
    }
    else
    {
      v295 = 0;
    }
    LODWORD(v491) = 46;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v294,
                 &v491) = v295;
    LODWORD(v491) = 4150;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v296, &v491) = v295;
    v297 = operator new(0x20u);
    v299 = v297;
    if ( v297 )
    {
      *v297 = 47;
      v297[1] = 4151;
      v297[2] = 25;
      *((_QWORD *)v297 + 2) = L"WCN_TYPE_REGISTRAR_LIST";
      *((_QWORD *)v297 + 3) = 131074;
    }
    else
    {
      v299 = 0;
    }
    LODWORD(v491) = 47;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v298,
                 &v491) = v299;
    LODWORD(v491) = 4151;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v300, &v491) = v299;
    v301 = operator new(0x20u);
    v303 = v301;
    if ( v301 )
    {
      *v301 = 48;
      v301[1] = 4152;
      v301[2] = 28;
      *((_QWORD *)v301 + 2) = L"WCN_TYPE_REGISTRAR_MAX";
      *((_QWORD *)v301 + 3) = 131074;
    }
    else
    {
      v303 = 0;
    }
    LODWORD(v491) = 48;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v302,
                 &v491) = v303;
    LODWORD(v491) = 4152;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v304, &v491) = v303;
    v305 = operator new(0x20u);
    v307 = v305;
    if ( v305 )
    {
      *v305 = 49;
      v305[1] = 4153;
      v305[2] = 20;
      *((_QWORD *)v305 + 2) = L"WCN_TYPE_REGISTRAR_NONCE";
      *((_QWORD *)v305 + 3) = 131074;
    }
    else
    {
      v307 = 0;
    }
    LODWORD(v491) = 49;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v306,
                 &v491) = v307;
    LODWORD(v491) = 4153;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v308, &v491) = v307;
    v309 = operator new(0x20u);
    v311 = v309;
    if ( v309 )
    {
      *v309 = 50;
      v309[1] = 4154;
      v309[2] = 28;
      *((_QWORD *)v309 + 2) = L"WCN_TYPE_REQUEST_TYPE";
      *((_QWORD *)v309 + 3) = 131074;
    }
    else
    {
      v311 = 0;
    }
    LODWORD(v491) = 50;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v310,
                 &v491) = v311;
    LODWORD(v491) = 4154;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v312, &v491) = v311;
    v313 = operator new(0x20u);
    v315 = v313;
    if ( v313 )
    {
      *v313 = 51;
      v313[1] = 4155;
      v313[2] = 28;
      *((_QWORD *)v313 + 2) = L"WCN_TYPE_RESPONSE_TYPE";
      *((_QWORD *)v313 + 3) = 131074;
    }
    else
    {
      v315 = 0;
    }
    LODWORD(v491) = 51;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v314,
                 &v491) = v315;
    LODWORD(v491) = 4155;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v316, &v491) = v315;
    v317 = operator new(0x20u);
    v319 = v317;
    if ( v317 )
    {
      *v317 = 52;
      v317[1] = 4156;
      v317[2] = 28;
      *((_QWORD *)v317 + 2) = L"WCN_TYPE_RF_BANDS";
      *((_QWORD *)v317 + 3) = 131074;
    }
    else
    {
      v319 = 0;
    }
    LODWORD(v491) = 52;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v318,
                 &v491) = v319;
    LODWORD(v491) = 4156;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v320, &v491) = v319;
    v321 = operator new(0x20u);
    v323 = v321;
    if ( v321 )
    {
      *v321 = 53;
      v321[1] = 4157;
      v321[2] = 12;
      *((_QWORD *)v321 + 2) = L"WCN_TYPE_R_HASH1";
      *((_QWORD *)v321 + 3) = 131074;
    }
    else
    {
      v323 = 0;
    }
    LODWORD(v491) = 53;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v322,
                 &v491) = v323;
    LODWORD(v491) = 4157;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v324, &v491) = v323;
    v325 = operator new(0x20u);
    v327 = v325;
    if ( v325 )
    {
      *v325 = 54;
      v325[1] = 4158;
      v325[2] = 12;
      *((_QWORD *)v325 + 2) = L"WCN_TYPE_R_HASH2";
      *((_QWORD *)v325 + 3) = 131074;
    }
    else
    {
      v327 = 0;
    }
    LODWORD(v491) = 54;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v326,
                 &v491) = v327;
    LODWORD(v491) = 4158;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v328, &v491) = v327;
    v329 = operator new(0x20u);
    v331 = v329;
    if ( v329 )
    {
      *v329 = 55;
      v329[1] = 4159;
      v329[2] = 20;
      *((_QWORD *)v329 + 2) = L"WCN_TYPE_R_SNONCE1";
      *((_QWORD *)v329 + 3) = 131074;
    }
    else
    {
      v331 = 0;
    }
    LODWORD(v491) = 55;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v330,
                 &v491) = v331;
    LODWORD(v491) = 4159;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v332, &v491) = v331;
    v333 = operator new(0x20u);
    v335 = v333;
    if ( v333 )
    {
      *v333 = 56;
      v333[1] = 4160;
      v333[2] = 20;
      *((_QWORD *)v333 + 2) = L"WCN_TYPE_R_SNONCE2";
      *((_QWORD *)v333 + 3) = 131074;
    }
    else
    {
      v335 = 0;
    }
    LODWORD(v491) = 56;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v334,
                 &v491) = v335;
    LODWORD(v491) = 4160;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v336, &v491) = v335;
    v337 = operator new(0x20u);
    v339 = v337;
    if ( v337 )
    {
      *v337 = 57;
      v337[1] = 4161;
      v337[2] = 5;
      *((_QWORD *)v337 + 2) = L"WCN_TYPE_SELECTED_REGISTRAR";
      *((_QWORD *)v337 + 3) = 131074;
    }
    else
    {
      v339 = 0;
    }
    LODWORD(v491) = 57;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v338,
                 &v491) = v339;
    LODWORD(v491) = 4161;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v340, &v491) = v339;
    v341 = operator new(0x20u);
    v343 = v341;
    if ( v341 )
    {
      *(_DWORD *)v341 = 58;
      *(_QWORD *)((char *)v341 + 4) = 4162;
      v341[2] = L"WCN_TYPE_SERIAL_NUMBER";
      v341[3] = 131074;
    }
    else
    {
      v343 = 0;
    }
    LODWORD(v491) = 58;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v342,
                 &v491) = v343;
    LODWORD(v491) = 4162;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v344, &v491) = v343;
    v345 = operator new(0x20u);
    v347 = v345;
    if ( v345 )
    {
      *v345 = 59;
      v345[1] = 4164;
      v345[2] = 28;
      *((_QWORD *)v345 + 2) = L"WCN_TYPE_WI_FI_PROTECTED_SETUP_STATE";
      *((_QWORD *)v345 + 3) = 131074;
    }
    else
    {
      v347 = 0;
    }
    LODWORD(v491) = 59;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v346,
                 &v491) = v347;
    LODWORD(v491) = 4164;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v348, &v491) = v347;
    v349 = operator new(0x20u);
    v351 = v349;
    if ( v349 )
    {
      *v349 = 60;
      v349[1] = 4165;
      v349[2] = 27;
      *((_QWORD *)v349 + 2) = L"WCN_TYPE_SSID";
      *((_QWORD *)v349 + 3) = 131074;
    }
    else
    {
      v351 = 0;
    }
    LODWORD(v491) = 60;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v350,
                 &v491) = v351;
    LODWORD(v491) = 4165;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v352, &v491) = v351;
    v353 = operator new(0x20u);
    v355 = v353;
    if ( v353 )
    {
      *v353 = 61;
      v353[1] = 4166;
      v353[2] = 28;
      *((_QWORD *)v353 + 2) = L"WCN_TYPE_TOTAL_NETWORKS";
      *((_QWORD *)v353 + 3) = 131074;
    }
    else
    {
      v355 = 0;
    }
    LODWORD(v491) = 61;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v354,
                 &v491) = v355;
    LODWORD(v491) = 4166;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v356, &v491) = v355;
    v357 = operator new(0x20u);
    v359 = v357;
    if ( v357 )
    {
      *v357 = 62;
      v357[1] = 4167;
      v357[2] = 34;
      *((_QWORD *)v357 + 2) = L"WCN_TYPE_UUID_E";
      *((_QWORD *)v357 + 3) = 131074;
    }
    else
    {
      v359 = 0;
    }
    LODWORD(v491) = 62;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v358,
                 &v491) = v359;
    LODWORD(v491) = 4167;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v360, &v491) = v359;
    v361 = operator new(0x20u);
    v363 = v361;
    if ( v361 )
    {
      *v361 = 63;
      v361[1] = 4168;
      v361[2] = 34;
      *((_QWORD *)v361 + 2) = L"WCN_TYPE_UUID_R";
      *((_QWORD *)v361 + 3) = 131074;
    }
    else
    {
      v363 = 0;
    }
    LODWORD(v491) = 63;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v362,
                 &v491) = v363;
    LODWORD(v491) = 4168;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v364, &v491) = v363;
    v365 = operator new(0x20u);
    v367 = v365;
    if ( v365 )
    {
      *v365 = 64;
      v365[1] = 4169;
      v365[2] = 35;
      *((_QWORD *)v365 + 2) = L"WCN_TYPE_VENDOR_EXTENSION";
      *((_QWORD *)v365 + 3) = 131074;
    }
    else
    {
      v367 = 0;
    }
    LODWORD(v491) = 64;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v366,
                 &v491) = v367;
    LODWORD(v491) = 4169;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v368, &v491) = v367;
    v369 = operator new(0x20u);
    v371 = v369;
    if ( v369 )
    {
      *v369 = 65;
      v369[1] = 4170;
      v369[2] = 28;
      *((_QWORD *)v369 + 2) = L"WCN_TYPE_VERSION";
      *((_QWORD *)v369 + 3) = 131074;
    }
    else
    {
      v371 = 0;
    }
    LODWORD(v491) = 65;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v370,
                 &v491) = v371;
    LODWORD(v491) = 4170;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v372, &v491) = v371;
    v373 = operator new(0x20u);
    v375 = v373;
    if ( v373 )
    {
      *v373 = 66;
      v373[1] = 4171;
      v373[2] = 36;
      *((_QWORD *)v373 + 2) = L"WCN_TYPE_X_509_CERTIFICATE_REQUEST";
      *((_QWORD *)v373 + 3) = 131074;
    }
    else
    {
      v375 = 0;
    }
    LODWORD(v491) = 66;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v374,
                 &v491) = v375;
    LODWORD(v491) = 4171;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v376, &v491) = v375;
    v377 = operator new(0x20u);
    v379 = v377;
    if ( v377 )
    {
      *v377 = 67;
      v377[1] = 4172;
      v377[2] = 37;
      *((_QWORD *)v377 + 2) = L"WCN_TYPE_X_509_CERTIFICATE";
      *((_QWORD *)v377 + 3) = 131074;
    }
    else
    {
      v379 = 0;
    }
    LODWORD(v491) = 67;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v378,
                 &v491) = v379;
    LODWORD(v491) = 4172;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v380, &v491) = v379;
    v381 = operator new(0x20u);
    v383 = v381;
    if ( v381 )
    {
      *v381 = 68;
      v381[1] = 4173;
      v381[2] = 9;
      *((_QWORD *)v381 + 2) = L"WCN_TYPE_EAP_IDENTITY";
      *((_QWORD *)v381 + 3) = 131074;
    }
    else
    {
      v383 = 0;
    }
    LODWORD(v491) = 68;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v382,
                 &v491) = v383;
    LODWORD(v491) = 4173;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v384, &v491) = v383;
    v385 = operator new(0x20u);
    v387 = v385;
    if ( v385 )
    {
      *v385 = 69;
      v385[1] = 4174;
      v385[2] = 31;
      *((_QWORD *)v385 + 2) = L"WCN_TYPE_MESSAGE_COUNTER";
      *((_QWORD *)v385 + 3) = 131074;
    }
    else
    {
      v387 = 0;
    }
    LODWORD(v491) = 69;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v386,
                 &v491) = v387;
    LODWORD(v491) = 4174;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v388, &v491) = v387;
    v389 = operator new(0x20u);
    v391 = v389;
    if ( v389 )
    {
      *v389 = 70;
      v389[1] = 4175;
      v389[2] = 24;
      *((_QWORD *)v389 + 2) = L"WCN_TYPE_PUBLIC_KEY_HASH";
      *((_QWORD *)v389 + 3) = 131074;
    }
    else
    {
      v391 = 0;
    }
    LODWORD(v491) = 70;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v390,
                 &v491) = v391;
    LODWORD(v491) = 4175;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v392, &v491) = v391;
    v393 = operator new(0x20u);
    v395 = v393;
    if ( v393 )
    {
      *v393 = 71;
      v393[1] = 4176;
      v393[2] = 26;
      *((_QWORD *)v393 + 2) = L"WCN_TYPE_REKEY_KEY";
      *((_QWORD *)v393 + 3) = 131074;
    }
    else
    {
      v395 = 0;
    }
    LODWORD(v491) = 71;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v394,
                 &v491) = v395;
    LODWORD(v491) = 4176;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v396, &v491) = v395;
    v397 = operator new(0x20u);
    v399 = v397;
    if ( v397 )
    {
      *v397 = 72;
      v397[1] = 4177;
      v397[2] = 30;
      *((_QWORD *)v397 + 2) = L"WCN_TYPE_KEY_LIFETIME";
      *((_QWORD *)v397 + 3) = 131074;
    }
    else
    {
      v399 = 0;
    }
    LODWORD(v491) = 72;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v398,
                 &v491) = v399;
    LODWORD(v491) = 4177;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v400, &v491) = v399;
    v401 = operator new(0x20u);
    v403 = v401;
    if ( v401 )
    {
      *v401 = 73;
      v401[1] = 4178;
      v401[2] = 29;
      *((_QWORD *)v401 + 2) = L"WCN_TYPE_PERMITTED_CONFIG_METHODS";
      *((_QWORD *)v401 + 3) = 131074;
    }
    else
    {
      v403 = 0;
    }
    LODWORD(v491) = 73;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v402,
                 &v491) = v403;
    LODWORD(v491) = 4178;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v404, &v491) = v403;
    v405 = operator new(0x20u);
    v407 = v405;
    if ( v405 )
    {
      *v405 = 74;
      v405[1] = 4179;
      v405[2] = 29;
      *((_QWORD *)v405 + 2) = L"WCN_TYPE_SELECTED_REGISTRAR_CONFIG_METHODS";
      *((_QWORD *)v405 + 3) = 131074;
    }
    else
    {
      v407 = 0;
    }
    LODWORD(v491) = 74;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v406,
                 &v491) = v407;
    LODWORD(v491) = 4179;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v408, &v491) = v407;
    v409 = operator new(0x20u);
    v411 = v409;
    if ( v409 )
    {
      *v409 = 75;
      v409[1] = 4180;
      v409[2] = 7;
      *((_QWORD *)v409 + 2) = L"WCN_TYPE_PRIMARY_DEVICE_TYPE";
      *((_QWORD *)v409 + 3) = 131074;
    }
    else
    {
      v411 = 0;
    }
    LODWORD(v491) = 75;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v410,
                 &v491) = v411;
    LODWORD(v491) = 4180;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v412, &v491) = v411;
    v413 = operator new(0x20u);
    v415 = v413;
    if ( v413 )
    {
      *v413 = 76;
      v413[1] = 4181;
      v413[2] = 8;
      *((_QWORD *)v413 + 2) = L"WCN_TYPE_SECONDARY_DEVICE_TYPE_LIST";
      *((_QWORD *)v413 + 3) = 131074;
    }
    else
    {
      v415 = 0;
    }
    LODWORD(v491) = 76;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v414,
                 &v491) = v415;
    LODWORD(v491) = 4181;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v416, &v491) = v415;
    v417 = operator new(0x20u);
    v419 = v417;
    if ( v417 )
    {
      *v417 = 77;
      v417[1] = 4182;
      v417[2] = 5;
      *((_QWORD *)v417 + 2) = L"WCN_TYPE_PORTABLE_DEVICE";
      *((_QWORD *)v417 + 3) = 131074;
    }
    else
    {
      v419 = 0;
    }
    LODWORD(v491) = 77;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v418,
                 &v491) = v419;
    LODWORD(v491) = 4182;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v420, &v491) = v419;
    v421 = operator new(0x20u);
    v423 = v421;
    if ( v421 )
    {
      *v421 = 78;
      v421[1] = 4183;
      v421[2] = 5;
      *((_QWORD *)v421 + 2) = L"WCN_TYPE_AP_SETUP_LOCKED";
      *((_QWORD *)v421 + 3) = 131074;
    }
    else
    {
      v423 = 0;
    }
    LODWORD(v491) = 78;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v422,
                 &v491) = v423;
    LODWORD(v491) = 4183;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v424, &v491) = v423;
    v425 = operator new(0x20u);
    v427 = v425;
    if ( v425 )
    {
      *v425 = 79;
      v425[1] = 4184;
      v425[2] = 2;
      *((_QWORD *)v425 + 2) = L"WCN_TYPE_APPLICATION_EXTENSION";
      *((_QWORD *)v425 + 3) = 131074;
    }
    else
    {
      v427 = 0;
    }
    LODWORD(v491) = 79;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v426,
                 &v491) = v427;
    LODWORD(v491) = 4184;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v428, &v491) = v427;
    v429 = operator new(0x20u);
    v431 = v429;
    if ( v429 )
    {
      *v429 = 80;
      v429[1] = 4185;
      v429[2] = 10;
      *((_QWORD *)v429 + 2) = L"WCN_TYPE_EAP_TYPE";
      *((_QWORD *)v429 + 3) = 131074;
    }
    else
    {
      v431 = 0;
    }
    LODWORD(v491) = 80;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v430,
                 &v491) = v431;
    LODWORD(v491) = 4185;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v432, &v491) = v431;
    v433 = operator new(0x20u);
    v435 = v433;
    if ( v433 )
    {
      *v433 = 81;
      v433[1] = 4192;
      v433[2] = 15;
      *((_QWORD *)v433 + 2) = L"WCN_TYPE_INITIALIZATION_VECTOR";
      *((_QWORD *)v433 + 3) = 131074;
    }
    else
    {
      v435 = 0;
    }
    LODWORD(v491) = 81;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v434,
                 &v491) = v435;
    LODWORD(v491) = 4192;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v436, &v491) = v435;
    v437 = operator new(0x20u);
    v439 = v437;
    if ( v437 )
    {
      *v437 = 82;
      v437[1] = 4193;
      v437[2] = 5;
      *((_QWORD *)v437 + 2) = L"WCN_TYPE_KEY_PROVIDED_AUTOMATICALLY";
      *((_QWORD *)v437 + 3) = 131074;
    }
    else
    {
      v439 = 0;
    }
    LODWORD(v491) = 82;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v438,
                 &v491) = v439;
    LODWORD(v491) = 4193;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v440, &v491) = v439;
    v441 = operator new(0x20u);
    v443 = v441;
    if ( v441 )
    {
      *v441 = 83;
      v441[1] = 4194;
      v441[2] = 5;
      *((_QWORD *)v441 + 2) = L"WCN_TYPE_802_1X_ENABLED";
      *((_QWORD *)v441 + 3) = 131074;
    }
    else
    {
      v443 = 0;
    }
    LODWORD(v491) = 83;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v442,
                 &v491) = v443;
    LODWORD(v491) = 4194;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v444, &v491) = v443;
    v445 = operator new(0x20u);
    v447 = v445;
    if ( v445 )
    {
      *v445 = 84;
      v445[1] = 4195;
      v445[2] = 3;
      *((_QWORD *)v445 + 2) = L"WCN_TYPE_APPSESSIONKEY";
      *((_QWORD *)v445 + 3) = 131074;
    }
    else
    {
      v447 = 0;
    }
    LODWORD(v491) = 84;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v446,
                 &v491) = v447;
    LODWORD(v491) = 4195;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v448, &v491) = v447;
    v449 = operator new(0x20u);
    v451 = v449;
    if ( v449 )
    {
      *v449 = 85;
      v449[1] = 4196;
      v449[2] = 28;
      *((_QWORD *)v449 + 2) = L"WCN_TYPE_WEPTRANSMITKEY";
      *((_QWORD *)v449 + 3) = 131074;
    }
    else
    {
      v451 = 0;
    }
    LODWORD(v491) = 85;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v450,
                 &v491) = v451;
    LODWORD(v491) = 4196;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v452, &v491) = v451;
    v453 = operator new(0x20u);
    v455 = v453;
    if ( v453 )
    {
      *(_QWORD *)v453 = 86;
      v453[2] = 34;
      *((_QWORD *)v453 + 2) = L"WCN_TYPE_UUID";
      *((_QWORD *)v453 + 3) = 131074;
    }
    else
    {
      v455 = 0;
    }
    LODWORD(v491) = 86;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v454,
                 &v491) = v455;
    v456 = operator new(0x20u);
    v458 = v456;
    if ( v456 )
    {
      *(_QWORD *)v456 = 87;
      v456[2] = 30;
      *((_QWORD *)v456 + 2) = L"WCN_TYPE_PRIMARY_DEVICE_TYPE_CATEGORY";
      *((_QWORD *)v456 + 3) = 131074;
    }
    else
    {
      v458 = 0;
    }
    LODWORD(v491) = 87;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v457,
                 &v491) = v458;
    v459 = operator new(0x20u);
    v461 = v459;
    if ( v459 )
    {
      *(_QWORD *)v459 = 88;
      v459[2] = 30;
      *((_QWORD *)v459 + 2) = L"WCN_TYPE_PRIMARY_DEVICE_TYPE_SUBCATEGORY_OUI";
      *((_QWORD *)v459 + 3) = 131074;
    }
    else
    {
      v461 = 0;
    }
    LODWORD(v491) = 88;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v460,
                 &v491) = v461;
    v462 = operator new(0x20u);
    v464 = v462;
    if ( v462 )
    {
      *(_QWORD *)v462 = 89;
      v462[2] = 30;
      *((_QWORD *)v462 + 2) = L"WCN_TYPE_PRIMARY_DEVICE_TYPE_SUBCATEGORY";
      *((_QWORD *)v462 + 3) = 131074;
    }
    else
    {
      v464 = 0;
    }
    LODWORD(v491) = 89;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v463,
                 &v491) = v464;
    v465 = operator new(0x20u);
    v467 = v465;
    if ( v465 )
    {
      *(_QWORD *)v465 = 90;
      v465[2] = 27;
      *((_QWORD *)v465 + 2) = L"WCN_TYPE_CURRENT_SSID";
      *((_QWORD *)v465 + 3) = 131074;
    }
    else
    {
      v467 = 0;
    }
    LODWORD(v491) = 90;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v466,
                 &v491) = v467;
    v468 = operator new(0x20u);
    v470 = v468;
    if ( v468 )
    {
      *(_QWORD *)v468 = 91;
      v468[2] = 18;
      *((_QWORD *)v468 + 2) = L"WCN_TYPE_BSSID";
      *((_QWORD *)v468 + 3) = 131074;
    }
    else
    {
      v470 = 0;
    }
    LODWORD(v491) = 91;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v469,
                 &v491) = v470;
    v471 = operator new(0x20u);
    v473 = v471;
    if ( v471 )
    {
      *(_QWORD *)v471 = 92;
      v471[2] = 18;
      *((_QWORD *)v471 + 2) = L"WCN_TYPE_DOT11_MAC_ADDRESS";
      *((_QWORD *)v471 + 3) = 131074;
    }
    else
    {
      v473 = 0;
    }
    LODWORD(v491) = 92;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v472,
                 &v491) = v473;
    v474 = operator new(0x20u);
    v476 = v474;
    if ( v474 )
    {
      *v474 = 99;
      v474[1] = 4169;
      v474[2] = 35;
      *((_QWORD *)v474 + 2) = L"WCN_TYPE_VENDOR_EXTENSION_WFA";
      *((_QWORD *)v474 + 3) = 131074;
    }
    else
    {
      v476 = 0;
    }
    LODWORD(v491) = 99;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v475,
                 &v491) = v476;
    v478 = operator new(0x20u);
    if ( v478 )
    {
      v477 = 1;
      *(_QWORD *)v478 = 98;
      v478[2] = 28;
      *((_QWORD *)v478 + 2) = L"WCN_TYPE_VERSION2";
      *((_WORD *)v478 + 12) = 1;
      *((_WORD *)v478 + 13) = 1;
      v478[7] = 14122;
    }
    LODWORD(v491) = 98;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v477,
                 &v491) = v478;
    LODWORD(v491) = 3615232;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](8, &v491) = v478;
    v480 = operator new(0x20u);
    if ( v480 )
    {
      v479 = 1;
      *v480 = 93;
      v480[1] = 1;
      v480[2] = 38;
      *((_QWORD *)v480 + 2) = L"WCN_TYPE_AUTHORIZED_MACS";
      *((_WORD *)v480 + 12) = 1;
      *((_WORD *)v480 + 13) = 1;
      v480[7] = 14122;
    }
    LODWORD(v491) = 93;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v479,
                 &v491) = v480;
    LODWORD(v491) = 3615233;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](8, &v491) = v480;
    v482 = operator new(0x20u);
    if ( v482 )
    {
      v481 = 1;
      *v482 = 94;
      v482[1] = 2;
      v482[2] = 5;
      *((_QWORD *)v482 + 2) = L"WCN_TYPE_NETWORK_KEY_SHAREABLE";
      *((_WORD *)v482 + 12) = 1;
      *((_WORD *)v482 + 13) = 1;
      v482[7] = 14122;
    }
    LODWORD(v491) = 94;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v481,
                 &v491) = v482;
    LODWORD(v491) = 3615234;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](8, &v491) = v482;
    v484 = operator new(0x20u);
    if ( v484 )
    {
      v483 = 1;
      *v484 = 95;
      v484[1] = 3;
      v484[2] = 5;
      *((_QWORD *)v484 + 2) = L"WCN_TYPE_REQUEST_TO_ENROLL";
      *((_WORD *)v484 + 12) = 1;
      *((_WORD *)v484 + 13) = 1;
      v484[7] = 14122;
    }
    LODWORD(v491) = 95;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v483,
                 &v491) = v484;
    LODWORD(v491) = 3615235;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](8, &v491) = v484;
    v486 = operator new(0x20u);
    if ( v486 )
    {
      v485 = 1;
      *v486 = 97;
      v486[1] = 4;
      v486[2] = 28;
      *((_QWORD *)v486 + 2) = L"WCN_TYPE_SETTINGS_DELAY_TIME";
      *((_WORD *)v486 + 12) = 1;
      *((_WORD *)v486 + 13) = 1;
      v486[7] = 14122;
    }
    LODWORD(v491) = 97;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v485,
                 &v491) = v486;
    LODWORD(v491) = 3615236;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](8, &v491) = v486;
    v487 = operator new(0x20u);
    v489 = v487;
    if ( v487 )
    {
      *v487 = 96;
      v487[1] = 4202;
      v487[2] = 7;
      *((_QWORD *)v487 + 2) = L"WCN_TYPE_REQUESTED_DEVICE_TYPE";
      *((_QWORD *)v487 + 3) = 131074;
    }
    LODWORD(v491) = 96;
    *(_QWORD *)std::map<enum tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](
                 v488,
                 &v491) = v487;
    LODWORD(v491) = 4202;
    *(_QWORD *)std::map<unsigned int,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *>::operator[](v490, &v491) = v489;
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v491) = -2147024882;
    return 2147942414LL;
  }
  v1 = operator new(0x10u);
}

```

## disassembly

```asm
0x1800113dc  mov     [rsp+arg_10], rbx
0x1800113e1  mov     [rsp+arg_18], rsi
0x1800113e6  push    rdi
0x1800113e7  push    r12
0x1800113e9  push    r13
0x1800113eb  push    r14
0x1800113ed  push    r15
0x1800113ef  sub     rsp, 20h
0x1800113f3  xor     r13d, r13d
0x1800113f6  mov     [rsp+48h+arg_8], r13d
0x1800113fb  cmp     cs:?m_fInitialized@CWcnAttributeRules@@0_NA, r13b; bool CWcnAttributeRules::m_fInitialized
0x180011402  jz      short loc_18001140E
0x180011404  mov     eax, 800700B7h
0x180011409  jmp     loc_18001450B
0x18001140e  mov     r15d, 1
0x180011414  mov     cs:?m_fInitialized@CWcnAttributeRules@@0_NA, r15b; bool CWcnAttributeRules::m_fInitialized
0x18001141b  lea     edi, [r15+0Fh]
0x18001141f  mov     ecx, edi; Size
0x180011421  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011426  mov     rbx, rax
0x180011429  mov     [rsp+48h+arg_0], rax
0x18001142e  test    rax, rax
0x180011431  jz      short loc_180011444
0x180011433  mov     [rax], r13
0x180011436  mov     [rax+8], r13
0x18001143a  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@V?$allocator@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>::_Buyheadnode(void)
0x18001143f  mov     [rbx], rax
0x180011442  jmp     short loc_180011447
0x180011444  mov     rbx, r13
0x180011447  mov     cs:?m_pDataTypeRules@CWcnAttributeRules@@0PEAV?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@EA, rbx; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *> * CWcnAttributeRules::m_pDataTypeRules
0x18001144e  mov     rcx, rdi; Size
0x180011451  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011456  mov     rbx, rax
0x180011459  mov     [rsp+48h+arg_0], rax
0x18001145e  test    rax, rax
0x180011461  jz      short loc_180011474
0x180011463  mov     [rax], r13
0x180011466  mov     [rax+8], r13
0x18001146a  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@V?$allocator@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>::_Buyheadnode(void)
0x18001146f  mov     [rbx], rax
0x180011472  jmp     short loc_180011477
0x180011474  mov     rbx, r13
0x180011477  mov     cs:?m_pAttributeRules@CWcnAttributeRules@@0PEAV?$map@W4tagWCN_ATTRIBUTE_TYPE@@PEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_ATTRIBUTE_TYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_ATTRIBUTE_TYPE@@PEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@@std@@@5@@std@@EA, rbx; std::map<tagWCN_ATTRIBUTE_TYPE,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *> * CWcnAttributeRules::m_pAttributeRules
0x18001147e  mov     rcx, rdi; Size
0x180011481  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011486  mov     rbx, rax
0x180011489  mov     [rsp+48h+arg_0], rax
0x18001148e  test    rax, rax
0x180011491  jz      short loc_1800114A4
0x180011493  mov     [rax], r13
0x180011496  mov     [rax+8], r13
0x18001149a  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@V?$allocator@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>::_Buyheadnode(void)
0x18001149f  mov     [rbx], rax
0x1800114a2  jmp     short loc_1800114A7
0x1800114a4  mov     rbx, r13
0x1800114a7  mov     cs:?m_pAttributeIds@CWcnAttributeRules@@0PEAV?$map@IPEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEBUtagWCN_ATTRIBUTE_RULE@CWcnAttributeRules@@@std@@@4@@std@@EA, rbx; std::map<uint,CWcnAttributeRules::tagWCN_ATTRIBUTE_RULE const *> * CWcnAttributeRules::m_pAttributeIds
0x1800114ae  mov     r12d, 14h
0x1800114b4  mov     ecx, r12d; Size
0x1800114b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800114bc  mov     rbx, rax
0x1800114bf  lea     r14d, [r12+0Ch]
0x1800114c4  lea     esi, [r12+13h]
0x1800114c9  test    rax, rax
0x1800114cc  jz      short loc_1800114E3
0x1800114ce  mov     qword ptr [rax], 1
0x1800114d5  mov     [rax+8], r14d
0x1800114d9  mov     [rax+0Ch], r13w
0x1800114de  mov     [rax+10h], esi
0x1800114e1  jmp     short loc_1800114E6
0x1800114e3  mov     rbx, r13
0x1800114e6  mov     dword ptr [rsp+48h+arg_0], r13d
0x1800114eb  lea     rdx, [rsp+48h+arg_0]
0x1800114f0  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x1800114f5  mov     [rax], rbx
0x1800114f8  mov     rcx, r12; Size
0x1800114fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011500  mov     rbx, rax
0x180011503  mov     r15d, 40h ; '@'
0x180011509  test    rax, rax
0x18001150c  jz      short loc_180011523
0x18001150e  mov     qword ptr [rax], 1
0x180011515  mov     [rax+8], r15d
0x180011519  mov     [rax+0Ch], r13w
0x18001151e  mov     [rax+10h], esi
0x180011521  jmp     short loc_180011526
0x180011523  mov     rbx, r13
0x180011526  mov     dword ptr [rsp+48h+arg_0], 1
0x18001152e  lea     rdx, [rsp+48h+arg_0]
0x180011533  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x180011538  mov     [rax], rbx
0x18001153b  mov     rcx, r12; Size
0x18001153e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011543  mov     rdi, rax
0x180011546  mov     ebx, 2
0x18001154b  test    rax, rax
0x18001154e  jz      short loc_180011564
0x180011550  mov     [rax], rbx
0x180011553  mov     dword ptr [rax+8], 200h
0x18001155a  mov     [rax+0Ch], r13w
0x18001155f  mov     [rax+10h], esi
0x180011562  jmp     short loc_180011567
0x180011564  mov     rdi, r13
0x180011567  mov     dword ptr [rsp+48h+arg_0], ebx
0x18001156b  lea     rdx, [rsp+48h+arg_0]
0x180011570  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x180011575  mov     [rax], rdi
0x180011578  mov     rcx, r12; Size
0x18001157b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011580  mov     rdi, rax
0x180011583  test    rax, rax
0x180011586  jz      short loc_1800115A0
0x180011588  mov     qword ptr [rax], 2
0x18001158f  mov     dword ptr [rax+8], 80h
0x180011596  mov     [rax+0Ch], r13w
0x18001159b  mov     [rax+10h], esi
0x18001159e  jmp     short loc_1800115A3
0x1800115a0  mov     rdi, r13
0x1800115a3  mov     dword ptr [rsp+48h+arg_0], 3
0x1800115ab  lea     rdx, [rsp+48h+arg_0]
0x1800115b0  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x1800115b5  mov     [rax], rdi
0x1800115b8  mov     rcx, r12; Size
0x1800115bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800115c0  mov     rdi, rax
0x1800115c3  mov     r12d, 8
0x1800115c9  test    rax, rax
0x1800115cc  jz      short loc_1800115E6
0x1800115ce  mov     [rax], ebx
0x1800115d0  mov     dword ptr [rax+4], 1
0x1800115d7  mov     [rax+8], r12d
0x1800115db  mov     word ptr [rax+0Ch], 1
0x1800115e1  mov     [rax+10h], esi
0x1800115e4  jmp     short loc_1800115E9
0x1800115e6  mov     rdi, r13
0x1800115e9  mov     dword ptr [rsp+48h+arg_0], 4
0x1800115f1  lea     rdx, [rsp+48h+arg_0]
0x1800115f6  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x1800115fb  mov     [rax], rdi
0x1800115fe  mov     ecx, 14h; Size
0x180011603  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011608  mov     rdi, rax
0x18001160b  test    rax, rax
0x18001160e  jz      short loc_180011628
0x180011610  mov     [rax], r13d
0x180011613  mov     eax, 1
0x180011618  mov     [rdi+4], eax
0x18001161b  mov     [rdi+8], eax
0x18001161e  mov     [rdi+0Ch], r13w
0x180011623  mov     [rdi+10h], esi
0x180011626  jmp     short loc_18001162B
0x180011628  mov     rdi, r13
0x18001162b  mov     dword ptr [rsp+48h+arg_0], 5
0x180011633  lea     rdx, [rsp+48h+arg_0]
0x180011638  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x18001163d  mov     [rax], rdi
0x180011640  mov     ecx, 14h; Size
0x180011645  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001164a  mov     rdi, rax
0x18001164d  test    rax, rax
0x180011650  jz      short loc_180011666
0x180011652  mov     [rax], ebx
0x180011654  mov     qword ptr [rax+4], 2
0x18001165c  mov     [rax+0Ch], r13w
0x180011661  mov     [rax+10h], esi
0x180011664  jmp     short loc_180011669
0x180011666  mov     rdi, r13
0x180011669  mov     dword ptr [rsp+48h+arg_0], 6
0x180011671  lea     rdx, [rsp+48h+arg_0]
0x180011676  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x18001167b  mov     [rax], rdi
0x18001167e  mov     ecx, 14h; Size
0x180011683  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011688  mov     rdi, rax
0x18001168b  test    rax, rax
0x18001168e  jz      short loc_1800116A7
0x180011690  mov     [rax], ebx
0x180011692  mov     dword ptr [rax+4], 1
0x180011699  mov     [rax+8], r12d
0x18001169d  mov     [rax+0Ch], r13w
0x1800116a2  mov     [rax+10h], esi
0x1800116a5  jmp     short loc_1800116AA
0x1800116a7  mov     rdi, r13
0x1800116aa  mov     dword ptr [rsp+48h+arg_0], 7
0x1800116b2  lea     rdx, [rsp+48h+arg_0]
0x1800116b7  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x1800116bc  mov     [rax], rdi
0x1800116bf  mov     ecx, 14h; Size
0x1800116c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800116c9  mov     rdi, rax
0x1800116cc  test    rax, rax
0x1800116cf  jz      short loc_1800116EE
0x1800116d1  mov     qword ptr [rax], 2
0x1800116d8  mov     dword ptr [rax+8], 80h
0x1800116df  mov     word ptr [rax+0Ch], 100h
0x1800116e5  mov     dword ptr [rax+10h], 7
0x1800116ec  jmp     short loc_1800116F1
0x1800116ee  mov     rdi, r13
0x1800116f1  mov     dword ptr [rsp+48h+arg_0], r12d
0x1800116f6  lea     rdx, [rsp+48h+arg_0]
0x1800116fb  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x180011700  mov     [rax], rdi
0x180011703  mov     ecx, 14h; Size
0x180011708  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001170d  mov     rdi, rax
0x180011710  test    rax, rax
0x180011713  jz      short loc_18001172A
0x180011715  mov     qword ptr [rax], 2
0x18001171c  mov     [rax+8], r15d
0x180011720  mov     [rax+0Ch], r13w
0x180011725  mov     [rax+10h], esi
0x180011728  jmp     short loc_18001172D
0x18001172a  mov     rdi, r13
0x18001172d  mov     dword ptr [rsp+48h+arg_0], 9
0x180011735  lea     rdx, [rsp+48h+arg_0]
0x18001173a  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x18001173f  mov     [rax], rdi
0x180011742  mov     ecx, 14h; Size
0x180011747  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001174c  mov     rdi, rax
0x18001174f  test    rax, rax
0x180011752  jz      short loc_180011769
0x180011754  mov     qword ptr [rax], 2
0x18001175b  mov     [rax+8], r12d
0x18001175f  mov     [rax+0Ch], r13w
0x180011764  mov     [rax+10h], esi
0x180011767  jmp     short loc_18001176C
0x180011769  mov     rdi, r13
0x18001176c  mov     dword ptr [rsp+48h+arg_0], 0Ah
0x180011774  lea     rdx, [rsp+48h+arg_0]
0x180011779  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x18001177e  mov     [rax], rdi
0x180011781  mov     ecx, 14h; Size
0x180011786  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001178b  mov     rdi, rax
0x18001178e  test    rax, rax
0x180011791  jz      short loc_1800117A7
0x180011793  mov     [rax], ebx
0x180011795  mov     qword ptr [rax+4], 2
0x18001179d  mov     [rax+0Ch], r13w
0x1800117a2  mov     [rax+10h], esi
0x1800117a5  jmp     short loc_1800117AA
0x1800117a7  mov     rdi, r13
0x1800117aa  mov     dword ptr [rsp+48h+arg_0], 0Bh
0x1800117b2  lea     rdx, [rsp+48h+arg_0]
0x1800117b7  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x1800117bc  mov     [rax], rdi
0x1800117bf  mov     ecx, 14h; Size
0x1800117c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800117c9  mov     rdi, rax
0x1800117cc  test    rax, rax
0x1800117cf  jz      short loc_1800117E8
0x1800117d1  mov     [rax], ebx
0x1800117d3  mov     dword ptr [rax+4], 1
0x1800117da  mov     [rax+8], r14d
0x1800117de  mov     [rax+0Ch], r13w
0x1800117e3  mov     [rax+10h], esi
0x1800117e6  jmp     short loc_1800117EB
0x1800117e8  mov     rdi, r13
0x1800117eb  mov     dword ptr [rsp+48h+arg_0], 0Ch
0x1800117f3  lea     rdx, [rsp+48h+arg_0]
0x1800117f8  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x1800117fd  mov     [rax], rdi
0x180011800  mov     ecx, 14h; Size
0x180011805  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001180a  mov     rdi, rax
0x18001180d  test    rax, rax
0x180011810  jz      short loc_18001182E
0x180011812  mov     qword ptr [rax], 2
0x180011819  mov     r13d, 50h ; 'P'
0x18001181f  mov     [rax+8], r13d
0x180011823  mov     word ptr [rax+0Ch], 0
0x180011829  mov     [rax+10h], esi
0x18001182c  jmp     short loc_180011837
0x18001182e  mov     rdi, r13
0x180011831  mov     r13d, 50h ; 'P'
0x180011837  mov     dword ptr [rsp+48h+arg_0], 0Dh
0x18001183f  lea     rdx, [rsp+48h+arg_0]
0x180011844  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x180011849  mov     [rax], rdi
0x18001184c  mov     ecx, 14h; Size
0x180011851  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011856  mov     rdi, rax
0x180011859  xor     eax, eax
0x18001185b  test    rdi, rdi
0x18001185e  jz      short loc_180011873
0x180011860  mov     [rdi], ebx
0x180011862  mov     qword ptr [rdi+4], 2
0x18001186a  mov     [rdi+0Ch], ax
0x18001186e  mov     [rdi+10h], esi
0x180011871  jmp     short loc_180011876
0x180011873  mov     rdi, rax
0x180011876  mov     dword ptr [rsp+48h+arg_0], 0Eh
0x18001187e  lea     rdx, [rsp+48h+arg_0]
0x180011883  call    ??A?$map@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@@std@@QEAAAEAPEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@$$QEAW4tagWCN_DATATYPE@@@Z; std::map<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>::operator[](tagWCN_DATATYPE &&)
0x180011888  mov     [rax], rdi
0x18001188b  mov     ecx, 14h; Size
0x180011890  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011895  mov     rdi, rax
0x180011898  test    rax, rax
0x18001189b  jz      short loc_1800118B5
  ... truncated ...
```
