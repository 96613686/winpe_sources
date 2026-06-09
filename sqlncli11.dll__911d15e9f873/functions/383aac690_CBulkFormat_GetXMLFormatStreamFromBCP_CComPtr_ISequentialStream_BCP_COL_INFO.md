# CBulkFormat::GetXMLFormatStreamFromBCP(CComPtr<ISequentialStream>,BCP_COL_INFO *)

- ea: `0x383aac690`
- end: `0x383aaf0f3`
- name: `?GetXMLFormatStreamFromBCP@CBulkFormat@@QEAA?AV?$CComPtr@UISequentialStream@@@@V2@PEAUBCP_COL_INFO@@@Z`
- size: `10851`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x383aa04a0`
- `0x383aa1b80`

## callees

- `0x3838434c0`
- `0x383844d50`
- `0x38387da60`
- `0x383892740`
- `0x3838be2fc`
- `0x383aa2740`
- `0x383aaba00`
- `0x383aabb00`
- `0x383aabf10`
- `0x383aabf90`
- `0x383aac0b0`
- `0x383aac110`
- `0x383aac2e0`
- `0x383aac460`
- `0x383aac690`
- `0x383aaf660`
- `0x383ade150`

## import_xrefs

- `MSVCR100!qsort` at `0x383aae7e3`
- `MSVCR100!qsort` at `0x383aae7e3`
- `MSVCR100!_ultow` at `0x383aad921`
- `MSVCR100!_ultow` at `0x383aadd1e`
- `MSVCR100!_ultow` at `0x383aade1a`
- `MSVCR100!_ultow` at `0x383aae16e`
- `MSVCR100!_ultow` at `0x383aae91d`
- `MSVCR100!_ultow` at `0x383aad921`
- `MSVCR100!_ultow` at `0x383aadd1e`
- `MSVCR100!_ultow` at `0x383aade1a`
- `MSVCR100!_ultow` at `0x383aae16e`
- `MSVCR100!_ultow` at `0x383aae91d`
- `MSVCR100!isspace` at `0x383aac8a5`
- `MSVCR100!isspace` at `0x383aac9c2`
- `MSVCR100!isspace` at `0x383aad0bd`
- `MSVCR100!isspace` at `0x383aad149`
- `MSVCR100!isspace` at `0x383aad1c9`
- `MSVCR100!isspace` at `0x383aac8a5`
- `MSVCR100!isspace` at `0x383aac9c2`
- `MSVCR100!isspace` at `0x383aad0bd`
- `MSVCR100!isspace` at `0x383aad149`
- `MSVCR100!isspace` at `0x383aad1c9`
- `MSVCR100!_strtoui64` at `0x383aac877`
- `MSVCR100!_strtoui64` at `0x383aac999`
- `MSVCR100!_strtoui64` at `0x383aad094`
- `MSVCR100!_strtoui64` at `0x383aad120`
- `MSVCR100!_strtoui64` at `0x383aad1a0`
- `MSVCR100!_strtoui64` at `0x383aac877`
- `MSVCR100!_strtoui64` at `0x383aac999`
- `MSVCR100!_strtoui64` at `0x383aad094`
- `MSVCR100!_strtoui64` at `0x383aad120`
- `MSVCR100!_strtoui64` at `0x383aad1a0`

## string_xrefs

- `0x383aad67f`: `http://schemas.microsoft.com/sqlserver/2004/bulkload/format`
- `0x383aad781`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x383aad632`: `xmlns`
- `0x383aad5f3`: `<?xml version="1.0"?>`
- `0x383aad73a`: `xmlns:xsi`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
_QWORD *__fastcall CBulkFormat::GetXMLFormatStreamFromBCP(__int64 a1, CFmtStream *a2, CFmtStream *a3, __int64 a4)
{
  unsigned int v6; // r14d
  __int64 v7; // rcx
  const OLECHAR **v8; // r12
  __int64 v9; // rax
  const OLECHAR *v10; // rsi
  bool v11; // zf
  const wchar_t *v12; // rdi
  __int64 v13; // rcx
  const OLECHAR *v14; // rsi
  bool v15; // zf
  const wchar_t *v16; // rdi
  __int64 v17; // rcx
  const OLECHAR *v18; // rsi
  bool v19; // zf
  const wchar_t *v20; // rdi
  __int64 v21; // rcx
  const OLECHAR *v22; // rsi
  bool v23; // zf
  const wchar_t *v24; // rdi
  __int64 v25; // rcx
  const OLECHAR *v26; // rsi
  bool v27; // zf
  const wchar_t *v28; // rdi
  __int64 v29; // rcx
  const OLECHAR *v30; // rsi
  bool v31; // zf
  const wchar_t *v32; // rdi
  __int64 v33; // rcx
  const OLECHAR *v34; // rsi
  bool v35; // zf
  const wchar_t *v36; // rdi
  __int64 v37; // rcx
  unsigned __int64 v38; // rbx
  __int64 v39; // rdx
  bool v40; // cf
  __int64 v41; // rdx
  _DWORD *v42; // rax
  char *v43; // r15
  __int64 v44; // rsi
  int v45; // eax
  unsigned __int64 v46; // rax
  int v47; // edi
  char *v48; // rbx
  unsigned int v49; // r13d
  char *v50; // r15
  __int64 v51; // rax
  const OLECHAR *v52; // rsi
  bool v53; // zf
  const wchar_t *v54; // rdi
  __int64 v55; // rcx
  const OLECHAR *v56; // rsi
  bool v57; // zf
  const wchar_t *v58; // rdi
  __int64 v59; // rcx
  const OLECHAR *v60; // rsi
  bool v61; // zf
  const wchar_t *v62; // rdi
  __int64 v63; // rcx
  const OLECHAR *v64; // rsi
  bool v65; // zf
  const wchar_t *v66; // rdi
  __int64 v67; // rcx
  const OLECHAR *v68; // rsi
  bool v69; // zf
  const wchar_t *v70; // rdi
  __int64 v71; // rcx
  const OLECHAR *v72; // rsi
  bool v73; // zf
  const wchar_t *v74; // rdi
  __int64 v75; // rcx
  const OLECHAR *v76; // rsi
  bool v77; // zf
  const wchar_t *v78; // rdi
  __int64 v79; // rcx
  const OLECHAR *v80; // rsi
  bool v81; // zf
  const wchar_t *v82; // rdi
  __int64 v83; // rcx
  const OLECHAR *v84; // rsi
  bool v85; // zf
  const wchar_t *v86; // rdi
  __int64 v87; // rcx
  const OLECHAR *v88; // rsi
  bool v89; // zf
  const wchar_t *v90; // rdi
  __int64 v91; // rcx
  const OLECHAR *v92; // rsi
  bool v93; // zf
  const wchar_t *v94; // rdi
  __int64 v95; // rcx
  const OLECHAR *v96; // rsi
  bool v97; // zf
  const wchar_t *v98; // rdi
  __int64 v99; // rcx
  const OLECHAR *v100; // rsi
  bool v101; // zf
  const wchar_t *v102; // rdi
  __int64 v103; // rcx
  const OLECHAR *v104; // rsi
  bool v105; // zf
  const wchar_t *v106; // rdi
  __int64 v107; // rcx
  const OLECHAR *v108; // rsi
  bool v109; // zf
  const wchar_t *v110; // rdi
  __int64 v111; // rcx
  const OLECHAR *v112; // rsi
  bool v113; // zf
  const wchar_t *v114; // rdi
  __int64 v115; // rcx
  const OLECHAR *v116; // rsi
  bool v117; // zf
  const wchar_t *v118; // rdi
  __int64 v119; // rcx
  const OLECHAR *v120; // rsi
  bool v121; // zf
  const wchar_t *v122; // rdi
  __int64 v123; // rcx
  const OLECHAR *v124; // rsi
  bool v125; // zf
  const wchar_t *v126; // rdi
  __int64 v127; // rcx
  const OLECHAR *v128; // rsi
  bool v129; // zf
  const wchar_t *v130; // rdi
  __int64 v131; // rcx
  const OLECHAR *v132; // rsi
  bool v133; // zf
  const wchar_t *v134; // rdi
  __int64 v135; // rcx
  const OLECHAR *v136; // rsi
  bool v137; // zf
  const wchar_t *v138; // rdi
  __int64 v139; // rcx
  const OLECHAR *v140; // rsi
  bool v141; // zf
  const wchar_t *v142; // rdi
  __int64 v143; // rcx
  const OLECHAR *v144; // rsi
  bool v145; // zf
  const wchar_t *v146; // rdi
  __int64 v147; // rcx
  const OLECHAR *v148; // rsi
  bool v149; // zf
  const wchar_t *v150; // rdi
  __int64 v151; // rcx
  const OLECHAR *v152; // rsi
  bool v153; // zf
  const wchar_t *v154; // rdi
  __int64 v155; // rcx
  const OLECHAR *v156; // rsi
  bool v157; // zf
  const wchar_t *v158; // rdi
  __int64 v159; // rcx
  const OLECHAR *v160; // rsi
  bool v161; // zf
  const wchar_t *v162; // rdi
  __int64 v163; // rcx
  const OLECHAR *v164; // rsi
  bool v165; // zf
  const wchar_t *v166; // rdi
  __int64 v167; // rcx
  const OLECHAR *v168; // rsi
  bool v169; // zf
  const wchar_t *v170; // rdi
  __int64 v171; // rcx
  const OLECHAR *v172; // rsi
  bool v173; // zf
  const wchar_t *v174; // rdi
  __int64 v175; // rcx
  const OLECHAR *v176; // rsi
  bool v177; // zf
  const wchar_t *v178; // rdi
  __int64 v179; // rcx
  const OLECHAR *v180; // rsi
  bool v181; // zf
  const wchar_t *v182; // rdi
  __int64 v183; // rcx
  const OLECHAR *v184; // rsi
  bool v185; // zf
  const wchar_t *v186; // rdi
  __int64 v187; // rcx
  const OLECHAR *v188; // rsi
  bool v189; // zf
  const wchar_t *v190; // rdi
  __int64 v191; // rcx
  const OLECHAR *v192; // rsi
  bool v193; // zf
  const wchar_t *v194; // rdi
  __int64 v195; // rcx
  const OLECHAR *v196; // rsi
  bool v197; // zf
  const wchar_t *v198; // rdi
  __int64 v199; // rcx
  const OLECHAR *v200; // rsi
  bool v201; // zf
  const wchar_t *v202; // rdi
  __int64 v203; // rcx
  const OLECHAR *v204; // rsi
  bool v205; // zf
  const wchar_t *v206; // rdi
  __int64 v207; // rcx
  const OLECHAR *v208; // rsi
  bool v209; // zf
  const wchar_t *v210; // rdi
  __int64 v211; // rcx
  const OLECHAR *v212; // rsi
  bool v213; // zf
  const wchar_t *v214; // rdi
  __int64 v215; // rcx
  const OLECHAR *v216; // rsi
  bool v217; // zf
  const wchar_t *v218; // rdi
  __int64 v219; // rcx
  const OLECHAR *v220; // rsi
  bool v221; // zf
  const wchar_t *v222; // rdi
  __int64 v223; // rcx
  const OLECHAR *v224; // rsi
  bool v225; // zf
  const wchar_t *v226; // rdi
  __int64 v227; // rcx
  const OLECHAR *v228; // rsi
  bool v229; // zf
  const wchar_t *v230; // rdi
  __int64 v231; // rcx
  const OLECHAR *v232; // rsi
  bool v233; // zf
  const wchar_t *v234; // rdi
  __int64 v235; // rcx
  const OLECHAR *v236; // rsi
  bool v237; // zf
  const wchar_t *v238; // rdi
  __int64 v239; // rcx
  const OLECHAR *v240; // rsi
  bool v241; // zf
  const wchar_t *v242; // rdi
  __int64 v243; // rcx
  int v244; // eax
  unsigned __int64 v245; // rax
  unsigned int v246; // edi
  int v247; // eax
  unsigned __int64 v248; // rax
  int v249; // edi
  int v250; // eax
  unsigned __int64 v251; // rax
  int v252; // edi
  const OLECHAR *v253; // rax
  const OLECHAR *v254; // rsi
  bool v255; // zf
  const wchar_t *v256; // rdi
  __int64 v257; // rcx
  const OLECHAR *v258; // rsi
  bool v259; // zf
  const wchar_t *v260; // rdi
  __int64 v261; // rcx
  const OLECHAR *v262; // rsi
  bool v263; // zf
  const wchar_t *v264; // rdi
  __int64 v265; // rcx
  const OLECHAR *v266; // rsi
  bool v267; // zf
  const wchar_t *v268; // rdi
  __int64 v269; // rcx
  __int64 v270; // rax
  const OLECHAR *v271; // rsi
  bool v272; // zf
  const OLECHAR *v273; // rdi
  __int64 v274; // rcx
  __int64 v275; // rax
  const OLECHAR *v276; // rsi
  bool v277; // zf
  const wchar_t *v278; // rdi
  __int64 v279; // rcx
  const OLECHAR *v280; // rsi
  bool v281; // zf
  const wchar_t *v282; // rdi
  __int64 v283; // rcx
  const OLECHAR *v284; // rsi
  bool v285; // zf
  const wchar_t *v286; // rdi
  __int64 v287; // rcx
  const OLECHAR *v288; // rsi
  bool v289; // zf
  const wchar_t *v290; // rdi
  __int64 v291; // rcx
  const OLECHAR *v292; // rsi
  bool v293; // zf
  const wchar_t *v294; // rdi
  __int64 v295; // rcx
  const OLECHAR *v296; // rsi
  bool v297; // zf
  const wchar_t *v298; // rdi
  __int64 v299; // rcx
  const OLECHAR *v300; // rsi
  bool v301; // zf
  const wchar_t *v302; // rdi
  __int64 v303; // rcx
  const OLECHAR *v304; // rsi
  bool v305; // zf
  const wchar_t *v306; // rdi
  __int64 v307; // rcx
  const OLECHAR *v308; // rsi
  bool v309; // zf
  const wchar_t *v310; // rdi
  __int64 v311; // rcx
  const OLECHAR *v312; // rsi
  bool v313; // zf
  const wchar_t *v314; // rdi
  __int64 v315; // rcx
  CFmtStream *v316; // rbx
  __int64 v317; // rax
  __int64 v318; // rax
  __int64 v319; // rax
  __int64 v320; // rdx
  unsigned __int16 *v321; // rax
  unsigned __int16 *v322; // rdi
  unsigned __int16 *v323; // rsi
  CFmtStream *v324; // rcx
  const wchar_t *v325; // rdx
  __int64 v326; // rax
  __int64 v327; // rax
  __int64 v328; // rdx
  unsigned __int16 *v329; // rax
  unsigned __int16 *v330; // rdi
  unsigned __int16 *v331; // rsi
  CFmtStream *v332; // rcx
  const wchar_t *v333; // rdx
  __int64 v334; // rax
  unsigned int v335; // r13d
  char *v336; // rax
  unsigned int v337; // edi
  char *v338; // r14
  __int64 v339; // rax
  const OLECHAR *v340; // rsi
  bool v341; // zf
  const OLECHAR *v342; // rdi
  __int64 v343; // rcx
  __int64 v344; // rax
  unsigned int v345; // esi
  __int64 v346; // rax
  __int64 v347; // rax
  __int64 v348; // rdi
  wchar_t *v349; // rax
  __int64 v350; // rax
  __int64 v351; // rax
  const OLECHAR *v352; // rsi
  bool v353; // zf
  const wchar_t *v354; // rdi
  __int64 v355; // rcx
  const OLECHAR *v356; // rsi
  bool v357; // zf
  const wchar_t *v358; // rdi
  __int64 v359; // rcx
  const OLECHAR *v360; // rsi
  bool v361; // zf
  const wchar_t *v362; // rdi
  __int64 v363; // rcx
  const OLECHAR *v364; // rsi
  bool v365; // zf
  const wchar_t *v366; // rdi
  __int64 v367; // rcx
  const OLECHAR *v368; // rsi
  bool v369; // zf
  const wchar_t *v370; // rdi
  __int64 v371; // rcx
  const OLECHAR *v372; // rsi
  bool v373; // zf
  const wchar_t *v374; // rdi
  __int64 v375; // rcx
  const OLECHAR *v376; // rsi
  bool v377; // zf
  const wchar_t *v378; // rdi
  __int64 v379; // rcx
  const OLECHAR *v380; // rsi
  bool v381; // zf
  const wchar_t *v382; // rdi
  __int64 v383; // rcx
  const OLECHAR *v384; // rsi
  bool v385; // zf
  const wchar_t *v386; // rdi
  __int64 v387; // rcx
  int v388; // r12d
  __int64 v389; // rax
  const OLECHAR *v390; // rsi
  bool v391; // zf
  const wchar_t *v392; // rdi
  __int64 v393; // rcx
  const OLECHAR *v394; // rsi
  bool v395; // zf
  const wchar_t *v396; // rdi
  __int64 v397; // rcx
  const OLECHAR *v398; // rsi
  bool v399; // zf
  const wchar_t *v400; // rdi
  __int64 v401; // rcx
  const OLECHAR *v402; // rsi
  bool v403; // zf
  const wchar_t *v404; // rdi
  __int64 v405; // rcx
  int v406; // eax
  __int64 v407; // rax
  __int64 v408; // rax
  __int64 v409; // rdx
  unsigned __int16 *v410; // rax
  unsigned __int16 *v411; // rdi
  __int64 v412; // rax
  __int64 v413; // rax
  __int64 v414; // rdx
  unsigned __int16 *v415; // rax
  __int64 v416; // rax
  __int64 v417; // rax
  __int64 v418; // rdx
  unsigned __int16 *v419; // rax
  unsigned int v420; // esi
  __int64 v421; // rax
  __int64 v422; // rax
  __int64 v423; // rdi
  wchar_t *v424; // rax
  __int64 v425; // rax
  __int64 v426; // rax
  const OLECHAR *v427; // rsi
  bool v428; // zf
  const wchar_t *v429; // rdi
  __int64 v430; // rcx
  const OLECHAR *v431; // rsi
  bool v432; // zf
  const wchar_t *v433; // rdi
  __int64 v434; // rcx
  const OLECHAR *v435; // rsi
  bool v436; // zf
  const wchar_t *v437; // rdi
  __int64 v438; // rcx
  const OLECHAR *v439; // rsi
  bool v440; // zf
  const wchar_t *v441; // rdi
  __int64 v442; // rcx
  unsigned int v443; // esi
  __int64 v444; // rax
  __int64 v445; // rax
  __int64 v446; // rdi
  wchar_t *v447; // rax
  __int64 v448; // rax
  __int64 v449; // rax
  const OLECHAR *v450; // rsi
  bool v451; // zf
  const OLECHAR *v452; // rdi
  __int64 v453; // rcx
  __int64 v454; // rax
  __int64 v455; // rax
  __int64 v456; // rax
  const OLECHAR *v457; // rsi
  bool v458; // zf
  const OLECHAR *v459; // rdi
  __int64 v460; // rcx
  __int64 v461; // rax
  __int64 v462; // rax
  __int64 v463; // rax
  __int64 v464; // rdx
  unsigned __int16 *v465; // rax
  unsigned __int16 *v466; // rdi
  __int64 v467; // rax
  __int64 v468; // rax
  __int64 v469; // rdx
  unsigned __int16 *v470; // rax
  __int64 v471; // rax
  __int64 v472; // rax
  __int64 v473; // rdx
  unsigned __int16 *v474; // rax
  __int64 v475; // rax
  __int64 v476; // rax
  char *v477; // r15
  __int64 v478; // rax
  __int64 v479; // rax
  __int64 v480; // rdi
  wchar_t *v481; // rax
  __int64 v482; // rax
  __int64 v483; // rax
  const OLECHAR *v484; // rsi
  bool v485; // zf
  const OLECHAR *v486; // rdi
  __int64 v487; // rcx
  __int64 v488; // rax
  __int64 v489; // rax
  __int64 v490; // rax
  const OLECHAR *v491; // rsi
  bool v492; // zf
  const OLECHAR *v493; // rdi
  __int64 v494; // rcx
  __int64 v495; // rax
  __int64 v496; // rax
  __int64 v497; // rdx
  unsigned __int16 *v498; // rax
  unsigned __int16 *v499; // rdi
  __int64 v500; // rax
  __int64 v501; // rax
  __int64 v502; // rdx
  unsigned __int16 *v503; // rax
  __int64 v504; // rax
  __int64 v505; // rax
  __int64 v506; // rdx
  unsigned __int16 *v507; // rax
  __int64 v508; // rax
  __int64 v509; // rax
  __int64 v510; // rax
  const OLECHAR *v511; // rsi
  bool v512; // zf
  const wchar_t *v513; // rdi
  __int64 v514; // rcx
  const OLECHAR *v515; // rsi
  bool v516; // zf
  const wchar_t *v517; // rdi
  __int64 v518; // rcx
  const OLECHAR *v519; // rsi
  bool v520; // zf
  const wchar_t *v521; // rdi
  __int64 v522; // rcx
  const OLECHAR *v523; // rsi
  bool v524; // zf
  const wchar_t *v525; // rdi
  __int64 v526; // rcx
  unsigned int v527; // edi
  __int64 v528; // rax
  __int64 v529; // rax
  __int64 v530; // rax
  __int64 v531; // rax
  __int64 v532; // rax
  char *v533; // rdx
  __int64 v534; // rax
  __int64 v535; // rax
  __int64 v536; // rax
  __int64 v537; // rax
  __int64 v538; // rax
  __int64 v539; // rax
  __int64 v540; // rax
  const OLECHAR *v541; // rsi
  bool v542; // zf
  const OLECHAR *v543; // rdi
  __int64 v544; // rcx
  __int64 v545; // rax
  __int64 v546; // rax
  __int64 v547; // rax
  __int64 v548; // rax
  __int64 v549; // rax
  char *v550; // rsi
  __int64 v551; // r13
  __int64 v552; // rax
  unsigned int v553; // r12d
  char *v554; // r14
  __int64 v555; // rax
  const OLECHAR *v556; // rsi
  bool v557; // zf
  const OLECHAR *v558; // rdi
  __int64 v559; // rcx
  unsigned int v560; // eax
  __int64 v561; // r15
  __int64 v562; // rax
  __int64 v563; // rax
  unsigned int v564; // esi
  __int64 v565; // rax
  __int64 v566; // rax
  __int64 v567; // rdi
  wchar_t *v568; // rax
  __int64 v569; // rax
  __int64 v570; // rax
  __int64 v571; // rax
  char *v572; // r13
  __int64 v573; // rax
  const OLECHAR *v574; // rsi
  bool v575; // zf
  const wchar_t *v576; // rdi
  __int64 v577; // rcx
  const OLECHAR *v578; // rsi
  bool v579; // zf
  const wchar_t *v580; // rdi
  __int64 v581; // rcx
  const OLECHAR *v582; // rsi
  bool v583; // zf
  const wchar_t *v584; // rdi
  __int64 v585; // rcx
  const OLECHAR *v586; // rsi
  bool v587; // zf
  const wchar_t *v588; // rdi
  __int64 v589; // rcx
  const OLECHAR *v590; // rsi
  bool v591; // zf
  const wchar_t *v592; // rdi
  __int64 v593; // rcx
  __int64 v594; // rax
  __int64 v595; // rax
  unsigned int v596; // edi
  __int64 v597; // rax
  __int64 v598; // rax
  __int64 v599; // rax
  __int64 v600; // rax
  unsigned int v601; // edi
  __int64 v602; // rax
  __int64 v603; // rax
  __int64 v604; // rax
  __int64 v605; // rax
  bool v606; // zf
  __int64 v607; // rax
  __int64 v608; // rax
  char **v609; // rax
  int v610; // r13d
  char *v611; // rax
  const OLECHAR *v612; // rsi
  bool v613; // zf
  const wchar_t *v614; // rdi
  __int64 v615; // rcx
  CWStr *v616; // rax
  const OLECHAR *v617; // rax
  const OLECHAR *v618; // rsi
  bool v619; // zf
  const wchar_t *v620; // rdi
  __int64 v621; // rcx
  char v622; // di
  unsigned int v623; // edi
  __int64 v624; // rax
  __int64 v625; // rax
  __int64 v626; // rax
  __int64 v627; // rax
  unsigned int v628; // edi
  __int64 v629; // rax
  __int64 v630; // rax
  __int64 v631; // rax
  __int64 v632; // rax
  __int64 *v633; // rax
  int v634; // r13d
  const OLECHAR *v635; // rax
  const OLECHAR *v636; // rsi
  bool v637; // zf
  const wchar_t *v638; // rdi
  __int64 v639; // rcx
  char **p_EndPtr; // rax
  char *v641; // rax
  const OLECHAR *v642; // rsi
  bool v643; // zf
  const wchar_t *v644; // rdi
  __int64 v645; // rcx
  char **v646; // rax
  char *v647; // rax
  const OLECHAR *v648; // rsi
  bool v649; // zf
  const wchar_t *v650; // rdi
  __int64 v651; // rcx
  char v652; // di
  unsigned int v653; // edi
  __int64 v654; // rax
  __int64 v655; // rax
  __int64 v656; // rax
  __int64 v657; // rax
  __int64 v658; // rax
  __int64 v659; // rax
  __int64 v660; // rax
  __int64 v661; // rax
  _QWORD *v662; // r14
  __int64 v664; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v665; // [rsp+38h] [rbp-C8h]
  _DWORD *v666; // [rsp+40h] [rbp-C0h] BYREF
  __int64 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  void *Base; // [rsp+50h] [rbp-B0h]
  char *v669; // [rsp+58h] [rbp-A8h] BYREF
  char *EndPtr; // [rsp+60h] [rbp-A0h] BYREF
  char *v671; // [rsp+68h] [rbp-98h] BYREF
  __int64 v672; // [rsp+70h] [rbp-90h] BYREF
  size_t NumOfElements; // [rsp+78h] [rbp-88h]
  __int64 v674; // [rsp+80h] [rbp-80h] BYREF
  __int64 v675; // [rsp+88h] [rbp-78h] BYREF
  __int64 v676; // [rsp+90h] [rbp-70h] BYREF
  char *v677; // [rsp+98h] [rbp-68h]
  _QWORD *v678; // [rsp+A0h] [rbp-60h]
  __int64 v679; // [rsp+A8h] [rbp-58h]
  CFmtStream *v680[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v681[514]; // [rsp+D0h] [rbp-30h] BYREF
  char String[32]; // [rsp+10E0h] [rbp+FE0h] BYREF
  wchar_t Buffer[40]; // [rsp+1100h] [rbp+1000h] BYREF

  v680[3] = (CFmtStream *)-2LL;
  v679 = a4;
  v676 = (__int64)a3;
  v678 = a2;
  v680[1] = a2;
  v680[2] = a3;
  v6 = 0;
  v665 = 0;
  v677 = 0;
  CFmtStream::Create(v680);
  v7 = *(_QWORD *)a3;
  v681[0] = v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v681[513] = 0;
  v8 = (const OLECHAR **)(a1 + 144);
  GetString((struct CWStr *)(a1 + 144), -1, (struct CBulkFmtStreamReader *)v681);
  v9 = *(_QWORD *)(a1 + 144);
  v10 = &WideCharStr;
  v11 = v9 == 0;
  if ( v9 )
    v10 = *v8;
  v12 = L"11.0";
  v13 = 5;
  do
  {
    if ( !v13 )
      break;
    v11 = *v10++ == *v12++;
    --v13;
  }
  while ( v11 );
  if ( !v11 )
  {
    v14 = &WideCharStr;
    v15 = v9 == 0;
    if ( v9 )
      v14 = *v8;
    v16 = L"10.0";
    v17 = 5;
    do
    {
      if ( !v17 )
        break;
      v15 = *v14++ == *v16++;
      --v17;
    }
    while ( v15 );
    if ( !v15 )
    {
      v18 = &WideCharStr;
      v19 = v9 == 0;
      if ( v9 )
        v18 = *v8;
      v20 = L"9.0";
      v21 = 4;
      do
      {
        if ( !v21 )
          break;
        v19 = *v18++ == *v20++;
        --v21;
      }
      while ( v19 );
      if ( !v19 )
      {
        v22 = &WideCharStr;
        v23 = v9 == 0;
        if ( v9 )
          v22 = *v8;
        v24 = L"8.0";
        v25 = 4;
        do
        {
          if ( !v25 )
            break;
          v23 = *v22++ == *v24++;
          --v25;
        }
        while ( v23 );
        if ( !v23 )
        {
          v26 = &WideCharStr;
          v27 = v9 == 0;
          if ( v9 )
            v26 = *v8;
          v28 = L"7.0";
          v29 = 4;
          do
          {
            if ( !v29 )
              break;
            v27 = *v26++ == *v28++;
            --v29;
          }
          while ( v27 );
          if ( !v27 )
          {
            v30 = &WideCharStr;
            v31 = v9 == 0;
            if ( v9 )
              v30 = *v8;
            v32 = L"6.0";
            v33 = 4;
            do
            {
              if ( !v33 )
                break;
              v31 = *v30++ == *v32++;
              --v33;
            }
            while ( v31 );
            if ( !v31 )
            {
              v34 = &WideCharStr;
              v35 = v9 == 0;
              if ( v9 )
                v34 = *v8;
              v36 = L"4.2";
              v37 = 4;
              do
              {
                if ( !v37 )
                  break;
                v35 = *v34++ == *v36++;
                --v37;
              }
              while ( v35 );
              if ( !v35 )
              {
                v664 = 1;
                pExceptionObject = 1;
                throw (CBcpFmtException *)&pExceptionObject;
              }
            }
          }
        }
      }
    }
  }
  CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)v681);
  if ( (unsigned int)CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)v681, String, 0x14u)
    || (v38 = _strtoui64(String, (char **)&pExceptionObject, 10), NumOfElements = v38, v38 > 0x7FFFFFFF)
    || pExceptionObject && *(_BYTE *)pExceptionObject && !isspace(*(unsigned __int8 *)pExceptionObject)
    || !(_DWORD)v38
    || (unsigned int)v38 > 0x1000 )
  {
    pExceptionObject = 2;
    v676 = 2;
    throw (CBcpFmtException *)&v676;
  }
  v39 = 56LL * (unsigned int)v38;
  if ( !is_mul_ok((unsigned int)v38, 0x38u) )
    v39 = -1;
  v40 = __CFADD__(v39, 8);
  v41 = v39 + 8;
  if ( v40 )
    v41 = -1;
  v42 = (_DWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v41);
  v666 = v42;
  if ( v42 )
  {
    *v42 = v38;
    v43 = (char *)(v42 + 2);
    Base = v42 + 2;
    `eh vector constructor iterator'(
      v42 + 2,
      0x38u,
      v38,
      (void (*)(void *))CBCPFormatField::CBCPFormatField,
      (void (*)(void *))CBCPFormatField::~CBCPFormatField);
  }
  else
  {
    v43 = 0;
    Base = 0;
  }
  v677 = v43;
  if ( !v43 )
  {
    LODWORD(v672) = -2147024882;
    throw (CHRESULTException *)&v672;
  }
  v44 = 0;
  v664 = 0;
  while ( 1 )
  {
    CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)v681);
    v45 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)v681, String, 0x14u);
    if ( v45 )
    {
      if ( v45 == -2147467259 )
      {
        LODWORD(v664) = 4;
        HIDWORD(v664) = v6 + 1;
        v666 = (_DWORD *)v664;
        throw (CBcpFmtException *)&v666;
      }
LABEL_484:
      LODWORD(v664) = 3;
      HIDWORD(v664) = v6 + 1;
      pExceptionObject = v664;
      throw (CBcpFmtException *)&pExceptionObject;
    }
    v46 = _strtoui64(String, (char **)&pExceptionObject, 10);
    v47 = v46;
    if ( v46 > 0x7FFFFFFF
      || pExceptionObject && *(_BYTE *)pExceptionObject && !isspace(*(unsigned __int8 *)pExceptionObject) )
    {
      goto LABEL_484;
    }
    v48 = &v43[56 * v44];
    *(_DWORD *)v48 = v47;
    v49 = v6 + 1;
    if ( v47 != v6 + 1 )
      goto LABEL_484;
    v50 = &v43[56 * v6];
    GetString((struct CWStr *)(v50 + 8), v6, (struct CBulkFmtStreamReader *)v681);
    v51 = *((_QWORD *)v48 + 1);
    v52 = &WideCharStr;
    v53 = v51 == 0;
    if ( v51 )
      v52 = (const OLECHAR *)*((_QWORD *)v48 + 1);
    v54 = L"SQLBIT";
    v55 = 7;
    do
    {
      if ( !v55 )
        break;
      v53 = *v52++ == *v54++;
      --v55;
    }
    while ( v53 );
    if ( !v53 )
    {
      v56 = &WideCharStr;
      v57 = v51 == 0;
      if ( v51 )
        v56 = (const OLECHAR *)*((_QWORD *)v48 + 1);
      v58 = L"SQLTINYINT";
      v59 = 11;
      do
      {
        if ( !v59 )
          break;
        v57 = *v56++ == *v58++;
        --v59;
      }
      while ( v57 );
      if ( !v57 )
      {
        v60 = &WideCharStr;
        v61 = v51 == 0;
        if ( v51 )
          v60 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v62 = L"SQLSMALLINT";
        v63 = 12;
        do
        {
          if ( !v63 )
            break;
          v61 = *v60++ == *v62++;
          --v63;
        }
        while ( v61 );
        if ( !v61 )
        {
          v64 = &WideCharStr;
          v65 = v51 == 0;
          if ( v51 )
            v64 = (const OLECHAR *)*((_QWORD *)v48 + 1);
          v66 = L"SQLINT";
          v67 = 7;
          do
          {
            if ( !v67 )
              break;
            v65 = *v64++ == *v66++;
            --v67;
          }
          while ( v65 );
          if ( !v65 )
          {
            v68 = &WideCharStr;
            v69 = v51 == 0;
            if ( v51 )
              v68 = (const OLECHAR *)*((_QWORD *)v48 + 1);
            v70 = L"SQLBIGINT";
            v71 = 10;
            do
            {
              if ( !v71 )
                break;
              v69 = *v68++ == *v70++;
              --v71;
            }
            while ( v69 );
            if ( !v69 )
            {
              v72 = &WideCharStr;
              v73 = v51 == 0;
              if ( v51 )
                v72 = (const OLECHAR *)*((_QWORD *)v48 + 1);
              v74 = L"SQLFLT4";
              v75 = 8;
              do
              {
                if ( !v75 )
                  break;
                v73 = *v72++ == *v74++;
                --v75;
              }
              while ( v73 );
              if ( !v73 )
              {
                v76 = &WideCharStr;
                v77 = v51 == 0;
                if ( v51 )
                  v76 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                v78 = L"SQLFLT8";
                v79 = 8;
                do
                {
                  if ( !v79 )
                    break;
                  v77 = *v76++ == *v78++;
                  --v79;
                }
                while ( v77 );
                if ( !v77 )
                {
                  v80 = &WideCharStr;
                  v81 = v51 == 0;
                  if ( v51 )
                    v80 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                  v82 = L"SQLDATETIME";
                  v83 = 12;
                  do
                  {
                    if ( !v83 )
                      break;
                    v81 = *v80++ == *v82++;
                    --v83;
                  }
                  while ( v81 );
                  if ( !v81 )
                  {
                    v84 = &WideCharStr;
                    v85 = v51 == 0;
                    if ( v51 )
                      v84 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                    v86 = L"SQLDATETIM4";
                    v87 = 12;
                    do
                    {
                      if ( !v87 )
                        break;
                      v85 = *v84++ == *v86++;
                      --v87;
                    }
                    while ( v85 );
                    if ( !v85 )
                    {
                      v88 = &WideCharStr;
                      v89 = v51 == 0;
                      if ( v51 )
                        v88 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                      v90 = L"SQLDATETIM8";
                      v91 = 12;
                      do
                      {
                        if ( !v91 )
                          break;
                        v89 = *v88++ == *v90++;
                        --v91;
                      }
                      while ( v89 );
                      if ( !v89 )
                      {
                        v92 = &WideCharStr;
                        v93 = v51 == 0;
                        if ( v51 )
                          v92 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                        v94 = L"SQLDATE";
                        v95 = 8;
                        do
                        {
                          if ( !v95 )
                            break;
                          v93 = *v92++ == *v94++;
                          --v95;
                        }
                        while ( v93 );
                        if ( !v93 )
                        {
                          v96 = &WideCharStr;
                          v97 = v51 == 0;
                          if ( v51 )
                            v96 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                          v98 = L"SQLTIME";
                          v99 = 8;
                          do
                          {
                            if ( !v99 )
                              break;
                            v97 = *v96++ == *v98++;
                            --v99;
                          }
                          while ( v97 );
                          if ( !v97 )
                          {
                            v100 = &WideCharStr;
                            v101 = v51 == 0;
                            if ( v51 )
                              v100 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                            v102 = L"SQLDATETIME2";
                            v103 = 13;
                            do
                            {
                              if ( !v103 )
                                break;
                              v101 = *v100++ == *v102++;
                              --v103;
                            }
                            while ( v101 );
                            if ( !v101 )
                            {
                              v104 = &WideCharStr;
                              v105 = v51 == 0;
                              if ( v51 )
                                v104 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                              v106 = L"SQLDATETIMEOFFSET";
                              v107 = 18;
                              do
                              {
                                if ( !v107 )
                                  break;
                                v105 = *v104++ == *v106++;
                                --v107;
                              }
                              while ( v105 );
                              if ( !v105 )
                              {
                                v108 = &WideCharStr;
                                v109 = v51 == 0;
                                if ( v51 )
                                  v108 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                v110 = L"SQLMONEY";
                                v111 = 9;
                                do
                                {
                                  if ( !v111 )
                                    break;
                                  v109 = *v108++ == *v110++;
                                  --v111;
                                }
                                while ( v109 );
                                if ( !v109 )
                                {
                                  v112 = &WideCharStr;
                                  v113 = v51 == 0;
                                  if ( v51 )
                                    v112 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                  v114 = L"SQLMONEY4";
                                  v115 = 10;
                                  do
                                  {
                                    if ( !v115 )
                                      break;
                                    v113 = *v112++ == *v114++;
                                    --v115;
                                  }
                                  while ( v113 );
                                  if ( !v113 )
                                  {
                                    v116 = &WideCharStr;
                                    v117 = v51 == 0;
                                    if ( v51 )
                                      v116 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                    v118 = L"SQLVARIANT";
                                    v119 = 11;
                                    do
                                    {
                                      if ( !v119 )
                                        break;
                                      v117 = *v116++ == *v118++;
                                      --v119;
                                    }
                                    while ( v117 );
                                    if ( !v117 )
                                    {
                                      v120 = &WideCharStr;
                                      v121 = v51 == 0;
                                      if ( v51 )
                                        v120 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                      v122 = L"SQLUNIQUEID";
                                      v123 = 12;
                                      do
                                      {
                                        if ( !v123 )
                                          break;
                                        v121 = *v120++ == *v122++;
                                        --v123;
                                      }
                                      while ( v121 );
                                      if ( !v121 )
                                      {
                                        v124 = &WideCharStr;
                                        v125 = v51 == 0;
                                        if ( v51 )
                                          v124 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                        v126 = L"SQLDECIMAL";
                                        v127 = 11;
                                        do
                                        {
                                          if ( !v127 )
                                            break;
                                          v125 = *v124++ == *v126++;
                                          --v127;
                                        }
                                        while ( v125 );
                                        if ( !v125 )
                                        {
                                          v128 = &WideCharStr;
                                          v129 = v51 == 0;
                                          if ( v51 )
                                            v128 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                          v130 = L"SQLNUMERIC";
                                          v131 = 11;
                                          do
                                          {
                                            if ( !v131 )
                                              break;
                                            v129 = *v128++ == *v130++;
                                            --v131;
                                          }
                                          while ( v129 );
                                          if ( !v129 )
                                          {
                                            v132 = &WideCharStr;
                                            v133 = v51 == 0;
                                            if ( v51 )
                                              v132 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                            v134 = L"SQLIMAGE";
                                            v135 = 9;
                                            do
                                            {
                                              if ( !v135 )
                                                break;
                                              v133 = *v132++ == *v134++;
                                              --v135;
                                            }
                                            while ( v133 );
                                            if ( !v133 )
                                            {
                                              v136 = &WideCharStr;
                                              v137 = v51 == 0;
                                              if ( v51 )
                                                v136 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                              v138 = L"SQLTEXT";
                                              v139 = 8;
                                              do
                                              {
                                                if ( !v139 )
                                                  break;
                                                v137 = *v136++ == *v138++;
                                                --v139;
                                              }
                                              while ( v137 );
                                              if ( !v137 )
                                              {
                                                v140 = &WideCharStr;
                                                v141 = v51 == 0;
                                                if ( v51 )
                                                  v140 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                v142 = L"SQLNTEXT";
                                                v143 = 9;
                                                do
                                                {
                                                  if ( !v143 )
                                                    break;
                                                  v141 = *v140++ == *v142++;
                                                  --v143;
                                                }
                                                while ( v141 );
                                                if ( !v141 )
                                                {
                                                  v144 = &WideCharStr;
                                                  v145 = v51 == 0;
                                                  if ( v51 )
                                                    v144 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                  v146 = L"SQLBINARY";
                                                  v147 = 10;
                                                  do
                                                  {
                                                    if ( !v147 )
                                                      break;
                                                    v145 = *v144++ == *v146++;
                                                    --v147;
                                                  }
                                                  while ( v145 );
                                                  if ( !v145 )
                                                  {
                                                    v148 = &WideCharStr;
                                                    v149 = v51 == 0;
                                                    if ( v51 )
                                                      v148 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                    v150 = L"SQLVARYBIN";
                                                    v151 = 11;
                                                    do
                                                    {
                                                      if ( !v151 )
                                                        break;
                                                      v149 = *v148++ == *v150++;
                                                      --v151;
                                                    }
                                                    while ( v149 );
                                                    if ( !v149 )
                                                    {
                                                      v152 = &WideCharStr;
                                                      v153 = v51 == 0;
                                                      if ( v51 )
                                                        v152 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                      v154 = L"SQLCHAR";
                                                      v155 = 8;
                                                      do
                                                      {
                                                        if ( !v155 )
                                                          break;
                                                        v153 = *v152++ == *v154++;
                                                        --v155;
                                                      }
                                                      while ( v153 );
                                                      if ( !v153 )
                                                      {
                                                        v156 = &WideCharStr;
                                                        v157 = v51 == 0;
                                                        if ( v51 )
                                                          v156 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                        v158 = L"SQLVARYCHAR";
                                                        v159 = 12;
                                                        do
                                                        {
                                                          if ( !v159 )
                                                            break;
                                                          v157 = *v156++ == *v158++;
                                                          --v159;
                                                        }
                                                        while ( v157 );
                                                        if ( !v157 )
                                                        {
                                                          v160 = &WideCharStr;
                                                          v161 = v51 == 0;
                                                          if ( v51 )
                                                            v160 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                          v162 = L"SQLNCHAR";
                                                          v163 = 9;
                                                          do
                                                          {
                                                            if ( !v163 )
                                                              break;
                                                            v161 = *v160++ == *v162++;
                                                            --v163;
                                                          }
                                                          while ( v161 );
                                                          if ( !v161 )
                                                          {
                                                            v164 = &WideCharStr;
                                                            v165 = v51 == 0;
                                                            if ( v51 )
                                                              v164 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                            v166 = L"SQLNVARCHAR";
                                                            v167 = 12;
                                                            do
                                                            {
                                                              if ( !v167 )
                                                                break;
                                                              v165 = *v164++ == *v166++;
                                                              --v167;
                                                            }
                                                            while ( v165 );
                                                            if ( !v165 )
                                                            {
                                                              v168 = &WideCharStr;
                                                              v169 = v51 == 0;
                                                              if ( v51 )
                                                                v168 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                              v170 = L"SQLUDT";
                                                              v171 = 7;
                                                              do
                                                              {
                                                                if ( !v171 )
                                                                  break;
                                                                v169 = *v168++ == *v170++;
                                                                --v171;
                                                              }
                                                              while ( v169 );
                                                              if ( !v169 )
                                                              {
                                                                v172 = &WideCharStr;
                                                                v173 = v51 == 0;
                                                                if ( v51 )
                                                                  v172 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                v174 = L"SYBBIT";
                                                                v175 = 7;
                                                                do
                                                                {
                                                                  if ( !v175 )
                                                                    break;
                                                                  v173 = *v172++ == *v174++;
                                                                  --v175;
                                                                }
                                                                while ( v173 );
                                                                if ( !v173 )
                                                                {
                                                                  v176 = &WideCharStr;
                                                                  v177 = v51 == 0;
                                                                  if ( v51 )
                                                                    v176 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                  v178 = L"SYBTINYINT";
                                                                  v179 = 11;
                                                                  do
                                                                  {
                                                                    if ( !v179 )
                                                                      break;
                                                                    v177 = *v176++ == *v178++;
                                                                    --v179;
                                                                  }
                                                                  while ( v177 );
                                                                  if ( !v177 )
                                                                  {
                                                                    v180 = &WideCharStr;
                                                                    v181 = v51 == 0;
                                                                    if ( v51 )
                                                                      v180 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                    v182 = L"SYBSMALLINT";
                                                                    v183 = 12;
                                                                    do
                                                                    {
                                                                      if ( !v183 )
                                                                        break;
                                                                      v181 = *v180++ == *v182++;
                                                                      --v183;
                                                                    }
                                                                    while ( v181 );
                                                                    if ( !v181 )
                                                                    {
                                                                      v184 = &WideCharStr;
                                                                      v185 = v51 == 0;
                                                                      if ( v51 )
                                                                        v184 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                      v186 = L"SYBINT";
                                                                      v187 = 7;
                                                                      do
                                                                      {
                                                                        if ( !v187 )
                                                                          break;
                                                                        v185 = *v184++ == *v186++;
                                                                        --v187;
                                                                      }
                                                                      while ( v185 );
                                                                      if ( !v185 )
                                                                      {
                                                                        v188 = &WideCharStr;
                                                                        v189 = v51 == 0;
                                                                        if ( v51 )
                                                                          v188 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                        v190 = L"SYBBIGINT";
                                                                        v191 = 10;
                                                                        do
                                                                        {
                                                                          if ( !v191 )
                                                                            break;
                                                                          v189 = *v188++ == *v190++;
                                                                          --v191;
                                                                        }
                                                                        while ( v189 );
                                                                        if ( !v189 )
                                                                        {
                                                                          v192 = &WideCharStr;
                                                                          v193 = v51 == 0;
                                                                          if ( v51 )
                                                                            v192 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                          v194 = L"SYBFLT4";
                                                                          v195 = 8;
                                                                          do
                                                                          {
                                                                            if ( !v195 )
                                                                              break;
                                                                            v193 = *v192++ == *v194++;
                                                                            --v195;
                                                                          }
                                                                          while ( v193 );
                                                                          if ( !v193 )
                                                                          {
                                                                            v196 = &WideCharStr;
                                                                            v197 = v51 == 0;
                                                                            if ( v51 )
                                                                              v196 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                            v198 = L"SYBFLT8";
                                                                            v199 = 8;
                                                                            do
                                                                            {
                                                                              if ( !v199 )
                                                                                break;
                                                                              v197 = *v196++ == *v198++;
                                                                              --v199;
                                                                            }
                                                                            while ( v197 );
                                                                            if ( !v197 )
                                                                            {
                                                                              v200 = &WideCharStr;
                                                                              v201 = v51 == 0;
                                                                              if ( v51 )
                                                                                v200 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                              v202 = L"SYBDATETIME";
                                                                              v203 = 12;
                                                                              do
                                                                              {
                                                                                if ( !v203 )
                                                                                  break;
                                                                                v201 = *v200++ == *v202++;
                                                                                --v203;
                                                                              }
                                                                              while ( v201 );
                                                                              if ( !v201 )
                                                                              {
                                                                                v204 = &WideCharStr;
                                                                                v205 = v51 == 0;
                                                                                if ( v51 )
                                                                                  v204 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                v206 = L"SYBDATETIM4";
                                                                                v207 = 12;
                                                                                do
                                                                                {
                                                                                  if ( !v207 )
                                                                                    break;
                                                                                  v205 = *v204++ == *v206++;
                                                                                  --v207;
                                                                                }
                                                                                while ( v205 );
                                                                                if ( !v205 )
                                                                                {
                                                                                  v208 = &WideCharStr;
                                                                                  v209 = v51 == 0;
                                                                                  if ( v51 )
                                                                                    v208 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                  v210 = L"SYBDATETIM8";
                                                                                  v211 = 12;
                                                                                  do
                                                                                  {
                                                                                    if ( !v211 )
                                                                                      break;
                                                                                    v209 = *v208++ == *v210++;
                                                                                    --v211;
                                                                                  }
                                                                                  while ( v209 );
                                                                                  if ( !v209 )
                                                                                  {
                                                                                    v212 = &WideCharStr;
                                                                                    v213 = v51 == 0;
                                                                                    if ( v51 )
                                                                                      v212 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                    v214 = L"SYBMONEY";
                                                                                    v215 = 9;
                                                                                    do
                                                                                    {
                                                                                      if ( !v215 )
                                                                                        break;
                                                                                      v213 = *v212++ == *v214++;
                                                                                      --v215;
                                                                                    }
                                                                                    while ( v213 );
                                                                                    if ( !v213 )
                                                                                    {
                                                                                      v216 = &WideCharStr;
                                                                                      v217 = v51 == 0;
                                                                                      if ( v51 )
                                                                                        v216 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                      v218 = L"SYBMONEY4";
                                                                                      v219 = 10;
                                                                                      do
                                                                                      {
                                                                                        if ( !v219 )
                                                                                          break;
                                                                                        v217 = *v216++ == *v218++;
                                                                                        --v219;
                                                                                      }
                                                                                      while ( v217 );
                                                                                      if ( !v217 )
                                                                                      {
                                                                                        v220 = &WideCharStr;
                                                                                        v221 = v51 == 0;
                                                                                        if ( v51 )
                                                                                          v220 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                        v222 = L"SYBIMAGE";
                                                                                        v223 = 9;
                                                                                        do
                                                                                        {
                                                                                          if ( !v223 )
                                                                                            break;
                                                                                          v221 = *v220++ == *v222++;
                                                                                          --v223;
                                                                                        }
                                                                                        while ( v221 );
                                                                                        if ( !v221 )
                                                                                        {
                                                                                          v224 = &WideCharStr;
                                                                                          v225 = v51 == 0;
                                                                                          if ( v51 )
                                                                                            v224 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                          v226 = L"SYBTEXT";
                                                                                          v227 = 8;
                                                                                          do
                                                                                          {
                                                                                            if ( !v227 )
                                                                                              break;
                                                                                            v225 = *v224++ == *v226++;
                                                                                            --v227;
                                                                                          }
                                                                                          while ( v225 );
                                                                                          if ( !v225 )
                                                                                          {
                                                                                            v228 = &WideCharStr;
                                                                                            v229 = v51 == 0;
                                                                                            if ( v51 )
                                                                                              v228 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                            v230 = L"SYBBINARY";
                                                                                            v231 = 10;
                                                                                            do
                                                                                            {
                                                                                              if ( !v231 )
                                                                                                break;
                                                                                              v229 = *v228++ == *v230++;
                                                                                              --v231;
                                                                                            }
                                                                                            while ( v229 );
                                                                                            if ( !v229 )
                                                                                            {
                                                                                              v232 = &WideCharStr;
                                                                                              v233 = v51 == 0;
                                                                                              if ( v51 )
                                                                                                v232 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                              v234 = L"SYBVARYBIN";
                                                                                              v235 = 11;
                                                                                              do
                                                                                              {
                                                                                                if ( !v235 )
                                                                                                  break;
                                                                                                v233 = *v232++ == *v234++;
                                                                                                --v235;
                                                                                              }
                                                                                              while ( v233 );
                                                                                              if ( !v233 )
                                                                                              {
                                                                                                v236 = &WideCharStr;
                                                                                                v237 = v51 == 0;
                                                                                                if ( v51 )
                                                                                                  v236 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                                v238 = L"SYBCHAR";
                                                                                                v239 = 8;
                                                                                                do
                                                                                                {
                                                                                                  if ( !v239 )
                                                                                                    break;
                                                                                                  v237 = *v236++ == *v238++;
                                                                                                  --v239;
                                                                                                }
                                                                                                while ( v237 );
                                                                                                if ( !v237 )
                                                                                                {
                                                                                                  v240 = &WideCharStr;
                                                                                                  v241 = v51 == 0;
                                                                                                  if ( v51 )
                                                                                                    v240 = (const OLECHAR *)*((_QWORD *)v48 + 1);
                                                                                                  v242 = L"SYBVARYCHAR";
                                                                                                  v243 = 12;
                                                                                                  do
                                                                                                  {
                                                                                                    if ( !v243 )
                                                                                                      break;
                                                                                                    v241 = *v240++ == *v242++;
                                                                                                    --v243;
                                                                                                  }
                                                                                                  while ( v241 );
                                                                                                  if ( !v241 )
                                                                                                  {
                                                                                                    LODWORD(v664) = 5;
                                                                                                    HIDWORD(v664) = v6 + 1;
                                                                                                    pExceptionObject = v664;
                                                                                                    throw (CBcpFmtException *)&pExceptionObject;
                                                                                                  }
                                                                                                }
                                                                                              }
                                                                                            }
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                }
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)v681);
    v244 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)v681, String, 0x14u);
    if ( v244 )
    {
      if ( v244 == -2147467259 )
      {
        LODWORD(v664) = 4;
        HIDWORD(v664) = v6 + 1;
        v672 = v664;
        throw (CBcpFmtException *)&v672;
      }
LABEL_481:
      LODWORD(v664) = 6;
      HIDWORD(v664) = v6 + 1;
      pExceptionObject = v664;
      throw (CBcpFmtException *)&pExceptionObject;
    }
    v245 = _strtoui64(String, &EndPtr, 10);
    v246 = v245;
    if ( v245 > 0x7FFFFFFF || EndPtr && *EndPtr && !isspace((unsigned __int8)*EndPtr) )
      goto LABEL_481;
    *((_DWORD *)v48 + 4) = v246;
    if ( v246 > 2 && v246 != 4 && v246 != 8 )
      goto LABEL_481;
    CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)v681);
    v247 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)v681, String, 0x14u);
    if ( v247 )
    {
      if ( v247 == -2147467259 )
      {
        LODWORD(v664) = 4;
        HIDWORD(v664) = v6 + 1;
        v674 = v664;
        throw (CBcpFmtException *)&v674;
      }
LABEL_478:
      LODWORD(v664) = 7;
      HIDWORD(v664) = v6 + 1;
      pExceptionObject = v664;
      throw (CBcpFmtException *)&pExceptionObject;
    }
    v248 = _strtoui64(String, &v671, 10);
    v249 = v248;
    if ( v248 > 0x7FFFFFFF || v671 && *v671 && !isspace((unsigned __int8)*v671) )
      goto LABEL_478;
    *((_DWORD *)v48 + 5) = v249;
    GetString((struct CWStr *)(v50 + 24), v6, (struct CBulkFmtStreamReader *)v681);
    CBulkFmtStreamReader::SkipWs((CBulkFmtStreamReader *)v681);
    v250 = CBulkFmtStreamReader::GetString((CBulkFmtStreamReader *)v681, String, 0x14u);
    if ( v250 )
    {
      if ( v250 == -2147467259 )
      {
        LODWORD(v664) = 4;
        HIDWORD(v664) = v6 + 1;
        v675 = v664;
        throw (CBcpFmtException *)&v675;
      }
LABEL_475:
      LODWORD(v664) = 9;
      HIDWORD(v664) = v6 + 1;
      pExceptionObject = v664;
      throw (CBcpFmtException *)&pExceptionObject;
    }
    v251 = _strtoui64(String, &v669, 10);
    v252 = v251;
    if ( v251 > 0x7FFFFFFF || v669 && *v669 && !isspace((unsigned __int8)*v669) )
      goto LABEL_475;
    *((_DWORD *)v48 + 8) = v252;
    GetString((struct CWStr *)(v50 + 40), v6, (struct CBulkFmtStreamReader *)v681);
    v253 = *v8;
    v254 = &WideCharStr;
    v255 = *v8 == 0;
    if ( *v8 )
      v254 = *v8;
    v256 = L"11.0";
    v257 = 5;
    do
    {
      if ( !v257 )
        break;
      v255 = *v254++ == *v256++;
      --v257;
    }
    while ( v255 );
    if ( v255 )
      goto LABEL_399;
    v258 = &WideCharStr;
    v259 = v253 == 0;
    if ( v253 )
      v258 = *v8;
    v260 = L"10.0";
    v261 = 5;
    do
    {
      if ( !v261 )
        break;
      v259 = *v258++ == *v260++;
      --v261;
    }
    while ( v259 );
    if ( v259 )
      goto LABEL_399;
    v262 = &WideCharStr;
    v263 = v253 == 0;
    if ( v253 )
      v262 = *v8;
    v264 = L"9.0";
    v265 = 4;
    do
    {
      if ( !v265 )
        break;
      v263 = *v262++ == *v264++;
      --v265;
    }
    while ( v263 );
    if ( v263 )
      goto LABEL_399;
    v266 = &WideCharStr;
    v267 = v253 == 0;
    if ( v253 )
      v266 = *v8;
    v268 = L"8.0";
    v269 = 4;
    do
    {
      if ( !v269 )
        break;
      v267 = *v266++ == *v268++;
      --v269;
    }
    while ( v267 );
    if ( v267 )
LABEL_399:
      GetString((struct CWStr *)(v50 + 48), v6, (struct CBulkFmtStreamReader *)v681);
    if ( !*((_DWORD *)v48 + 8) && !*((_DWORD *)v48 + 5) )
    {
      v270 = *((_QWORD *)v48 + 3);
      v271 = &WideCharStr;
      v272 = v270 == 0;
      if ( v270 )
        v271 = (const OLECHAR *)*((_QWORD *)v48 + 3);
      v273 = &WideCharStr;
      v274 = 1;
      do
      {
        if ( !v274 )
          break;
        v272 = *v271++ == *v273++;
        --v274;
      }
      while ( v272 );
      if ( !v272 && *((_DWORD *)v48 + 4) != 1 || *((_DWORD *)v48 + 4) >= 2u )
      {
        v275 = *((_QWORD *)v48 + 1);
        v276 = &WideCharStr;
        v277 = v275 == 0;
        if ( v275 )
          v276 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v278 = L"SQLIMAGE";
        v279 = 9;
        do
        {
          if ( !v279 )
            break;
          v277 = *v276++ == *v278++;
          --v279;
        }
        while ( v277 );
        if ( v277 )
          goto LABEL_470;
        v280 = &WideCharStr;
        v281 = v275 == 0;
        if ( v275 )
          v280 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v282 = L"SQLTEXT";
        v283 = 8;
        do
        {
          if ( !v283 )
            break;
          v281 = *v280++ == *v282++;
          --v283;
        }
        while ( v281 );
        if ( v281 )
          goto LABEL_470;
        v284 = &WideCharStr;
        v285 = v275 == 0;
        if ( v275 )
          v284 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v286 = L"SQLNTEXT";
        v287 = 9;
        do
        {
          if ( !v287 )
            break;
          v285 = *v284++ == *v286++;
          --v287;
        }
        while ( v285 );
        if ( v285 )
          goto LABEL_470;
        v288 = &WideCharStr;
        v289 = v275 == 0;
        if ( v275 )
          v288 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v290 = L"SQLBINARY";
        v291 = 10;
        do
        {
          if ( !v291 )
            break;
          v289 = *v288++ == *v290++;
          --v291;
        }
        while ( v289 );
        if ( v289 )
          goto LABEL_470;
        v292 = &WideCharStr;
        v293 = v275 == 0;
        if ( v275 )
          v292 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v294 = L"SQLVARYBIN";
        v295 = 11;
        do
        {
          if ( !v295 )
            break;
          v293 = *v292++ == *v294++;
          --v295;
        }
        while ( v293 );
        if ( v293 )
          goto LABEL_470;
        v296 = &WideCharStr;
        v297 = v275 == 0;
        if ( v275 )
          v296 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v298 = L"SQLCHAR";
        v299 = 8;
        do
        {
          if ( !v299 )
            break;
          v297 = *v296++ == *v298++;
          --v299;
        }
        while ( v297 );
        if ( v297 )
          goto LABEL_470;
        v300 = &WideCharStr;
        v301 = v275 == 0;
        if ( v275 )
          v300 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v302 = L"SQLVARYCHAR";
        v303 = 12;
        do
        {
          if ( !v303 )
            break;
          v301 = *v300++ == *v302++;
          --v303;
        }
        while ( v301 );
        if ( v301 )
          goto LABEL_470;
        v304 = &WideCharStr;
        v305 = v275 == 0;
        if ( v275 )
          v304 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v306 = L"SQLNCHAR";
        v307 = 9;
        do
        {
          if ( !v307 )
            break;
          v305 = *v304++ == *v306++;
          --v307;
        }
        while ( v305 );
        if ( v305 )
          goto LABEL_470;
        v308 = &WideCharStr;
        v309 = v275 == 0;
        if ( v275 )
          v308 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v310 = L"SQLNVARCHAR";
        v311 = 12;
        do
        {
          if ( !v311 )
            break;
          v309 = *v308++ == *v310++;
          --v311;
        }
        while ( v309 );
        if ( v309 )
          goto LABEL_470;
        v312 = &WideCharStr;
        v313 = v275 == 0;
        if ( v275 )
          v312 = (const OLECHAR *)*((_QWORD *)v48 + 1);
        v314 = L"SQLUDT";
        v315 = 7;
        do
        {
          if ( !v315 )
            break;
          v313 = *v312++ == *v314++;
          --v315;
        }
        while ( v313 );
        if ( v313 )
LABEL_470:
          *((_DWORD *)v48 + 5) = 0x7FFFFFFF;
      }
    }
    ++v6;
    v44 = ++v664;
    if ( v49 >= (unsigned int)NumOfElements )
      break;
    v43 = (char *)Base;
  }
  v316 = v680[0];
  CFmtStream::operator<<(v680[0], 65279);
  CFmtStream::operator<<(v316, L"<?xml version=\"1.0\"?>");
  v317 = CFmtStream::operator<<(v316, L"\r\n<");
  CFmtStream::operator<<(v317, L"BCPFORMAT");
  v318 = CFmtStream::operator<<(v316, L" ");
  v319 = CFmtStream::operator<<(v318, L"xmlns");
  CFmtStream::operator<<(v319, L"=\"");
  v320 = 120;
  if ( !is_mul_ok(0x3Cu, 2u) )
    v320 = -1;
  v321 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v320);
  v322 = v321;
  v666 = v321;
  if ( v321 )
    StringCchCopyW(v321, 0x3Cu, L"http://schemas.microsoft.com/sqlserver/2004/bulkload/format");
  if ( v322 )
  {
    v323 = v322;
    if ( *v322 )
    {
      while ( 1 )
      {
        if ( *v323 == 34 )
        {
          v325 = L"&quot;";
          goto LABEL_503;
        }
        if ( *v323 == 38 )
        {
          v325 = L"&amp;";
          goto LABEL_503;
        }
        if ( *v323 == 39 )
          break;
        if ( *v323 == 60 )
        {
          v325 = L"&lt;";
LABEL_503:
          v324 = v316;
          goto LABEL_504;
        }
        v324 = v316;
        if ( *v323 == 62 )
        {
          v325 = L"&gt;";
LABEL_504:
          CFmtStream::operator<<(v324, v325);
          goto LABEL_505;
        }
        CFmtStream::operator<<(v316, *v323);
LABEL_505:
        if ( !*++v323 )
          goto LABEL_506;
      }
      v325 = L"&apos;";
      goto LABEL_503;
    }
  }
LABEL_506:
  if ( v322 )
    ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v322);
  CFmtStream::operator<<(v316, L"\"");
  v326 = CFmtStream::operator<<(v316, L" ");
  v327 = CFmtStream::operator<<(v326, L"xmlns:xsi");
  CFmtStream::operator<<(v327, L"=\"");
  v328 = 84;
  if ( !is_mul_ok(0x2Au, 2u) )
    v328 = -1;
  v329 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v328);
  v330 = v329;
  v666 = v329;
  if ( v329 )
    StringCchCopyW(v329, 0x2Au, L"http://www.w3.org/2001/XMLSchema-instance");
  if ( v330 )
  {
    v331 = v330;
    if ( *v330 )
    {
      while ( 1 )
      {
        if ( *v331 == 34 )
        {
          v333 = L"&quot;";
          goto LABEL_525;
        }
        if ( *v331 == 38 )
        {
          v333 = L"&amp;";
          goto LABEL_525;
        }
        if ( *v331 == 39 )
          break;
        if ( *v331 == 60 )
        {
          v333 = L"&lt;";
LABEL_525:
          v332 = v316;
          goto LABEL_526;
        }
        v332 = v316;
        if ( *v331 == 62 )
        {
          v333 = L"&gt;";
LABEL_526:
          CFmtStream::operator<<(v332, v333);
          goto LABEL_527;
        }
        CFmtStream::operator<<(v316, *v331);
LABEL_527:
        if ( !*++v331 )
          goto LABEL_528;
      }
      v333 = L"&apos;";
      goto LABEL_525;
    }
  }
LABEL_528:
  if ( v330 )
    ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v330);
  CFmtStream::operator<<(v316, L"\"");
  CFmtStream::operator<<(v316, L">");
  v334 = CFmtStream::operator<<(v316, L"\r\n <");
  CFmtStream::operator<<(v334, L"RECORD");
  CFmtStream::operator<<(v316, L">");
  v335 = 0;
  v336 = 0;
  v669 = 0;
  v337 = NumOfElements;
  while ( v335 < (unsigned int)NumOfElements )
  {
    v338 = (char *)Base + 56 * (_QWORD)v336;
    if ( !*((_DWORD *)v338 + 4) && !*((_DWORD *)v338 + 5) )
    {
      v339 = *((_QWORD *)v338 + 3);
      v340 = &WideCharStr;
      v341 = v339 == 0;
      if ( v339 )
        v340 = (const OLECHAR *)*((_QWORD *)v338 + 3);
      v342 = &WideCharStr;
      v343 = 1;
      do
      {
        if ( !v343 )
          break;
        v341 = *v340++ == *v342++;
        --v343;
      }
      while ( v341 );
      if ( v341 )
        goto LABEL_781;
    }
    v344 = CFmtStream::operator<<(v316, L"\r\n  <");
    CFmtStream::operator<<(v344, L"FIELD");
    v345 = *(_DWORD *)v338;
    v346 = CFmtStream::operator<<(v316, L" ");
    v347 = CFmtStream::operator<<(v346, L"ID");
    v348 = CFmtStream::operator<<(v347, L"=\"");
    v349 = _ultow(v345, Buffer, 10);
    v350 = CFmtStream::operator<<(v348, v349);
    CFmtStream::operator<<(v350, L"\"");
    v351 = *((_QWORD *)v338 + 1);
    v352 = &WideCharStr;
    v353 = v351 == 0;
    if ( v351 )
      v352 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v354 = L"SQLTEXT";
    v355 = 8;
    do
    {
      if ( !v355 )
        break;
      v353 = *v352++ == *v354++;
      --v355;
    }
    while ( v353 );
    if ( v353 )
      goto LABEL_595;
    v356 = &WideCharStr;
    v357 = v351 == 0;
    if ( v351 )
      v356 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v358 = L"SQLCHAR";
    v359 = 8;
    do
    {
      if ( !v359 )
        break;
      v357 = *v356++ == *v358++;
      --v359;
    }
    while ( v357 );
    if ( v357 )
      goto LABEL_595;
    v360 = &WideCharStr;
    v361 = v351 == 0;
    if ( v351 )
      v360 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v362 = L"SQLVARYCHAR";
    v363 = 12;
    do
    {
      if ( !v363 )
        break;
      v361 = *v360++ == *v362++;
      --v363;
    }
    while ( v361 );
    if ( v361 )
      goto LABEL_595;
    v364 = &WideCharStr;
    v365 = v351 == 0;
    if ( v351 )
      v364 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v366 = L"SYBTEXT";
    v367 = 8;
    do
    {
      if ( !v367 )
        break;
      v365 = *v364++ == *v366++;
      --v367;
    }
    while ( v365 );
    if ( v365 )
      goto LABEL_595;
    v368 = &WideCharStr;
    v369 = v351 == 0;
    if ( v351 )
      v368 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v370 = L"SYBCHAR";
    v371 = 8;
    do
    {
      if ( !v371 )
        break;
      v369 = *v368++ == *v370++;
      --v371;
    }
    while ( v369 );
    if ( v369 )
      goto LABEL_595;
    v372 = &WideCharStr;
    v373 = v351 == 0;
    if ( v351 )
      v372 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v374 = L"SYBVARYCHAR";
    v375 = 12;
    do
    {
      if ( !v375 )
        break;
      v373 = *v372++ == *v374++;
      --v375;
    }
    while ( v373 );
    if ( v373 )
    {
LABEL_595:
      v388 = 1;
    }
    else
    {
      v376 = &WideCharStr;
      v377 = v351 == 0;
      if ( v351 )
        v376 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v378 = L"SQLNTEXT";
      v379 = 9;
      do
      {
        if ( !v379 )
          break;
        v377 = *v376++ == *v378++;
        --v379;
      }
      while ( v377 );
      if ( v377 )
        goto LABEL_594;
      v380 = &WideCharStr;
      v381 = v351 == 0;
      if ( v351 )
        v380 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v382 = L"SQLNCHAR";
      v383 = 9;
      do
      {
        if ( !v383 )
          break;
        v381 = *v380++ == *v382++;
        --v383;
      }
      while ( v381 );
      if ( v381 )
        goto LABEL_594;
      v384 = &WideCharStr;
      v385 = v351 == 0;
      if ( v351 )
        v384 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v386 = L"SQLNVARCHAR";
      v387 = 12;
      do
      {
        if ( !v387 )
          break;
        v385 = *v384++ == *v386++;
        --v387;
      }
      while ( v385 );
      if ( v385 )
LABEL_594:
        v388 = 2;
      else
        v388 = 3;
    }
    v389 = *((_QWORD *)v338 + 1);
    v390 = &WideCharStr;
    v391 = v389 == 0;
    if ( v389 )
      v390 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v392 = L"SQLVARYCHAR";
    v393 = 12;
    do
    {
      if ( !v393 )
        break;
      v391 = *v390++ == *v392++;
      --v393;
    }
    while ( v391 );
    if ( v391 )
      goto LABEL_620;
    v394 = &WideCharStr;
    v395 = v389 == 0;
    if ( v389 )
      v394 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v396 = L"SYBVARYCHAR";
    v397 = 12;
    do
    {
      if ( !v397 )
        break;
      v395 = *v394++ == *v396++;
      --v397;
    }
    while ( v395 );
    if ( v395 )
      goto LABEL_620;
    v398 = &WideCharStr;
    v399 = v389 == 0;
    if ( v389 )
      v398 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v400 = L"SQLVARYBIN";
    v401 = 11;
    do
    {
      if ( !v401 )
        break;
      v399 = *v398++ == *v400++;
      --v401;
    }
    while ( v399 );
    if ( v399 )
      goto LABEL_620;
    v402 = &WideCharStr;
    v403 = v389 == 0;
    if ( v389 )
      v402 = (const OLECHAR *)*((_QWORD *)v338 + 1);
    v404 = L"SYBVARYBIN";
    v405 = 11;
    do
    {
      if ( !v405 )
        break;
      v403 = *v402++ == *v404++;
      --v405;
    }
    while ( v403 );
    if ( v403 )
    {
LABEL_620:
      v406 = *((_DWORD *)v338 + 4);
      if ( !v406 )
        v406 = 2;
      *((_DWORD *)v338 + 4) = v406;
    }
    if ( *((_DWORD *)v338 + 4) )
    {
      if ( v388 == 1 )
      {
        v416 = CFmtStream::operator<<(v316, L" ");
        v417 = CFmtStream::operator<<(v416, L"xsi:type");
        CFmtStream::operator<<(v417, L"=\"");
        v418 = 22;
        if ( !is_mul_ok(0xBu, 2u) )
          v418 = -1;
        v419 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v418);
        v411 = v419;
        v666 = v419;
        if ( v419 )
          StringCchCopyW(v419, 0xBu, L"CharPrefix");
      }
      else if ( v388 == 2 )
      {
        v412 = CFmtStream::operator<<(v316, L" ");
        v413 = CFmtStream::operator<<(v412, L"xsi:type");
        CFmtStream::operator<<(v413, L"=\"");
        v414 = 24;
        if ( !is_mul_ok(0xCu, 2u) )
          v414 = -1;
        v415 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v414);
        v411 = v415;
        v666 = v415;
        if ( v415 )
          StringCchCopyW(v415, 0xCu, L"NCharPrefix");
      }
      else
      {
        v407 = CFmtStream::operator<<(v316, L" ");
        v408 = CFmtStream::operator<<(v407, L"xsi:type");
        CFmtStream::operator<<(v408, L"=\"");
        v409 = 26;
        if ( !is_mul_ok(0xDu, 2u) )
          v409 = -1;
        v410 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v409);
        v411 = v410;
        v666 = v410;
        if ( v410 )
          StringCchCopyW(v410, 0xDu, L"NativePrefix");
      }
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)&v666);
      if ( v411 )
        ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v411);
      CFmtStream::operator<<(v316, L"\"");
      v420 = *((_DWORD *)v338 + 4);
      v421 = CFmtStream::operator<<(v316, L" ");
      v422 = CFmtStream::operator<<(v421, L"PREFIX_LENGTH");
      v423 = CFmtStream::operator<<(v422, L"=\"");
      v424 = _ultow(v420, Buffer, 10);
      v425 = CFmtStream::operator<<(v423, v424);
      CFmtStream::operator<<(v425, L"\"");
      if ( v388 == 1 || v388 == 2 )
        goto LABEL_668;
      v426 = *((_QWORD *)v338 + 1);
      v427 = &WideCharStr;
      v428 = v426 == 0;
      if ( v426 )
        v427 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v429 = L"SQLBINARY";
      v430 = 10;
      do
      {
        if ( !v430 )
          break;
        v428 = *v427++ == *v429++;
        --v430;
      }
      while ( v428 );
      if ( v428 )
        goto LABEL_668;
      v431 = &WideCharStr;
      v432 = v426 == 0;
      if ( v426 )
        v431 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v433 = L"SQLVARYBIN";
      v434 = 11;
      do
      {
        if ( !v434 )
          break;
        v432 = *v431++ == *v433++;
        --v434;
      }
      while ( v432 );
      if ( v432 )
        goto LABEL_668;
      v435 = &WideCharStr;
      v436 = v426 == 0;
      if ( v426 )
        v435 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v437 = L"SYBBINARY";
      v438 = 10;
      do
      {
        if ( !v438 )
          break;
        v436 = *v435++ == *v437++;
        --v438;
      }
      while ( v436 );
      if ( v436 )
        goto LABEL_668;
      v439 = &WideCharStr;
      v440 = v426 == 0;
      if ( v426 )
        v439 = (const OLECHAR *)*((_QWORD *)v338 + 1);
      v441 = L"SYBVARYBIN";
      v442 = 11;
      do
      {
        if ( !v442 )
          break;
        v440 = *v439++ == *v441++;
        --v442;
      }
      while ( v440 );
      if ( v440 )
      {
LABEL_668:
        v443 = *((_DWORD *)v338 + 5);
        if ( v443 )
        {
          v444 = CFmtStream::operator<<(v316, L" ");
          v445 = CFmtStream::operator<<(v444, L"MAX_LENGTH");
          v446 = CFmtStream::operator<<(v445, L"=\"");
          v447 = _ultow(v443, Buffer, 10);
          v448 = CFmtStream::operator<<(v446, v447);
          CFmtStream::operator<<(v448, L"\"");
        }
      }
      if ( v388 != 3 )
      {
        v449 = *((_QWORD *)v338 + 6);
        v450 = &WideCharStr;
        v451 = v449 == 0;
        if ( v449 )
          v450 = (const OLECHAR *)*((_QWORD *)v338 + 6);
        v452 = &WideCharStr;
        v453 = 1;
        do
        {
          if ( !v453 )
            break;
          v451 = *v450++ == *v452++;
          --v453;
        }
        while ( v451 );
        if ( !v451 )
        {
          v454 = CFmtStream::operator<<(v316, L" ");
          v455 = CFmtStream::operator<<(v454, L"COLLATION");
          CFmtStream::operator<<(v455, L"=\"");
          CFmtStream::WriteXMLString(v316, (const struct CWStr *)((char *)Base + 56 * v335 + 48));
          CFmtStream::operator<<(v316, L"\"");
        }
      }
      v456 = *((_QWORD *)v338 + 3);
      v457 = &WideCharStr;
      v458 = v456 == 0;
      if ( v456 )
        v457 = (const OLECHAR *)*((_QWORD *)v338 + 3);
      v459 = &WideCharStr;
      v460 = 1;
      do
      {
        if ( !v460 )
          break;
        v458 = *v457++ == *v459++;
        --v460;
      }
      while ( v458 );
      if ( v458 )
        goto LABEL_780;
      CFmtStream::operator<<(v316, L"/>");
      v461 = CFmtStream::operator<<(v316, L"\r\n  <");
      CFmtStream::operator<<(v461, L"FIELD");
      if ( v388 == 1 )
      {
        v471 = CFmtStream::operator<<(v316, L" ");
        v472 = CFmtStream::operator<<(v471, L"xsi:type");
        CFmtStream::operator<<(v472, L"=\"");
        v473 = 18;
        if ( !is_mul_ok(9u, 2u) )
          v473 = -1;
        v474 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v473);
        v466 = v474;
        v666 = v474;
        if ( v474 )
          StringCchCopyW(v474, 9u, L"CharTerm");
      }
      else if ( v388 == 2 )
      {
        v467 = CFmtStream::operator<<(v316, L" ");
        v468 = CFmtStream::operator<<(v467, L"xsi:type");
        CFmtStream::operator<<(v468, L"=\"");
        v469 = 20;
        if ( !is_mul_ok(0xAu, 2u) )
          v469 = -1;
        v470 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v469);
        v466 = v470;
        v666 = v470;
        if ( v470 )
          StringCchCopyW(v470, 0xAu, L"NCharTerm");
      }
      else
      {
        v462 = CFmtStream::operator<<(v316, L" ");
        v463 = CFmtStream::operator<<(v462, L"xsi:type");
        CFmtStream::operator<<(v463, L"=\"");
        v464 = 22;
        if ( !is_mul_ok(0xBu, 2u) )
          v464 = -1;
        v465 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v464);
        v466 = v465;
        v666 = v465;
        if ( v465 )
          StringCchCopyW(v465, 0xBu, L"NativeTerm");
      }
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)&v666);
      if ( v466 )
        ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v466);
      CFmtStream::operator<<(v316, L"\"");
      v475 = CFmtStream::operator<<(v316, L" ");
      v476 = CFmtStream::operator<<(v475, L"TERMINATOR");
      CFmtStream::operator<<(v476, L"=\"");
      v477 = (char *)Base + 56 * v335;
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)(v477 + 24));
      CFmtStream::operator<<(v316, L"\"");
      v478 = CFmtStream::operator<<(v316, L" ");
      v479 = CFmtStream::operator<<(v478, L"MAX_LENGTH");
      v480 = CFmtStream::operator<<(v479, L"=\"");
      v481 = _ultow(2u, Buffer, 10);
      v482 = CFmtStream::operator<<(v480, v481);
    }
    else
    {
      v490 = *((_QWORD *)v338 + 3);
      v491 = &WideCharStr;
      v492 = v490 == 0;
      if ( v490 )
        v491 = (const OLECHAR *)*((_QWORD *)v338 + 3);
      v493 = &WideCharStr;
      v494 = 1;
      do
      {
        if ( !v494 )
          break;
        v492 = *v491++ == *v493++;
        --v494;
      }
      while ( v492 );
      if ( v492 )
      {
        if ( *((_DWORD *)v338 + 5) )
        {
          if ( v388 == 1 )
          {
            v534 = CFmtStream::operator<<(v316, L" ");
            v535 = CFmtStream::operator<<(v534, L"xsi:type");
            CFmtStream::operator<<(v535, L"=\"");
            CWStr::CWStr((CWStr *)&v671, L"CharFixed");
            CFmtStream::WriteXMLString(v316, (const struct CWStr *)&v671);
            v533 = v671;
          }
          else
          {
            v531 = CFmtStream::operator<<(v316, L" ");
            v532 = CFmtStream::operator<<(v531, L"xsi:type");
            CFmtStream::operator<<(v532, L"=\"");
            if ( v388 == 2 )
            {
              CWStr::CWStr((CWStr *)&EndPtr, L"NCharFixed");
              CFmtStream::WriteXMLString(v316, (const struct CWStr *)&EndPtr);
              v533 = EndPtr;
            }
            else
            {
              CWStr::CWStr((CWStr *)&v664, L"NativeFixed");
              CFmtStream::WriteXMLString(v316, (const struct CWStr *)&v664);
              v533 = (char *)v664;
            }
          }
          if ( v533 )
            ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
          CFmtStream::operator<<(v316, L"\"");
          v536 = CFmtStream::operator<<(v316, L" ");
          v537 = CFmtStream::operator<<(v536, L"LENGTH");
          v538 = CFmtStream::operator<<(v537, L"=\"");
          v539 = CFmtStream::operator<<(v538, *((unsigned int *)v338 + 5));
          CFmtStream::operator<<(v539, L"\"");
          if ( v388 != 3 )
          {
            v540 = *((_QWORD *)v338 + 6);
            v541 = &WideCharStr;
            v542 = v540 == 0;
            if ( v540 )
              v541 = (const OLECHAR *)*((_QWORD *)v338 + 6);
            v543 = &WideCharStr;
            v544 = 1;
            do
            {
              if ( !v544 )
                break;
              v542 = *v541++ == *v543++;
              --v544;
            }
            while ( v542 );
            if ( !v542 )
            {
              v545 = CFmtStream::operator<<(v316, L" ");
              v546 = CFmtStream::operator<<(v545, L"COLLATION");
              CFmtStream::operator<<(v546, L"=\"");
              CFmtStream::WriteXMLString(v316, (const struct CWStr *)((char *)Base + 56 * v335 + 48));
              CFmtStream::operator<<(v316, L"\"");
            }
          }
        }
        goto LABEL_780;
      }
      if ( v388 == 1 )
      {
        v504 = CFmtStream::operator<<(v316, L" ");
        v505 = CFmtStream::operator<<(v504, L"xsi:type");
        CFmtStream::operator<<(v505, L"=\"");
        v506 = 18;
        if ( !is_mul_ok(9u, 2u) )
          v506 = -1;
        v507 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v506);
        v499 = v507;
        v666 = v507;
        if ( v507 )
          StringCchCopyW(v507, 9u, L"CharTerm");
      }
      else if ( v388 == 2 )
      {
        v500 = CFmtStream::operator<<(v316, L" ");
        v501 = CFmtStream::operator<<(v500, L"xsi:type");
        CFmtStream::operator<<(v501, L"=\"");
        v502 = 20;
        if ( !is_mul_ok(0xAu, 2u) )
          v502 = -1;
        v503 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v502);
        v499 = v503;
        v666 = v503;
        if ( v503 )
          StringCchCopyW(v503, 0xAu, L"NCharTerm");
      }
      else
      {
        v495 = CFmtStream::operator<<(v316, L" ");
        v496 = CFmtStream::operator<<(v495, L"xsi:type");
        CFmtStream::operator<<(v496, L"=\"");
        v497 = 22;
        if ( !is_mul_ok(0xBu, 2u) )
          v497 = -1;
        v498 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(
                                     g_pMO,
                                     v497);
        v499 = v498;
        v666 = v498;
        if ( v498 )
          StringCchCopyW(v498, 0xBu, L"NativeTerm");
      }
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)&v666);
      if ( v499 )
        ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v499);
      CFmtStream::operator<<(v316, L"\"");
      v508 = CFmtStream::operator<<(v316, L" ");
      v509 = CFmtStream::operator<<(v508, L"TERMINATOR");
      CFmtStream::operator<<(v509, L"=\"");
      v477 = (char *)Base + 56 * v335;
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)(v477 + 24));
      CFmtStream::operator<<(v316, L"\"");
      if ( v388 != 1 && v388 != 2 )
      {
        v510 = *((_QWORD *)v338 + 1);
        v511 = &WideCharStr;
        v512 = v510 == 0;
        if ( v510 )
          v511 = (const OLECHAR *)*((_QWORD *)v338 + 1);
        v513 = L"SQLBINARY";
        v514 = 10;
        do
        {
          if ( !v514 )
            break;
          v512 = *v511++ == *v513++;
          --v514;
        }
        while ( v512 );
        if ( !v512 )
        {
          v515 = &WideCharStr;
          v516 = v510 == 0;
          if ( v510 )
            v515 = (const OLECHAR *)*((_QWORD *)v338 + 1);
          v517 = L"SQLVARYBIN";
          v518 = 11;
          do
          {
            if ( !v518 )
              break;
            v516 = *v515++ == *v517++;
            --v518;
          }
          while ( v516 );
          if ( !v516 )
          {
            v519 = &WideCharStr;
            v520 = v510 == 0;
            if ( v510 )
              v519 = (const OLECHAR *)*((_QWORD *)v338 + 1);
            v521 = L"SYBBINARY";
            v522 = 10;
            do
            {
              if ( !v522 )
                break;
              v520 = *v519++ == *v521++;
              --v522;
            }
            while ( v520 );
            if ( !v520 )
            {
              v523 = &WideCharStr;
              v524 = v510 == 0;
              if ( v510 )
                v523 = (const OLECHAR *)*((_QWORD *)v338 + 1);
              v525 = L"SYBVARYBIN";
              v526 = 11;
              do
              {
                if ( !v526 )
                  break;
                v524 = *v523++ == *v525++;
                --v526;
              }
              while ( v524 );
              if ( !v524 )
                goto LABEL_704;
            }
          }
        }
      }
      v527 = *((_DWORD *)v338 + 5);
      if ( !v527 )
        goto LABEL_704;
      v528 = CFmtStream::operator<<(v316, L" ");
      v529 = CFmtStream::operator<<(v528, L"MAX_LENGTH");
      v530 = CFmtStream::operator<<(v529, L"=\"");
      v482 = CFmtStream::operator<<(v530, v527);
    }
    CFmtStream::operator<<(v482, L"\"");
LABEL_704:
    if ( v388 != 3 )
    {
      v483 = *((_QWORD *)v338 + 6);
      v484 = &WideCharStr;
      v485 = v483 == 0;
      if ( v483 )
        v484 = (const OLECHAR *)*((_QWORD *)v338 + 6);
      v486 = &WideCharStr;
      v487 = 1;
      do
      {
        if ( !v487 )
          break;
        v485 = *v484++ == *v486++;
        --v487;
      }
      while ( v485 );
      if ( !v485 )
      {
        v488 = CFmtStream::operator<<(v316, L" ");
        v489 = CFmtStream::operator<<(v488, L"COLLATION");
        CFmtStream::operator<<(v489, L"=\"");
        CFmtStream::WriteXMLString(v316, (const struct CWStr *)(v477 + 48));
        CFmtStream::operator<<(v316, L"\"");
      }
    }
LABEL_780:
    CFmtStream::operator<<(v316, L"/>");
LABEL_781:
    ++v335;
    v336 = ++v669;
    v337 = NumOfElements;
  }
  v547 = CFmtStream::operator<<(v316, L"\r\n </");
  v548 = CFmtStream::operator<<(v547, L"RECORD");
  CFmtStream::operator<<(v548, L">");
  v549 = CFmtStream::operator<<(v316, L"\r\n <");
  CFmtStream::operator<<(v549, L"ROW");
  CFmtStream::operator<<(v316, L">");
  v550 = (char *)Base;
  qsort(Base, v337, 0x38u, CBCPFormatField::CompareFunc);
  v551 = 0;
  LODWORD(v672) = 0;
  v552 = 0;
  v553 = 1;
  for ( pExceptionObject = 0; (unsigned int)v551 < v337; v550 = (char *)Base )
  {
    v554 = &v550[56 * v552];
    if ( !*((_DWORD *)v554 + 4) && !*((_DWORD *)v554 + 5) )
    {
      v555 = *((_QWORD *)v554 + 3);
      v556 = &WideCharStr;
      v557 = v555 == 0;
      if ( v555 )
        v556 = (const OLECHAR *)*((_QWORD *)v554 + 3);
      v558 = &WideCharStr;
      v559 = 1;
      do
      {
        if ( !v559 )
          break;
        v557 = *v556++ == *v558++;
        --v559;
      }
      while ( v557 );
      v337 = NumOfElements;
      if ( v557 )
        goto LABEL_913;
    }
    v560 = *((_DWORD *)v554 + 8);
    if ( !v560 )
      goto LABEL_913;
    if ( v679 )
      v561 = v679 + 76LL * (unsigned int)v551;
    else
      v561 = 0;
    if ( v553 < v560 )
    {
      do
      {
        ++v553;
        v562 = CFmtStream::operator<<(v316, L"\r\n  <");
        CFmtStream::operator<<(v562, L"COLUMN");
        CFmtStream::operator<<(v316, L"/>");
      }
      while ( v553 < *((_DWORD *)v554 + 8) );
    }
    v553 = *((_DWORD *)v554 + 8) + 1;
    v563 = CFmtStream::operator<<(v316, L"\r\n  <");
    CFmtStream::operator<<(v563, L"COLUMN");
    v564 = *(_DWORD *)v554;
    v565 = CFmtStream::operator<<(v316, L" ");
    v566 = CFmtStream::operator<<(v565, L"SOURCE");
    v567 = CFmtStream::operator<<(v566, L"=\"");
    v568 = _ultow(v564, Buffer, 10);
    v569 = CFmtStream::operator<<(v567, v568);
    CFmtStream::operator<<(v569, L"\"");
    v570 = CFmtStream::operator<<(v316, L" ");
    v571 = CFmtStream::operator<<(v570, L"NAME");
    CFmtStream::operator<<(v571, L"=\"");
    v572 = (char *)Base + 56 * v551;
    CFmtStream::WriteXMLString(v316, (const struct CWStr *)(v572 + 40));
    CFmtStream::operator<<(v316, L"\"");
    v573 = *((_QWORD *)v554 + 1);
    v574 = &WideCharStr;
    v575 = v573 == 0;
    if ( v573 )
      v574 = (const OLECHAR *)*((_QWORD *)v554 + 1);
    v576 = L"SQLCHAR";
    v577 = 8;
    do
    {
      if ( !v577 )
        break;
      v575 = *v574++ == *v576++;
      --v577;
    }
    while ( v575 );
    if ( v575 )
      goto LABEL_928;
    v578 = &WideCharStr;
    v579 = v573 == 0;
    if ( v573 )
      v578 = (const OLECHAR *)*((_QWORD *)v554 + 1);
    v580 = L"SQLVARYCHAR";
    v581 = 12;
    do
    {
      if ( !v581 )
        break;
      v579 = *v578++ == *v580++;
      --v581;
    }
    while ( v579 );
    if ( v579 )
      goto LABEL_928;
    v582 = &WideCharStr;
    v583 = v573 == 0;
    if ( v573 )
      v582 = (const OLECHAR *)*((_QWORD *)v554 + 1);
    v584 = L"SYBCHAR";
    v585 = 8;
    do
    {
      if ( !v585 )
        break;
      v583 = *v582++ == *v584++;
      --v585;
    }
    while ( v583 );
    if ( v583 )
      goto LABEL_928;
    v586 = &WideCharStr;
    v587 = v573 == 0;
    if ( v573 )
      v586 = (const OLECHAR *)*((_QWORD *)v554 + 1);
    v588 = L"SYBVARYCHAR";
    v589 = 12;
    do
    {
      if ( !v589 )
        break;
      v587 = *v586++ == *v588++;
      --v589;
    }
    while ( v587 );
    if ( v587 )
      goto LABEL_928;
    v590 = &WideCharStr;
    v591 = v573 == 0;
    if ( v573 )
      v590 = (const OLECHAR *)*((_QWORD *)v554 + 1);
    v592 = L"SQLNCHAR";
    v593 = 9;
    do
    {
      if ( !v593 )
        break;
      v591 = *v590++ == *v592++;
      --v593;
    }
    while ( v591 );
    if ( v591 || (unsigned __int8)CWStr::operator==(v572 + 8, L"SQLNVARCHAR") )
    {
LABEL_928:
      if ( !v561 || *(_DWORD *)v561 )
        goto LABEL_912;
      v607 = CFmtStream::operator<<(v316, L" ");
      v608 = CFmtStream::operator<<(v607, L"xsi:type");
      CFmtStream::operator<<(v608, L"=\"");
      if ( v561 == -4 )
        v674 = 0;
      else
        CWStr::CWStr((CWStr *)&v674, (const unsigned __int16 *)(v561 + 4));
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)&v674);
      if ( v674 )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
      CFmtStream::operator<<(v316, L"\"");
      if ( v561 == -4 )
      {
        v669 = 0;
        v609 = &v669;
      }
      else
      {
        v609 = (char **)CWStr::CWStr((CWStr *)&v669, (const unsigned __int16 *)(v561 + 4));
      }
      v610 = v665 | 1;
      v665 |= 1u;
      v611 = *v609;
      v612 = &WideCharStr;
      v613 = v611 == 0;
      if ( v611 )
        v612 = (const OLECHAR *)v611;
      v614 = L"SQLDECIMAL";
      v615 = 11;
      do
      {
        if ( !v615 )
          break;
        v613 = *v612++ == *v614++;
        --v615;
      }
      while ( v613 );
      if ( v613 )
        goto LABEL_862;
      if ( v561 == -4 )
      {
        v675 = 0;
        v616 = (CWStr *)&v675;
      }
      else
      {
        v616 = CWStr::CWStr((CWStr *)&v675, (const unsigned __int16 *)(v561 + 4));
      }
      v610 |= 2u;
      v665 = v610;
      v617 = *(const OLECHAR **)v616;
      v618 = &WideCharStr;
      v619 = v617 == 0;
      if ( v617 )
        v618 = v617;
      v620 = L"SQLNUMERIC";
      v621 = 11;
      do
      {
        if ( !v621 )
          break;
        v619 = *v618++ == *v620++;
        --v621;
      }
      while ( v619 );
      if ( v619 )
LABEL_862:
        v622 = 1;
      else
        v622 = 0;
      if ( (v610 & 2) != 0 )
      {
        v610 &= ~2u;
        v665 = v610;
        if ( v675 )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
      }
      if ( (v610 & 1) != 0 )
      {
        v610 &= ~1u;
        v665 = v610;
        if ( v669 )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
      }
      if ( v622 )
      {
        v623 = *(unsigned __int8 *)(v561 + 68);
        v624 = CFmtStream::operator<<(v316, L" ");
        v625 = CFmtStream::operator<<(v624, L"PRECISION");
        v626 = CFmtStream::operator<<(v625, L"=\"");
        v627 = CFmtStream::operator<<(v626, v623);
        CFmtStream::operator<<(v627, L"\"");
        v628 = *(unsigned __int8 *)(v561 + 69);
        v629 = CFmtStream::operator<<(v316, L" ");
        v630 = CFmtStream::operator<<(v629, L"SCALE");
        v631 = CFmtStream::operator<<(v630, L"=\"");
        v632 = CFmtStream::operator<<(v631, v628);
        CFmtStream::operator<<(v632, L"\"");
      }
      if ( v561 == -4 )
      {
        v664 = 0;
        v633 = &v664;
      }
      else
      {
        v633 = (__int64 *)CWStr::CWStr((CWStr *)&v664, (const unsigned __int16 *)(v561 + 4));
      }
      v634 = v610 | 4;
      v665 = v634;
      v635 = (const OLECHAR *)*v633;
      v636 = &WideCharStr;
      v637 = v635 == 0;
      if ( v635 )
        v636 = v635;
      v638 = L"SQLTIME";
      v639 = 8;
      do
      {
        if ( !v639 )
          break;
        v637 = *v636++ == *v638++;
        --v639;
      }
      while ( v637 );
      if ( v637 )
        goto LABEL_899;
      if ( v561 == -4 )
      {
        EndPtr = 0;
        p_EndPtr = &EndPtr;
      }
      else
      {
        p_EndPtr = (char **)CWStr::CWStr((CWStr *)&EndPtr, (const unsigned __int16 *)(v561 + 4));
      }
      v634 |= 8u;
      v665 = v634;
      v641 = *p_EndPtr;
      v642 = &WideCharStr;
      v643 = v641 == 0;
      if ( v641 )
        v642 = (const OLECHAR *)v641;
      v644 = L"SQLDATETIME2";
      v645 = 13;
      do
      {
        if ( !v645 )
          break;
        v643 = *v642++ == *v644++;
        --v645;
      }
      while ( v643 );
      if ( v643 )
        goto LABEL_899;
      if ( v561 == -4 )
      {
        v671 = 0;
        v646 = &v671;
      }
      else
      {
        v646 = (char **)CWStr::CWStr((CWStr *)&v671, (const unsigned __int16 *)(v561 + 4));
      }
      v634 |= 0x10u;
      v665 = v634;
      v647 = *v646;
      v648 = &WideCharStr;
      v649 = v647 == 0;
      if ( v647 )
        v648 = (const OLECHAR *)v647;
      v650 = L"SQLDATETIMEOFFSET";
      v651 = 18;
      do
      {
        if ( !v651 )
          break;
        v649 = *v648++ == *v650++;
        --v651;
      }
      while ( v649 );
      if ( v649 )
LABEL_899:
        v652 = 1;
      else
        v652 = 0;
      if ( (v634 & 0x10) != 0 )
      {
        v634 &= ~0x10u;
        v665 = v634;
        if ( v671 )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
      }
      if ( (v634 & 8) != 0 )
      {
        v634 &= ~8u;
        v665 = v634;
        if ( EndPtr )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
      }
      if ( (v634 & 4) != 0 )
      {
        v665 = v634 & 0xFFFFFFFB;
        if ( v664 )
          ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].Realloc)(g_pMO);
      }
      v606 = v652 == 0;
    }
    else
    {
      v594 = CFmtStream::operator<<(v316, L" ");
      v595 = CFmtStream::operator<<(v594, L"xsi:type");
      CFmtStream::operator<<(v595, L"=\"");
      CFmtStream::WriteXMLString(v316, (const struct CWStr *)(v572 + 8));
      CFmtStream::operator<<(v316, L"\"");
      if ( !v561 || *(_DWORD *)v561 )
        goto LABEL_912;
      if ( (unsigned __int8)CWStr::operator==(v572 + 8, L"SQLDECIMAL")
        || (unsigned __int8)CWStr::operator==(v572 + 8, L"SQLNUMERIC") )
      {
        v596 = *(unsigned __int8 *)(v561 + 68);
        v597 = CFmtStream::operator<<(v316, L" ");
        v598 = CFmtStream::operator<<(v597, L"PRECISION");
        v599 = CFmtStream::operator<<(v598, L"=\"");
        v600 = CFmtStream::operator<<(v599, v596);
        CFmtStream::operator<<(v600, L"\"");
        v601 = *(unsigned __int8 *)(v561 + 69);
        v602 = CFmtStream::operator<<(v316, L" ");
        v603 = CFmtStream::operator<<(v602, L"SCALE");
        v604 = CFmtStream::operator<<(v603, L"=\"");
        v605 = CFmtStream::operator<<(v604, v601);
        CFmtStream::operator<<(v605, L"\"");
      }
      if ( (unsigned __int8)CWStr::operator==(v572 + 8, L"SQLTIME")
        || (unsigned __int8)CWStr::operator==(v572 + 8, L"SQLDATETIME2") )
      {
LABEL_911:
        v653 = *(unsigned __int8 *)(v561 + 69);
        v654 = CFmtStream::operator<<(v316, L" ");
        v655 = CFmtStream::operator<<(v654, L"SCALE");
        v656 = CFmtStream::operator<<(v655, L"=\"");
        v657 = CFmtStream::operator<<(v656, v653);
        CFmtStream::operator<<(v657, L"\"");
        goto LABEL_912;
      }
      v606 = (unsigned __int8)CWStr::operator==(v572 + 8, L"SQLDATETIMEOFFSET") == 0;
    }
    if ( !v606 )
      goto LABEL_911;
LABEL_912:
    CFmtStream::operator<<(v316, L"/>");
    LODWORD(v551) = v672;
    v337 = NumOfElements;
LABEL_913:
    v551 = (unsigned int)(v551 + 1);
    LODWORD(v672) = v551;
    v552 = ++pExceptionObject;
  }
  v658 = CFmtStream::operator<<(v316, L"\r\n </");
  v659 = CFmtStream::operator<<(v658, L"ROW");
  CFmtStream::operator<<(v659, L">");
  v660 = CFmtStream::operator<<(v316, L"\r\n</");
  v661 = CFmtStream::operator<<(v660, L"BCPFORMAT");
  CFmtStream::operator<<(v661, L">");
  v662 = v678;
  *v678 = v316;
  if ( v316 )
    (*(void (__fastcall **)(CFmtStream *))(*(_QWORD *)v316 + 8LL))(v316);
  v665 |= 0x20u;
  if ( v681[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v681[0] + 16LL))(v681[0]);
  if ( v316 )
    (*(void (__fastcall **)(CFmtStream *))(*(_QWORD *)v316 + 16LL))(v316);
  `eh vector destructor iterator'(
    v550,
    0x38u,
    *((_DWORD *)v550 - 2),
    (void (*)(void *))CBCPFormatField::~CBCPFormatField);
  if ( v550 != (char *)8 )
    ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v550 - 8);
  if ( *(_QWORD *)v676 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v676 + 16LL))(*(_QWORD *)v676);
  return v662;
}

```

## disassembly

```asm
0x383aac690  push    rbp
0x383aac692  push    rbx
0x383aac693  push    rsi
0x383aac694  push    rdi
0x383aac695  push    r12
0x383aac697  push    r13
0x383aac699  push    r14
0x383aac69b  push    r15
0x383aac69d  lea     rbp, [rsp-1068h]
0x383aac6a5  mov     eax, 1168h
0x383aac6aa  call    _alloca_probe
0x383aac6af  sub     rsp, rax
0x383aac6b2  mov     [rbp+10A0h+var_10D8], 0FFFFFFFFFFFFFFFEh
0x383aac6ba  mov     rax, cs:__security_cookie
0x383aac6c1  xor     rax, rsp
0x383aac6c4  mov     [rbp+10A0h+var_50], rax
0x383aac6cb  mov     [rbp+10A0h+var_10F8], r9
0x383aac6cf  mov     rsi, r8
0x383aac6d2  mov     [rbp+10A0h+var_1110], r8
0x383aac6d6  mov     [rbp+10A0h+var_1100], rdx
0x383aac6da  mov     rdi, rcx
0x383aac6dd  mov     [rbp+10A0h+var_10E8], rdx
0x383aac6e1  mov     [rbp+10A0h+var_10E0], r8
0x383aac6e5  xor     r14d, r14d
0x383aac6e8  mov     [rsp+11A0h+var_1168], r14d
0x383aac6ed  mov     [rbp+10A0h+var_1108], r14
0x383aac6f1  lea     rcx, [rbp+10A0h+var_10F0]
0x383aac6f5  call    ?Create@CFmtStream@@SA?AV?$CComPtr@VCFmtStream@@@@XZ; CFmtStream::Create(void)
0x383aac6fa  nop
0x383aac6fb  mov     rcx, [rsi]
0x383aac6fe  mov     [rbp+10A0h+var_10D0], rcx
0x383aac702  test    rcx, rcx
0x383aac705  jz      short loc_383AAC70D
0x383aac707  mov     rax, [rcx]
0x383aac70a  call    qword ptr [rax+8]
0x383aac70d  mov     [rbp+10A0h+var_C8], r14
0x383aac714  lea     r12, [rdi+90h]
0x383aac71b  lea     r8, [rbp+10A0h+var_10D0]; struct CBulkFmtStreamReader *
0x383aac71f  or      r13, 0FFFFFFFFFFFFFFFFh
0x383aac723  mov     edx, r13d; int
0x383aac726  mov     rcx, r12; struct CWStr *
0x383aac729  call    ?GetString@@YAXAEAVCWStr@@JAEAVCBulkFmtStreamReader@@@Z; GetString(CWStr &,long,CBulkFmtStreamReader &)
0x383aac72e  mov     rax, [r12]
0x383aac732  lea     rsi, WideCharStr
0x383aac739  test    rax, rax
0x383aac73c  cmovnz  rsi, rax
0x383aac740  lea     rdi, a110_1; "11.0"
0x383aac747  mov     ecx, 5
0x383aac74c  repe cmpsw
0x383aac74f  jz      loc_383AAC840
0x383aac755  lea     rsi, WideCharStr
0x383aac75c  test    rax, rax
0x383aac75f  cmovnz  rsi, rax
0x383aac763  lea     rdi, a100_0; "10.0"
0x383aac76a  mov     ecx, 5
0x383aac76f  repe cmpsw
0x383aac772  jz      loc_383AAC840
0x383aac778  lea     rsi, WideCharStr
0x383aac77f  test    rax, rax
0x383aac782  cmovnz  rsi, rax
0x383aac786  lea     rdi, a90; "9.0"
0x383aac78d  mov     ecx, 4
0x383aac792  repe cmpsw
0x383aac795  jz      loc_383AAC840
0x383aac79b  lea     rsi, WideCharStr
0x383aac7a2  test    rax, rax
0x383aac7a5  cmovnz  rsi, rax
0x383aac7a9  lea     rdi, a80; "8.0"
0x383aac7b0  mov     ecx, 4
0x383aac7b5  repe cmpsw
0x383aac7b8  jz      loc_383AAC840
0x383aac7be  lea     rsi, WideCharStr
0x383aac7c5  test    rax, rax
0x383aac7c8  cmovnz  rsi, rax
0x383aac7cc  lea     rdi, a70_0; "7.0"
0x383aac7d3  mov     ecx, 4
0x383aac7d8  repe cmpsw
0x383aac7db  jz      short loc_383AAC840
0x383aac7dd  lea     rsi, WideCharStr
0x383aac7e4  test    rax, rax
0x383aac7e7  cmovnz  rsi, rax
0x383aac7eb  lea     rdi, a60_0; "6.0"
0x383aac7f2  mov     ecx, 4
0x383aac7f7  repe cmpsw
0x383aac7fa  jz      short loc_383AAC840
0x383aac7fc  lea     rsi, WideCharStr
0x383aac803  test    rax, rax
0x383aac806  cmovnz  rsi, rax
0x383aac80a  lea     rdi, a42_0; "4.2"
0x383aac811  mov     ecx, 4
0x383aac816  repe cmpsw
0x383aac819  jz      short loc_383AAC840
0x383aac81b  mov     [rsp+11A0h+var_1170], 1
0x383aac824  mov     rax, [rsp+11A0h+var_1170]
0x383aac829  mov     [rsp+11A0h+pExceptionObject], rax
0x383aac82e  lea     rdx, _TI1?AVCBcpFmtException@@; pThrowInfo
0x383aac835  lea     rcx, [rsp+11A0h+pExceptionObject]; pExceptionObject
0x383aac83a  call    _CxxThrowException
0x383aac840  lea     rcx, [rbp+10A0h+var_10D0]; this
0x383aac844  call    ?SkipWs@CBulkFmtStreamReader@@AEAAJXZ; CBulkFmtStreamReader::SkipWs(void)
0x383aac849  mov     r8d, 14h; unsigned int
0x383aac84f  lea     rdx, [rbp+10A0h+String]; char *
0x383aac856  lea     rcx, [rbp+10A0h+var_10D0]; this
0x383aac85a  call    ?GetString@CBulkFmtStreamReader@@QEAAJPEADK@Z; CBulkFmtStreamReader::GetString(char *,ulong)
0x383aac85f  test    eax, eax
0x383aac861  jnz     loc_383AAF0AD
0x383aac867  lea     r8d, [rax+0Ah]; Radix
0x383aac86b  lea     rdx, [rsp+11A0h+pExceptionObject]; EndPtr
0x383aac870  lea     rcx, [rbp+10A0h+String]; String
0x383aac877  call    cs:__imp__strtoui64
0x383aac87d  mov     rbx, rax
0x383aac880  mov     [rsp+11A0h+NumOfElements], rax
0x383aac885  cmp     rax, 7FFFFFFFh
0x383aac88b  ja      loc_383AAF0AD
0x383aac891  mov     rcx, [rsp+11A0h+pExceptionObject]
0x383aac896  test    rcx, rcx
0x383aac899  jz      short loc_383AAC8B3
0x383aac89b  movzx   edx, byte ptr [rcx]
0x383aac89e  test    dl, dl
0x383aac8a0  jz      short loc_383AAC8B3
0x383aac8a2  movzx   ecx, dl; C
0x383aac8a5  call    cs:__imp_isspace
0x383aac8ab  test    eax, eax
0x383aac8ad  jz      loc_383AAF0AD
0x383aac8b3  cmp     ebx, 1
0x383aac8b6  jb      loc_383AAF0AD
0x383aac8bc  cmp     ebx, 1000h
0x383aac8c2  ja      loc_383AAF0AD
0x383aac8c8  mov     edi, ebx
0x383aac8ca  mov     eax, 38h ; '8'
0x383aac8cf  mul     rdi
0x383aac8d2  mov     rdx, rax
0x383aac8d5  cmovo   rdx, r13
0x383aac8d9  add     rdx, 8
0x383aac8dd  cmovb   rdx, r13
0x383aac8e1  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383aac8e8  mov     rax, [rcx]
0x383aac8eb  call    qword ptr [rax+70h]
0x383aac8ee  mov     [rsp+11A0h+var_1160], rax
0x383aac8f3  lea     rcx, ??1CBCPFormatField@@QEAA@XZ; CBCPFormatField::~CBCPFormatField(void)
0x383aac8fa  test    rax, rax
0x383aac8fd  jz      short loc_383AAC928
0x383aac8ff  mov     [rax], edi
0x383aac901  lea     r15, [rax+8]
0x383aac905  mov     [rsp+11A0h+Base], r15
0x383aac90a  mov     [rsp+11A0h+var_1180], rcx; void (*)(void *)
0x383aac90f  lea     r9, ??0CBCPFormatField@@QEAA@XZ; void (*)(void *)
0x383aac916  mov     r8d, edi; int
0x383aac919  mov     edx, 38h ; '8'; unsigned __int64
0x383aac91e  mov     rcx, r15; void *
0x383aac921  call    ??_L@YAXPEAX_KHP6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,int,void (*)(void *),void (*)(void *))
0x383aac926  jmp     short loc_383AAC930
0x383aac928  mov     r15, r14
0x383aac92b  mov     [rsp+11A0h+Base], r14
0x383aac930  mov     [rbp+10A0h+var_1108], r15
0x383aac934  test    r15, r15
0x383aac937  jnz     short loc_383AAC953
0x383aac939  mov     dword ptr [rsp+11A0h+var_1130], 8007000Eh
0x383aac941  lea     rdx, _TI1?AVCHRESULTException@@; pThrowInfo
0x383aac948  lea     rcx, [rsp+11A0h+var_1130]; pExceptionObject
0x383aac94d  call    _CxxThrowException
0x383aac953  xor     esi, esi
0x383aac955  mov     [rsp+11A0h+var_1170], rsi
0x383aac95a  test    ebx, ebx
0x383aac95c  jz      loc_383AAD5E2
0x383aac962  lea     rcx, [rbp+10A0h+var_10D0]; this
0x383aac966  call    ?SkipWs@CBulkFmtStreamReader@@AEAAJXZ; CBulkFmtStreamReader::SkipWs(void)
0x383aac96b  mov     r8d, 14h; unsigned int
0x383aac971  lea     rdx, [rbp+10A0h+String]; char *
0x383aac978  lea     rcx, [rbp+10A0h+var_10D0]; this
0x383aac97c  call    ?GetString@CBulkFmtStreamReader@@QEAAJPEADK@Z; CBulkFmtStreamReader::GetString(char *,ulong)
0x383aac981  test    eax, eax
0x383aac983  jnz     loc_383AAD57F
0x383aac989  lea     r8d, [rax+0Ah]; Radix
0x383aac98d  lea     rdx, [rsp+11A0h+pExceptionObject]; EndPtr
0x383aac992  lea     rcx, [rbp+10A0h+String]; String
0x383aac999  call    cs:__imp__strtoui64
0x383aac99f  mov     rdi, rax
0x383aac9a2  cmp     rax, 7FFFFFFFh
0x383aac9a8  ja      loc_383AAD586
0x383aac9ae  mov     rcx, [rsp+11A0h+pExceptionObject]
0x383aac9b3  test    rcx, rcx
0x383aac9b6  jz      short loc_383AAC9D0
0x383aac9b8  movzx   edx, byte ptr [rcx]
0x383aac9bb  test    dl, dl
0x383aac9bd  jz      short loc_383AAC9D0
0x383aac9bf  movzx   ecx, dl; C
0x383aac9c2  call    cs:__imp_isspace
0x383aac9c8  test    eax, eax
0x383aac9ca  jz      loc_383AAD586
0x383aac9d0  mov     rbx, rsi
0x383aac9d3  imul    rbx, 38h ; '8'
0x383aac9d7  add     rbx, r15
0x383aac9da  mov     [rbx], edi
0x383aac9dc  lea     r13d, [r14+1]
0x383aac9e0  cmp     edi, r13d
0x383aac9e3  jnz     loc_383AAD586
0x383aac9e9  mov     eax, r14d
0x383aac9ec  imul    rax, 38h ; '8'
0x383aac9f0  add     r15, rax
0x383aac9f3  lea     rcx, [r15+8]; struct CWStr *
0x383aac9f7  lea     r8, [rbp+10A0h+var_10D0]; struct CBulkFmtStreamReader *
0x383aac9fb  mov     edx, r14d; int
0x383aac9fe  call    ?GetString@@YAXAEAVCWStr@@JAEAVCBulkFmtStreamReader@@@Z; GetString(CWStr &,long,CBulkFmtStreamReader &)
0x383aaca03  mov     rax, [rbx+8]
0x383aaca07  lea     rsi, WideCharStr
0x383aaca0e  test    rax, rax
0x383aaca11  cmovnz  rsi, rax
0x383aaca15  lea     rdi, aSqlbit_0; "SQLBIT"
0x383aaca1c  mov     ecx, 7
0x383aaca21  repe cmpsw
0x383aaca24  jz      loc_383AAD059
0x383aaca2a  lea     rsi, WideCharStr
0x383aaca31  test    rax, rax
0x383aaca34  cmovnz  rsi, rax
0x383aaca38  lea     rdi, aSqltinyint_0; "SQLTINYINT"
0x383aaca3f  mov     edx, 0Bh
0x383aaca44  mov     ecx, edx
0x383aaca46  repe cmpsw
0x383aaca49  jz      loc_383AAD059
0x383aaca4f  lea     rsi, WideCharStr
0x383aaca56  test    rax, rax
0x383aaca59  cmovnz  rsi, rax
0x383aaca5d  lea     rdi, aSqlsmallint_0; "SQLSMALLINT"
0x383aaca64  mov     r8d, 0Ch
0x383aaca6a  mov     ecx, r8d
0x383aaca6d  repe cmpsw
0x383aaca70  jz      loc_383AAD059
0x383aaca76  lea     rsi, WideCharStr
0x383aaca7d  test    rax, rax
0x383aaca80  cmovnz  rsi, rax
0x383aaca84  lea     rdi, aSqlint_0; "SQLINT"
0x383aaca8b  mov     ecx, 7
0x383aaca90  repe cmpsw
0x383aaca93  jz      loc_383AAD059
0x383aaca99  lea     rsi, WideCharStr
0x383aacaa0  test    rax, rax
0x383aacaa3  cmovnz  rsi, rax
0x383aacaa7  lea     rdi, aSqlbigint; "SQLBIGINT"
0x383aacaae  mov     r9d, 0Ah
0x383aacab4  mov     ecx, r9d
0x383aacab7  repe cmpsw
0x383aacaba  jz      loc_383AAD059
0x383aacac0  lea     rsi, WideCharStr
0x383aacac7  test    rax, rax
0x383aacaca  cmovnz  rsi, rax
0x383aacace  lea     rdi, aSqlflt4; "SQLFLT4"
0x383aacad5  mov     ecx, 8
0x383aacada  repe cmpsw
0x383aacadd  jz      loc_383AAD059
0x383aacae3  lea     rsi, WideCharStr
0x383aacaea  test    rax, rax
0x383aacaed  cmovnz  rsi, rax
0x383aacaf1  lea     rdi, aSqlflt8_0; "SQLFLT8"
0x383aacaf8  mov     ecx, 8
0x383aacafd  repe cmpsw
0x383aacb00  jz      loc_383AAD059
0x383aacb06  lea     rsi, WideCharStr
0x383aacb0d  test    rax, rax
0x383aacb10  cmovnz  rsi, rax
0x383aacb14  lea     rdi, aSqldatetime; "SQLDATETIME"
0x383aacb1b  mov     ecx, r8d
0x383aacb1e  repe cmpsw
0x383aacb21  jz      loc_383AAD059
0x383aacb27  lea     rsi, WideCharStr
0x383aacb2e  test    rax, rax
0x383aacb31  cmovnz  rsi, rax
0x383aacb35  lea     rdi, aSqldatetim4_0; "SQLDATETIM4"
0x383aacb3c  mov     ecx, r8d
0x383aacb3f  repe cmpsw
0x383aacb42  jz      loc_383AAD059
0x383aacb48  lea     rsi, WideCharStr
0x383aacb4f  test    rax, rax
0x383aacb52  cmovnz  rsi, rax
0x383aacb56  lea     rdi, aSqldatetim8; "SQLDATETIM8"
0x383aacb5d  mov     ecx, r8d
0x383aacb60  repe cmpsw
0x383aacb63  jz      loc_383AAD059
0x383aacb69  lea     rsi, WideCharStr
0x383aacb70  test    rax, rax
0x383aacb73  cmovnz  rsi, rax
0x383aacb77  lea     rdi, aSqldate; "SQLDATE"
0x383aacb7e  mov     ecx, 8
0x383aacb83  repe cmpsw
0x383aacb86  jz      loc_383AAD059
0x383aacb8c  lea     rsi, WideCharStr
0x383aacb93  test    rax, rax
0x383aacb96  cmovnz  rsi, rax
0x383aacb9a  lea     rdi, aSqltime; "SQLTIME"
0x383aacba1  mov     ecx, 8
0x383aacba6  repe cmpsw
0x383aacba9  jz      loc_383AAD059
0x383aacbaf  lea     rsi, WideCharStr
0x383aacbb6  test    rax, rax
0x383aacbb9  cmovnz  rsi, rax
0x383aacbbd  lea     rdi, aSqldatetime2_0; "SQLDATETIME2"
0x383aacbc4  mov     ecx, 0Dh
0x383aacbc9  repe cmpsw
0x383aacbcc  jz      loc_383AAD059
0x383aacbd2  lea     rsi, WideCharStr
  ... truncated ...
```
