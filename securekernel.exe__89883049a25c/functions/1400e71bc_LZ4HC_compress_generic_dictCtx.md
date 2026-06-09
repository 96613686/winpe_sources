# LZ4HC_compress_generic_dictCtx

- ea: `0x1400e71bc`
- end: `0x1400ee142`
- name: `LZ4HC_compress_generic_dictCtx`
- size: `28550`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, void *Src@<rdx>, int, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400e4bd0`

## callees

- `0x1400e71bc`
- `0x1400ee148`
- `0x1400ee238`
- `0x1400ee280`
- `0x1400ee298`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall LZ4HC_compress_generic_dictCtx(
        unsigned int *a1,
        char *Src,
        __int64 a3,
        int *a4,
        int a5,
        int a6,
        int a7)
{
  __int64 v7; // r10
  unsigned int *v8; // rdi
  unsigned __int64 v12; // rcx
  unsigned int v13; // r12d
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  char *v17; // r8
  char *v18; // r14
  unsigned __int64 v19; // r13
  char *v20; // r9
  __int64 v21; // rbx
  int v22; // edi
  __int64 v23; // rcx
  _QWORD *v24; // rsi
  unsigned int v25; // r12d
  __int64 v26; // r13
  unsigned int v27; // r15d
  _DWORD *v28; // rdx
  unsigned int v29; // r14d
  int v30; // r9d
  int v31; // r10d
  unsigned int v32; // r8d
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  _DWORD *v35; // r8
  unsigned int v36; // r11d
  _DWORD *v37; // r10
  __int64 v38; // r8
  _QWORD *v39; // r9
  _QWORD *v40; // rdx
  char *v42; // rcx
  unsigned int v44; // ecx
  signed int v47; // ecx
  char *v48; // r10
  char *v49; // r9
  _QWORD *v50; // rdx
  char *v52; // rcx
  signed int v54; // r10d
  char *v57; // r8
  int v58; // ecx
  char *v60; // rcx
  _QWORD *v61; // rdx
  unsigned int v63; // ecx
  unsigned int v66; // r15d
  int v67; // r12d
  _DWORD *v68; // rdi
  char *v69; // r14
  unsigned __int64 v70; // rsi
  __int64 v71; // r8
  unsigned __int64 v72; // rax
  _DWORD *v73; // rdx
  unsigned int v74; // eax
  __int64 v75; // r8
  unsigned int v76; // r11d
  int v77; // eax
  int v78; // r11d
  unsigned int v79; // eax
  unsigned __int64 v80; // rcx
  unsigned __int64 v81; // rdx
  unsigned int v82; // ecx
  __int16 v83; // r15
  __int16 v84; // r11
  _DWORD *v85; // rdx
  unsigned __int64 v86; // rcx
  __int64 v87; // r14
  _DWORD *v88; // r10
  _DWORD *v89; // r15
  char *v90; // rdi
  _QWORD *v91; // r12
  unsigned int v92; // r10d
  unsigned int v93; // r14d
  unsigned int v94; // r9d
  char *v95; // rdx
  unsigned int v96; // r8d
  unsigned int v97; // esi
  unsigned __int64 v98; // rdx
  unsigned __int64 v99; // rcx
  unsigned int v100; // r13d
  int v101; // eax
  int v102; // r8d
  int v103; // r9d
  int v104; // edx
  _DWORD *v105; // r10
  __int64 v106; // rax
  int v107; // edx
  int j; // eax
  char *v109; // r12
  _QWORD *v110; // rdx
  _QWORD *v111; // r10
  char *v113; // rcx
  unsigned int v114; // eax
  unsigned int v116; // ecx
  int v119; // ecx
  char *v120; // r14
  _QWORD *v121; // rdx
  __int64 v122; // r10
  char *v123; // rdi
  char *v124; // r10
  char *v126; // rcx
  signed int v128; // esi
  int v131; // edi
  char *v132; // r9
  char *v134; // rcx
  _QWORD *v135; // rdx
  unsigned int v137; // ecx
  int v140; // edx
  int v141; // r8d
  int i; // eax
  int v143; // edi
  unsigned int v144; // eax
  unsigned int v145; // eax
  unsigned int v146; // r12d
  unsigned int v147; // ecx
  bool v148; // cf
  unsigned int v149; // r15d
  int v150; // r12d
  char *v151; // rsi
  unsigned __int64 v152; // r14
  __int64 v153; // r8
  unsigned __int64 v154; // rax
  char *v155; // rdx
  unsigned int v156; // eax
  char *v157; // r8
  unsigned int v158; // esi
  bool v159; // zf
  __int64 v160; // r8
  unsigned __int64 v161; // rcx
  unsigned __int64 v162; // rdx
  int v163; // r12d
  __int16 v164; // r9
  unsigned __int64 v165; // rsi
  int v166; // edx
  int v167; // ecx
  __int64 v168; // r10
  _DWORD *v169; // r13
  unsigned int *v170; // rax
  char *v171; // r14
  unsigned int v172; // edx
  unsigned int v173; // esi
  char *v174; // rdi
  _QWORD *v175; // r15
  unsigned int v176; // r12d
  char *v177; // r9
  unsigned int v178; // r8d
  unsigned int v179; // r11d
  unsigned __int64 v180; // rdx
  unsigned __int64 v181; // rcx
  unsigned int v182; // r13d
  int v183; // eax
  int v184; // r8d
  int v185; // esi
  _DWORD *v186; // r10
  int v187; // r9d
  __int64 v188; // rax
  int v189; // edx
  int n; // eax
  char *v191; // r15
  _QWORD *v192; // rdx
  _QWORD *v193; // r10
  char *v195; // rcx
  unsigned int v196; // eax
  unsigned int v198; // ecx
  int v201; // ecx
  char *v202; // rsi
  char *v203; // r10
  char *v204; // r11
  _QWORD *v205; // rdx
  char *v207; // rcx
  signed int v209; // edi
  int v212; // r10d
  char *v213; // r9
  char *v215; // rcx
  _QWORD *v216; // rdx
  unsigned int v218; // ecx
  int v221; // edx
  int v222; // r8d
  int m; // eax
  int v224; // r10d
  unsigned int v225; // eax
  unsigned int v226; // r10d
  unsigned int v227; // ecx
  unsigned int v228; // r12d
  int v229; // r15d
  char *v230; // rsi
  unsigned __int64 v231; // r14
  unsigned int v232; // esi
  __int64 v233; // r8
  unsigned __int64 v234; // rax
  char *v235; // r13
  char *v236; // rdx
  unsigned int v237; // eax
  char *v238; // r8
  unsigned int v239; // r11d
  __int64 v240; // r8
  int v241; // eax
  int v242; // r11d
  unsigned __int64 v243; // rcx
  unsigned __int64 v244; // rdx
  int v245; // r14d
  __int64 v246; // r11
  char *v247; // r10
  int v248; // r10d
  int v249; // ecx
  __int64 v250; // rdi
  _BYTE *v251; // rcx
  unsigned int v252; // esi
  char *v253; // r9
  char *v254; // rbx
  unsigned __int64 v255; // r8
  unsigned __int64 v256; // rax
  char *v257; // rdx
  _WORD *v258; // rbx
  __int64 v259; // rax
  unsigned __int64 v260; // rcx
  char v261; // al
  unsigned __int64 mm; // rax
  _BYTE *v263; // rbx
  int v264; // ecx
  __int16 v265; // r13
  _BYTE *v266; // rcx
  char *v267; // r9
  unsigned __int64 v268; // r8
  unsigned __int64 v269; // rax
  char *v270; // rdx
  _WORD *v271; // rbx
  __int64 v272; // rax
  unsigned __int64 v273; // rcx
  char v274; // al
  unsigned __int64 nn; // rax
  _BYTE *v276; // rbx
  int v277; // r11d
  _BYTE *v278; // rcx
  unsigned __int64 v279; // r8
  unsigned __int64 v280; // rax
  char *v281; // rdx
  _WORD *v282; // r9
  __int64 v283; // rax
  __int64 v284; // rcx
  __int16 v285; // r15
  __int64 v286; // r9
  unsigned __int64 v287; // r8
  char v288; // al
  unsigned __int64 ii; // rax
  _BYTE *v290; // rcx
  _BYTE *v291; // r8
  char *v292; // r11
  unsigned __int64 v293; // r9
  unsigned __int64 v294; // rax
  char *v295; // rdx
  _WORD *v296; // rbx
  __int64 v297; // rax
  __int16 v298; // r9
  unsigned __int64 v299; // r8
  char v300; // al
  unsigned __int64 jj; // rax
  _BYTE *v302; // rbx
  _BYTE *v303; // rcx
  char *v304; // r9
  unsigned __int64 v305; // r8
  unsigned __int64 v306; // rax
  char *v307; // rdx
  _WORD *v308; // rbx
  __int64 v309; // rax
  unsigned __int64 v310; // rcx
  char v311; // al
  unsigned __int64 k; // rcx
  _BYTE *v313; // rbx
  size_t v314; // r9
  size_t v315; // rdi
  int v316; // r10d
  unsigned __int64 v317; // r8
  unsigned __int64 v318; // r9
  _BYTE *v319; // rcx
  unsigned __int64 v320; // rax
  _WORD *v321; // rbx
  __int64 v322; // rax
  char v323; // cl
  unsigned __int64 kk; // rax
  _BYTE *v325; // rbx
  int v326; // eax
  unsigned __int64 v327; // rax
  unsigned int v329; // esi
  __int64 v330; // rax
  char *v331; // r8
  __int64 v332; // rdx
  char *v333; // r14
  char *v334; // r9
  __int64 v335; // rbx
  unsigned __int64 v336; // r13
  _QWORD *v337; // r15
  __int64 v338; // r13
  __int64 v339; // rdi
  unsigned int v340; // esi
  unsigned int v341; // r12d
  int v342; // r14d
  _QWORD *v343; // rdx
  unsigned int v344; // r9d
  int v345; // r10d
  unsigned int v346; // r8d
  unsigned __int64 v347; // rdx
  unsigned __int64 v348; // rcx
  _DWORD *v349; // r8
  unsigned int v350; // r11d
  _DWORD *v351; // r9
  __int64 v352; // r8
  _QWORD *v353; // r9
  _QWORD *v354; // rdx
  char *v356; // rcx
  unsigned int v358; // ecx
  signed int v361; // ecx
  char *v362; // r10
  char *v363; // r9
  _QWORD *v364; // rdx
  char *v366; // rcx
  signed int v368; // r10d
  char *v371; // r8
  int v372; // ecx
  char *v374; // rcx
  _QWORD *v375; // rdx
  unsigned int v377; // ecx
  unsigned int v380; // r14d
  int v381; // r12d
  _DWORD *v382; // rdi
  char *v383; // r15
  unsigned __int64 v384; // rsi
  unsigned int v385; // eax
  _QWORD *v386; // rdx
  unsigned int v387; // eax
  unsigned int v388; // r11d
  unsigned int v389; // eax
  int v390; // eax
  int v391; // r11d
  unsigned int v392; // eax
  unsigned __int64 v393; // rcx
  unsigned __int64 v394; // rdx
  unsigned int v395; // ecx
  int v396; // r9d
  __int16 v397; // r15
  __int16 v398; // r11
  _DWORD *v399; // rdx
  unsigned __int64 v400; // rcx
  __int64 v401; // r14
  _DWORD *v402; // r10
  int v403; // r14d
  _DWORD *v404; // r15
  unsigned int v405; // r10d
  _QWORD *v406; // r12
  char *v407; // rdi
  unsigned int v408; // r14d
  unsigned int v409; // r9d
  char *v410; // rdx
  unsigned int v411; // r8d
  unsigned int v412; // esi
  unsigned __int64 v413; // rdx
  unsigned __int64 v414; // rcx
  unsigned int v415; // r13d
  int v416; // eax
  int v417; // r8d
  int v418; // r9d
  int v419; // edx
  _DWORD *v420; // r10
  __int64 v421; // rax
  int v422; // edx
  int i2; // eax
  char *v424; // r12
  _QWORD *v425; // rdx
  _QWORD *v426; // r10
  char *v428; // rcx
  unsigned int v429; // eax
  unsigned int v431; // ecx
  int v434; // ecx
  char *v435; // r14
  _QWORD *v436; // rdx
  __int64 v437; // r10
  char *v438; // rdi
  char *v439; // r10
  char *v441; // rcx
  signed int v443; // esi
  int v446; // edi
  char *v447; // r9
  char *v449; // rcx
  _QWORD *v450; // rdx
  unsigned int v452; // ecx
  int v455; // edx
  int v456; // r8d
  int i1; // eax
  int v458; // edi
  unsigned int v459; // eax
  unsigned int v460; // eax
  unsigned int v461; // ecx
  unsigned int v462; // r15d
  int v463; // r12d
  char *v464; // r14
  unsigned __int64 v465; // rsi
  unsigned int v466; // eax
  char *v467; // rdx
  unsigned int v468; // eax
  char *v469; // r9
  unsigned int v470; // r14d
  unsigned int v471; // eax
  int v472; // eax
  unsigned int v473; // eax
  unsigned __int64 v474; // rcx
  unsigned __int64 v475; // rdx
  int v476; // r12d
  __int16 v477; // di
  unsigned __int64 v478; // rsi
  int v479; // edx
  int v480; // ecx
  __int64 v481; // r10
  _DWORD *v482; // r13
  _DWORD *v483; // r13
  unsigned int v484; // edx
  unsigned int v485; // esi
  char *v486; // rdi
  _QWORD *v487; // r15
  unsigned int v488; // r12d
  char *v489; // r10
  unsigned int v490; // r9d
  unsigned int v491; // r11d
  unsigned int v492; // r8d
  unsigned __int64 v493; // rdx
  unsigned __int64 v494; // rcx
  unsigned int v495; // r14d
  int v496; // eax
  int v497; // r8d
  int v498; // r9d
  int v499; // esi
  _DWORD *v500; // r10
  __int64 v501; // rax
  int v502; // edx
  int i4; // eax
  char *v504; // r15
  _QWORD *v505; // rdx
  _QWORD *v506; // r10
  char *v508; // rcx
  unsigned int v509; // eax
  unsigned int v511; // ecx
  int v514; // ecx
  char *v515; // rsi
  char *v516; // r10
  char *v517; // r11
  _QWORD *v518; // rdx
  char *v520; // rcx
  signed int v522; // edi
  int v525; // r10d
  char *v526; // r9
  char *v528; // rcx
  _QWORD *v529; // rdx
  unsigned int v531; // ecx
  int v534; // edx
  int v535; // r8d
  int i3; // eax
  int v537; // r10d
  unsigned int v538; // eax
  int v539; // r12d
  unsigned int v540; // r10d
  unsigned int v541; // ecx
  unsigned int v542; // r15d
  char *v543; // r14
  unsigned __int64 v544; // rsi
  unsigned int v545; // r14d
  unsigned int v546; // eax
  char *v547; // rdx
  unsigned int v548; // eax
  char *v549; // r8
  unsigned int v550; // r11d
  unsigned int v551; // eax
  int v552; // eax
  int v553; // r11d
  unsigned __int64 v554; // rcx
  unsigned __int64 v555; // rdx
  int v556; // r14d
  __int64 v557; // r11
  char *v558; // r10
  int v559; // r10d
  int v560; // ecx
  __int64 v561; // rdi
  _BYTE *v562; // rcx
  unsigned int v563; // esi
  char *v564; // r9
  char *v565; // rbx
  unsigned __int64 v566; // r8
  unsigned __int64 v567; // rax
  char *v568; // rdx
  _WORD *v569; // rbx
  __int64 v570; // rax
  unsigned __int64 v571; // rcx
  char v572; // al
  unsigned __int64 i7; // rax
  _BYTE *v574; // rbx
  int v575; // ecx
  __int16 v576; // r13
  _BYTE *v577; // rcx
  char *v578; // r9
  unsigned __int64 v579; // r8
  unsigned __int64 v580; // rax
  char *v581; // rdx
  _WORD *v582; // rbx
  __int64 v583; // rax
  unsigned __int64 v584; // rcx
  char v585; // al
  unsigned __int64 i8; // rax
  _BYTE *v587; // rbx
  int v588; // r11d
  _BYTE *v589; // rcx
  unsigned __int64 v590; // r8
  unsigned __int64 v591; // rax
  char *v592; // rdx
  _WORD *v593; // r9
  __int64 v594; // rax
  __int64 v595; // rcx
  __int16 v596; // r15
  __int64 v597; // r9
  unsigned __int64 v598; // r8
  char v599; // al
  unsigned __int64 i5; // rax
  _BYTE *v601; // rcx
  _BYTE *v602; // r8
  char *v603; // r11
  unsigned __int64 v604; // r9
  unsigned __int64 v605; // rax
  char *v606; // rdx
  _WORD *v607; // rbx
  __int64 v608; // rax
  __int16 v609; // r9
  unsigned __int64 v610; // r8
  char v611; // al
  unsigned __int64 i6; // rax
  _BYTE *v613; // rbx
  _BYTE *v614; // rcx
  char *v615; // r9
  unsigned __int64 v616; // r8
  unsigned __int64 v617; // rax
  char *v618; // rdx
  _WORD *v619; // rbx
  __int64 v620; // rax
  unsigned __int64 v621; // rcx
  char v622; // al
  unsigned __int64 i10; // rcx
  _BYTE *v624; // rbx
  int v625; // r10d
  unsigned __int64 v626; // r8
  unsigned __int64 v627; // r9
  _BYTE *v628; // rcx
  unsigned __int64 v629; // rax
  _WORD *v630; // rbx
  __int64 v631; // rax
  char v632; // cl
  unsigned __int64 i9; // rax
  _BYTE *v634; // rbx
  size_t v635; // r9
  size_t v636; // rdi
  unsigned __int64 v637; // rax
  int v638; // eax
  __int64 v639; // rax
  __int64 v640; // r12
  __int64 v641; // rdx
  char *v642; // r10
  char *v643; // r15
  char *v644; // r8
  unsigned __int64 v645; // r13
  __int64 v646; // rcx
  int v647; // r15d
  _QWORD *v648; // r14
  unsigned int v649; // ebx
  __int64 v650; // r13
  unsigned int v651; // r9d
  _QWORD *v652; // rdx
  unsigned int v653; // r10d
  int v654; // edi
  int v655; // esi
  unsigned int v656; // r8d
  unsigned __int64 v657; // rdx
  unsigned __int64 v658; // rcx
  unsigned __int64 v659; // r8
  unsigned int v660; // r11d
  int v661; // r13d
  __int64 v662; // r14
  __int64 v663; // r15
  unsigned int v664; // edi
  __int64 v665; // rsi
  int v666; // r11d
  char *v667; // r8
  _QWORD *v668; // r10
  _QWORD *v669; // rdx
  char *v671; // rcx
  __int64 v672; // r8
  _QWORD *v673; // r9
  _QWORD *v674; // rdx
  char *v676; // rcx
  unsigned int v678; // ecx
  signed int v681; // ecx
  __int64 v682; // rax
  char *v683; // r8
  char *v684; // r9
  char *v685; // r10
  _QWORD *v686; // rdx
  char *v688; // rcx
  signed int v690; // ebx
  int v693; // ecx
  char *v694; // r9
  unsigned __int64 v695; // r10
  char *v697; // rcx
  _QWORD *v698; // rdx
  unsigned int v700; // ecx
  unsigned int *v703; // r9
  int v704; // r15d
  unsigned int v705; // ecx
  unsigned int v706; // esi
  _DWORD *v707; // rbx
  char *v708; // r14
  unsigned __int64 v709; // rdi
  unsigned int v710; // eax
  _QWORD *v711; // rdx
  unsigned int v712; // eax
  unsigned int v713; // r8d
  unsigned int v714; // r11d
  unsigned int v715; // eax
  int v716; // eax
  int v717; // r11d
  unsigned int v718; // eax
  unsigned __int64 v719; // rcx
  unsigned __int64 v720; // rdx
  unsigned int v722; // ecx
  signed int v725; // ecx
  int v726; // ecx
  int v727; // r9d
  __int16 v728; // r11
  _DWORD *v729; // rdi
  unsigned __int64 v730; // rcx
  _DWORD *v731; // rdx
  char *v732; // r15
  __int64 v733; // r14
  _DWORD *v734; // rbx
  _DWORD *v735; // r10
  unsigned int v736; // esi
  unsigned int v737; // edi
  _QWORD *v738; // r15
  int v739; // r14d
  char *v740; // rbx
  unsigned int v741; // r14d
  char *v742; // rcx
  unsigned int v743; // r9d
  unsigned int v744; // r8d
  _DWORD *v745; // rdx
  unsigned __int64 v746; // rdx
  unsigned __int64 v747; // rcx
  unsigned __int64 v748; // r8
  unsigned int v749; // r13d
  int v750; // edi
  _DWORD *v751; // r9
  unsigned __int64 v752; // rdx
  int v753; // r10d
  __int64 v754; // rax
  int v755; // r8d
  unsigned int v756; // edx
  unsigned int v757; // eax
  char *v758; // r15
  _QWORD *v759; // rdx
  _QWORD *v760; // rbx
  char *v762; // rcx
  unsigned int v764; // ecx
  unsigned int v767; // r9d
  int v768; // ecx
  __int64 v769; // rax
  char *v770; // r14
  char *v771; // r8
  _QWORD *v772; // rdx
  char *v773; // rdi
  char *v774; // r10
  char *v776; // rcx
  signed int v778; // esi
  int v781; // ebx
  char *v782; // r10
  unsigned __int64 v783; // r9
  char *v785; // rcx
  _QWORD *v786; // rdx
  unsigned int v788; // ecx
  int v791; // edx
  int v792; // r9d
  int i11; // eax
  int v794; // ebx
  unsigned int v795; // eax
  unsigned int v796; // ecx
  int v797; // ecx
  unsigned int v798; // r14d
  int v799; // r15d
  char *v800; // rdi
  unsigned __int64 v801; // rsi
  unsigned int v802; // eax
  char *v803; // r13
  char *v804; // rdx
  unsigned int v805; // eax
  char *v806; // r8
  unsigned int v807; // edi
  unsigned int v808; // eax
  unsigned int v809; // eax
  unsigned __int64 v810; // rcx
  unsigned __int64 v811; // rdx
  __int64 v812; // rdx
  __int64 v813; // r13
  unsigned int v814; // r14d
  __int64 v815; // r15
  int v816; // esi
  unsigned int v817; // r12d
  _DWORD *v818; // rdi
  _QWORD *v819; // rdx
  char *v820; // r9
  char *v821; // r10
  char *v823; // rcx
  unsigned int v825; // ecx
  int v828; // edx
  unsigned __int64 v829; // r9
  int v830; // r8d
  unsigned int v831; // r9d
  unsigned int v832; // eax
  int v833; // ecx
  int v834; // r10d
  __int16 v835; // r8
  unsigned __int64 v836; // rsi
  int v837; // r8d
  int v838; // ecx
  __int64 v839; // r11
  _DWORD *v840; // r13
  unsigned int *v841; // rax
  char *v842; // r10
  unsigned int v843; // esi
  unsigned int v844; // r15d
  _DWORD *v845; // rbx
  _QWORD *v846; // rdi
  unsigned int v847; // r9d
  _QWORD *v848; // r14
  _DWORD *v849; // rdx
  unsigned int v850; // r11d
  unsigned int v851; // r8d
  unsigned __int64 v852; // rdx
  unsigned __int64 v853; // rcx
  unsigned __int64 v854; // rcx
  unsigned int v855; // r13d
  int v856; // r11d
  _DWORD *v857; // r9
  int v858; // r10d
  char *v859; // rdx
  int v860; // r8d
  __int64 v861; // rax
  unsigned int v862; // edx
  _QWORD *v863; // rdx
  _QWORD *v864; // r11
  char *v866; // rcx
  unsigned int v867; // eax
  unsigned int v869; // ecx
  unsigned int v872; // r9d
  int v873; // ecx
  __int64 v874; // rcx
  _DWORD *v875; // rsi
  _QWORD *v876; // rdx
  char *v877; // rbx
  char *v878; // r10
  char *v880; // rcx
  signed int v882; // edi
  int v885; // r11d
  char *v886; // r10
  _QWORD *v887; // rdx
  char *v889; // rcx
  unsigned int v891; // ecx
  int v894; // edx
  int v895; // r9d
  int i12; // eax
  int v897; // r11d
  unsigned int v898; // eax
  unsigned int v899; // r14d
  int v900; // r15d
  char *v901; // rdi
  unsigned __int64 v902; // rsi
  unsigned int v903; // eax
  _QWORD *v904; // rdx
  unsigned int v905; // eax
  unsigned int v906; // r8d
  unsigned int v907; // r11d
  unsigned int v908; // eax
  int v909; // eax
  int v910; // r11d
  unsigned __int64 v911; // rcx
  unsigned __int64 v912; // rdx
  unsigned int v913; // ecx
  int v914; // edx
  __int64 v915; // r15
  __int64 v916; // r13
  unsigned int v917; // esi
  __int64 v918; // r14
  int v919; // edi
  int v920; // r12d
  _DWORD *v921; // rbx
  _QWORD *v922; // rdx
  unsigned __int64 v923; // r9
  _QWORD *v924; // r10
  _QWORD *v926; // rcx
  unsigned int v928; // ecx
  int v931; // edx
  char *v932; // r9
  int v933; // r8d
  unsigned int v934; // r9d
  unsigned int v935; // eax
  int v936; // ecx
  int v937; // r14d
  __int16 v938; // r15
  __int64 v939; // rbx
  char *v940; // r11
  int v941; // r11d
  int v942; // ecx
  char *v943; // rbx
  _BYTE *v944; // rcx
  __int64 v945; // rdi
  unsigned __int64 v946; // r8
  unsigned int v947; // esi
  char *v948; // r9
  unsigned __int64 v949; // rax
  char *v950; // rdx
  _WORD *v951; // r10
  __int64 v952; // rax
  unsigned __int64 v953; // rcx
  char v954; // al
  unsigned __int64 i13; // rax
  _BYTE *v956; // r12
  int v957; // ecx
  int v958; // r10d
  int v959; // r13d
  _BYTE *v960; // rcx
  unsigned __int64 v961; // r8
  char *v962; // r9
  unsigned __int64 v963; // rax
  char *v964; // rdx
  _WORD *v965; // r10
  __int64 v966; // rax
  unsigned __int64 v967; // rcx
  char v968; // al
  unsigned __int64 i14; // rax
  _BYTE *v970; // r12
  int v971; // ebx
  _BYTE *v972; // rcx
  unsigned __int64 v973; // r8
  unsigned __int64 v974; // rax
  char *v975; // rdx
  _WORD *v976; // r9
  __int64 v977; // rax
  __int64 v978; // rcx
  __int64 v979; // r9
  unsigned __int64 v980; // r8
  char v981; // al
  unsigned __int64 i16; // rax
  _BYTE *v983; // rcx
  _BYTE *v984; // r8
  unsigned __int64 v985; // r9
  unsigned __int64 v986; // rax
  char *v987; // rdx
  _WORD *v988; // r10
  __int64 v989; // rax
  __int16 v990; // r9
  unsigned __int64 v991; // r8
  char v992; // al
  unsigned __int64 i17; // rax
  _BYTE *v994; // r12
  _BYTE *v995; // rcx
  unsigned __int64 v996; // r8
  char *v997; // r9
  unsigned __int64 v998; // rax
  char *v999; // rdx
  _WORD *v1000; // r10
  __int64 v1001; // rax
  __int16 v1002; // r11
  unsigned __int64 v1003; // rcx
  char v1004; // al
  unsigned __int64 i18; // rcx
  _BYTE *v1006; // r12
  unsigned __int64 v1007; // r8
  unsigned __int64 v1008; // r9
  _BYTE *v1009; // rcx
  unsigned __int64 v1010; // rax
  _WORD *v1011; // r9
  __int64 v1012; // rax
  char v1013; // cl
  unsigned __int64 i15; // rax
  _BYTE *v1015; // r12
  size_t v1016; // r8
  size_t v1017; // rbx
  unsigned __int64 v1018; // rax
  int v1019; // [rsp+28h] [rbp-E0h]
  unsigned int v1020; // [rsp+28h] [rbp-E0h]
  int v1021; // [rsp+28h] [rbp-E0h]
  unsigned int v1022; // [rsp+28h] [rbp-E0h]
  unsigned int v1023; // [rsp+28h] [rbp-E0h]
  unsigned int v1024; // [rsp+28h] [rbp-E0h]
  int v1025; // [rsp+2Ch] [rbp-DCh]
  __int16 v1026; // [rsp+2Ch] [rbp-DCh]
  int v1027; // [rsp+2Ch] [rbp-DCh]
  __int16 v1028; // [rsp+2Ch] [rbp-DCh]
  unsigned int v1029; // [rsp+2Ch] [rbp-DCh]
  __int16 v1030; // [rsp+2Ch] [rbp-DCh]
  unsigned int v1031; // [rsp+30h] [rbp-D8h]
  unsigned int v1032; // [rsp+30h] [rbp-D8h]
  unsigned int v1033; // [rsp+30h] [rbp-D8h]
  unsigned int v1034; // [rsp+34h] [rbp-D4h]
  int v1035; // [rsp+34h] [rbp-D4h]
  unsigned int v1036; // [rsp+34h] [rbp-D4h]
  int v1037; // [rsp+34h] [rbp-D4h]
  int v1038; // [rsp+34h] [rbp-D4h]
  int v1039; // [rsp+34h] [rbp-D4h]
  unsigned int v1040; // [rsp+38h] [rbp-D0h]
  int v1041; // [rsp+38h] [rbp-D0h]
  unsigned int v1042; // [rsp+38h] [rbp-D0h]
  int v1043; // [rsp+38h] [rbp-D0h]
  unsigned int v1044; // [rsp+38h] [rbp-D0h]
  int v1045; // [rsp+38h] [rbp-D0h]
  unsigned int v1046; // [rsp+3Ch] [rbp-CCh]
  unsigned int v1047; // [rsp+3Ch] [rbp-CCh]
  int v1048; // [rsp+3Ch] [rbp-CCh]
  unsigned int v1049; // [rsp+3Ch] [rbp-CCh]
  int v1050; // [rsp+3Ch] [rbp-CCh]
  __int16 v1051; // [rsp+3Ch] [rbp-CCh]
  int v1052; // [rsp+3Ch] [rbp-CCh]
  unsigned int v1053; // [rsp+3Ch] [rbp-CCh]
  unsigned int v1054; // [rsp+3Ch] [rbp-CCh]
  _DWORD *v1055; // [rsp+40h] [rbp-C8h]
  char *v1056; // [rsp+40h] [rbp-C8h]
  _DWORD *v1057; // [rsp+40h] [rbp-C8h]
  char *v1058; // [rsp+48h] [rbp-C0h]
  _DWORD *v1059; // [rsp+48h] [rbp-C0h]
  char *v1060; // [rsp+48h] [rbp-C0h]
  int v1061; // [rsp+50h] [rbp-B8h]
  int v1062; // [rsp+50h] [rbp-B8h]
  int v1063; // [rsp+50h] [rbp-B8h]
  unsigned int v1064; // [rsp+54h] [rbp-B4h]
  unsigned int v1065; // [rsp+54h] [rbp-B4h]
  __int16 v1066; // [rsp+54h] [rbp-B4h]
  unsigned int v1067; // [rsp+54h] [rbp-B4h]
  unsigned int v1068; // [rsp+54h] [rbp-B4h]
  unsigned int v1069; // [rsp+54h] [rbp-B4h]
  int v1070; // [rsp+54h] [rbp-B4h]
  int v1071; // [rsp+54h] [rbp-B4h]
  __int16 v1072; // [rsp+54h] [rbp-B4h]
  unsigned int v1073; // [rsp+58h] [rbp-B0h]
  int v1074; // [rsp+58h] [rbp-B0h]
  __int16 v1075; // [rsp+58h] [rbp-B0h]
  unsigned int v1076; // [rsp+58h] [rbp-B0h]
  int v1077; // [rsp+58h] [rbp-B0h]
  unsigned int v1078; // [rsp+58h] [rbp-B0h]
  unsigned int v1079; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v1080; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v1081; // [rsp+60h] [rbp-A8h]
  int v1082; // [rsp+64h] [rbp-A4h]
  unsigned __int64 v1083; // [rsp+68h] [rbp-A0h]
  _WORD *v1084; // [rsp+68h] [rbp-A0h]
  int v1085; // [rsp+6Ch] [rbp-9Ch]
  unsigned __int64 v1086; // [rsp+70h] [rbp-98h]
  unsigned __int64 v1087; // [rsp+70h] [rbp-98h]
  char *v1088; // [rsp+70h] [rbp-98h]
  char *v1089; // [rsp+70h] [rbp-98h]
  __int64 v1090; // [rsp+78h] [rbp-90h]
  char *v1091; // [rsp+78h] [rbp-90h]
  char *v1092; // [rsp+78h] [rbp-90h]
  __int64 v1093; // [rsp+78h] [rbp-90h]
  char *v1094; // [rsp+78h] [rbp-90h]
  char *v1095; // [rsp+78h] [rbp-90h]
  _QWORD *v1096; // [rsp+78h] [rbp-90h]
  char *v1097; // [rsp+78h] [rbp-90h]
  _QWORD *v1098; // [rsp+78h] [rbp-90h]
  _DWORD *v1099; // [rsp+80h] [rbp-88h]
  unsigned int v1100; // [rsp+80h] [rbp-88h]
  int v1101; // [rsp+80h] [rbp-88h]
  unsigned int v1102; // [rsp+80h] [rbp-88h]
  unsigned int v1103; // [rsp+80h] [rbp-88h]
  unsigned int v1104; // [rsp+80h] [rbp-88h]
  unsigned int v1105; // [rsp+80h] [rbp-88h]
  unsigned int v1106; // [rsp+80h] [rbp-88h]
  int v1107; // [rsp+88h] [rbp-80h]
  __int16 v1108; // [rsp+88h] [rbp-80h]
  unsigned int v1109; // [rsp+88h] [rbp-80h]
  unsigned int v1110; // [rsp+88h] [rbp-80h]
  __int16 v1111; // [rsp+88h] [rbp-80h]
  __int16 v1112; // [rsp+88h] [rbp-80h]
  unsigned int v1113; // [rsp+88h] [rbp-80h]
  unsigned __int64 v1114; // [rsp+88h] [rbp-80h]
  int v1115; // [rsp+88h] [rbp-80h]
  _DWORD *v1116; // [rsp+90h] [rbp-78h]
  char *v1117; // [rsp+90h] [rbp-78h]
  char *v1118; // [rsp+90h] [rbp-78h]
  char *v1119; // [rsp+90h] [rbp-78h]
  char *v1120; // [rsp+90h] [rbp-78h]
  _WORD *v1121; // [rsp+90h] [rbp-78h]
  char *v1122; // [rsp+98h] [rbp-70h]
  char *v1123; // [rsp+98h] [rbp-70h]
  unsigned __int64 v1124; // [rsp+98h] [rbp-70h]
  unsigned int v1125; // [rsp+A0h] [rbp-68h]
  __int64 v1126; // [rsp+A0h] [rbp-68h]
  unsigned int v1127; // [rsp+A0h] [rbp-68h]
  unsigned int v1128; // [rsp+A0h] [rbp-68h]
  int v1129; // [rsp+A0h] [rbp-68h]
  int v1130; // [rsp+A0h] [rbp-68h]
  int v1131; // [rsp+A0h] [rbp-68h]
  int v1132; // [rsp+A0h] [rbp-68h]
  char *v1133; // [rsp+A8h] [rbp-60h]
  __int16 v1134; // [rsp+A8h] [rbp-60h]
  char *v1135; // [rsp+A8h] [rbp-60h]
  _QWORD *v1136; // [rsp+A8h] [rbp-60h]
  __int16 v1137; // [rsp+A8h] [rbp-60h]
  _QWORD *v1138; // [rsp+A8h] [rbp-60h]
  __int16 v1139; // [rsp+A8h] [rbp-60h]
  _QWORD *v1140; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v1141; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v1142; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v1143; // [rsp+B0h] [rbp-58h]
  _DWORD *v1144; // [rsp+B8h] [rbp-50h]
  char *v1145; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v1146; // [rsp+B8h] [rbp-50h]
  _QWORD *v1147; // [rsp+B8h] [rbp-50h]
  _DWORD *v1148; // [rsp+B8h] [rbp-50h]
  char *v1149; // [rsp+B8h] [rbp-50h]
  __int64 v1150; // [rsp+C0h] [rbp-48h]
  char *v1151; // [rsp+C0h] [rbp-48h]
  unsigned int v1152; // [rsp+C8h] [rbp-40h]
  int v1153; // [rsp+C8h] [rbp-40h]
  int v1154; // [rsp+C8h] [rbp-40h]
  int v1155; // [rsp+C8h] [rbp-40h]
  int v1156; // [rsp+C8h] [rbp-40h]
  int v1157; // [rsp+C8h] [rbp-40h]
  unsigned int v1158; // [rsp+C8h] [rbp-40h]
  char *v1159; // [rsp+D0h] [rbp-38h]
  char *v1160; // [rsp+D0h] [rbp-38h]
  char *v1161; // [rsp+D0h] [rbp-38h]
  __int64 v1162; // [rsp+D8h] [rbp-30h]
  __int64 v1163; // [rsp+D8h] [rbp-30h]
  char *v1164; // [rsp+D8h] [rbp-30h]
  char *v1165; // [rsp+D8h] [rbp-30h]
  char *v1166; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v1167; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v1168; // [rsp+E0h] [rbp-28h]
  unsigned __int64 v1169; // [rsp+E0h] [rbp-28h]
  char *v1170; // [rsp+E8h] [rbp-20h]
  char *v1171; // [rsp+E8h] [rbp-20h]
  char *v1172; // [rsp+E8h] [rbp-20h]
  char *v1173; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v1174; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v1175; // [rsp+E8h] [rbp-20h]
  __int64 v1176; // [rsp+E8h] [rbp-20h]
  int v1177; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v1178; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v1179; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v1180; // [rsp+F0h] [rbp-18h]
  __int64 v1181; // [rsp+F0h] [rbp-18h]
  __int64 v1182; // [rsp+F0h] [rbp-18h]
  __int64 v1183; // [rsp+F0h] [rbp-18h]
  _DWORD *v1184; // [rsp+F8h] [rbp-10h]
  __int64 v1185; // [rsp+F8h] [rbp-10h]
  unsigned __int64 v1186; // [rsp+F8h] [rbp-10h]
  _DWORD *v1187; // [rsp+F8h] [rbp-10h]
  _DWORD *v1188; // [rsp+100h] [rbp-8h]
  unsigned __int64 v1189; // [rsp+100h] [rbp-8h]
  _DWORD *v1190; // [rsp+108h] [rbp+0h]
  _DWORD *v1191; // [rsp+108h] [rbp+0h]
  _DWORD *v1192; // [rsp+108h] [rbp+0h]
  _DWORD *v1193; // [rsp+108h] [rbp+0h]
  char *v1194; // [rsp+108h] [rbp+0h]
  unsigned __int64 v1195; // [rsp+110h] [rbp+8h]
  _DWORD *v1196; // [rsp+110h] [rbp+8h]
  _DWORD *v1197; // [rsp+118h] [rbp+10h]
  unsigned __int64 v1198; // [rsp+118h] [rbp+10h]
  int v1203; // [rsp+1A0h] [rbp+98h]
  int v1204; // [rsp+1A0h] [rbp+98h]
  int v1205; // [rsp+1A0h] [rbp+98h]

  v7 = *((_QWORD *)a1 + 0x8000);
  v8 = a1;
  v12 = v7 + a1[65542] - a1[65543] - *((_QWORD *)a1 + 32769);
  if ( v12 >= 0x10000 )
  {
    v13 = 0;
    *((_QWORD *)v8 + 32773) = 0;
    if ( a7 == 2 && a5 < 1 )
      return v13;
    v14 = *a4;
    if ( (unsigned int)v14 > 0x7E000000 )
      return v13;
    v15 = a3 + a5;
    *((_QWORD *)v8 + 0x8000) = v7 + v14;
    v16 = *a4;
    v17 = Src;
    v18 = Src;
    *a4 = 0;
    v19 = v15 - 5;
    v1055 = Src;
    v20 = &Src[v16];
    v1122 = Src;
    v21 = a3;
    v1170 = v20;
    if ( a7 != 2 )
      v19 = v15;
    v1090 = a3;
    v1085 = HIDWORD(a3);
    v1086 = v19;
    if ( (int)v16 < 13 || (v1159 = v20 - 12, Src > v20 - 12) )
    {
LABEL_623:
      v314 = v20 - v18;
      v315 = v314;
      if ( a7 != 2 )
      {
        if ( !a7 )
          goto LABEL_664;
        goto LABEL_660;
      }
LABEL_624:
      v19 += 5LL;
LABEL_660:
      if ( v21 + (v314 + 240) / 0xFF + v314 + 1 > v19 )
      {
        if ( a7 == 1 )
          goto LABEL_662;
        v315 = v19 - v21 - 1 - ((v19 - v21 - 1 + 241) >> 8);
      }
LABEL_664:
      if ( v315 < 0xF )
      {
        LOBYTE(v327) = 16 * v315;
      }
      else
      {
        *(_BYTE *)v21 = -16;
        v327 = v315 - 15;
        ++v21;
        while ( v327 >= 0xFF )
        {
          *(_BYTE *)v21++ = -1;
          v327 -= 255LL;
        }
      }
      *(_BYTE *)v21 = v327;
      memmove((void *)(v21 + 1), v18, v315);
      *a4 = v315 + (_DWORD)v18 - (_DWORD)Src;
      v326 = v315 - a3 + v21 + 1;
      if ( v326 > 0 )
        return (unsigned int)v326;
      goto LABEL_671;
    }
    v1080 = 0;
    v1058 = v20 - 5;
    v1141 = 0;
    while ( 1 )
    {
      v22 = 3;
      v1203 = 3;
      v23 = a1[65543];
      v24 = (_QWORD *)*((_QWORD *)a1 + 32769);
      v25 = v23;
      v26 = a1[65542];
      v1116 = v24;
      v1152 = a1[65543];
      v27 = (_DWORD)v17 + a1[65542] - (_DWORD)v24;
      v1073 = v27;
      if ( (int)v23 + 0x10000 <= v27 )
        v25 = v27 - 0xFFFF;
      v28 = (_DWORD *)*((_QWORD *)a1 + 32770);
      v29 = *(_DWORD *)v17;
      v1064 = v25;
      v1144 = v28;
      v1025 = 0;
      v30 = 0;
      v1168 = 0;
      v1031 = 0;
      v31 = 256;
      v1133 = (char *)v28 + v26 - v23;
      v1107 = 256;
      v1046 = *(_DWORD *)v17;
      v32 = a1[65544];
      if ( v32 < v27 )
      {
        do
        {
          v33 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v24 + v32 - v26)) >> 17;
          v34 = v32 - a1[v33];
          if ( v34 > 0xFFFF )
            LOWORD(v34) = -1;
          *((_WORD *)a1 + (unsigned __int16)v32 + 0x10000) = v34;
          a1[v33] = v32++;
        }
        while ( v32 < v27 );
        v29 = v1046;
        v30 = 0;
        v28 = v1144;
      }
      v35 = v1055;
      a1[65544] = v27;
      v36 = a1[(unsigned __int64)(unsigned int)(-1640531535 * *v1055) >> 17];
      if ( v36 >= v25 )
      {
        while ( 1 )
        {
          if ( v31 <= 0 )
          {
LABEL_142:
            v21 = v1090;
            goto LABEL_143;
          }
          if ( v36 < (unsigned int)v26 )
          {
            if ( v36 <= (int)v26 - 4 && *(_DWORD *)((char *)v28 + v36 - v1152) == v29 )
            {
              v48 = (char *)(v35 + 1);
              v49 = (char *)v35 + (unsigned int)v26 - v36;
              if ( v49 > v1058 )
                v49 = v1058;
              v50 = (_QWORD *)((char *)v28 + v36 - v1152 + 4);
              if ( v48 >= v49 - 7 )
              {
                v52 = (char *)(v35 + 1);
                while ( v52 < v49 - 7 )
                {
                  if ( *(_QWORD *)v52 != *v50 )
                  {
                    __asm { tzcnt   rax, r8 }
                    v54 = (_DWORD)v52 + ((unsigned int)_RAX >> 3) - (_DWORD)v48;
                    goto LABEL_68;
                  }
                  v52 += 8;
LABEL_56:
                  ++v50;
                }
                if ( v52 < v49 - 3 && *(_DWORD *)v50 == *(_DWORD *)v52 )
                {
                  v52 += 4;
                  v50 = (_QWORD *)((char *)v50 + 4);
                }
                if ( v52 < v49 - 1 && *(_WORD *)v50 == *(_WORD *)v52 )
                {
                  v52 += 2;
                  v50 = (_QWORD *)((char *)v50 + 2);
                }
                if ( v52 < v49 && *(_BYTE *)v50 == *v52 )
                  LODWORD(v52) = (_DWORD)v52 + 1;
                v54 = (_DWORD)v52 - (_DWORD)v48;
LABEL_68:
                v35 = v1055;
              }
              else
              {
                if ( *(_QWORD *)v48 == *v50 )
                {
                  v52 = (char *)(v35 + 3);
                  goto LABEL_56;
                }
                __asm { tzcnt   r10, rcx }
                v54 = (unsigned int)_R10 >> 3;
              }
              v57 = (char *)v35 + v54 + 4;
              v58 = v54 + 4;
              if ( v57 == v49 && v49 < v1058 )
              {
                if ( v57 >= v1058 - 7 )
                {
                  v61 = v24;
                  v60 = v57;
LABEL_76:
                  while ( v60 < v1058 - 7 )
                  {
                    if ( *(_QWORD *)v60 != *v61 )
                    {
                      __asm { tzcnt   rax, r9 }
                      v63 = ((unsigned int)_RAX >> 3) - (_DWORD)v57 + (_DWORD)v60;
                      goto LABEL_90;
                    }
                    v60 += 8;
                    ++v61;
                  }
                  if ( v60 < v1058 - 3 && *(_DWORD *)v61 == *(_DWORD *)v60 )
                  {
                    v60 += 4;
                    v61 = (_QWORD *)((char *)v61 + 4);
                  }
                  if ( v60 < v1058 - 1 && *(_WORD *)v61 == *(_WORD *)v60 )
                  {
                    v60 += 2;
                    v61 = (_QWORD *)((char *)v61 + 2);
                  }
                  if ( v60 < v1058 && *(_BYTE *)v61 == *v60 )
                    LODWORD(v60) = (_DWORD)v60 + 1;
                  v63 = (_DWORD)v60 - (_DWORD)v57;
                }
                else
                {
                  if ( *(_QWORD *)v57 == *v24 )
                  {
                    v60 = v57 + 8;
                    v61 = v24 + 1;
                    goto LABEL_76;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v63 = (unsigned int)_RCX >> 3;
                }
LABEL_90:
                v58 = v54 + v63 + 4;
              }
              v30 = v1025;
              v37 = v1055;
              if ( v58 > v1203 )
              {
                v1203 = v58;
                v1031 = v27 - v36;
              }
            }
            else
            {
              v37 = v1055;
            }
          }
          else
          {
            v37 = v1055;
            v38 = v36 - (unsigned int)v26;
            if ( *(_WORD *)((char *)v1055 + v22 - 1) == *(_WORD *)((char *)v24 + v22 + v38 - 1)
              && *(_DWORD *)((char *)v24 + v38) == v29 )
            {
              v39 = v1055 + 1;
              v40 = (_QWORD *)((char *)v24 + v38 + 4);
              if ( v1055 + 1 >= (_DWORD *)(v1058 - 7) )
              {
                v42 = (char *)(v1055 + 1);
                while ( v42 < v1058 - 7 )
                {
                  if ( *v40 != *(_QWORD *)v42 )
                  {
                    __asm { tzcnt   rax, r8 }
                    v44 = ((unsigned int)_RAX >> 3) - (_DWORD)v39 + (_DWORD)v42;
                    goto LABEL_42;
                  }
                  v42 += 8;
LABEL_30:
                  ++v40;
                }
                if ( v42 < v1058 - 3 && *(_DWORD *)v40 == *(_DWORD *)v42 )
                {
                  v42 += 4;
                  v40 = (_QWORD *)((char *)v40 + 4);
                }
                if ( v42 < v1058 - 1 && *(_WORD *)v40 == *(_WORD *)v42 )
                {
                  v42 += 2;
                  v40 = (_QWORD *)((char *)v40 + 2);
                }
                if ( v42 < v1058 && *(_BYTE *)v40 == *v42 )
                  LODWORD(v42) = (_DWORD)v42 + 1;
                v44 = (_DWORD)v42 - (_DWORD)v39;
              }
              else
              {
                if ( *v40 == *v39 )
                {
                  v42 = (char *)(v1055 + 3);
                  goto LABEL_30;
                }
                __asm { tzcnt   rcx, rcx }
                v44 = (unsigned int)_RCX >> 3;
              }
LABEL_42:
              v30 = v1025;
              v47 = v44 + 4;
              v37 = v1055;
              if ( v47 > v22 )
              {
                v1203 = v47;
                v1031 = v27 - v36;
              }
            }
          }
          if ( *((_WORD *)a1 + (unsigned __int16)v36 + 0x10000) != 1 )
            goto LABEL_139;
          if ( v30 )
          {
            v1025 = v30;
            if ( v30 != 2 )
              goto LABEL_139;
          }
          else
          {
            if ( (_BYTE)v29 != HIBYTE(v29) || (unsigned __int16)v29 != HIWORD(v29) )
            {
              v30 = 1;
              v1025 = 1;
              goto LABEL_139;
            }
            v1025 = 2;
            v1168 = (unsigned int)LZ4HC_countPattern(v37 + 1, v1058, v29) + 4LL;
            v30 = 2;
          }
          v66 = v36 - 1;
          if ( v36 - 1 < v25 || (unsigned int)v26 - v36 < 3 )
            goto LABEL_139;
          if ( v66 >= (unsigned int)v26 )
          {
            v67 = 0;
            v68 = (_DWORD *)((char *)v24 + v66 - (unsigned int)v26);
          }
          else
          {
            v67 = 1;
            v68 = (_DWORD *)((char *)v1144 + v66 - v1152);
          }
          if ( *v68 != v29 )
            break;
          v69 = v1058;
          if ( v67 )
            v69 = v1133;
          v70 = (unsigned int)LZ4HC_countPattern(v68 + 1, v69, v1046) + 4LL;
          if ( v67 )
          {
            if ( (char *)v68 + v70 == v69 )
            {
              v71 = v1046;
              v72 = v70 & 3;
              if ( 8 * v72 )
                v71 = (unsigned int)__ROL4__(v1046, 8 * v72);
              v70 += (unsigned int)LZ4HC_countPattern(v1116, v1058, v71);
            }
            v73 = v1144;
          }
          else
          {
            v73 = v1116;
          }
          v29 = v1046;
          v74 = LZ4HC_reverseCountPattern(v68, v73, v1046);
          v76 = v74;
          if ( !v67 && (_DWORD *)((char *)v68 - v74) == v1116 && v1152 < (unsigned int)v26 )
          {
            if ( 8LL * (-v74 & 3) )
              v75 = (unsigned int)__ROL4__(v75, 8 * (-(char)v74 & 3));
            v77 = LZ4HC_reverseCountPattern(v1133, v1144, v75);
            v76 = v77 + v78;
          }
          v25 = v1064;
          v79 = v66 - v76;
          v36 = v1064;
          if ( v79 > v1064 )
            v36 = v79;
          v80 = v70 + v66 - v36;
          if ( v80 < v1168 || v70 > v1168 )
          {
            if ( (unsigned int)v26 - v36 - 1 >= 3 )
            {
              v22 = v1203;
              v24 = v1116;
              v81 = v1168;
              v35 = v1055;
              if ( v80 < v1168 )
                v81 = v80;
              if ( v1203 < v81 )
              {
                if ( (unsigned __int64)v1055 + v26 - v36 - (_QWORD)v1116 > 0xFFFF )
                  goto LABEL_142;
                v22 = v81;
                v1203 = v81;
                v1031 = v1073 - v36;
              }
              v82 = *((unsigned __int16 *)a1 + (unsigned __int16)v36 + 0x10000);
              if ( v82 > v36 )
                goto LABEL_142;
              v30 = v1025;
              goto LABEL_140;
            }
            v36 = v26;
          }
          else
          {
            v36 = v26;
            if ( (unsigned int)v26 - ((_DWORD)v70 - (_DWORD)v1168 + v66) - 1 >= 3 )
              v36 = v70 - v1168 + v66;
          }
          v24 = v1116;
          v30 = v1025;
LABEL_141:
          v27 = v1073;
          v31 = v1107 - 1;
          v28 = v1144;
          v35 = v1055;
          v22 = v1203;
          --v1107;
          if ( v36 < v25 )
            goto LABEL_142;
        }
        v25 = v1064;
LABEL_139:
        v82 = *((unsigned __int16 *)a1 + (unsigned __int16)v36 + 0x10000);
LABEL_140:
        v36 -= v82;
        goto LABEL_141;
      }
LABEL_143:
      v83 = v1031;
      if ( v22 >= 4 )
        break;
      v18 = v1122;
      v17 = (char *)v35 + 1;
      v1055 = v17;
LABEL_621:
      if ( v17 > v1159 )
      {
        v19 = v1086;
        v20 = v1170;
        goto LABEL_623;
      }
    }
    v84 = v1031;
    v85 = v35;
    v86 = __PAIR64__(v22, v1031) >> 32;
    while ( 1 )
    {
      v1177 = v86;
      v1188 = v85;
      v1134 = v84;
      while ( 1 )
      {
        v87 = v22;
        v1162 = v22;
        v88 = (_DWORD *)((char *)v35 + v22);
        v1190 = v88;
        if ( v88 > (_DWORD *)v1159 )
        {
          v164 = 0;
          v1026 = 0;
          v163 = 0;
          v1061 = 0;
        }
        else
        {
          v1061 = v22;
          v89 = (_DWORD *)((char *)v88 - 2);
          v1080 = (unsigned __int64)v89;
          v1099 = (_DWORD *)((char *)v88 - 2);
          v90 = (char *)a1[65542];
          v91 = (_QWORD *)*((_QWORD *)a1 + 32769);
          v92 = a1[65543];
          v93 = (_DWORD)v89 + a1[65542] - (_DWORD)v91;
          v1117 = (char *)v91;
          v1034 = a1[65542];
          v1108 = (_WORD)v89 + *((_WORD *)a1 + 131084) - (_WORD)v91;
          v1065 = v92;
          if ( v92 + 0x10000 <= v93 )
          {
            v94 = v93 - 0xFFFF;
            v1040 = v93 - 0xFFFF;
          }
          else
          {
            v1040 = a1[65543];
            v94 = v1040;
          }
          v95 = (char *)*((_QWORD *)a1 + 32770);
          v96 = a1[65544];
          v97 = *v89;
          v1091 = v95;
          v1047 = *v89;
          v1026 = 0;
          if ( v96 < v93 )
          {
            do
            {
              v98 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v91 + v96 - (_QWORD)v90)) >> 17;
              v99 = v96 - a1[v98];
              if ( v99 > 0xFFFF )
                LOWORD(v99) = -1;
              *((_WORD *)a1 + (unsigned __int16)v96 + 0x10000) = v99;
              a1[v98] = v96++;
            }
            while ( v96 < v93 );
            v84 = v1134;
            v97 = v1047;
            v95 = v1091;
          }
          a1[65544] = v93;
          v100 = a1[(unsigned __int64)(unsigned int)(-1640531535 * *v89) >> 17];
          if ( v100 >= v94 )
          {
            v101 = 256;
            v1145 = &v90[(_QWORD)v95 - v92];
            v102 = (_DWORD)v89 - (_DWORD)v1055;
            v1153 = 256;
            v103 = 0;
            v1074 = (_DWORD)v89 - (_DWORD)v1055;
            v104 = 0;
            v1169 = 0;
            v1019 = 0;
            while ( v101 > 0 )
            {
              if ( v100 < (unsigned int)v90 )
              {
                if ( v100 > (int)v90 - 4 )
                  goto LABEL_261;
                v120 = &v1091[v100 - v92];
                if ( *(_DWORD *)v120 != v97 )
                  goto LABEL_261;
                v121 = v120 + 4;
                v122 = (unsigned int)v90 - v100;
                v123 = (char *)(v89 + 1);
                v124 = (char *)v89 + v122;
                if ( v124 > v1058 )
                  v124 = v1058;
                if ( v123 >= v124 - 7 )
                {
                  v126 = (char *)(v89 + 1);
                  while ( v126 < v124 - 7 )
                  {
                    if ( *v121 != *(_QWORD *)v126 )
                    {
                      __asm { tzcnt   rsi, r8 }
                      v128 = (_DWORD)v126 + ((unsigned int)_RSI >> 3) - (_DWORD)v123;
                      goto LABEL_222;
                    }
                    v126 += 8;
LABEL_210:
                    ++v121;
                  }
                  if ( v126 < v124 - 3 && *(_DWORD *)v121 == *(_DWORD *)v126 )
                  {
                    v126 += 4;
                    v121 = (_QWORD *)((char *)v121 + 4);
                  }
                  if ( v126 < v124 - 1 && *(_WORD *)v121 == *(_WORD *)v126 )
                  {
                    v126 += 2;
                    v121 = (_QWORD *)((char *)v121 + 2);
                  }
                  if ( v126 < v124 && *(_BYTE *)v121 == *v126 )
                    LODWORD(v126) = (_DWORD)v126 + 1;
                  v128 = (_DWORD)v126 - (_DWORD)v123;
LABEL_222:
                  v102 = v1074;
                }
                else
                {
                  if ( *v121 == *(_QWORD *)v123 )
                  {
                    v126 = (char *)(v89 + 3);
                    goto LABEL_210;
                  }
                  __asm { tzcnt   rsi, rcx }
                  v128 = (unsigned int)_RSI >> 3;
                }
                v131 = v128 + 4;
                v132 = (char *)v89 + v128 + 4;
                if ( v132 == v124 && v124 < v1058 )
                {
                  if ( v132 >= v1058 - 7 )
                  {
                    v135 = v91;
                    v134 = (char *)v89 + v128 + 4;
LABEL_230:
                    while ( v134 < v1058 - 7 )
                    {
                      if ( *v135 != *(_QWORD *)v134 )
                      {
                        __asm { tzcnt   rax, r8 }
                        v137 = ((unsigned int)_RAX >> 3) - (_DWORD)v132 + (_DWORD)v134;
                        goto LABEL_244;
                      }
                      v134 += 8;
                      ++v135;
                    }
                    if ( v134 < v1058 - 3 && *(_DWORD *)v135 == *(_DWORD *)v134 )
                    {
                      v134 += 4;
                      v135 = (_QWORD *)((char *)v135 + 4);
                    }
                    if ( v134 < v1058 - 1 && *(_WORD *)v135 == *(_WORD *)v134 )
                    {
                      v134 += 2;
                      v135 = (_QWORD *)((char *)v135 + 2);
                    }
                    if ( v134 < v1058 && *(_BYTE *)v135 == *v134 )
                      LODWORD(v134) = (_DWORD)v134 + 1;
                    v137 = (_DWORD)v134 - (_DWORD)v132;
                  }
                  else
                  {
                    if ( *v91 == *(_QWORD *)v132 )
                    {
                      v134 = v132 + 8;
                      v135 = v91 + 1;
                      goto LABEL_230;
                    }
                    __asm { tzcnt   rcx, rcx }
                    v137 = (unsigned int)_RCX >> 3;
                  }
LABEL_244:
                  v102 = v1074;
                  v131 = v128 + v137 + 4;
                }
                v140 = 0;
                if ( v102 )
                {
                  v141 = (_DWORD)v1055 - (_DWORD)v89;
                  if ( (char *)v1055 - (char *)v89 <= v1091 - v120 )
                    v141 = (_DWORD)v1091 - (_DWORD)v120;
                  for ( i = -v141; i > 3; i = v140 - v141 )
                  {
                    if ( *(_DWORD *)&v120[v140 - 4] != *(_DWORD *)((char *)v89 + v140 - 4) )
                    {
                      _BitScanReverse(&v144, *(_DWORD *)&v120[v140 - 4] ^ *(_DWORD *)((char *)v89 + v140 - 4));
                      v140 -= (31 - v144) >> 3;
                      goto LABEL_256;
                    }
                    v140 -= 4;
                  }
                  if ( v140 > v141 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v89 + v140 - 1) != v120[v140 - 1] )
                        break;
                      --v140;
                    }
                    while ( v140 > v141 );
                    v84 = v1134;
                  }
                }
LABEL_256:
                v97 = v1047;
                v143 = v131 - v140;
                v109 = v1058;
                if ( v143 > v1061 )
                {
                  v1061 = v143;
                  v1026 = v1108 - v100;
                  v1080 = (unsigned __int64)v89 + v140;
                }
                LODWORD(v90) = v1034;
                v104 = v1019;
              }
              else
              {
                v105 = (_DWORD *)((char *)v91 + v100 - (unsigned int)v90);
                if ( *(_WORD *)((char *)v1055 + v1061 - 1) != *(_WORD *)((char *)v105 + v1061 - (__int64)v102 - 1)
                  || *v105 != v97 )
                {
                  v104 = v1019;
LABEL_261:
                  v109 = v1058;
                  goto LABEL_262;
                }
                if ( v102 )
                {
                  v106 = -(__int64)(v100 - (unsigned int)v90);
                  v107 = (_DWORD)v1055 - (_DWORD)v89;
                  if ( (char *)v1055 - (char *)v89 <= v106 )
                    v107 = v106;
                  for ( j = -v107; j > 3; j = v103 - v107 )
                  {
                    if ( *(_DWORD *)((char *)v89 + v103 - 4) != *(_DWORD *)((char *)v105 + v103 - 4) )
                    {
                      _BitScanReverse(&v114, *(_DWORD *)((char *)v89 + v103 - 4) ^ *(_DWORD *)((char *)v105 + v103 - 4));
                      v103 -= (31 - v114) >> 3;
                      goto LABEL_174;
                    }
                    v103 -= 4;
                  }
                  if ( v103 > v107 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v89 + v103 - 1) != *((_BYTE *)v105 + v103 - 1) )
                        break;
                      --v103;
                    }
                    while ( v103 > v107 );
                    v84 = v1134;
                  }
                }
LABEL_174:
                v109 = v1058;
                v110 = v105 + 1;
                v111 = v89 + 1;
                if ( v89 + 1 >= (_DWORD *)(v1058 - 7) )
                {
                  v113 = (char *)(v89 + 1);
                  while ( v113 < v1058 - 7 )
                  {
                    if ( *v110 != *(_QWORD *)v113 )
                    {
                      __asm { tzcnt   rax, r8 }
                      v116 = ((unsigned int)_RAX >> 3) - (_DWORD)v111 + (_DWORD)v113;
                      goto LABEL_195;
                    }
                    v113 += 8;
LABEL_183:
                    ++v110;
                  }
                  if ( v113 < v1058 - 3 && *(_DWORD *)v110 == *(_DWORD *)v113 )
                  {
                    v113 += 4;
                    v110 = (_QWORD *)((char *)v110 + 4);
                  }
                  if ( v113 < v1058 - 1 && *(_WORD *)v110 == *(_WORD *)v113 )
                  {
                    v113 += 2;
                    v110 = (_QWORD *)((char *)v110 + 2);
                  }
                  if ( v113 < v1058 && *(_BYTE *)v110 == *v113 )
                    LODWORD(v113) = (_DWORD)v113 + 1;
                  v116 = (_DWORD)v113 - (_DWORD)v111;
                }
                else
                {
                  if ( *v110 == *v111 )
                  {
                    v113 = (char *)(v89 + 3);
                    goto LABEL_183;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v116 = (unsigned int)_RCX >> 3;
                }
LABEL_195:
                LODWORD(v90) = v1034;
                v104 = v1019;
                v119 = v116 - v103 + 4;
                if ( v119 > v1061 )
                {
                  v1061 = v119;
                  v1026 = v93 - v100;
                  v1080 = (unsigned __int64)v89 + v103;
                }
              }
LABEL_262:
              if ( *((_WORD *)a1 + (unsigned __int16)v100 + 0x10000) != 1 )
                goto LABEL_267;
              if ( v104 )
              {
                v1019 = v104;
                if ( v104 != 2 )
                  goto LABEL_267;
              }
              else
              {
                if ( (_BYTE)v97 != HIBYTE(v97) || (unsigned __int16)v97 != HIWORD(v97) )
                {
                  v104 = 1;
                  v1019 = 1;
LABEL_267:
                  v146 = v1040;
LABEL_268:
                  LODWORD(v90) = v1034;
                  v147 = *((unsigned __int16 *)a1 + (unsigned __int16)v100 + 0x10000);
LABEL_269:
                  v100 -= v147;
                  goto LABEL_270;
                }
                v1019 = 2;
                v145 = LZ4HC_countPattern(v89 + 1, v109, v97);
                v104 = 2;
                v1169 = v145 + 4LL;
              }
              v146 = v1040;
              v149 = v100 - 1;
              if ( v100 - 1 < v1040 || (unsigned int)v90 - v100 < 3 )
                goto LABEL_268;
              if ( v149 >= (unsigned int)v90 )
              {
                v150 = 0;
                v90 = &v1117[v149 - (unsigned int)v90];
              }
              else
              {
                v150 = 1;
                v90 = &v1091[v149 - v1065];
              }
              if ( *(_DWORD *)v90 != v97 )
                goto LABEL_267;
              v151 = v1058;
              if ( v150 )
                v151 = v1145;
              v152 = (unsigned int)LZ4HC_countPattern(v90 + 4, v151, v1047) + 4LL;
              if ( v150 )
              {
                if ( &v90[v152] == v151 )
                {
                  v153 = v1047;
                  v154 = v152 & 3;
                  if ( 8 * v154 )
                    v153 = (unsigned int)__ROL4__(v1047, 8 * v154);
                  v152 += (unsigned int)LZ4HC_countPattern(v1117, v1058, v153);
                }
                v155 = v1091;
              }
              else
              {
                v155 = v1117;
              }
              v156 = LZ4HC_reverseCountPattern(v90, v155, v1047);
              v157 = v1117;
              v158 = v156;
              if ( v150 )
              {
                LODWORD(v90) = v1034;
              }
              else
              {
                v159 = &v90[-v156] == v1117;
                LODWORD(v90) = v1034;
                if ( v159 && v1065 < v1034 )
                {
                  v160 = v1047;
                  if ( 8LL * (-v156 & 3) )
                    v160 = (unsigned int)__ROL4__(v1047, 8 * (-(char)v156 & 3));
                  v158 = LZ4HC_reverseCountPattern(v1145, v1091, v160) + v156;
                  v157 = v1117;
                }
              }
              v146 = v1040;
              v100 = v1040;
              if ( v149 - v158 > v1040 )
                v100 = v149 - v158;
              v161 = v152 + v149 - v100;
              if ( v161 < v1169 || v152 > v1169 )
              {
                if ( (unsigned int)v90 - v100 - 1 < 3 )
                {
                  v100 = (unsigned int)v90;
                }
                else if ( !v1074 )
                {
                  v162 = v1169;
                  if ( v161 < v1169 )
                    v162 = v152 + v149 - v100;
                  if ( v1061 < v162 )
                  {
                    if ( (unsigned __int64)v1099 + (unsigned int)v90 - (unsigned __int64)v100 - (_QWORD)v157 > 0xFFFF )
                      break;
                    v1061 = v162;
                    v1026 = v1108 - v100;
                    v1080 = (unsigned __int64)v1099;
                  }
                  v147 = *((unsigned __int16 *)a1 + (unsigned __int16)v100 + 0x10000);
                  if ( v147 > v100 )
                    break;
                  v104 = v1019;
                  goto LABEL_269;
                }
              }
              else
              {
                v100 = (unsigned int)v90;
                if ( (unsigned int)v90 - ((_DWORD)v152 - (_DWORD)v1169 + v149) - 1 >= 3 )
                  v100 = v152 - v1169 + v149;
              }
              v104 = v1019;
LABEL_270:
              v89 = v1099;
              v101 = v1153 - 1;
              v97 = v1047;
              v148 = v100 < v146;
              v91 = v1117;
              LOWORD(v93) = v1108;
              v102 = v1074;
              v92 = v1065;
              --v1153;
              if ( v148 )
                break;
              v103 = 0;
            }
          }
          LODWORD(v86) = v1177;
          v85 = v1188;
          v88 = v1190;
          v87 = v1162;
          v163 = v1061;
          v35 = v1055;
          v22 = v1203;
          v164 = v1026;
          v83 = v1031;
        }
        if ( v163 <= v22 )
        {
          v19 = v1086;
          v303 = (_BYTE *)(v21 + 1);
          v252 = v21;
          v250 = v21 >> 32;
          v304 = (char *)v21;
          v254 = v1122;
          v305 = (char *)v35 - v1122;
          if ( a7 && (unsigned __int64)&v303[v305 + 8 + v305 / 0xFF] > v1086 )
            goto LABEL_629;
          if ( v305 < 0xF )
          {
            *v304 = 16 * v305;
          }
          else
          {
            v306 = v305 - 15;
            *v304 = -16;
            while ( v306 >= 0xFF )
            {
              *v303++ = -1;
              v306 -= 255LL;
            }
            *v303++ = v306;
          }
          v307 = v1122;
          v308 = &v303[v305];
          do
          {
            v309 = *(_QWORD *)v307;
            v307 += 8;
            *(_QWORD *)v303 = v309;
            v303 += 8;
          }
          while ( v303 < (_BYTE *)v308 );
          *v308 = v83;
          v310 = v87 - 4;
          v21 = (__int64)(v308 + 1);
          v1090 = v21;
          v1085 = HIDWORD(v21);
          if ( a7 && v21 + v310 / 0xFF + 6 > v1086 )
          {
            v18 = v1122;
            goto LABEL_630;
          }
          v311 = *v304;
          if ( v310 < 0xF )
          {
            *v304 = v311 + v310;
          }
          else
          {
            *v304 = v311 + 15;
            for ( k = v87 - 19; k >= 0x1FE; k -= 510LL )
            {
              *(_BYTE *)v21 = -1;
              v313 = (_BYTE *)(v21 + 1);
              *v313 = -1;
              v21 = (__int64)(v313 + 1);
            }
            if ( k >= 0xFF )
            {
              LOBYTE(k) = k + 1;
              *(_BYTE *)v21++ = -1;
            }
            *(_BYTE *)v21++ = k;
            v1090 = v21;
            v1085 = HIDWORD(v21);
          }
          v17 = (char *)v88;
          v1055 = v88;
          v18 = (char *)v88;
          v1122 = (char *)v88;
          goto LABEL_621;
        }
        v165 = v1080;
        if ( v85 < v35 && v1080 < (unsigned __int64)v35 + (int)v86 )
        {
          v35 = v85;
          v1055 = v85;
          LOWORD(v1031) = v84;
          v22 = v86;
          v1203 = v86;
        }
        if ( (__int64)(v1080 - (_QWORD)v35) >= 3 )
          break;
        v35 = (_DWORD *)v1080;
        v1055 = (_DWORD *)v1080;
        v83 = v164;
        LOWORD(v1031) = v164;
        v22 = v163;
        v1203 = v163;
      }
      while ( 1 )
      {
        if ( (__int64)(v165 - (_QWORD)v35) < 18 )
        {
          v166 = v22;
          if ( v22 > 18 )
            v166 = 18;
          if ( (unsigned __int64)v35 + v166 > v165 + v163 - 4LL )
            v166 = v163 + v165 - (_DWORD)v35 - 4;
          v167 = v166 + (_DWORD)v35 - v165;
          if ( v167 > 0 )
          {
            v165 += v167;
            v163 -= v167;
            v1080 = v165;
            v1061 = v163;
          }
        }
        v168 = v163;
        v1163 = v163;
        v169 = (_DWORD *)(v163 + v165);
        v1191 = v169;
        if ( v169 > (_DWORD *)v1159 )
        {
          v83 = 0;
          v245 = 0;
        }
        else
        {
          v170 = (_DWORD *)((char *)v169 - 3);
          v1041 = v163;
          v171 = (char *)v169 - 3;
          v1141 = (unsigned __int64)v169 - 3;
          v1146 = (unsigned __int64)v169 - 3;
          v172 = a1[65543];
          v173 = v172;
          v174 = (char *)a1[65542];
          v175 = (_QWORD *)*((_QWORD *)a1 + 32769);
          v1118 = (char *)v175;
          v176 = (_DWORD)v169 - 3 + a1[65542] - (_DWORD)v175;
          v1100 = a1[65542];
          v1066 = (_WORD)v169 - 3 + *((_WORD *)a1 + 131084) - (_WORD)v175;
          v1109 = v172;
          if ( v172 + 0x10000 <= v176 )
            v173 = v176 - 0xFFFF;
          v177 = (char *)*((_QWORD *)a1 + 32770);
          v178 = a1[65544];
          v179 = *v170;
          v1125 = v173;
          v1092 = v177;
          v1020 = *v170;
          v1075 = 0;
          if ( v178 < v176 )
          {
            do
            {
              v180 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v175 + v178 - (_QWORD)v174)) >> 17;
              v181 = v178 - a1[v180];
              if ( v181 > 0xFFFF )
                LOWORD(v181) = -1;
              *((_WORD *)a1 + (unsigned __int16)v178 + 0x10000) = v181;
              a1[v180] = v178++;
            }
            while ( v178 < v176 );
            v179 = v1020;
            v172 = v1109;
          }
          a1[65544] = v176;
          v182 = a1[(unsigned __int64)(-1640531535 * *v170) >> 17];
          if ( v182 >= v173 )
          {
            v183 = 256;
            v1135 = &v174[(_QWORD)v177 - v172];
            v184 = (_DWORD)v171 - v1080;
            v1154 = 256;
            v1048 = (_DWORD)v171 - v1080;
            v185 = 0;
            v1035 = 0;
            v1189 = 0;
            while ( 1 )
            {
              if ( v183 <= 0 )
                goto LABEL_492;
              if ( v182 < (unsigned int)v174 )
              {
                if ( v182 > (int)v174 - 4 )
                  goto LABEL_439;
                v202 = &v177[v182 - v172];
                if ( *(_DWORD *)v202 != v179 )
                {
                  v185 = v1035;
LABEL_439:
                  v191 = v1058;
                  goto LABEL_440;
                }
                v203 = v171 + 4;
                v204 = &v171[(unsigned int)v174 - v182];
                v205 = v202 + 4;
                if ( v204 > v1058 )
                  v204 = v1058;
                if ( v203 >= v204 - 7 )
                {
                  v207 = v171 + 4;
                  while ( v207 < v204 - 7 )
                  {
                    if ( *v205 != *(_QWORD *)v207 )
                    {
                      __asm { tzcnt   rdi, r8 }
                      v209 = (_DWORD)v207 + ((unsigned int)_RDI >> 3) - (_DWORD)v203;
                      goto LABEL_401;
                    }
                    v207 += 8;
LABEL_389:
                    ++v205;
                  }
                  if ( v207 < v204 - 3 && *(_DWORD *)v205 == *(_DWORD *)v207 )
                  {
                    v207 += 4;
                    v205 = (_QWORD *)((char *)v205 + 4);
                  }
                  if ( v207 < v204 - 1 && *(_WORD *)v205 == *(_WORD *)v207 )
                  {
                    v207 += 2;
                    v205 = (_QWORD *)((char *)v205 + 2);
                  }
                  if ( v207 < v204 && *(_BYTE *)v205 == *v207 )
                    LODWORD(v207) = (_DWORD)v207 + 1;
                  v209 = (_DWORD)v207 - (_DWORD)v203;
LABEL_401:
                  v184 = v1048;
                }
                else
                {
                  if ( *v205 == *(_QWORD *)v203 )
                  {
                    v207 = v171 + 12;
                    goto LABEL_389;
                  }
                  __asm { tzcnt   rdi, rcx }
                  v209 = (unsigned int)_RDI >> 3;
                }
                v212 = v209 + 4;
                v213 = &v171[v209 + 4];
                if ( v213 == v204 && v204 < v1058 )
                {
                  if ( v213 >= v1058 - 7 )
                  {
                    v216 = v175;
                    v215 = &v171[v209 + 4];
LABEL_409:
                    while ( v215 < v1058 - 7 )
                    {
                      if ( *v216 != *(_QWORD *)v215 )
                      {
                        __asm { tzcnt   rax, r8 }
                        v218 = ((unsigned int)_RAX >> 3) - (_DWORD)v213 + (_DWORD)v215;
                        goto LABEL_423;
                      }
                      v215 += 8;
                      ++v216;
                    }
                    if ( v215 < v1058 - 3 && *(_DWORD *)v216 == *(_DWORD *)v215 )
                    {
                      v215 += 4;
                      v216 = (_QWORD *)((char *)v216 + 4);
                    }
                    if ( v215 < v1058 - 1 && *(_WORD *)v216 == *(_WORD *)v215 )
                    {
                      v215 += 2;
                      v216 = (_QWORD *)((char *)v216 + 2);
                    }
                    if ( v215 < v1058 && *(_BYTE *)v216 == *v215 )
                      LODWORD(v215) = (_DWORD)v215 + 1;
                    v218 = (_DWORD)v215 - (_DWORD)v213;
                  }
                  else
                  {
                    if ( *v175 == *(_QWORD *)v213 )
                    {
                      v215 = v213 + 8;
                      v216 = v175 + 1;
                      goto LABEL_409;
                    }
                    __asm { tzcnt   rcx, rcx }
                    v218 = (unsigned int)_RCX >> 3;
                  }
LABEL_423:
                  v184 = v1048;
                  v212 = v209 + v218 + 4;
                }
                v221 = 0;
                if ( v184 )
                {
                  v222 = v1080 - (_DWORD)v171;
                  if ( (__int64)(v1080 - (_QWORD)v171) <= v1092 - v202 )
                    v222 = (_DWORD)v1092 - (_DWORD)v202;
                  for ( m = -v222; m > 3; m = v221 - v222 )
                  {
                    if ( *(_DWORD *)&v202[v221 - 4] != *(_DWORD *)&v171[v221 - 4] )
                    {
                      _BitScanReverse(&v225, *(_DWORD *)&v202[v221 - 4] ^ *(_DWORD *)&v171[v221 - 4]);
                      v221 -= (31 - v225) >> 3;
                      goto LABEL_435;
                    }
                    v221 -= 4;
                  }
                  if ( v221 > v222 )
                  {
                    do
                    {
                      if ( v171[v221 - 1] != v202[v221 - 1] )
                        break;
                      --v221;
                    }
                    while ( v221 > v222 );
                    LOWORD(v176) = v1066;
                  }
                }
LABEL_435:
                LODWORD(v174) = v1100;
                v224 = v212 - v221;
                v179 = v1020;
                v185 = v1035;
                v191 = v1058;
                if ( v224 > v1041 )
                {
                  v1041 = v224;
                  v1075 = v176 - v182;
                  v1141 = (unsigned __int64)&v171[v221];
                }
              }
              else
              {
                v186 = (_DWORD *)((char *)v175 + v182 - (unsigned int)v174);
                if ( *(_WORD *)(v1041 + v1080 - 1) != *(_WORD *)((char *)v186 + v1041 - (__int64)v184 - 1)
                  || *v186 != v179 )
                {
                  goto LABEL_439;
                }
                v187 = 0;
                if ( v184 )
                {
                  v188 = -(__int64)(v182 - (unsigned int)v174);
                  v189 = v1080 - (_DWORD)v171;
                  if ( (__int64)(v1080 - (_QWORD)v171) <= v188 )
                    v189 = v188;
                  for ( n = -v189; n > 3; n = v187 - v189 )
                  {
                    if ( *(_DWORD *)((char *)v186 + v187 - 4) != *(_DWORD *)&v171[v187 - 4] )
                    {
                      _BitScanReverse(&v196, *(_DWORD *)((char *)v186 + v187 - 4) ^ *(_DWORD *)&v171[v187 - 4]);
                      v187 -= (31 - v196) >> 3;
                      goto LABEL_353;
                    }
                    v187 -= 4;
                  }
                  if ( v187 > v189 )
                  {
                    do
                    {
                      if ( v171[v187 - 1] != *((_BYTE *)v186 + v187 - 1) )
                        break;
                      --v187;
                    }
                    while ( v187 > v189 );
                    LOWORD(v176) = v1066;
                  }
                }
LABEL_353:
                v191 = v1058;
                v192 = v186 + 1;
                v193 = v171 + 4;
                if ( v171 + 4 >= v1058 - 7 )
                {
                  v195 = v171 + 4;
                  while ( v195 < v1058 - 7 )
                  {
                    if ( *v192 != *(_QWORD *)v195 )
                    {
                      __asm { tzcnt   rax, r8 }
                      v198 = ((unsigned int)_RAX >> 3) - (_DWORD)v193 + (_DWORD)v195;
                      goto LABEL_374;
                    }
                    v195 += 8;
LABEL_362:
                    ++v192;
                  }
                  if ( v195 < v1058 - 3 && *(_DWORD *)v192 == *(_DWORD *)v195 )
                  {
                    v195 += 4;
                    v192 = (_QWORD *)((char *)v192 + 4);
                  }
                  if ( v195 < v1058 - 1 && *(_WORD *)v192 == *(_WORD *)v195 )
                  {
                    v195 += 2;
                    v192 = (_QWORD *)((char *)v192 + 2);
                  }
                  if ( v195 < v1058 && *(_BYTE *)v192 == *v195 )
                    LODWORD(v195) = (_DWORD)v195 + 1;
                  v198 = (_DWORD)v195 - (_DWORD)v193;
                }
                else
                {
                  if ( *v192 == *v193 )
                  {
                    v195 = v171 + 12;
                    goto LABEL_362;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v198 = (unsigned int)_RCX >> 3;
                }
LABEL_374:
                v179 = v1020;
                v201 = v198 - v187 + 4;
                if ( v201 > v1041 )
                {
                  v1041 = v201;
                  v1075 = v176 - v182;
                  v1141 = (unsigned __int64)&v171[v187];
                }
              }
LABEL_440:
              if ( *((_WORD *)a1 + (unsigned __int16)v182 + 0x10000) != 1 )
                goto LABEL_445;
              if ( v185 )
              {
                v1035 = v185;
                if ( v185 != 2 )
                  goto LABEL_445;
              }
              else
              {
                if ( (_BYTE)v179 != HIBYTE(v179) || (unsigned __int16)v179 != HIWORD(v179) )
                {
                  v185 = 1;
                  v1035 = 1;
LABEL_445:
                  v226 = v1125;
LABEL_446:
                  LODWORD(v174) = v1100;
                  v227 = *((unsigned __int16 *)a1 + (unsigned __int16)v182 + 0x10000);
                  goto LABEL_447;
                }
                v185 = 2;
                v1035 = 2;
                v1189 = (unsigned int)LZ4HC_countPattern(v171 + 4, v191, v179) + 4LL;
              }
              v226 = v1125;
              v228 = v182 - 1;
              if ( v182 - 1 < v1125 || (unsigned int)v174 - v182 < 3 )
                goto LABEL_446;
              if ( v228 >= (unsigned int)v174 )
              {
                v229 = 0;
                v174 = &v1118[v228 - (unsigned int)v174];
              }
              else
              {
                v229 = 1;
                v174 = &v1092[v228 - v1109];
              }
              if ( *(_DWORD *)v174 != v179 )
                goto LABEL_446;
              v230 = v1058;
              if ( v229 )
                v230 = v1135;
              v231 = (unsigned int)LZ4HC_countPattern(v174 + 4, v230, v179) + 4LL;
              if ( v229 )
              {
                v159 = &v174[v231] == v230;
                v232 = v1020;
                if ( v159 )
                {
                  v233 = v1020;
                  v234 = v231 & 3;
                  if ( 8 * v234 )
                    v233 = (unsigned int)__ROL4__(v1020, 8 * v234);
                  v231 += (unsigned int)LZ4HC_countPattern(v1118, v1058, v233);
                }
                v235 = v1092;
                v236 = v1092;
              }
              else
              {
                v236 = v1118;
                v232 = v1020;
                v235 = v1092;
              }
              v237 = LZ4HC_reverseCountPattern(v174, v236, v232);
              v238 = v1118;
              v239 = v237;
              if ( v229 )
              {
                LODWORD(v174) = v1100;
              }
              else
              {
                v159 = &v174[-v237] == v1118;
                LODWORD(v174) = v1100;
                if ( v159 && v1109 < v1100 )
                {
                  v240 = v232;
                  if ( 8LL * (-v237 & 3) )
                    v240 = (unsigned int)__ROL4__(v232, 8 * (-(char)v237 & 3));
                  v241 = LZ4HC_reverseCountPattern(v1135, v235, v240);
                  v239 = v241 + v242;
                  v238 = v1118;
                }
              }
              v226 = v1125;
              v182 = v1125;
              if ( v228 - v239 > v1125 )
                v182 = v228 - v239;
              v243 = v231 + v228 - v182;
              if ( v243 >= v1189 && v231 <= v1189 )
              {
                v182 = (unsigned int)v174;
                if ( (unsigned int)v174 - ((_DWORD)v231 - (_DWORD)v1189 + v228) - 1 >= 3 )
                  v182 = v231 - v1189 + v228;
                goto LABEL_490;
              }
              if ( (unsigned int)v174 - v182 - 1 < 3 )
              {
                v182 = (unsigned int)v174;
LABEL_490:
                v171 = (char *)v1146;
                v185 = v1035;
                goto LABEL_448;
              }
              if ( v1048 )
                goto LABEL_490;
              v171 = (char *)v1146;
              v244 = v1189;
              if ( v243 < v1189 )
                v244 = v243;
              if ( v1041 < v244 )
              {
                if ( v1146 + (unsigned int)v174 - (unsigned __int64)v182 - (_QWORD)v238 > 0xFFFF )
                  goto LABEL_492;
                v1041 = v244;
                v1075 = v1066 - v182;
                v1141 = v1146;
              }
              v227 = *((unsigned __int16 *)a1 + (unsigned __int16)v182 + 0x10000);
              if ( v227 > v182 )
                goto LABEL_492;
              v185 = v1035;
LABEL_447:
              v182 -= v227;
LABEL_448:
              v179 = v1020;
              v183 = v1154 - 1;
              v175 = v1118;
              LOWORD(v176) = v1066;
              v184 = v1048;
              v172 = v1109;
              v177 = v1092;
              --v1154;
              if ( v182 < v226 )
                goto LABEL_492;
            }
          }
          v1141 = (unsigned __int64)v170;
LABEL_492:
          v245 = v1041;
          v83 = v1075;
          v169 = v1191;
          v168 = v1163;
          v163 = v1061;
          v35 = v1055;
          v22 = v1203;
          v165 = v1080;
        }
        v246 = v22;
        if ( v245 <= v163 )
        {
          if ( v165 >= (unsigned __int64)v35 + v22 )
          {
            v277 = v1203;
          }
          else
          {
            v277 = v165 - (_DWORD)v35;
            v1203 = v165 - (_DWORD)v35;
          }
          v18 = v1122;
          v278 = (_BYTE *)(v21 + 1);
          v250 = v21 >> 32;
          v279 = (char *)v35 - v1122;
          v252 = v21;
          if ( a7 && (unsigned __int64)&v278[v279 + 8 + v279 / 0xFF] > v1086 )
          {
            v292 = (char *)v1055;
            v316 = v1203;
            v285 = v1031;
            v19 = v1086;
          }
          else
          {
            if ( v279 < 0xF )
            {
              *(_BYTE *)v21 = 16 * v279;
            }
            else
            {
              v280 = v279 - 15;
              *(_BYTE *)v21 = -16;
              while ( v280 >= 0xFF )
              {
                *v278++ = -1;
                v280 -= 255LL;
              }
              *v278++ = v280;
            }
            v281 = v1122;
            v282 = &v278[v279];
            do
            {
              v283 = *(_QWORD *)v281;
              v281 += 8;
              *(_QWORD *)v278 = v283;
              v278 += 8;
            }
            while ( v278 < (_BYTE *)v282 );
            v284 = (__int64)(v282 + 1);
            v285 = v1031;
            *v282 = v1031;
            v286 = v277;
            v287 = v277 - 4LL;
            if ( a7 && v284 + v287 / 0xFF + 6 > v1086 )
            {
              v19 = v1086;
              goto LABEL_631;
            }
            v288 = *(_BYTE *)v21;
            if ( v287 < 0xF )
            {
              *(_BYTE *)v21 = v288 + v287;
            }
            else
            {
              *(_BYTE *)v21 = v288 + 15;
              for ( ii = v277 - 19LL; ii >= 0x1FE; ii -= 510LL )
              {
                *(_BYTE *)v284 = -1;
                v290 = (_BYTE *)(v284 + 1);
                *v290 = -1;
                v284 = (__int64)(v290 + 1);
              }
              if ( ii >= 0xFF )
              {
                LOBYTE(ii) = ii + 1;
                *(_BYTE *)v284++ = -1;
              }
              *(_BYTE *)v284++ = ii;
            }
            v291 = (_BYTE *)(v284 + 1);
            v292 = (char *)v1080;
            v18 = (char *)v1055 + v286;
            v293 = v1080 - ((_QWORD)v1055 + v286);
            v250 = v284 >> 32;
            v252 = v284;
            if ( !a7 || (unsigned __int64)&v291[v293 + 8 + v293 / 0xFF] <= v1086 )
            {
              if ( v293 < 0xF )
              {
                *(_BYTE *)v284 = 16 * v293;
              }
              else
              {
                v294 = v293 - 15;
                *(_BYTE *)v284 = -16;
                while ( v294 >= 0xFF )
                {
                  *v291++ = -1;
                  v294 -= 255LL;
                }
                *v291++ = v294;
              }
              v295 = v18;
              v296 = &v291[v293];
              do
              {
                v297 = *(_QWORD *)v295;
                v295 += 8;
                *(_QWORD *)v291 = v297;
                v291 += 8;
              }
              while ( v291 < (_BYTE *)v296 );
              v298 = v1026;
              v299 = v168 - 4;
              *v296 = v1026;
              v21 = (__int64)(v296 + 1);
              v1090 = v21;
              v1085 = HIDWORD(v21);
              if ( a7 && v21 + v299 / 0xFF + 6 > v1086 )
                goto LABEL_626;
              v300 = *(_BYTE *)v284;
              if ( v299 < 0xF )
              {
                *(_BYTE *)v284 = v300 + v299;
              }
              else
              {
                *(_BYTE *)v284 = v300 + 15;
                for ( jj = v168 - 19; jj >= 0x1FE; jj -= 510LL )
                {
                  *(_BYTE *)v21 = -1;
                  v302 = (_BYTE *)(v21 + 1);
                  *v302 = -1;
                  v21 = (__int64)(v302 + 1);
                }
                if ( jj >= 0xFF )
                {
                  LOBYTE(jj) = jj + 1;
                  *(_BYTE *)v21++ = -1;
                }
                *(_BYTE *)v21++ = jj;
                v1090 = v21;
                v1085 = HIDWORD(v21);
              }
              v17 = (char *)v169;
              v1055 = v169;
              v18 = (char *)v169;
              v1122 = (char *)v169;
              goto LABEL_621;
            }
            v298 = v1026;
LABEL_626:
            v19 = v1086;
            v316 = v163;
            v285 = v298;
          }
LABEL_632:
          if ( a7 != 2 )
          {
LABEL_662:
            v326 = 0;
LABEL_671:
            *((_BYTE *)a1 + 262183) = 1;
            return (unsigned int)v326;
          }
          v21 = __PAIR64__(v250, v252);
          v317 = v292 - v18;
          v318 = (v292 - v18 + 240) / 0xFFuLL + v292 - v18 + 1;
          if ( v318 + __PAIR64__(v250, v252) <= v19 - 3 )
          {
            if ( v316 > 255 * (v19 - 3 - v318 - __PAIR64__(v250, v252)) + 18 )
              v316 = 255 * (v19 - 3 - v318 - v252) + 18;
            if ( (__int64)(v316 + v19 - v318 - __PAIR64__(v250, v252) + 2) >= 12 )
            {
              v319 = (_BYTE *)(__PAIR64__(v250, v252) + 1);
              if ( v317 < 0xF )
              {
                *(_BYTE *)__PAIR64__(v250, v252) = 16 * v317;
              }
              else
              {
                v320 = v317 - 15;
                *(_BYTE *)__PAIR64__(v250, v252) = -16;
                while ( v320 >= 0xFF )
                {
                  *v319++ = -1;
                  v320 -= 255LL;
                }
                *v319++ = v320;
              }
              v321 = &v319[v317];
              do
              {
                v322 = *(_QWORD *)v18;
                v18 += 8;
                *(_QWORD *)v319 = v322;
                v319 += 8;
              }
              while ( v319 < (_BYTE *)v321 );
              *v321 = v285;
              v323 = *(_BYTE *)__PAIR64__(v250, v252);
              v21 = (__int64)(v321 + 1);
              if ( (unsigned __int64)(v316 - 4LL) < 0xF )
              {
                *(_BYTE *)__PAIR64__(v250, v252) = v323 + v316 - 4;
              }
              else
              {
                *(_BYTE *)__PAIR64__(v250, v252) = v323 + 15;
                for ( kk = v316 - 19LL; kk >= 0x1FE; kk -= 510LL )
                {
                  *(_BYTE *)v21 = -1;
                  v325 = (_BYTE *)(v21 + 1);
                  *v325 = -1;
                  v21 = (__int64)(v325 + 1);
                }
                if ( kk >= 0xFF )
                {
                  LOBYTE(kk) = kk + 1;
                  *(_BYTE *)v21++ = -1;
                }
                *(_BYTE *)v21++ = kk;
              }
              v18 = &v292[v316];
            }
          }
          v314 = v1170 - v18;
          v315 = v1170 - v18;
          goto LABEL_624;
        }
        v247 = (char *)v35 + v22;
        if ( v1141 < (unsigned __int64)(v247 + 3) )
          break;
        if ( v165 >= (unsigned __int64)v247 )
        {
          v248 = v1203;
        }
        else if ( (__int64)(v165 - (_QWORD)v35) >= 18 )
        {
          v248 = v165 - (_DWORD)v35;
          v1203 = v165 - (_DWORD)v35;
        }
        else
        {
          if ( v22 > 18 )
            v22 = 18;
          v1203 = v22;
          if ( (_DWORD *)((char *)v35 + v22) > v169 - 1 )
          {
            v22 = v163 + v165 - (_DWORD)v35 - 4;
            v1203 = v22;
          }
          v248 = v1203;
          v249 = v22 + (_DWORD)v35 - v165;
          if ( v249 > 0 )
          {
            v1080 = v249 + v165;
            v163 -= v249;
          }
        }
        LODWORD(v250) = v1085;
        v251 = (_BYTE *)(v21 + 1);
        v19 = v1086;
        v252 = v21;
        v253 = (char *)v21;
        v254 = v1122;
        v255 = (char *)v35 - v1122;
        if ( a7 && (unsigned __int64)&v251[v255 / 0xFF + 8 + v255] > v1086 )
          goto LABEL_629;
        if ( v255 < 0xF )
        {
          *v253 = 16 * v255;
        }
        else
        {
          v256 = v255 - 15;
          *v253 = -16;
          while ( v256 >= 0xFF )
          {
            *v251++ = -1;
            v256 -= 255LL;
          }
          *v251++ = v256;
        }
        v257 = v1122;
        v258 = &v251[v255];
        do
        {
          v259 = *(_QWORD *)v257;
          v257 += 8;
          *(_QWORD *)v251 = v259;
          v251 += 8;
        }
        while ( v251 < (_BYTE *)v258 );
        *v258 = v1031;
        v21 = (__int64)(v258 + 1);
        v1085 = HIDWORD(v21);
        v260 = v248 - 4LL;
        if ( a7 && v21 + v260 / 0xFF + 6 > v1086 )
          goto LABEL_642;
        v261 = *v253;
        if ( v260 < 0xF )
        {
          *v253 = v261 + v260;
        }
        else
        {
          *v253 = v261 + 15;
          for ( mm = v248 - 19LL; mm >= 0x1FE; mm -= 510LL )
          {
            *(_BYTE *)v21 = -1;
            v263 = (_BYTE *)(v21 + 1);
            *v263 = -1;
            v21 = (__int64)(v263 + 1);
          }
          if ( mm >= 0xFF )
          {
            LOBYTE(mm) = mm + 1;
            *(_BYTE *)v21++ = -1;
          }
          *(_BYTE *)v21++ = mm;
          v1085 = HIDWORD(v21);
        }
        v22 = v163;
        v35 = (_DWORD *)v1080;
        v1122 = (char *)v1055 + v248;
        v165 = v1141;
        v1080 = v1141;
        v1055 = v35;
        LOWORD(v1031) = v1026;
        v1203 = v163;
LABEL_498:
        v1026 = v83;
        v163 = v245;
        v1061 = v245;
      }
      if ( v1141 < (unsigned __int64)v247 )
        break;
      if ( v165 >= (unsigned __int64)v247 )
        goto LABEL_534;
      v264 = v22 + (_DWORD)v35 - v165;
      v163 -= v264;
      if ( v163 >= 4 )
      {
        v1080 = v264 + v165;
LABEL_534:
        v265 = v1026;
        goto LABEL_535;
      }
      v1080 = v1141;
      v265 = v83;
      v163 = v245;
LABEL_535:
      v266 = (_BYTE *)(v21 + 1);
      v252 = v21;
      v250 = v21 >> 32;
      v267 = (char *)v21;
      v254 = v1122;
      v268 = (char *)v35 - v1122;
      if ( a7 && (unsigned __int64)&v266[v268 + 8 + v268 / 0xFF] > v1086 )
      {
        v19 = v1086;
LABEL_629:
        v18 = v254;
LABEL_630:
        v285 = v1031;
LABEL_631:
        v292 = (char *)v1055;
        v316 = v1203;
        goto LABEL_632;
      }
      if ( v268 < 0xF )
      {
        *v267 = 16 * v268;
      }
      else
      {
        v269 = v268 - 15;
        *v267 = -16;
        while ( v269 >= 0xFF )
        {
          *v266++ = -1;
          v269 -= 255LL;
        }
        *v266++ = v269;
      }
      v270 = v1122;
      v271 = &v266[v268];
      do
      {
        v272 = *(_QWORD *)v270;
        v270 += 8;
        *(_QWORD *)v266 = v272;
        v266 += 8;
      }
      while ( v266 < (_BYTE *)v271 );
      v273 = v246 - 4;
      *v271 = v1031;
      v21 = (__int64)(v271 + 1);
      v1085 = HIDWORD(v21);
      if ( a7 && v21 + v273 / 0xFF + 6 > v1086 )
      {
        v19 = v1086;
LABEL_642:
        v18 = v1122;
        goto LABEL_630;
      }
      v274 = *v267;
      if ( v273 < 0xF )
      {
        *v267 = v274 + v273;
      }
      else
      {
        *v267 = v274 + 15;
        for ( nn = v246 - 19; nn >= 0x1FE; nn -= 510LL )
        {
          *(_BYTE *)v21 = -1;
          v276 = (_BYTE *)(v21 + 1);
          *v276 = -1;
          v21 = (__int64)(v276 + 1);
        }
        if ( nn >= 0xFF )
        {
          LOBYTE(nn) = nn + 1;
          *(_BYTE *)v21++ = -1;
        }
        *(_BYTE *)v21++ = nn;
        v1085 = HIDWORD(v21);
      }
      v22 = v245;
      v85 = (_DWORD *)v1080;
      v35 = (_DWORD *)v1141;
      v1055 = (_DWORD *)v1141;
      v84 = v265;
      v1122 = v247;
      LODWORD(v86) = v163;
      LOWORD(v1031) = v83;
      v1203 = v245;
    }
    v165 = v1141;
    v1080 = v1141;
    goto LABEL_498;
  }
  v329 = 0;
  if ( !v12 && *a4 > 4096 )
  {
    memmove(v8, *((const void **)v8 + 32773), 0x40030u);
    LZ4HC_setExternalDict(v8, Src);
    *((_WORD *)v8 + 131090) = 9;
    if ( a7 == 2 && a5 < 1 )
      return v329;
    v330 = *a4;
    if ( (unsigned int)v330 > 0x7E000000 )
      return v329;
    *((_QWORD *)v8 + 0x8000) += v330;
    v331 = Src;
    v332 = *a4;
    v333 = Src;
    *a4 = 0;
    v334 = &Src[v332];
    v1059 = Src;
    v1123 = Src;
    v335 = a3;
    v336 = a3 + a5 - 5;
    v1164 = v334;
    if ( a7 != 2 )
      v336 = a3 + a5;
    v1093 = a3;
    v1087 = v336;
    v1082 = HIDWORD(a3);
    if ( (int)v332 < 13 || (v1160 = v334 - 12, Src > v334 - 12) )
    {
LABEL_1323:
      v635 = v334 - v333;
      v636 = v635;
      if ( a7 != 2 )
      {
        if ( !a7 )
          goto LABEL_1329;
        goto LABEL_1326;
      }
LABEL_1324:
      v336 += 5LL;
LABEL_1326:
      if ( v335 + (v635 + 240) / 0xFF + v635 + 1 > v336 )
      {
        if ( a7 != 1 )
        {
          v636 = v336 - v335 - 1 - ((v336 - v335 - 1 + 241) >> 8);
          goto LABEL_1329;
        }
        goto LABEL_2107;
      }
LABEL_1329:
      if ( v636 < 0xF )
      {
        LOBYTE(v637) = 16 * v636;
      }
      else
      {
        *(_BYTE *)v335 = -16;
        v637 = v636 - 15;
        ++v335;
        while ( v637 >= 0xFF )
        {
          *(_BYTE *)v335++ = -1;
          v637 -= 255LL;
        }
      }
      *(_BYTE *)v335 = v637;
      memmove((void *)(v335 + 1), v333, v636);
      *a4 = v636 + (_DWORD)v333 - (_DWORD)Src;
      v638 = v636 - a3 + v335 + 1;
      goto LABEL_2116;
    }
    v1083 = 0;
    v1056 = v334 - 5;
    v1142 = 0;
    while ( 1 )
    {
      v337 = (_QWORD *)*((_QWORD *)v8 + 32769);
      v338 = v8[65542];
      v339 = v8[65543];
      v1204 = 3;
      v340 = (_DWORD)v331 + v338 - (_DWORD)v337;
      v1136 = v337;
      v1049 = v340;
      v341 = v339;
      v1076 = v339;
      if ( (int)v339 + 0x10000 <= v340 )
        v341 = v340 - 0xFFFF;
      v1067 = v341;
      v342 = 256;
      v1101 = 256;
      v343 = (_QWORD *)*((_QWORD *)a1 + 32770);
      v344 = (_DWORD)v331 + v338 - (_DWORD)v337;
      v1110 = *(_DWORD *)v331;
      v345 = 0;
      v1027 = 0;
      v1178 = 0;
      v1032 = 0;
      v1147 = v343;
      v1171 = (char *)v343 + v338 - v339;
      v346 = a1[65544];
      if ( v346 < v344 )
      {
        do
        {
          v347 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v337 + v346 - v338)) >> 17;
          v348 = v346 - a1[v347];
          if ( v348 > 0xFFFF )
            LOWORD(v348) = -1;
          *((_WORD *)a1 + (unsigned __int16)v346 + 0x10000) = v348;
          a1[v347] = v346++;
        }
        while ( v346 < v344 );
        v343 = v1147;
      }
      v349 = v1059;
      a1[65544] = v344;
      v350 = a1[(unsigned __int64)(unsigned int)(-1640531535 * *v1059) >> 17];
      if ( v350 >= v341 )
      {
        while ( 1 )
        {
          if ( v342 <= 0 )
          {
LABEL_816:
            v335 = v1093;
            goto LABEL_817;
          }
          if ( v350 < (unsigned int)v338 )
          {
            if ( v350 > (int)v338 - 4 )
            {
              v351 = v1059;
            }
            else if ( *(_DWORD *)((char *)v343 + v350 - (unsigned int)v339) == v1110 )
            {
              v362 = (char *)(v349 + 1);
              v363 = (char *)v349 + (unsigned int)v338 - v350;
              if ( v363 > v1056 )
                v363 = v1056;
              v364 = (_QWORD *)((char *)v343 + v350 - (unsigned int)v339 + 4);
              if ( v362 >= v363 - 7 )
              {
                v366 = (char *)(v349 + 1);
                while ( v366 < v363 - 7 )
                {
                  if ( *(_QWORD *)v366 != *v364 )
                  {
                    __asm { tzcnt   rax, r8 }
                    v368 = (_DWORD)v366 + ((unsigned int)_RAX >> 3) - (_DWORD)v362;
                    goto LABEL_742;
                  }
                  v366 += 8;
LABEL_730:
                  ++v364;
                }
                if ( v366 < v363 - 3 && *(_DWORD *)v364 == *(_DWORD *)v366 )
                {
                  v366 += 4;
                  v364 = (_QWORD *)((char *)v364 + 4);
                }
                if ( v366 < v363 - 1 && *(_WORD *)v364 == *(_WORD *)v366 )
                {
                  v366 += 2;
                  v364 = (_QWORD *)((char *)v364 + 2);
                }
                if ( v366 < v363 && *(_BYTE *)v364 == *v366 )
                  LODWORD(v366) = (_DWORD)v366 + 1;
                v368 = (_DWORD)v366 - (_DWORD)v362;
LABEL_742:
                v349 = v1059;
              }
              else
              {
                if ( *(_QWORD *)v362 == *v364 )
                {
                  v366 = (char *)(v349 + 3);
                  goto LABEL_730;
                }
                __asm { tzcnt   r10, rcx }
                v368 = (unsigned int)_R10 >> 3;
              }
              v371 = (char *)v349 + v368 + 4;
              v372 = v368 + 4;
              if ( v371 == v363 && v363 < v1056 )
              {
                if ( v371 >= v1056 - 7 )
                {
                  v375 = v337;
                  v374 = v371;
LABEL_750:
                  while ( v374 < v1056 - 7 )
                  {
                    if ( *(_QWORD *)v374 != *v375 )
                    {
                      __asm { tzcnt   rax, r9 }
                      v377 = ((unsigned int)_RAX >> 3) - (_DWORD)v371 + (_DWORD)v374;
                      goto LABEL_764;
                    }
                    v374 += 8;
                    ++v375;
                  }
                  if ( v374 < v1056 - 3 && *(_DWORD *)v375 == *(_DWORD *)v374 )
                  {
                    v374 += 4;
                    v375 = (_QWORD *)((char *)v375 + 4);
                  }
                  if ( v374 < v1056 - 1 && *(_WORD *)v375 == *(_WORD *)v374 )
                  {
                    v374 += 2;
                    v375 = (_QWORD *)((char *)v375 + 2);
                  }
                  if ( v374 < v1056 && *(_BYTE *)v375 == *v374 )
                    LODWORD(v374) = (_DWORD)v374 + 1;
                  v377 = (_DWORD)v374 - (_DWORD)v371;
                }
                else
                {
                  if ( *(_QWORD *)v371 == *v337 )
                  {
                    v374 = v371 + 8;
                    v375 = v337 + 1;
                    goto LABEL_750;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v377 = (unsigned int)_RCX >> 3;
                }
LABEL_764:
                v372 = v368 + v377 + 4;
              }
              v345 = v1027;
              LODWORD(v339) = v1076;
              v351 = v1059;
              if ( v372 > v1204 )
              {
                v1204 = v372;
                v1032 = v340 - v350;
              }
            }
            else
            {
              v351 = v1059;
            }
          }
          else
          {
            v351 = v1059;
            v352 = v350 - (unsigned int)v338;
            if ( *(_WORD *)((char *)v1059 + v1204 - 1) == *(_WORD *)((char *)v337 + v1204 + v352 - 1)
              && *(_DWORD *)((char *)v337 + v352) == v1110 )
            {
              v353 = v1059 + 1;
              v354 = (_QWORD *)((char *)v337 + v352 + 4);
              if ( v1059 + 1 >= (_DWORD *)(v1056 - 7) )
              {
                v356 = (char *)(v1059 + 1);
                while ( v356 < v1056 - 7 )
                {
                  if ( *v354 != *(_QWORD *)v356 )
                  {
                    __asm { tzcnt   rax, r8 }
                    v358 = ((unsigned int)_RAX >> 3) - (_DWORD)v353 + (_DWORD)v356;
                    goto LABEL_716;
                  }
                  v356 += 8;
LABEL_704:
                  ++v354;
                }
                if ( v356 < v1056 - 3 && *(_DWORD *)v354 == *(_DWORD *)v356 )
                {
                  v356 += 4;
                  v354 = (_QWORD *)((char *)v354 + 4);
                }
                if ( v356 < v1056 - 1 && *(_WORD *)v354 == *(_WORD *)v356 )
                {
                  v356 += 2;
                  v354 = (_QWORD *)((char *)v354 + 2);
                }
                if ( v356 < v1056 && *(_BYTE *)v354 == *v356 )
                  LODWORD(v356) = (_DWORD)v356 + 1;
                v358 = (_DWORD)v356 - (_DWORD)v353;
              }
              else
              {
                if ( *v353 == *v354 )
                {
                  v356 = (char *)(v1059 + 3);
                  goto LABEL_704;
                }
                __asm { tzcnt   rcx, rcx }
                v358 = (unsigned int)_RCX >> 3;
              }
LABEL_716:
              v345 = v1027;
              v361 = v358 + 4;
              v351 = v1059;
              if ( v361 > v1204 )
              {
                v1204 = v361;
                v1032 = v340 - v350;
              }
            }
          }
          if ( *((_WORD *)a1 + (unsigned __int16)v350 + 0x10000) != 1 )
            goto LABEL_813;
          if ( v345 )
          {
            v1027 = v345;
            if ( v345 != 2 )
              goto LABEL_813;
          }
          else
          {
            if ( (_BYTE)v1110 != HIBYTE(v1110) || (unsigned __int16)v1110 != HIWORD(v1110) )
            {
              v345 = 1;
              v1027 = 1;
              goto LABEL_813;
            }
            v1027 = 2;
            v1178 = (unsigned int)LZ4HC_countPattern(v351 + 1, v1056, v1110) + 4LL;
            v345 = 2;
          }
          v380 = v350 - 1;
          if ( v350 - 1 < v341 || (unsigned int)v338 - v350 < 3 )
            goto LABEL_812;
          if ( v380 >= (unsigned int)v338 )
          {
            v381 = 0;
            v382 = (_DWORD *)((char *)v337 + v380 - (unsigned int)v338);
          }
          else
          {
            v381 = 1;
            v382 = (_DWORD *)((char *)v1147 + v380 - (unsigned int)v339);
          }
          if ( *v382 != v1110 )
            break;
          v383 = v1056;
          if ( v381 )
            v383 = v1171;
          v384 = (unsigned int)LZ4HC_countPattern(v382 + 1, v383, v1110) + 4LL;
          if ( v381 )
          {
            if ( (char *)v382 + v384 == v383 )
            {
              v385 = LZ4HC_rotatePattern(v384, v1110);
              v337 = v1136;
              v384 += (unsigned int)LZ4HC_countPattern(v1136, v1056, v385);
            }
            else
            {
              v337 = v1136;
            }
            v386 = v1147;
          }
          else
          {
            v337 = v1136;
            v386 = v1136;
          }
          v387 = LZ4HC_reverseCountPattern(v382, v386, v1110);
          v388 = v387;
          if ( !v381 && (_QWORD *)((char *)v382 - v387) == v337 && v1076 < (unsigned int)v338 )
          {
            v389 = LZ4HC_rotatePattern(-v387, v1110);
            v390 = LZ4HC_reverseCountPattern(v1171, v1147, v389);
            v388 = v390 + v391;
          }
          v341 = v1067;
          v392 = v380 - v388;
          v350 = v1067;
          if ( v392 > v1067 )
            v350 = v392;
          v393 = v384 + v380 - v350;
          if ( v393 < v1178 || v384 > v1178 )
          {
            if ( (unsigned int)v338 - v350 - 1 >= 3 )
            {
              v349 = v1059;
              v394 = v1178;
              if ( v393 < v1178 )
                v394 = v384 + v380 - v350;
              if ( v1204 >= v394 )
              {
                v340 = v1049;
              }
              else
              {
                if ( (unsigned __int64)v1059 + v338 - v350 - (_QWORD)v337 > 0xFFFF )
                  goto LABEL_816;
                v340 = v1049;
                v1204 = v394;
                v1032 = v1049 - v350;
              }
              v395 = *((unsigned __int16 *)a1 + (unsigned __int16)v350 + 0x10000);
              if ( v395 > v350 )
                goto LABEL_816;
              v345 = v1027;
              v342 = v1101;
              goto LABEL_814;
            }
            v350 = v338;
          }
          else
          {
            v350 = v338;
            if ( (unsigned int)v338 - ((_DWORD)v384 - (_DWORD)v1178 + v380) - 1 >= 3 )
              v350 = v384 - v1178 + v380;
          }
          v340 = v1049;
          v345 = v1027;
          v342 = v1101;
LABEL_815:
          LODWORD(v339) = v1076;
          v343 = v1147;
          --v342;
          v349 = v1059;
          v1101 = v342;
          if ( v350 < v341 )
            goto LABEL_816;
        }
        v341 = v1067;
LABEL_812:
        v342 = v1101;
LABEL_813:
        v395 = *((unsigned __int16 *)a1 + (unsigned __int16)v350 + 0x10000);
LABEL_814:
        v350 -= v395;
        goto LABEL_815;
      }
LABEL_817:
      v396 = v1204;
      v397 = v1032;
      if ( v1204 < 4 )
      {
        v333 = v1123;
        v331 = (char *)v349 + 1;
        v1059 = v331;
        goto LABEL_1287;
      }
      v398 = v1032;
      v399 = v349;
      v400 = __PAIR64__(v1204, v1032) >> 32;
LABEL_820:
      v1155 = v400;
      v1148 = v399;
      v1137 = v398;
      while ( 1 )
      {
        v401 = v396;
        v1126 = v396;
        v402 = (_DWORD *)((char *)v349 + v396);
        v1192 = v402;
        if ( v402 > (_DWORD *)v1160 )
        {
          v477 = 0;
          v1028 = 0;
          v476 = 0;
          v1062 = 0;
        }
        else
        {
          v403 = (_DWORD)v402 - 2;
          v1083 = (unsigned __int64)v402 - 2;
          v404 = (_DWORD *)((char *)v402 - 2);
          v1184 = (_DWORD *)((char *)v402 - 2);
          v1062 = v396;
          v405 = a1[65543];
          v406 = (_QWORD *)*((_QWORD *)a1 + 32769);
          v407 = (char *)a1[65542];
          v408 = (_DWORD)v407 + v403 - (_DWORD)v406;
          v1119 = (char *)v406;
          v1042 = a1[65542];
          v1111 = v408;
          v1068 = v405;
          if ( v405 + 0x10000 <= v408 )
          {
            v409 = v408 - 0xFFFF;
            v1102 = v408 - 0xFFFF;
          }
          else
          {
            v1102 = a1[65543];
            v409 = v1102;
          }
          v410 = (char *)*((_QWORD *)a1 + 32770);
          v411 = a1[65544];
          v412 = *v404;
          v1094 = v410;
          v1036 = *v404;
          v1028 = 0;
          if ( v411 < v408 )
          {
            do
            {
              v413 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v406 + v411 - (_QWORD)v407)) >> 17;
              v414 = v411 - a1[v413];
              if ( v414 > 0xFFFF )
                LOWORD(v414) = -1;
              *((_WORD *)a1 + (unsigned __int16)v411 + 0x10000) = v414;
              a1[v413] = v411++;
            }
            while ( v411 < v408 );
            v398 = v1137;
            v412 = v1036;
            v410 = v1094;
          }
          a1[65544] = v408;
          v415 = a1[(unsigned __int64)(unsigned int)(-1640531535 * *v404) >> 17];
          if ( v415 >= v409 )
          {
            v416 = 256;
            v1172 = &v410[(_QWORD)v407 - v405];
            v417 = (_DWORD)v404 - (_DWORD)v1059;
            v1077 = 256;
            v418 = 0;
            v1050 = (_DWORD)v404 - (_DWORD)v1059;
            v419 = 0;
            v1179 = 0;
            v1021 = 0;
            while ( v416 > 0 )
            {
              if ( v415 < (unsigned int)v407 )
              {
                if ( v415 > (int)v407 - 4 )
                  goto LABEL_935;
                v435 = &v1094[v415 - v405];
                if ( *(_DWORD *)v435 != v412 )
                  goto LABEL_935;
                v436 = v435 + 4;
                v437 = (unsigned int)v407 - v415;
                v438 = (char *)(v404 + 1);
                v439 = (char *)v404 + v437;
                if ( v439 > v1056 )
                  v439 = v1056;
                if ( v438 >= v439 - 7 )
                {
                  v441 = (char *)(v404 + 1);
                  while ( v441 < v439 - 7 )
                  {
                    if ( *v436 != *(_QWORD *)v441 )
                    {
                      __asm { tzcnt   rsi, r8 }
                      v443 = (_DWORD)v441 + ((unsigned int)_RSI >> 3) - (_DWORD)v438;
                      goto LABEL_896;
                    }
                    v441 += 8;
LABEL_884:
                    ++v436;
                  }
                  if ( v441 < v439 - 3 && *(_DWORD *)v436 == *(_DWORD *)v441 )
                  {
                    v441 += 4;
                    v436 = (_QWORD *)((char *)v436 + 4);
                  }
                  if ( v441 < v439 - 1 && *(_WORD *)v436 == *(_WORD *)v441 )
                  {
                    v441 += 2;
                    v436 = (_QWORD *)((char *)v436 + 2);
                  }
                  if ( v441 < v439 && *(_BYTE *)v436 == *v441 )
                    LODWORD(v441) = (_DWORD)v441 + 1;
                  v443 = (_DWORD)v441 - (_DWORD)v438;
LABEL_896:
                  v417 = v1050;
                }
                else
                {
                  if ( *(_QWORD *)v438 == *v436 )
                  {
                    v441 = (char *)(v404 + 3);
                    goto LABEL_884;
                  }
                  __asm { tzcnt   rsi, rcx }
                  v443 = (unsigned int)_RSI >> 3;
                }
                v446 = v443 + 4;
                v447 = (char *)v404 + v443 + 4;
                if ( v447 == v439 && v439 < v1056 )
                {
                  if ( v447 >= v1056 - 7 )
                  {
                    v450 = v406;
                    v449 = (char *)v404 + v443 + 4;
LABEL_904:
                    while ( v449 < v1056 - 7 )
                    {
                      if ( *v450 != *(_QWORD *)v449 )
                      {
                        __asm { tzcnt   rax, r8 }
                        v452 = ((unsigned int)_RAX >> 3) - (_DWORD)v447 + (_DWORD)v449;
                        goto LABEL_918;
                      }
                      v449 += 8;
                      ++v450;
                    }
                    if ( v449 < v1056 - 3 && *(_DWORD *)v450 == *(_DWORD *)v449 )
                    {
                      v449 += 4;
                      v450 = (_QWORD *)((char *)v450 + 4);
                    }
                    if ( v449 < v1056 - 1 && *(_WORD *)v450 == *(_WORD *)v449 )
                    {
                      v449 += 2;
                      v450 = (_QWORD *)((char *)v450 + 2);
                    }
                    if ( v449 < v1056 && *(_BYTE *)v450 == *v449 )
                      LODWORD(v449) = (_DWORD)v449 + 1;
                    v452 = (_DWORD)v449 - (_DWORD)v447;
                  }
                  else
                  {
                    if ( *(_QWORD *)v447 == *v406 )
                    {
                      v449 = v447 + 8;
                      v450 = v406 + 1;
                      goto LABEL_904;
                    }
                    __asm { tzcnt   rcx, rcx }
                    v452 = (unsigned int)_RCX >> 3;
                  }
LABEL_918:
                  v417 = v1050;
                  v446 = v443 + v452 + 4;
                }
                v455 = 0;
                if ( v417 )
                {
                  v456 = (_DWORD)v1059 - (_DWORD)v404;
                  if ( (char *)v1059 - (char *)v404 <= v1094 - v435 )
                    v456 = (_DWORD)v1094 - (_DWORD)v435;
                  for ( i1 = -v456; i1 > 3; i1 = v455 - v456 )
                  {
                    if ( *(_DWORD *)&v435[v455 - 4] != *(_DWORD *)((char *)v404 + v455 - 4) )
                    {
                      _BitScanReverse(&v459, *(_DWORD *)&v435[v455 - 4] ^ *(_DWORD *)((char *)v404 + v455 - 4));
                      v455 -= (31 - v459) >> 3;
                      goto LABEL_930;
                    }
                    v455 -= 4;
                  }
                  if ( v455 > v456 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v404 + v455 - 1) != v435[v455 - 1] )
                        break;
                      --v455;
                    }
                    while ( v455 > v456 );
                    v398 = v1137;
                  }
                }
LABEL_930:
                v412 = v1036;
                v458 = v446 - v455;
                v424 = v1056;
                if ( v458 > v1062 )
                {
                  v1062 = v458;
                  v1028 = v1111 - v415;
                  v1083 = (unsigned __int64)v404 + v455;
                }
                LODWORD(v407) = v1042;
                v419 = v1021;
              }
              else
              {
                v420 = (_DWORD *)((char *)v406 + v415 - (unsigned int)v407);
                if ( *(_WORD *)((char *)v1059 + v1062 - 1) != *(_WORD *)((char *)v420 + v1062 - (__int64)v417 - 1)
                  || *v420 != v412 )
                {
                  v419 = v1021;
LABEL_935:
                  v424 = v1056;
                  goto LABEL_936;
                }
                if ( v417 )
                {
                  v421 = -(__int64)(v415 - (unsigned int)v407);
                  v422 = (_DWORD)v1059 - (_DWORD)v404;
                  if ( (char *)v1059 - (char *)v404 <= v421 )
                    v422 = v421;
                  for ( i2 = -v422; i2 > 3; i2 = v418 - v422 )
                  {
                    if ( *(_DWORD *)((char *)v420 + v418 - 4) != *(_DWORD *)((char *)v404 + v418 - 4) )
                    {
                      _BitScanReverse(
                        &v429,
                        *(_DWORD *)((char *)v420 + v418 - 4) ^ *(_DWORD *)((char *)v404 + v418 - 4));
                      v418 -= (31 - v429) >> 3;
                      goto LABEL_848;
                    }
                    v418 -= 4;
                  }
                  if ( v418 > v422 )
                  {
                    do
                    {
                      if ( *((_BYTE *)v404 + v418 - 1) != *((_BYTE *)v420 + v418 - 1) )
                        break;
                      --v418;
                    }
                    while ( v418 > v422 );
                    v398 = v1137;
                  }
                }
LABEL_848:
                v424 = v1056;
                v425 = v420 + 1;
                v426 = v404 + 1;
                if ( v404 + 1 >= (_DWORD *)(v1056 - 7) )
                {
                  v428 = (char *)(v404 + 1);
                  while ( v428 < v1056 - 7 )
                  {
                    if ( *v425 != *(_QWORD *)v428 )
                    {
                      __asm { tzcnt   rax, r8 }
                      v431 = ((unsigned int)_RAX >> 3) - (_DWORD)v426 + (_DWORD)v428;
                      goto LABEL_869;
                    }
                    v428 += 8;
LABEL_857:
                    ++v425;
                  }
                  if ( v428 < v1056 - 3 && *(_DWORD *)v425 == *(_DWORD *)v428 )
                  {
                    v428 += 4;
                    v425 = (_QWORD *)((char *)v425 + 4);
                  }
                  if ( v428 < v1056 - 1 && *(_WORD *)v425 == *(_WORD *)v428 )
                  {
                    v428 += 2;
                    v425 = (_QWORD *)((char *)v425 + 2);
                  }
                  if ( v428 < v1056 && *(_BYTE *)v425 == *v428 )
                    LODWORD(v428) = (_DWORD)v428 + 1;
                  v431 = (_DWORD)v428 - (_DWORD)v426;
                }
                else
                {
                  if ( *v426 == *v425 )
                  {
                    v428 = (char *)(v404 + 3);
                    goto LABEL_857;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v431 = (unsigned int)_RCX >> 3;
                }
LABEL_869:
                LODWORD(v407) = v1042;
                v419 = v1021;
                v434 = v431 - v418 + 4;
                if ( v434 > v1062 )
                {
                  v1062 = v434;
                  v1028 = v408 - v415;
                  v1083 = (unsigned __int64)v404 + v418;
                }
              }
LABEL_936:
              if ( *((_WORD *)a1 + (unsigned __int16)v415 + 0x10000) != 1 )
                goto LABEL_941;
              if ( v419 )
              {
                v1021 = v419;
                if ( v419 != 2 )
                  goto LABEL_941;
              }
              else
              {
                if ( (_BYTE)v412 != HIBYTE(v412) || (unsigned __int16)v412 != HIWORD(v412) )
                {
                  v419 = 1;
                  v1021 = 1;
LABEL_941:
                  v408 = v1102;
LABEL_942:
                  LODWORD(v407) = v1042;
                  v461 = *((unsigned __int16 *)a1 + (unsigned __int16)v415 + 0x10000);
LABEL_943:
                  v415 -= v461;
                  goto LABEL_944;
                }
                v1021 = 2;
                v460 = LZ4HC_countPattern(v404 + 1, v424, v412);
                v419 = 2;
                v1179 = v460 + 4LL;
              }
              v408 = v1102;
              v462 = v415 - 1;
              if ( v415 - 1 < v1102 || (unsigned int)v407 - v415 < 3 )
                goto LABEL_942;
              if ( v462 >= (unsigned int)v407 )
              {
                v463 = 0;
                v407 = &v1119[v462 - (unsigned int)v407];
              }
              else
              {
                v463 = 1;
                v407 = &v1094[v462 - v1068];
              }
              if ( *(_DWORD *)v407 != v412 )
                goto LABEL_942;
              v464 = v1056;
              if ( v463 )
                v464 = v1172;
              v465 = (unsigned int)LZ4HC_countPattern(v407 + 4, v464, v412) + 4LL;
              if ( v463 )
              {
                if ( &v407[v465] == v464 )
                {
                  v466 = LZ4HC_rotatePattern(v465, v1036);
                  v465 += (unsigned int)LZ4HC_countPattern(v1119, v1056, v466);
                }
                v467 = v1094;
              }
              else
              {
                v467 = v1119;
              }
              v468 = LZ4HC_reverseCountPattern(v407, v467, v1036);
              v469 = v1119;
              v470 = v468;
              if ( v463 )
              {
                LODWORD(v407) = v1042;
              }
              else
              {
                v159 = &v407[-v468] == v1119;
                LODWORD(v407) = v1042;
                if ( v159 && v1068 < v1042 )
                {
                  v471 = LZ4HC_rotatePattern(-v468, v1036);
                  v472 = LZ4HC_reverseCountPattern(v1172, v1094, v471);
                  v469 = v1119;
                  v470 += v472;
                }
              }
              v473 = v462 - v470;
              v408 = v1102;
              v415 = v1102;
              if ( v473 > v1102 )
                v415 = v473;
              v474 = v465 + v462 - v415;
              if ( v474 < v1179 || v465 > v1179 )
              {
                if ( (unsigned int)v407 - v415 - 1 < 3 )
                {
                  v415 = (unsigned int)v407;
                }
                else if ( !v1050 )
                {
                  v475 = v1179;
                  if ( v474 < v1179 )
                    v475 = v465 + v462 - v415;
                  if ( v1062 < v475 )
                  {
                    if ( (unsigned __int64)(unsigned int)v407 + (char *)v1184 - v415 - v469 > 0xFFFF )
                      break;
                    v1062 = v475;
                    v1028 = v1111 - v415;
                    v1083 = (unsigned __int64)v1184;
                  }
                  v461 = *((unsigned __int16 *)a1 + (unsigned __int16)v415 + 0x10000);
                  if ( v461 > v415 )
                    break;
                  v419 = v1021;
                  goto LABEL_943;
                }
              }
              else
              {
                v415 = (unsigned int)v407;
                if ( (unsigned int)v407 - ((_DWORD)v465 - (_DWORD)v1179 + v462) - 1 >= 3 )
                  v415 = v465 - v1179 + v462;
              }
              v419 = v1021;
LABEL_944:
              v404 = v1184;
              v416 = v1077 - 1;
              v406 = v1119;
              v148 = v415 < v408;
              LOWORD(v408) = v1111;
              v412 = v1036;
              v417 = v1050;
              v405 = v1068;
              --v1077;
              if ( v148 )
                break;
              v418 = 0;
            }
          }
          LODWORD(v400) = v1155;
          v399 = v1148;
          v402 = v1192;
          v401 = v1126;
          v476 = v1062;
          v349 = v1059;
          v396 = v1204;
          v477 = v1028;
          v397 = v1032;
        }
        if ( v476 <= v396 )
          break;
        v478 = v1083;
        if ( v399 < v349 && v1083 < (unsigned __int64)v349 + (int)v400 )
        {
          v349 = v399;
          v1059 = v399;
          LOWORD(v1032) = v398;
          v396 = v400;
          v1204 = v400;
        }
        if ( (__int64)(v1083 - (_QWORD)v349) >= 3 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              if ( (__int64)(v478 - (_QWORD)v349) < 18 )
              {
                v479 = v396;
                if ( v396 > 18 )
                  v479 = 18;
                if ( (unsigned __int64)v349 + v479 > v478 + v476 - 4LL )
                  v479 = v476 + v478 - (_DWORD)v349 - 4;
                v480 = v479 + (_DWORD)v349 - v478;
                if ( v480 > 0 )
                {
                  v478 += v480;
                  v476 -= v480;
                  v1083 = v478;
                  v1062 = v476;
                }
              }
              v481 = v476;
              v1185 = v476;
              v482 = (_DWORD *)(v476 + v478);
              v1193 = v482;
              if ( v482 > (_DWORD *)v1160 )
              {
                v397 = 0;
                v556 = 0;
              }
              else
              {
                v1043 = v476;
                v483 = (_DWORD *)((char *)v482 - 3);
                v1142 = (unsigned __int64)v483;
                v484 = a1[65543];
                v485 = v484;
                v486 = (char *)a1[65542];
                v487 = (_QWORD *)*((_QWORD *)a1 + 32769);
                v1120 = (char *)v487;
                v488 = (_DWORD)v483 + a1[65542] - (_DWORD)v487;
                v1103 = a1[65542];
                v1051 = (_WORD)v483 + *((_WORD *)a1 + 131084) - (_WORD)v487;
                v1069 = v484;
                if ( v484 + 0x10000 <= v488 )
                  v485 = v488 - 0xFFFF;
                v489 = (char *)*((_QWORD *)a1 + 32770);
                v490 = a1[65544];
                v491 = *v483;
                v492 = (_DWORD)v486 + (_DWORD)v483 - (_DWORD)v487;
                v1127 = v485;
                v1095 = v489;
                v1022 = *v483;
                v1112 = 0;
                if ( v490 < v492 )
                {
                  do
                  {
                    v493 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v487 + v490 - (_QWORD)v486)) >> 17;
                    v494 = v490 - a1[v493];
                    if ( v494 > 0xFFFF )
                      LOWORD(v494) = -1;
                    *((_WORD *)a1 + (unsigned __int16)v490 + 0x10000) = v494;
                    a1[v493] = v490++;
                  }
                  while ( v490 < v492 );
                  v491 = v1022;
                  v484 = v1069;
                }
                a1[65544] = v492;
                v495 = a1[(unsigned __int64)(unsigned int)(-1640531535 * *v483) >> 17];
                if ( v495 >= v485 )
                {
                  v496 = 256;
                  v1173 = &v489[(_QWORD)v486 - v484];
                  v497 = (_DWORD)v483 - v1083;
                  v1156 = 256;
                  v498 = 0;
                  v499 = 0;
                  v1037 = 0;
                  v1180 = 0;
                  while ( 1 )
                  {
                    if ( v496 <= 0 )
                      goto LABEL_1159;
                    if ( v495 < (unsigned int)v486 )
                    {
                      if ( v495 > (int)v486 - 4 )
                        goto LABEL_1110;
                      v515 = &v489[v495 - v484];
                      if ( *(_DWORD *)v515 != v491 )
                      {
                        v499 = v1037;
LABEL_1110:
                        v504 = v1056;
                        goto LABEL_1111;
                      }
                      v516 = (char *)(v483 + 1);
                      v517 = (char *)v483 + (unsigned int)v486 - v495;
                      v518 = v515 + 4;
                      if ( v517 > v1056 )
                        v517 = v1056;
                      if ( v516 >= v517 - 7 )
                      {
                        v520 = (char *)(v483 + 1);
                        while ( v520 < v517 - 7 )
                        {
                          if ( *v518 != *(_QWORD *)v520 )
                          {
                            __asm { tzcnt   rdi, r8 }
                            v522 = (_DWORD)v520 + ((unsigned int)_RDI >> 3) - (_DWORD)v516;
                            goto LABEL_1072;
                          }
                          v520 += 8;
LABEL_1060:
                          ++v518;
                        }
                        if ( v520 < v517 - 3 && *(_DWORD *)v518 == *(_DWORD *)v520 )
                        {
                          v520 += 4;
                          v518 = (_QWORD *)((char *)v518 + 4);
                        }
                        if ( v520 < v517 - 1 && *(_WORD *)v518 == *(_WORD *)v520 )
                        {
                          v520 += 2;
                          v518 = (_QWORD *)((char *)v518 + 2);
                        }
                        if ( v520 < v517 && *(_BYTE *)v518 == *v520 )
                          LODWORD(v520) = (_DWORD)v520 + 1;
                        v522 = (_DWORD)v520 - (_DWORD)v516;
LABEL_1072:
                        v497 = (_DWORD)v483 - v1083;
                      }
                      else
                      {
                        if ( *v518 == *(_QWORD *)v516 )
                        {
                          v520 = (char *)(v483 + 3);
                          goto LABEL_1060;
                        }
                        __asm { tzcnt   rdi, rcx }
                        v522 = (unsigned int)_RDI >> 3;
                      }
                      v525 = v522 + 4;
                      v526 = (char *)v483 + v522 + 4;
                      if ( v526 == v517 && v517 < v1056 )
                      {
                        if ( v526 >= v1056 - 7 )
                        {
                          v529 = v487;
                          v528 = (char *)v483 + v522 + 4;
LABEL_1080:
                          while ( v528 < v1056 - 7 )
                          {
                            if ( *v529 != *(_QWORD *)v528 )
                            {
                              __asm { tzcnt   rax, r8 }
                              v531 = ((unsigned int)_RAX >> 3) - (_DWORD)v526 + (_DWORD)v528;
                              goto LABEL_1094;
                            }
                            v528 += 8;
                            ++v529;
                          }
                          if ( v528 < v1056 - 3 && *(_DWORD *)v529 == *(_DWORD *)v528 )
                          {
                            v528 += 4;
                            v529 = (_QWORD *)((char *)v529 + 4);
                          }
                          if ( v528 < v1056 - 1 && *(_WORD *)v529 == *(_WORD *)v528 )
                          {
                            v528 += 2;
                            v529 = (_QWORD *)((char *)v529 + 2);
                          }
                          if ( v528 < v1056 && *(_BYTE *)v529 == *v528 )
                            LODWORD(v528) = (_DWORD)v528 + 1;
                          v531 = (_DWORD)v528 - (_DWORD)v526;
                        }
                        else
                        {
                          if ( *(_QWORD *)v526 == *v487 )
                          {
                            v528 = v526 + 8;
                            v529 = v487 + 1;
                            goto LABEL_1080;
                          }
                          __asm { tzcnt   rcx, rcx }
                          v531 = (unsigned int)_RCX >> 3;
                        }
LABEL_1094:
                        v497 = (_DWORD)v483 - v1083;
                        v525 = v522 + v531 + 4;
                      }
                      v534 = 0;
                      if ( v497 )
                      {
                        v535 = v1083 - (_DWORD)v483;
                        if ( (__int64)(v1083 - (_QWORD)v483) <= v1095 - v515 )
                          v535 = (_DWORD)v1095 - (_DWORD)v515;
                        for ( i3 = -v535; i3 > 3; i3 = v534 - v535 )
                        {
                          if ( *(_DWORD *)((char *)v483 + v534 - 4) != *(_DWORD *)&v515[v534 - 4] )
                          {
                            _BitScanReverse(&v538, *(_DWORD *)((char *)v483 + v534 - 4) ^ *(_DWORD *)&v515[v534 - 4]);
                            v534 -= (31 - v538) >> 3;
                            goto LABEL_1106;
                          }
                          v534 -= 4;
                        }
                        if ( v534 > v535 )
                        {
                          do
                          {
                            if ( *((_BYTE *)v483 + v534 - 1) != v515[v534 - 1] )
                              break;
                            --v534;
                          }
                          while ( v534 > v535 );
                          LOWORD(v488) = v1051;
                        }
                      }
LABEL_1106:
                      LODWORD(v486) = v1103;
                      v537 = v525 - v534;
                      v491 = v1022;
                      v499 = v1037;
                      v504 = v1056;
                      if ( v537 > v1043 )
                      {
                        v1043 = v537;
                        v1112 = v488 - v495;
                        v1142 = (unsigned __int64)v483 + v534;
                      }
                    }
                    else
                    {
                      v500 = (_DWORD *)((char *)v487 + v495 - (unsigned int)v486);
                      if ( *(_WORD *)(v1043 + v1083 - 1) != *(_WORD *)((char *)v500 + v1043 - (__int64)v497 - 1)
                        || *v500 != v491 )
                      {
                        goto LABEL_1110;
                      }
                      if ( v497 )
                      {
                        v501 = -(__int64)(v495 - (unsigned int)v486);
                        v502 = v1083 - (_DWORD)v483;
                        if ( (__int64)(v1083 - (_QWORD)v483) <= v501 )
                          v502 = v501;
                        for ( i4 = -v502; i4 > 3; i4 = v498 - v502 )
                        {
                          if ( *(_DWORD *)((char *)v483 + v498 - 4) != *(_DWORD *)((char *)v500 + v498 - 4) )
                          {
                            _BitScanReverse(
                              &v509,
                              *(_DWORD *)((char *)v483 + v498 - 4) ^ *(_DWORD *)((char *)v500 + v498 - 4));
                            v498 -= (31 - v509) >> 3;
                            goto LABEL_1024;
                          }
                          v498 -= 4;
                        }
                        if ( v498 > v502 )
                        {
                          do
                          {
                            if ( *((_BYTE *)v483 + v498 - 1) != *((_BYTE *)v500 + v498 - 1) )
                              break;
                            --v498;
                          }
                          while ( v498 > v502 );
                          LOWORD(v488) = v1051;
                        }
                      }
LABEL_1024:
                      v504 = v1056;
                      v505 = v500 + 1;
                      v506 = v483 + 1;
                      if ( v483 + 1 >= (_DWORD *)(v1056 - 7) )
                      {
                        v508 = (char *)(v483 + 1);
                        while ( v508 < v1056 - 7 )
                        {
                          if ( *v505 != *(_QWORD *)v508 )
                          {
                            __asm { tzcnt   rax, r8 }
                            v511 = ((unsigned int)_RAX >> 3) - (_DWORD)v506 + (_DWORD)v508;
                            goto LABEL_1045;
                          }
                          v508 += 8;
LABEL_1033:
                          ++v505;
                        }
                        if ( v508 < v1056 - 3 && *(_DWORD *)v505 == *(_DWORD *)v508 )
                        {
                          v508 += 4;
                          v505 = (_QWORD *)((char *)v505 + 4);
                        }
                        if ( v508 < v1056 - 1 && *(_WORD *)v505 == *(_WORD *)v508 )
                        {
                          v508 += 2;
                          v505 = (_QWORD *)((char *)v505 + 2);
                        }
                        if ( v508 < v1056 && *(_BYTE *)v505 == *v508 )
                          LODWORD(v508) = (_DWORD)v508 + 1;
                        v511 = (_DWORD)v508 - (_DWORD)v506;
                      }
                      else
                      {
                        if ( *v505 == *v506 )
                        {
                          v508 = (char *)(v483 + 3);
                          goto LABEL_1033;
                        }
                        __asm { tzcnt   rcx, rcx }
                        v511 = (unsigned int)_RCX >> 3;
                      }
LABEL_1045:
                      v491 = v1022;
                      v514 = v511 - v498 + 4;
                      if ( v514 > v1043 )
                      {
                        v1043 = v514;
                        v1112 = v488 - v495;
                        v1142 = (unsigned __int64)v483 + v498;
                      }
                    }
LABEL_1111:
                    v539 = 1;
                    if ( *((_WORD *)a1 + (unsigned __int16)v495 + 0x10000) != 1 )
                      goto LABEL_1116;
                    if ( v499 )
                    {
                      v1037 = v499;
                      if ( v499 != 2 )
                        goto LABEL_1116;
                    }
                    else
                    {
                      if ( (_BYTE)v491 != HIBYTE(v491) || (unsigned __int16)v491 != HIWORD(v491) )
                      {
                        v499 = 1;
                        v1037 = 1;
LABEL_1116:
                        v540 = v1127;
LABEL_1117:
                        LODWORD(v486) = v1103;
                        v541 = *((unsigned __int16 *)a1 + (unsigned __int16)v495 + 0x10000);
LABEL_1118:
                        v495 -= v541;
                        goto LABEL_1119;
                      }
                      v499 = 2;
                      v1037 = 2;
                      v1180 = (unsigned int)LZ4HC_countPattern(v483 + 1, v504, v491) + 4LL;
                    }
                    v540 = v1127;
                    v542 = v495 - 1;
                    if ( v495 - 1 < v1127 || (unsigned int)v486 - v495 < 3 )
                      goto LABEL_1117;
                    if ( v542 >= (unsigned int)v486 )
                    {
                      v539 = 0;
                      v486 = &v1120[v542 - (unsigned int)v486];
                    }
                    else
                    {
                      v486 = &v1095[v542 - v1069];
                    }
                    if ( *(_DWORD *)v486 != v491 )
                      goto LABEL_1117;
                    v543 = v1056;
                    if ( v539 )
                      v543 = v1173;
                    v544 = (unsigned int)LZ4HC_countPattern(v486 + 4, v543, v491) + 4LL;
                    if ( v539 )
                    {
                      v159 = &v486[v544] == v543;
                      v545 = v1022;
                      if ( v159 )
                      {
                        v546 = LZ4HC_rotatePattern(v544, v1022);
                        v544 += (unsigned int)LZ4HC_countPattern(v1120, v1056, v546);
                      }
                      v547 = v1095;
                    }
                    else
                    {
                      v547 = v1120;
                      v545 = v1022;
                    }
                    v548 = LZ4HC_reverseCountPattern(v486, v547, v545);
                    v549 = v1120;
                    v550 = v548;
                    if ( v539 )
                    {
                      LODWORD(v486) = v1103;
                    }
                    else
                    {
                      v159 = &v486[-v548] == v1120;
                      LODWORD(v486) = v1103;
                      if ( v159 && v1069 < v1103 )
                      {
                        v551 = LZ4HC_rotatePattern(-v548, v545);
                        v552 = LZ4HC_reverseCountPattern(v1173, v1095, v551);
                        v550 = v552 + v553;
                        v549 = v1120;
                      }
                    }
                    v540 = v1127;
                    v495 = v1127;
                    if ( v542 - v550 > v1127 )
                      v495 = v542 - v550;
                    v554 = v544 + v542 - v495;
                    if ( v554 < v1180 || v544 > v1180 )
                    {
                      if ( (unsigned int)v486 - v495 - 1 < 3 )
                      {
                        v495 = (unsigned int)v486;
                      }
                      else if ( (_DWORD)v483 == (_DWORD)v1083 )
                      {
                        v555 = v1180;
                        if ( v554 < v1180 )
                          v555 = v544 + v542 - v495;
                        if ( v1043 < v555 )
                        {
                          if ( (unsigned __int64)(unsigned int)v486 + (char *)v483 - v495 - v549 > 0xFFFF )
                            goto LABEL_1159;
                          v1043 = v555;
                          v1112 = v1051 - v495;
                          v1142 = (unsigned __int64)v483;
                        }
                        v541 = *((unsigned __int16 *)a1 + (unsigned __int16)v495 + 0x10000);
                        if ( v541 > v495 )
                          goto LABEL_1159;
                        v499 = v1037;
                        goto LABEL_1118;
                      }
                    }
                    else
                    {
                      v495 = (unsigned int)v486;
                      if ( (unsigned int)v486 - ((_DWORD)v544 - (_DWORD)v1180 + v542) - 1 >= 3 )
                        v495 = v544 - v1180 + v542;
                    }
                    v499 = v1037;
LABEL_1119:
                    v487 = v1120;
                    v496 = v1156 - 1;
                    v491 = v1022;
                    v148 = v495 < v540;
                    v489 = v1095;
                    LOWORD(v488) = v1051;
                    v497 = (_DWORD)v483 - v1083;
                    v484 = v1069;
                    --v1156;
                    if ( v148 )
                      goto LABEL_1159;
                    v498 = 0;
                  }
                }
                v1142 = (unsigned __int64)v483;
LABEL_1159:
                v556 = v1043;
                v397 = v1112;
                v482 = v1193;
                v481 = v1185;
                v476 = v1062;
                v349 = v1059;
                v396 = v1204;
                v478 = v1083;
              }
              v557 = v396;
              if ( v556 <= v476 )
              {
                if ( v478 >= (unsigned __int64)v349 + v396 )
                {
                  v588 = v1204;
                }
                else
                {
                  v588 = v478 - (_DWORD)v349;
                  v1204 = v478 - (_DWORD)v349;
                }
                v333 = v1123;
                v589 = (_BYTE *)(v335 + 1);
                v561 = v335 >> 32;
                v590 = (char *)v349 - v1123;
                v563 = v335;
                if ( a7 && (unsigned __int64)&v589[v590 + 8 + v590 / 0xFF] > v1087 )
                  goto LABEL_1292;
                if ( v590 < 0xF )
                {
                  *(_BYTE *)v335 = 16 * v590;
                }
                else
                {
                  v591 = v590 - 15;
                  *(_BYTE *)v335 = -16;
                  while ( v591 >= 0xFF )
                  {
                    *v589++ = -1;
                    v591 -= 255LL;
                  }
                  *v589++ = v591;
                }
                v592 = v1123;
                v593 = &v589[v590];
                do
                {
                  v594 = *(_QWORD *)v592;
                  v592 += 8;
                  *(_QWORD *)v589 = v594;
                  v589 += 8;
                }
                while ( v589 < (_BYTE *)v593 );
                v595 = (__int64)(v593 + 1);
                v596 = v1032;
                *v593 = v1032;
                v597 = v588;
                v598 = v588 - 4LL;
                if ( a7 && v595 + v598 / 0xFF + 6 > v1087 )
                {
                  v336 = v1087;
                  goto LABEL_1296;
                }
                v599 = *(_BYTE *)v335;
                if ( v598 < 0xF )
                {
                  *(_BYTE *)v335 = v599 + v598;
                }
                else
                {
                  *(_BYTE *)v335 = v599 + 15;
                  for ( i5 = v588 - 19LL; i5 >= 0x1FE; i5 -= 510LL )
                  {
                    *(_BYTE *)v595 = -1;
                    v601 = (_BYTE *)(v595 + 1);
                    *v601 = -1;
                    v595 = (__int64)(v601 + 1);
                  }
                  if ( i5 >= 0xFF )
                  {
                    LOBYTE(i5) = i5 + 1;
                    *(_BYTE *)v595++ = -1;
                  }
                  *(_BYTE *)v595++ = i5;
                }
                v602 = (_BYTE *)(v595 + 1);
                v603 = (char *)v1083;
                v333 = (char *)v1059 + v597;
                v604 = v1083 - ((_QWORD)v1059 + v597);
                v561 = v595 >> 32;
                v563 = v595;
                if ( a7 && (unsigned __int64)&v602[v604 + 8 + v604 / 0xFF] > v1087 )
                {
                  v609 = v1028;
LABEL_1290:
                  v336 = v1087;
                  v625 = v476;
                  v596 = v609;
                  goto LABEL_1297;
                }
                if ( v604 < 0xF )
                {
                  *(_BYTE *)v595 = 16 * v604;
                }
                else
                {
                  v605 = v604 - 15;
                  *(_BYTE *)v595 = -16;
                  while ( v605 >= 0xFF )
                  {
                    *v602++ = -1;
                    v605 -= 255LL;
                  }
                  *v602++ = v605;
                }
                v606 = v333;
                v607 = &v602[v604];
                do
                {
                  v608 = *(_QWORD *)v606;
                  v606 += 8;
                  *(_QWORD *)v602 = v608;
                  v602 += 8;
                }
                while ( v602 < (_BYTE *)v607 );
                v609 = v1028;
                v610 = v481 - 4;
                *v607 = v1028;
                v335 = (__int64)(v607 + 1);
                v1093 = v335;
                v1082 = HIDWORD(v335);
                if ( a7 && v335 + v610 / 0xFF + 6 > v1087 )
                  goto LABEL_1290;
                v611 = *(_BYTE *)v595;
                if ( v610 < 0xF )
                {
                  *(_BYTE *)v595 = v611 + v610;
                }
                else
                {
                  *(_BYTE *)v595 = v611 + 15;
                  for ( i6 = v481 - 19; i6 >= 0x1FE; i6 -= 510LL )
                  {
                    *(_BYTE *)v335 = -1;
                    v613 = (_BYTE *)(v335 + 1);
                    *v613 = -1;
                    v335 = (__int64)(v613 + 1);
                  }
                  if ( i6 >= 0xFF )
                  {
                    LOBYTE(i6) = i6 + 1;
                    *(_BYTE *)v335++ = -1;
                  }
                  *(_BYTE *)v335++ = i6;
                  v1093 = v335;
                  v1082 = HIDWORD(v335);
                }
                v331 = (char *)v482;
                v1059 = v482;
                v333 = (char *)v482;
                v1123 = (char *)v482;
                goto LABEL_1287;
              }
              v558 = (char *)v349 + v396;
              if ( v1142 < (unsigned __int64)(v558 + 3) )
                break;
              if ( v478 >= (unsigned __int64)v558 )
              {
                v559 = v1204;
              }
              else if ( (__int64)(v478 - (_QWORD)v349) >= 18 )
              {
                v559 = v478 - (_DWORD)v349;
                v1204 = v478 - (_DWORD)v349;
              }
              else
              {
                if ( v396 > 18 )
                  v396 = 18;
                v1204 = v396;
                if ( (_DWORD *)((char *)v349 + v396) > v482 - 1 )
                {
                  v396 = v476 + v478 - (_DWORD)v349 - 4;
                  v1204 = v396;
                }
                v559 = v1204;
                v560 = v396 + (_DWORD)v349 - v478;
                if ( v560 > 0 )
                {
                  v1083 = v560 + v478;
                  v476 -= v560;
                }
              }
              LODWORD(v561) = v1082;
              v562 = (_BYTE *)(v335 + 1);
              v336 = v1087;
              v563 = v335;
              v564 = (char *)v335;
              v565 = v1123;
              v566 = (char *)v349 - v1123;
              if ( a7 && (unsigned __int64)&v562[v566 / 0xFF + 8 + v566] > v1087 )
                goto LABEL_1294;
              if ( v566 < 0xF )
              {
                *v564 = 16 * v566;
              }
              else
              {
                v567 = v566 - 15;
                *v564 = -16;
                while ( v567 >= 0xFF )
                {
                  *v562++ = -1;
                  v567 -= 255LL;
                }
                *v562++ = v567;
              }
              v568 = v1123;
              v569 = &v562[v566];
              do
              {
                v570 = *(_QWORD *)v568;
                v568 += 8;
                *(_QWORD *)v562 = v570;
                v562 += 8;
              }
              while ( v562 < (_BYTE *)v569 );
              *v569 = v1032;
              v335 = (__int64)(v569 + 1);
              v1082 = HIDWORD(v335);
              v571 = v559 - 4LL;
              if ( a7 && v335 + v571 / 0xFF + 6 > v1087 )
                goto LABEL_1293;
              v572 = *v564;
              if ( v571 < 0xF )
              {
                *v564 = v572 + v571;
              }
              else
              {
                *v564 = v572 + 15;
                for ( i7 = v559 - 19LL; i7 >= 0x1FE; i7 -= 510LL )
                {
                  *(_BYTE *)v335 = -1;
                  v574 = (_BYTE *)(v335 + 1);
                  *v574 = -1;
                  v335 = (__int64)(v574 + 1);
                }
                if ( i7 >= 0xFF )
                {
                  LOBYTE(i7) = i7 + 1;
                  *(_BYTE *)v335++ = -1;
                }
                *(_BYTE *)v335++ = i7;
                v1082 = HIDWORD(v335);
              }
              LOWORD(v1032) = v1028;
              v349 = (_DWORD *)v1083;
              v396 = v476;
              v1123 = (char *)v1059 + v559;
              v1204 = v476;
              v478 = v1142;
              v1083 = v1142;
              v476 = v556;
              v1059 = v349;
              v1028 = v397;
              v1062 = v556;
            }
            if ( v1142 >= (unsigned __int64)v558 )
              break;
            v478 = v1142;
            v1083 = v1142;
            v1028 = v397;
            v476 = v556;
            v1062 = v556;
          }
          if ( v478 < (unsigned __int64)v558 )
          {
            v575 = v396 + (_DWORD)v349 - v478;
            v476 -= v575;
            if ( v476 < 4 )
            {
              v1083 = v1142;
              v576 = v397;
              v476 = v556;
LABEL_1201:
              v577 = (_BYTE *)(v335 + 1);
              v563 = v335;
              v561 = v335 >> 32;
              v578 = (char *)v335;
              v565 = v1123;
              v579 = (char *)v349 - v1123;
              if ( a7 && (unsigned __int64)&v577[v579 / 0xFF + 8 + v579] > v1087 )
              {
                v336 = v1087;
LABEL_1294:
                v333 = v565;
              }
              else
              {
                if ( v579 < 0xF )
                {
                  *v578 = 16 * v579;
                }
                else
                {
                  v580 = v579 - 15;
                  *v578 = -16;
                  while ( v580 >= 0xFF )
                  {
                    *v577++ = -1;
                    v580 -= 255LL;
                  }
                  *v577++ = v580;
                }
                v581 = v1123;
                v582 = &v577[v579];
                do
                {
                  v583 = *(_QWORD *)v581;
                  v581 += 8;
                  *(_QWORD *)v577 = v583;
                  v577 += 8;
                }
                while ( v577 < (_BYTE *)v582 );
                v584 = v557 - 4;
                *v582 = v1032;
                v335 = (__int64)(v582 + 1);
                v1082 = HIDWORD(v335);
                if ( !a7 || v335 + v584 / 0xFF + 6 <= v1087 )
                {
                  v585 = *v578;
                  if ( v584 < 0xF )
                  {
                    *v578 = v585 + v584;
                  }
                  else
                  {
                    *v578 = v585 + 15;
                    for ( i8 = v557 - 19; i8 >= 0x1FE; i8 -= 510LL )
                    {
                      *(_BYTE *)v335 = -1;
                      v587 = (_BYTE *)(v335 + 1);
                      *v587 = -1;
                      v335 = (__int64)(v587 + 1);
                    }
                    if ( i8 >= 0xFF )
                    {
                      LOBYTE(i8) = i8 + 1;
                      *(_BYTE *)v335++ = -1;
                    }
                    *(_BYTE *)v335++ = i8;
                    v1082 = HIDWORD(v335);
                  }
                  v396 = v556;
                  v399 = (_DWORD *)v1083;
                  v349 = (_DWORD *)v1142;
                  v1059 = (_DWORD *)v1142;
                  v398 = v576;
                  v1123 = v558;
                  LODWORD(v400) = v476;
                  LOWORD(v1032) = v397;
                  v1204 = v556;
                  goto LABEL_820;
                }
                v333 = v1123;
LABEL_1292:
                v336 = v1087;
              }
LABEL_1295:
              v596 = v1032;
LABEL_1296:
              v625 = v1204;
              v603 = (char *)v1059;
LABEL_1297:
              if ( a7 == 2 )
              {
                v626 = v603 - v333;
                v335 = __PAIR64__(v561, v563);
                v627 = (v603 - v333 + 240) / 0xFFuLL + v603 - v333 + 1;
                if ( __PAIR64__(v561, v563) + v627 <= v336 - 3 )
                {
                  if ( v625 > 255 * (v336 - 3 - __PAIR64__(v561, v563) - v627) + 18 )
                    v625 = 255 * (v336 - 3 - v563 - v627) + 18;
                  if ( (__int64)(v336 + v625 - __PAIR64__(v561, v563) - v627 + 2) >= 12 )
                  {
                    v628 = (_BYTE *)(__PAIR64__(v561, v563) + 1);
                    if ( v626 < 0xF )
                    {
                      *(_BYTE *)__PAIR64__(v561, v563) = 16 * v626;
                    }
                    else
                    {
                      v629 = v626 - 15;
                      *(_BYTE *)__PAIR64__(v561, v563) = -16;
                      while ( v629 >= 0xFF )
                      {
                        *v628++ = -1;
                        v629 -= 255LL;
                      }
                      *v628++ = v629;
                    }
                    v630 = &v628[v626];
                    do
                    {
                      v631 = *(_QWORD *)v333;
                      v333 += 8;
                      *(_QWORD *)v628 = v631;
                      v628 += 8;
                    }
                    while ( v628 < (_BYTE *)v630 );
                    *v630 = v596;
                    v632 = *(_BYTE *)__PAIR64__(v561, v563);
                    v335 = (__int64)(v630 + 1);
                    if ( (unsigned __int64)(v625 - 4LL) < 0xF )
                    {
                      *(_BYTE *)__PAIR64__(v561, v563) = v632 + v625 - 4;
                    }
                    else
                    {
                      *(_BYTE *)__PAIR64__(v561, v563) = v632 + 15;
                      for ( i9 = v625 - 19LL; i9 >= 0x1FE; i9 -= 510LL )
                      {
                        *(_BYTE *)v335 = -1;
                        v634 = (_BYTE *)(v335 + 1);
                        *v634 = -1;
                        v335 = (__int64)(v634 + 1);
                      }
                      if ( i9 >= 0xFF )
                      {
                        LOBYTE(i9) = i9 + 1;
                        *(_BYTE *)v335++ = -1;
                      }
                      *(_BYTE *)v335++ = i9;
                    }
                    v333 = &v603[v625];
                  }
                }
                v635 = v1164 - v333;
                v636 = v1164 - v333;
                goto LABEL_1324;
              }
LABEL_2100:
              v638 = 0;
LABEL_2117:
              *((_BYTE *)a1 + 262183) = 1;
              return (unsigned int)v638;
            }
            v1083 = v575 + v478;
          }
          v576 = v1028;
          goto LABEL_1201;
        }
        v349 = (_DWORD *)v1083;
        v1059 = (_DWORD *)v1083;
        v397 = v477;
        LOWORD(v1032) = v477;
        v396 = v476;
        v1204 = v476;
      }
      v336 = v1087;
      v614 = (_BYTE *)(v335 + 1);
      v563 = v335;
      v561 = v335 >> 32;
      v615 = (char *)v335;
      v565 = v1123;
      v616 = (char *)v349 - v1123;
      if ( a7 && (unsigned __int64)&v614[v616 + 8 + v616 / 0xFF] > v1087 )
        goto LABEL_1294;
      if ( v616 < 0xF )
      {
        *v615 = 16 * v616;
      }
      else
      {
        v617 = v616 - 15;
        *v615 = -16;
        while ( v617 >= 0xFF )
        {
          *v614++ = -1;
          v617 -= 255LL;
        }
        *v614++ = v617;
      }
      v618 = v1123;
      v619 = &v614[v616];
      do
      {
        v620 = *(_QWORD *)v618;
        v618 += 8;
        *(_QWORD *)v614 = v620;
        v614 += 8;
      }
      while ( v614 < (_BYTE *)v619 );
      *v619 = v397;
      v621 = v401 - 4;
      v335 = (__int64)(v619 + 1);
      v1093 = v335;
      v1082 = HIDWORD(v335);
      if ( a7 && v335 + v621 / 0xFF + 6 > v1087 )
      {
LABEL_1293:
        v333 = v1123;
        goto LABEL_1295;
      }
      v622 = *v615;
      if ( v621 < 0xF )
      {
        *v615 = v622 + v621;
      }
      else
      {
        *v615 = v622 + 15;
        for ( i10 = v401 - 19; i10 >= 0x1FE; i10 -= 510LL )
        {
          *(_BYTE *)v335 = -1;
          v624 = (_BYTE *)(v335 + 1);
          *v624 = -1;
          v335 = (__int64)(v624 + 1);
        }
        if ( i10 >= 0xFF )
        {
          LOBYTE(i10) = i10 + 1;
          *(_BYTE *)v335++ = -1;
        }
        *(_BYTE *)v335++ = i10;
        v1093 = v335;
        v1082 = HIDWORD(v335);
      }
      v331 = (char *)v402;
      v1059 = v402;
      v333 = (char *)v402;
      v1123 = (char *)v402;
LABEL_1287:
      if ( v331 > v1160 )
      {
        v336 = v1087;
        v334 = v1164;
        goto LABEL_1323;
      }
      v8 = a1;
    }
  }
  if ( a7 == 2 && a5 < 1 )
    return v329;
  v639 = *a4;
  if ( (unsigned int)v639 > 0x7E000000 )
    return v329;
  *((_QWORD *)v8 + 0x8000) = v7 + v639;
  v640 = a3;
  v641 = *a4;
  v642 = Src;
  v643 = Src;
  *a4 = 0;
  v1121 = (_WORD *)a3;
  HIDWORD(v1084) = HIDWORD(a3);
  v644 = &Src[v641];
  v1057 = Src;
  v1161 = Src;
  v1194 = &Src[v641];
  v645 = a5 + a3 - 5;
  if ( a7 != 2 )
    v645 = a5 + a3;
  v1124 = v645;
  if ( (int)v641 >= 13 )
  {
    v1149 = v644 - 12;
    if ( Src <= v644 - 12 )
    {
      v1081 = 0;
      v1060 = v644 - 5;
      v1143 = 0;
      while ( 1 )
      {
        v646 = v8[65543];
        v647 = 3;
        v648 = (_QWORD *)*((_QWORD *)v8 + 32769);
        v649 = v646;
        v650 = v8[65542];
        v1181 = *((_QWORD *)v8 + 32773);
        v1205 = 3;
        v651 = (_DWORD)v642 + v8[65542] - (_DWORD)v648;
        v1138 = v648;
        v1104 = v651;
        v1113 = v8[65543];
        if ( (int)v646 + 0x10000 <= v651 )
          v649 = v651 - 0xFFFF;
        v652 = (_QWORD *)*((_QWORD *)v8 + 32770);
        v653 = *(_DWORD *)v642;
        v1174 = 0;
        v1033 = 0;
        v654 = 0;
        v1165 = (char *)v652 + v650 - v646;
        v655 = 256;
        v1128 = v649;
        v1096 = v652;
        v1029 = v653;
        v656 = a1[65544];
        if ( v656 < v651 )
        {
          do
          {
            v657 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v648 + v656 - v650)) >> 17;
            v658 = v656 - a1[v657];
            if ( v658 > 0xFFFF )
              LOWORD(v658) = -1;
            *((_WORD *)a1 + (unsigned __int16)v656 + 0x10000) = v658;
            a1[v657] = v656++;
          }
          while ( v656 < v651 );
          LODWORD(v646) = v1113;
          v652 = v1096;
        }
        a1[65544] = v651;
        v659 = (unsigned __int64)(unsigned int)(-1640531535 * *v1057) >> 17;
        v1186 = v659;
        v660 = a1[v659];
        if ( v660 >= v649 )
          break;
        v661 = 256;
LABEL_1353:
        if ( v651 - v649 < 0xFFFF )
        {
          v662 = *(_QWORD *)(v1181 + 262152);
          v663 = *(unsigned int *)(v1181 + 262168);
          v664 = *(_DWORD *)(v1181 + 4 * v659);
          v665 = v663 + *(_QWORD *)(v1181 + 0x40000) - v662;
          v666 = v649 + v664 - v665;
          if ( v651 - v666 <= 0xFFFF )
          {
            do
            {
              if ( !v661 )
                break;
              --v661;
              if ( *(_DWORD *)(v662 - v663 + v664) == v653 )
              {
                v667 = (char *)v1057 + v665 - v664;
                if ( v667 > v1060 )
                  v667 = v1060;
                v668 = v1057 + 1;
                v669 = (_QWORD *)(v662 - v663 + v664 + 4LL);
                if ( v1057 + 1 >= (_DWORD *)(v667 - 7) )
                {
                  v671 = (char *)(v1057 + 1);
                  while ( v671 < v667 - 7 )
                  {
                    if ( *v669 != *(_QWORD *)v671 )
                    {
                      __asm { tzcnt   rax, r9 }
                      v722 = ((unsigned int)_RAX >> 3) - (_DWORD)v668 + (_DWORD)v671;
                      goto LABEL_1501;
                    }
                    v671 += 8;
LABEL_1489:
                    ++v669;
                  }
                  if ( v671 < v667 - 3 && *(_DWORD *)v669 == *(_DWORD *)v671 )
                  {
                    v671 += 4;
                    v669 = (_QWORD *)((char *)v669 + 4);
                  }
                  if ( v671 < v667 - 1 && *(_WORD *)v669 == *(_WORD *)v671 )
                  {
                    v671 += 2;
                    v669 = (_QWORD *)((char *)v669 + 2);
                  }
                  if ( v671 < v667 && *(_BYTE *)v669 == *v671 )
                    LODWORD(v671) = (_DWORD)v671 + 1;
                  v722 = (_DWORD)v671 - (_DWORD)v668;
LABEL_1501:
                  v651 = v1104;
                }
                else
                {
                  if ( *v669 == *v668 )
                  {
                    v671 = (char *)(v1057 + 3);
                    goto LABEL_1489;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v722 = (unsigned int)_RCX >> 3;
                }
                v653 = v1029;
                v725 = v722 + 4;
                if ( v725 > v1205 )
                {
                  v1205 = v725;
                  v1033 = v651 - v666;
                }
              }
              v726 = *(unsigned __int16 *)(v1181 + 2LL * (unsigned __int16)v664 + 0x20000);
              v666 -= v726;
              v664 -= v726;
            }
            while ( v651 - v666 <= 0xFFFF );
            v640 = (__int64)v1121;
          }
        }
LABEL_1506:
        v727 = v1205;
        if ( v1205 < 4 )
        {
          v643 = v1161;
          v642 = (char *)v1057 + 1;
          v1057 = (_DWORD *)((char *)v1057 + 1);
          goto LABEL_2066;
        }
        v728 = v1033;
        v729 = v1057;
        v730 = __PAIR64__(v1205, v1033) >> 32;
        v731 = v1057;
LABEL_1509:
        v732 = v1149;
        v1157 = v730;
        v1187 = v731;
        v1139 = v728;
        while ( 1 )
        {
          v733 = v727;
          v1150 = v727;
          v734 = (_DWORD *)((char *)v729 + v727);
          v1197 = v734;
          if ( v734 > (_DWORD *)v732 )
          {
            v835 = 0;
            v834 = 0;
            v1030 = 0;
            v1063 = 0;
          }
          else
          {
            v735 = (_DWORD *)((char *)v734 - 2);
            v1081 = (unsigned __int64)v734 - 2;
            v1114 = (unsigned __int64)v734 - 2;
            v1063 = v727;
            v736 = a1[65543];
            v737 = v736;
            v738 = (_QWORD *)*((_QWORD *)a1 + 32769);
            v739 = (_DWORD)v734 - 2 - (_DWORD)v738;
            v740 = (char *)a1[65542];
            v741 = (_DWORD)v740 + v739;
            v1182 = *((_QWORD *)a1 + 32773);
            v1088 = (char *)v738;
            v1044 = a1[65542];
            v1105 = v741;
            v1053 = v736;
            if ( v736 + 0x10000 <= v741 )
              v737 = v741 - 0xFFFF;
            v742 = (char *)*((_QWORD *)a1 + 32770);
            v1030 = 0;
            v743 = a1[65544];
            v1071 = (_DWORD)v735 - (_DWORD)v1057;
            v744 = (_DWORD)v735 + (_DWORD)v740 - (_DWORD)v738;
            v1078 = v737;
            v745 = (_DWORD *)a1[65542];
            v1097 = v742;
            v1129 = 256;
            v1023 = *v735;
            if ( v743 < v744 )
            {
              do
              {
                v746 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v738 + v743 - (_QWORD)v740)) >> 17;
                v747 = v743 - a1[v746];
                if ( v747 > 0xFFFF )
                  LOWORD(v747) = -1;
                *((_WORD *)a1 + (unsigned __int16)v743 + 0x10000) = v747;
                a1[v746] = v743++;
              }
              while ( v743 < v744 );
              v728 = v1139;
              v742 = v1097;
              v745 = v740;
            }
            a1[65544] = v744;
            v748 = (unsigned __int64)(unsigned int)(-1640531535 * *v735) >> 17;
            v1195 = v748;
            v749 = a1[v748];
            if ( v749 >= v737 )
            {
              v750 = 0;
              v1166 = (char *)v745 + (_QWORD)v742 - v736;
              v1038 = 0;
              v1175 = 0;
              while ( 1 )
              {
                if ( v1129 <= 0 )
                  goto LABEL_1716;
                --v1129;
                if ( v749 < (unsigned int)v740 )
                {
                  v767 = v1023;
                  if ( v749 > (int)v740 - 4 )
                    goto LABEL_1622;
                  v770 = &v742[v749 - v736];
                  if ( *(_DWORD *)v770 != v1023 )
                    goto LABEL_1622;
                  v771 = v1060;
                  v772 = v770 + 4;
                  v773 = (char *)v735 + (unsigned int)v740 - v749;
                  if ( v773 > v1060 )
                    v773 = v1060;
                  v774 = (char *)(v735 + 1);
                  if ( v774 >= v773 - 7 )
                  {
                    v776 = v774;
                    while ( v776 < v773 - 7 )
                    {
                      if ( *v772 != *(_QWORD *)v776 )
                      {
                        __asm { tzcnt   rsi, r8 }
                        v778 = (_DWORD)v776 + ((unsigned int)_RSI >> 3) - (_DWORD)v774;
                        goto LABEL_1582;
                      }
                      v776 += 8;
LABEL_1570:
                      ++v772;
                    }
                    if ( v776 < v773 - 3 && *(_DWORD *)v772 == *(_DWORD *)v776 )
                    {
                      v776 += 4;
                      v772 = (_QWORD *)((char *)v772 + 4);
                    }
                    if ( v776 < v773 - 1 && *(_WORD *)v772 == *(_WORD *)v776 )
                    {
                      v776 += 2;
                      v772 = (_QWORD *)((char *)v772 + 2);
                    }
                    if ( v776 < v773 && *(_BYTE *)v772 == *v776 )
                      LODWORD(v776) = (_DWORD)v776 + 1;
                    v778 = (_DWORD)v776 - (_DWORD)v774;
LABEL_1582:
                    v771 = v1060;
                  }
                  else
                  {
                    if ( *v772 == *(_QWORD *)v774 )
                    {
                      v776 = v774 + 8;
                      goto LABEL_1570;
                    }
                    __asm { tzcnt   rsi, rcx }
                    v778 = (unsigned int)_RSI >> 3;
                  }
                  v781 = v778 + 4;
                  v782 = (char *)(v778 + v1114 + 4);
                  if ( v782 == v773 && v773 < v771 )
                  {
                    v783 = (unsigned __int64)(v771 - 7);
                    if ( v782 >= v771 - 7 )
                    {
                      v786 = v738;
                      v785 = (char *)(v778 + v1114 + 4);
LABEL_1590:
                      while ( (unsigned __int64)v785 < v783 )
                      {
                        if ( *v786 != *(_QWORD *)v785 )
                        {
                          __asm { tzcnt   rax, r8 }
                          v788 = ((unsigned int)_RAX >> 3) - (_DWORD)v782 + (_DWORD)v785;
                          goto LABEL_1604;
                        }
                        v785 += 8;
                        ++v786;
                      }
                      if ( v785 < v1060 - 3 && *(_DWORD *)v786 == *(_DWORD *)v785 )
                      {
                        v785 += 4;
                        v786 = (_QWORD *)((char *)v786 + 4);
                      }
                      if ( v785 < v1060 - 1 && *(_WORD *)v786 == *(_WORD *)v785 )
                      {
                        v785 += 2;
                        v786 = (_QWORD *)((char *)v786 + 2);
                      }
                      if ( v785 < v1060 && *(_BYTE *)v786 == *v785 )
                        LODWORD(v785) = (_DWORD)v785 + 1;
                      v788 = (_DWORD)v785 - (_DWORD)v782;
                    }
                    else
                    {
                      if ( *v738 == *(_QWORD *)v782 )
                      {
                        v785 = v782 + 8;
                        v786 = v738 + 1;
                        goto LABEL_1590;
                      }
                      __asm { tzcnt   rcx, rcx }
                      v788 = (unsigned int)_RCX >> 3;
                    }
LABEL_1604:
                    v781 = v778 + v788 + 4;
                  }
                  v735 = (_DWORD *)v1114;
                  v791 = 0;
                  if ( v1071 )
                  {
                    v792 = (_DWORD)v1057 - v1114;
                    if ( (__int64)((__int64)v1057 - v1114) <= v1097 - v770 )
                      v792 = (_DWORD)v1097 - (_DWORD)v770;
                    for ( i11 = -v792; i11 > 3; i11 = v791 - v792 )
                    {
                      if ( *(_DWORD *)(v1114 + v791 - 4) != *(_DWORD *)&v770[v791 - 4] )
                      {
                        _BitScanReverse(&v795, *(_DWORD *)(v1114 + v791 - 4) ^ *(_DWORD *)&v770[v791 - 4]);
                        v791 -= (31 - v795) >> 3;
                        goto LABEL_1616;
                      }
                      v791 -= 4;
                    }
                    if ( v791 > v792 )
                    {
                      do
                      {
                        if ( *(_BYTE *)(v1114 + v791 - 1) != v770[v791 - 1] )
                          break;
                        --v791;
                      }
                      while ( v791 > v792 );
                      v728 = v1139;
                    }
                  }
LABEL_1616:
                  v750 = v1038;
                  v794 = v781 - v791;
                  v736 = v1053;
                  v767 = v1023;
                  v758 = v1060;
                  if ( v794 > v1063 )
                  {
                    v1063 = v794;
                    v1030 = v1105 - v749;
                    v1081 = v1114 + v791;
                  }
                  LODWORD(v740) = v1044;
                }
                else
                {
                  v751 = (_DWORD *)((char *)v738 + v749 - (unsigned int)v740);
                  if ( *(_WORD *)((char *)v1057 + v1063 - 1) != *(_WORD *)((char *)v751 + v1063 - (__int64)v1071 - 1)
                    || *v751 != v1023 )
                  {
                    v767 = v1023;
LABEL_1622:
                    v758 = v1060;
                    goto LABEL_1623;
                  }
                  if ( v1071 )
                  {
                    v752 = v1114;
                    v753 = 0;
                    v754 = -(__int64)(v749 - (unsigned int)v740);
                    v755 = (_DWORD)v1057 - v1114;
                    if ( (__int64)((__int64)v1057 - v1114) <= v754 )
                      v755 = v754;
                    if ( -v755 <= 3 )
                    {
LABEL_1530:
                      if ( v753 > v755 )
                      {
                        do
                        {
                          if ( *(_BYTE *)(v752 + v753 - 1) != *((_BYTE *)v751 + v753 - 1) )
                            break;
                          --v753;
                        }
                        while ( v753 > v755 );
                        v728 = v1139;
                      }
                    }
                    else
                    {
                      while ( 1 )
                      {
                        v756 = *(_DWORD *)((char *)v751 + v753 - 4) ^ *(_DWORD *)(v752 + v753 - 4);
                        if ( v756 )
                          break;
                        v752 = v1114;
                        v753 -= 4;
                        if ( v753 - v755 <= 3 )
                          goto LABEL_1530;
                      }
                      _BitScanReverse(&v757, v756);
                      v753 -= (31 - v757) >> 3;
                    }
                  }
                  else
                  {
                    v753 = 0;
                  }
                  v758 = v1060;
                  v759 = v751 + 1;
                  v760 = (_QWORD *)(v1114 + 4);
                  if ( v1114 + 4 >= (unsigned __int64)(v1060 - 7) )
                  {
                    v762 = (char *)(v1114 + 4);
                    while ( v762 < v1060 - 7 )
                    {
                      if ( *v759 != *(_QWORD *)v762 )
                      {
                        __asm { tzcnt   rax, r8 }
                        v764 = ((unsigned int)_RAX >> 3) - (_DWORD)v760 + (_DWORD)v762;
                        goto LABEL_1556;
                      }
                      v762 += 8;
LABEL_1544:
                      ++v759;
                    }
                    if ( v762 < v1060 - 3 && *(_DWORD *)v759 == *(_DWORD *)v762 )
                    {
                      v762 += 4;
                      v759 = (_QWORD *)((char *)v759 + 4);
                    }
                    if ( v762 < v1060 - 1 && *(_WORD *)v759 == *(_WORD *)v762 )
                    {
                      v762 += 2;
                      v759 = (_QWORD *)((char *)v759 + 2);
                    }
                    if ( v762 < v1060 && *(_BYTE *)v759 == *v762 )
                      LODWORD(v762) = (_DWORD)v762 + 1;
                    v764 = (_DWORD)v762 - (_DWORD)v760;
                  }
                  else
                  {
                    if ( *v759 == *v760 )
                    {
                      v762 = (char *)(v1114 + 12);
                      goto LABEL_1544;
                    }
                    __asm { tzcnt   rcx, rcx }
                    v764 = (unsigned int)_RCX >> 3;
                  }
LABEL_1556:
                  LODWORD(v740) = v1044;
                  v767 = v1023;
                  v768 = v764 - v753 + 4;
                  if ( v768 <= v1063 )
                  {
                    v735 = (_DWORD *)v1114;
                  }
                  else
                  {
                    v1063 = v768;
                    v769 = v753;
                    v735 = (_DWORD *)v1114;
                    v1030 = v741 - v749;
                    v1081 = v1114 + v769;
                  }
                }
LABEL_1623:
                if ( *((_WORD *)a1 + (unsigned __int16)v749 + 0x10000) != 1 )
                  goto LABEL_1628;
                if ( v750 )
                {
                  v1038 = v750;
                  if ( v750 != 2 )
                    goto LABEL_1628;
                }
                else
                {
                  if ( (_BYTE)v767 != HIBYTE(v767) || (unsigned __int16)v767 != HIWORD(v767) )
                  {
                    v750 = 1;
                    v1038 = 1;
LABEL_1628:
                    LODWORD(v740) = v1044;
                    v796 = *((unsigned __int16 *)a1 + (unsigned __int16)v749 + 0x10000);
                    goto LABEL_1629;
                  }
                  v750 = 2;
                  v1038 = 2;
                  v1175 = (unsigned int)LZ4HC_countPattern(v735 + 1, v758, v767) + 4LL;
                }
                v798 = v749 - 1;
                if ( v749 - 1 < v1078 || (unsigned int)v740 - v749 < 3 )
                  goto LABEL_1628;
                if ( v798 >= (unsigned int)v740 )
                {
                  v799 = 0;
                  v740 = &v1088[v798 - (unsigned int)v740];
                }
                else
                {
                  v799 = 1;
                  v740 = &v1097[v798 - v736];
                }
                if ( *(_DWORD *)v740 != v1023 )
                  goto LABEL_1628;
                v800 = v1060;
                if ( v799 )
                  v800 = v1166;
                v801 = (unsigned int)LZ4HC_countPattern(v740 + 4, v800, v1023) + 4LL;
                if ( v799 )
                {
                  if ( &v740[v801] == v800 )
                  {
                    v802 = LZ4HC_rotatePattern(v801, v1023);
                    v801 += (unsigned int)LZ4HC_countPattern(v1088, v1060, v802);
                  }
                  v803 = v1097;
                  v804 = v1097;
                }
                else
                {
                  v804 = v1088;
                  v803 = v1097;
                }
                v805 = LZ4HC_reverseCountPattern(v740, v804, v1023);
                v806 = v1088;
                v807 = v805;
                if ( v799 )
                {
                  LODWORD(v740) = v1044;
                }
                else
                {
                  v159 = &v740[-v805] == v1088;
                  LODWORD(v740) = v1044;
                  if ( v159 && v1053 < v1044 )
                  {
                    v808 = LZ4HC_rotatePattern(-v805, v1023);
                    v807 += LZ4HC_reverseCountPattern(v1166, v803, v808);
                    v806 = v1088;
                  }
                }
                v809 = v798 - v807;
                v737 = v1078;
                v749 = v1078;
                if ( v809 > v1078 )
                  v749 = v809;
                v810 = v801 + v798 - v749;
                if ( v810 >= v1175 && v801 <= v1175 )
                {
                  v749 = (unsigned int)v740;
                  if ( (unsigned int)v740 - ((_DWORD)v801 - (_DWORD)v1175 + v798) - 1 >= 3 )
                    v749 = v801 - v1175 + v798;
                  goto LABEL_1670;
                }
                if ( (unsigned int)v740 - v749 - 1 < 3 )
                {
                  v749 = (unsigned int)v740;
LABEL_1670:
                  v750 = v1038;
                  goto LABEL_1630;
                }
                if ( v1071 )
                  goto LABEL_1670;
                v811 = v1175;
                if ( v810 < v1175 )
                  v811 = v801 + v798 - v749;
                if ( v1063 < v811 )
                {
                  if ( (unsigned int)v740 + v1114 - v749 - (unsigned __int64)v806 > 0xFFFF )
                    goto LABEL_1632;
                  v1063 = v811;
                  v1030 = v1105 - v749;
                  v1081 = v1114;
                }
                v796 = *((unsigned __int16 *)a1 + (unsigned __int16)v749 + 0x10000);
                if ( v796 > v749 )
                  goto LABEL_1632;
                v750 = v1038;
LABEL_1629:
                v749 -= v796;
LABEL_1630:
                v738 = v1088;
                v736 = v1053;
                v742 = v1097;
                v735 = (_DWORD *)v1114;
                LOWORD(v741) = v1105;
                if ( v749 < v1078 )
                {
                  v737 = v1078;
LABEL_1632:
                  v797 = v1129;
                  if ( v1129 <= 0 )
                    goto LABEL_1716;
                  v735 = (_DWORD *)v1114;
                  v748 = v1195;
                  v741 = v1105;
                  goto LABEL_1672;
                }
              }
            }
            v797 = 256;
LABEL_1672:
            if ( v741 - v737 < 0xFFFF )
            {
              v812 = *(unsigned int *)(v1182 + 262168);
              v813 = *(_QWORD *)(v1182 + 262152);
              v814 = *(_DWORD *)(v1182 + 4 * v748);
              v815 = v812 + *(_QWORD *)(v1182 + 0x40000) - v813;
              v816 = v737 + v814 - v815;
              if ( v1105 - v816 <= 0xFFFF )
              {
                v817 = v1023;
                do
                {
                  if ( !v797 )
                    break;
                  v1130 = v797 - 1;
                  v818 = (_DWORD *)(v813 + v814 - v812);
                  if ( *v818 == v817 )
                  {
                    v819 = v818 + 1;
                    v820 = (char *)v735 + v815 - v814;
                    if ( v820 > v1060 )
                      v820 = v1060;
                    v821 = (char *)(v735 + 1);
                    if ( v821 >= v820 - 7 )
                    {
                      v823 = v821;
                      while ( v823 < v820 - 7 )
                      {
                        if ( *v819 != *(_QWORD *)v823 )
                        {
                          __asm { tzcnt   rax, r8 }
                          v825 = ((unsigned int)_RAX >> 3) - (_DWORD)v821 + (_DWORD)v823;
                          goto LABEL_1699;
                        }
                        v823 += 8;
LABEL_1687:
                        ++v819;
                      }
                      if ( v823 < v820 - 3 && *(_DWORD *)v819 == *(_DWORD *)v823 )
                      {
                        v823 += 4;
                        v819 = (_QWORD *)((char *)v819 + 4);
                      }
                      if ( v823 < v820 - 1 && *(_WORD *)v819 == *(_WORD *)v823 )
                      {
                        v823 += 2;
                        v819 = (_QWORD *)((char *)v819 + 2);
                      }
                      if ( v823 < v820 && *(_BYTE *)v819 == *v823 )
                        LODWORD(v823) = (_DWORD)v823 + 1;
                      v825 = (_DWORD)v823 - (_DWORD)v821;
                    }
                    else
                    {
                      if ( *v819 == *(_QWORD *)v821 )
                      {
                        v823 = v821 + 8;
                        goto LABEL_1687;
                      }
                      __asm { tzcnt   rcx, rcx }
                      v825 = (unsigned int)_RCX >> 3;
                    }
LABEL_1699:
                    v828 = 0;
                    if ( v1071 )
                    {
                      v829 = v1114;
                      v830 = (_DWORD)v1057 - v1114;
                      if ( (__int64)((__int64)v1057 - v1114) <= v813 - (__int64)v818 )
                        v830 = v813 - (_DWORD)v818;
                      if ( -v830 <= 3 )
                      {
LABEL_1705:
                        if ( v828 > v830 )
                        {
                          do
                          {
                            if ( *(_BYTE *)(v828 + v829 - 1) != *((_BYTE *)v818 + v828 - 1) )
                              break;
                            --v828;
                          }
                          while ( v828 > v830 );
                          v817 = v1023;
                        }
                      }
                      else
                      {
                        while ( 1 )
                        {
                          v831 = *(_DWORD *)((char *)v818 + v828 - 4) ^ *(_DWORD *)(v828 + v829 - 4);
                          if ( v831 )
                            break;
                          v829 = v1114;
                          v828 -= 4;
                          if ( v828 - v830 <= 3 )
                            goto LABEL_1705;
                        }
                        _BitScanReverse(&v832, v831);
                        v828 -= (31 - v832) >> 3;
                      }
                    }
                    if ( (int)(v825 + 4 - v828) <= v1063 )
                    {
                      v735 = (_DWORD *)v1114;
                    }
                    else
                    {
                      v1063 = v825 + 4 - v828;
                      v735 = (_DWORD *)v1114;
                      v1030 = v1105 - v816;
                      v1081 = v1114 + v828;
                    }
                    v812 = *(unsigned int *)(v1182 + 262168);
                  }
                  v833 = *(unsigned __int16 *)(v1182 + 2LL * (unsigned __int16)v814 + 0x20000);
                  v816 -= v833;
                  v814 -= v833;
                  v797 = v1130;
                }
                while ( v1105 - v816 <= 0xFFFF );
                v728 = v1139;
                v640 = (__int64)v1121;
              }
            }
LABEL_1716:
            LODWORD(v730) = v1157;
            v731 = v1187;
            v734 = v1197;
            v733 = v1150;
            v834 = v1063;
            v835 = v1030;
            v727 = v1205;
            v729 = v1057;
            v732 = v1149;
          }
          if ( v834 <= v727 )
            break;
          v836 = v1081;
          if ( v731 < v729 && v1081 < (unsigned __int64)v729 + (int)v730 )
          {
            v729 = v731;
            v1057 = v731;
            LOWORD(v1033) = v728;
            v727 = v730;
            v1205 = v730;
          }
          if ( (__int64)(v1081 - (_QWORD)v729) >= 3 )
          {
            while ( 1 )
            {
              if ( (__int64)(v836 - (_QWORD)v729) < 18 )
              {
                v837 = v727;
                if ( v727 > 18 )
                  v837 = 18;
                if ( (unsigned __int64)v729 + v837 > v836 + v834 - 4LL )
                  v837 = v834 + v836 - (_DWORD)v729 - 4;
                v838 = v837 + (_DWORD)v729 - v836;
                if ( v838 > 0 )
                {
                  v836 += v838;
                  v834 -= v838;
                  v1081 = v836;
                  v1063 = v834;
                }
              }
              v839 = v834;
              v1183 = v834;
              v840 = (_DWORD *)(v834 + v836);
              v1196 = v840;
              if ( v840 > (_DWORD *)v732 )
              {
                v938 = 0;
                v937 = 0;
              }
              else
              {
                v841 = (_DWORD *)((char *)v840 - 3);
                v1045 = v834;
                v842 = (char *)v840 - 3;
                v1143 = (unsigned __int64)v840 - 3;
                v1089 = (char *)v840 - 3;
                v843 = a1[65543];
                v844 = v843;
                v845 = (_DWORD *)a1[65542];
                v846 = (_QWORD *)*((_QWORD *)a1 + 32769);
                v847 = (_DWORD)v840 - 3 + a1[65542] - (_DWORD)v846;
                v1176 = *((_QWORD *)a1 + 32773);
                v1098 = v846;
                v1106 = a1[65542];
                v1054 = v847;
                v1158 = v843;
                if ( v843 + 0x10000 <= v847 )
                  v844 = v847 - 0xFFFF;
                v848 = (_QWORD *)*((_QWORD *)a1 + 32770);
                v849 = (_DWORD *)a1[65542];
                v850 = *v841;
                v1072 = 0;
                v851 = a1[65544];
                v1079 = v844;
                v1140 = v848;
                v1115 = (_DWORD)v841 - v1081;
                v1131 = 256;
                v1024 = *v841;
                if ( v851 < v847 )
                {
                  do
                  {
                    v852 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v846 + v851 - (_QWORD)v845)) >> 17;
                    v853 = v851 - a1[v852];
                    if ( v853 > 0xFFFF )
                      LOWORD(v853) = -1;
                    *((_WORD *)a1 + (unsigned __int16)v851 + 0x10000) = v853;
                    a1[v852] = v851++;
                  }
                  while ( v851 < v847 );
                  v849 = v845;
                }
                a1[65544] = v847;
                v854 = (unsigned __int64)(-1640531535 * *v841) >> 17;
                v1198 = v854;
                v855 = a1[v854];
                if ( v855 >= v844 )
                {
                  v1151 = (char *)v849 + (_QWORD)v848 - v843;
                  v856 = 0;
                  v1039 = 0;
                  v1167 = 0;
                  while ( 1 )
                  {
                    if ( v1131 <= 0 )
                      goto LABEL_1937;
                    --v1131;
                    if ( v855 < (unsigned int)v845 )
                    {
                      v872 = v1024;
                      if ( v855 <= (int)v845 - 4 )
                      {
                        v875 = (_DWORD *)((char *)v848 + v855 - v843);
                        if ( *v875 == v1024 )
                        {
                          v876 = v875 + 1;
                          v877 = &v842[(unsigned int)v845 - v855];
                          if ( v877 > v1060 )
                            v877 = v1060;
                          v878 = v842 + 4;
                          if ( v878 >= v877 - 7 )
                          {
                            v880 = v878;
                            while ( v880 < v877 - 7 )
                            {
                              if ( *v876 != *(_QWORD *)v880 )
                              {
                                __asm { tzcnt   rdi, r8 }
                                v882 = (_DWORD)v880 + ((unsigned int)_RDI >> 3) - (_DWORD)v878;
                                goto LABEL_1802;
                              }
                              v880 += 8;
LABEL_1790:
                              ++v876;
                            }
                            if ( v880 < v877 - 3 && *(_DWORD *)v876 == *(_DWORD *)v880 )
                            {
                              v880 += 4;
                              v876 = (_QWORD *)((char *)v876 + 4);
                            }
                            if ( v880 < v877 - 1 && *(_WORD *)v876 == *(_WORD *)v880 )
                            {
                              v880 += 2;
                              v876 = (_QWORD *)((char *)v876 + 2);
                            }
                            if ( v880 < v877 && *(_BYTE *)v876 == *v880 )
                              LODWORD(v880) = (_DWORD)v880 + 1;
                            v882 = (_DWORD)v880 - (_DWORD)v878;
                          }
                          else
                          {
                            if ( *v876 == *(_QWORD *)v878 )
                            {
                              v880 = v878 + 8;
                              goto LABEL_1790;
                            }
                            __asm { tzcnt   rdi, rcx }
                            v882 = (unsigned int)_RDI >> 3;
                          }
LABEL_1802:
                          v885 = v882 + 4;
                          v886 = &v1089[v882 + 4];
                          if ( v886 == v877 && v877 < v1060 )
                          {
                            v887 = v1098;
                            if ( v886 >= v1060 - 7 )
                            {
                              v889 = &v1089[v882 + 4];
                              while ( v889 < v1060 - 7 )
                              {
                                if ( *v887 != *(_QWORD *)v889 )
                                {
                                  __asm { tzcnt   rax, r8 }
                                  v891 = ((unsigned int)_RAX >> 3) - (_DWORD)v886 + (_DWORD)v889;
                                  goto LABEL_1824;
                                }
                                v889 += 8;
LABEL_1812:
                                ++v887;
                              }
                              if ( v889 < v1060 - 3 && *(_DWORD *)v887 == *(_DWORD *)v889 )
                              {
                                v889 += 4;
                                v887 = (_QWORD *)((char *)v887 + 4);
                              }
                              if ( v889 < v1060 - 1 && *(_WORD *)v887 == *(_WORD *)v889 )
                              {
                                v889 += 2;
                                v887 = (_QWORD *)((char *)v887 + 2);
                              }
                              if ( v889 < v1060 && *(_BYTE *)v887 == *v889 )
                                LODWORD(v889) = (_DWORD)v889 + 1;
                              v891 = (_DWORD)v889 - (_DWORD)v886;
                            }
                            else
                            {
                              if ( *(_QWORD *)v886 == *v1098 )
                              {
                                v889 = v886 + 8;
                                goto LABEL_1812;
                              }
                              __asm { tzcnt   rcx, rcx }
                              v891 = (unsigned int)_RCX >> 3;
                            }
LABEL_1824:
                            v885 = v882 + v891 + 4;
                          }
                          v842 = v1089;
                          v894 = 0;
                          if ( v1115 )
                          {
                            v895 = v1081 - (_DWORD)v1089;
                            if ( (__int64)(v1081 - (_QWORD)v1089) <= (char *)v848 - (char *)v875 )
                              v895 = (_DWORD)v848 - (_DWORD)v875;
                            for ( i12 = -v895; i12 > 3; i12 = v894 - v895 )
                            {
                              if ( *(_DWORD *)((char *)v875 + v894 - 4) != *(_DWORD *)&v1089[v894 - 4] )
                              {
                                _BitScanReverse(
                                  &v898,
                                  *(_DWORD *)((char *)v875 + v894 - 4) ^ *(_DWORD *)&v1089[v894 - 4]);
                                v894 -= (31 - v898) >> 3;
                                goto LABEL_1836;
                              }
                              v894 -= 4;
                            }
                            if ( v894 > v895 )
                            {
                              do
                              {
                                if ( v1089[v894 - 1] != *((_BYTE *)v875 + v894 - 1) )
                                  break;
                                --v894;
                              }
                              while ( v894 > v895 );
                              v844 = v1079;
                            }
                          }
LABEL_1836:
                          LODWORD(v845) = v1106;
                          v897 = v885 - v894;
                          v846 = v1098;
                          v843 = v1158;
                          v872 = v1024;
                          if ( v897 > v1045 )
                          {
                            v1045 = v897;
                            v1072 = v1054 - v855;
                            v1143 = (unsigned __int64)&v1089[v894];
                          }
                          v856 = v1039;
                        }
                        else
                        {
                          v843 = v1158;
                        }
                      }
                    }
                    else
                    {
                      v857 = (_DWORD *)((char *)v846 + v855 - (unsigned int)v845);
                      if ( *(_WORD *)(v1045 + v1081 - 1) == *(_WORD *)((char *)v857 + v1045 - (__int64)v1115 - 1)
                        && *v857 == v1024 )
                      {
                        v858 = 0;
                        if ( v1115 )
                        {
                          v859 = v1089;
                          v860 = v1081 - (_DWORD)v1089;
                          v861 = -(__int64)(v855 - (unsigned int)v845);
                          if ( (__int64)(v1081 - (_QWORD)v1089) <= v861 )
                            v860 = v861;
                          if ( -v860 <= 3 )
                          {
LABEL_1751:
                            if ( v858 > v860 )
                            {
                              do
                              {
                                if ( v859[v858 - 1] != *((_BYTE *)v857 + v858 - 1) )
                                  break;
                                --v858;
                              }
                              while ( v858 > v860 );
                              v844 = v1079;
                            }
                          }
                          else
                          {
                            while ( 1 )
                            {
                              v862 = *(_DWORD *)((char *)v857 + v858 - 4) ^ *(_DWORD *)&v859[v858 - 4];
                              if ( v862 )
                                break;
                              v859 = v1089;
                              v858 -= 4;
                              if ( v858 - v860 <= 3 )
                                goto LABEL_1751;
                            }
                            _BitScanReverse(&v867, v862);
                            v858 -= (31 - v867) >> 3;
                          }
                        }
                        v863 = v857 + 1;
                        v864 = v1089 + 4;
                        if ( v1089 + 4 >= v1060 - 7 )
                        {
                          v866 = v1089 + 4;
                          while ( v866 < v1060 - 7 )
                          {
                            if ( *(_QWORD *)v866 != *v863 )
                            {
                              __asm { tzcnt   rax, r8 }
                              v869 = ((unsigned int)_RAX >> 3) - (_DWORD)v864 + (_DWORD)v866;
                              goto LABEL_1776;
                            }
                            v866 += 8;
LABEL_1764:
                            ++v863;
                          }
                          if ( v866 < v1060 - 3 && *(_DWORD *)v863 == *(_DWORD *)v866 )
                          {
                            v866 += 4;
                            v863 = (_QWORD *)((char *)v863 + 4);
                          }
                          if ( v866 < v1060 - 1 && *(_WORD *)v863 == *(_WORD *)v866 )
                          {
                            v866 += 2;
                            v863 = (_QWORD *)((char *)v863 + 2);
                          }
                          if ( v866 < v1060 && *(_BYTE *)v863 == *v866 )
                            LODWORD(v866) = (_DWORD)v866 + 1;
                          v869 = (_DWORD)v866 - (_DWORD)v864;
                        }
                        else
                        {
                          if ( *v863 == *v864 )
                          {
                            v866 = v1089 + 12;
                            goto LABEL_1764;
                          }
                          __asm { tzcnt   rcx, rcx }
                          v869 = (unsigned int)_RCX >> 3;
                        }
LABEL_1776:
                        v856 = v1039;
                        v872 = v1024;
                        v873 = v869 - v858 + 4;
                        if ( v873 <= v1045 )
                        {
                          v842 = v1089;
                        }
                        else
                        {
                          v1045 = v873;
                          v1072 = v1054 - v855;
                          v874 = v858;
                          v842 = v1089;
                          v1143 = (unsigned __int64)&v1089[v874];
                        }
                      }
                      else
                      {
                        v872 = v1024;
                      }
                    }
                    if ( *((_WORD *)a1 + (unsigned __int16)v855 + 0x10000) != 1 )
                      goto LABEL_1887;
                    if ( v856 )
                    {
                      v1039 = v856;
                      if ( v856 != 2 )
                        goto LABEL_1887;
                    }
                    else
                    {
                      if ( (_BYTE)v872 != HIBYTE(v872) || (unsigned __int16)v872 != HIWORD(v872) )
                      {
                        v856 = 1;
                        v1039 = 1;
                        goto LABEL_1887;
                      }
                      v1039 = 2;
                      v1167 = (unsigned int)LZ4HC_countPattern(v842 + 4, v1060, v872) + 4LL;
                    }
                    v899 = v855 - 1;
                    if ( v855 - 1 < v844 || (unsigned int)v845 - v855 < 3 )
                      goto LABEL_1887;
                    if ( v899 >= (unsigned int)v845 )
                    {
                      v900 = 0;
                      v845 = (_DWORD *)((char *)v846 + v899 - (unsigned int)v845);
                    }
                    else
                    {
                      v900 = 1;
                      v845 = (_DWORD *)((char *)v1140 + v899 - v843);
                    }
                    if ( *v845 != v1024 )
                      break;
                    v901 = v1060;
                    if ( v900 )
                      v901 = v1151;
                    v902 = (unsigned int)LZ4HC_countPattern(v845 + 1, v901, v1024) + 4LL;
                    if ( v900 )
                    {
                      if ( (char *)v845 + v902 == v901 )
                      {
                        v903 = LZ4HC_rotatePattern(v902, v1024);
                        v846 = v1098;
                        v902 += (unsigned int)LZ4HC_countPattern(v1098, v1060, v903);
                      }
                      else
                      {
                        v846 = v1098;
                      }
                      v904 = v1140;
                    }
                    else
                    {
                      v846 = v1098;
                      v904 = v1098;
                    }
                    v905 = LZ4HC_reverseCountPattern(v845, v904, v1024);
                    v907 = v905;
                    if ( v900 )
                    {
                      LODWORD(v845) = v1106;
                    }
                    else
                    {
                      v159 = (_QWORD *)((char *)v845 - v905) == v846;
                      LODWORD(v845) = v1106;
                      if ( v159 && v1158 < v1106 )
                      {
                        v908 = LZ4HC_rotatePattern(-v905, v906);
                        v909 = LZ4HC_reverseCountPattern(v1151, v1140, v908);
                        v907 = v909 + v910;
                      }
                    }
                    v844 = v1079;
                    v855 = v1079;
                    if ( v899 - v907 > v1079 )
                      v855 = v899 - v907;
                    v911 = v902 + v899 - v855;
                    if ( v911 < v1167 || v902 > v1167 )
                    {
                      if ( (unsigned int)v845 - v855 - 1 < 3 )
                      {
                        v855 = (unsigned int)v845;
                      }
                      else if ( !v1115 )
                      {
                        v912 = v1167;
                        if ( v911 < v1167 )
                          v912 = v902 + v899 - v855;
                        if ( v1045 < v912 )
                        {
                          if ( (unsigned __int64)&v1089[(unsigned int)v845 - (unsigned __int64)v855 - (_QWORD)v846] > 0xFFFF )
                            goto LABEL_1890;
                          v1045 = v912;
                          v1072 = v1054 - v855;
                          v1143 = (unsigned __int64)v1089;
                        }
                        v913 = *((unsigned __int16 *)a1 + (unsigned __int16)v855 + 0x10000);
                        if ( v913 > v855 )
                        {
LABEL_1890:
                          v914 = v1131;
                          if ( v1131 <= 0 )
                            goto LABEL_1937;
                          v842 = v1089;
                          v854 = v1198;
                          v847 = v1054;
                          v850 = v1024;
                          goto LABEL_1893;
                        }
                        v856 = v1039;
                        goto LABEL_1888;
                      }
                    }
                    else
                    {
                      v855 = (unsigned int)v845;
                      if ( (unsigned int)v845 - ((_DWORD)v902 - (_DWORD)v1167 + v899) - 1 >= 3 )
                        v855 = v902 - v1167 + v899;
                    }
                    v856 = v1039;
LABEL_1889:
                    v843 = v1158;
                    v848 = v1140;
                    v842 = v1089;
                    if ( v855 < v844 )
                      goto LABEL_1890;
                  }
                  v844 = v1079;
LABEL_1887:
                  LODWORD(v845) = v1106;
                  v913 = *((unsigned __int16 *)a1 + (unsigned __int16)v855 + 0x10000);
LABEL_1888:
                  v855 -= v913;
                  goto LABEL_1889;
                }
                v914 = 256;
                v1143 = (unsigned __int64)v841;
LABEL_1893:
                if ( v847 - v844 < 0xFFFF )
                {
                  v915 = *(_QWORD *)(v1176 + 262152);
                  v916 = *(unsigned int *)(v1176 + 262168);
                  v917 = *(_DWORD *)(v1176 + 4 * v854);
                  v918 = v916 + *(_QWORD *)(v1176 + 0x40000) - v915;
                  v919 = v1079 + v917 - v918;
                  if ( v847 - v919 <= 0xFFFF )
                  {
                    v920 = v1115;
                    do
                    {
                      if ( !v914 )
                        break;
                      v1132 = --v914;
                      v921 = (_DWORD *)(v917 + v915 - v916);
                      if ( *v921 == v850 )
                      {
                        v922 = v921 + 1;
                        v923 = (unsigned __int64)&v842[v918 - v917];
                        if ( v923 > (unsigned __int64)v1060 )
                          v923 = (unsigned __int64)v1060;
                        v924 = v842 + 4;
                        if ( (unsigned __int64)v924 >= v923 - 7 )
                        {
                          v926 = v924;
                          while ( (unsigned __int64)v926 < v923 - 7 )
                          {
                            if ( *v922 != *v926 )
                            {
                              __asm { tzcnt   rax, r8 }
                              v928 = ((unsigned int)_RAX >> 3) - (_DWORD)v924 + (_DWORD)v926;
                              goto LABEL_1920;
                            }
                            ++v926;
LABEL_1908:
                            ++v922;
                          }
                          if ( (unsigned __int64)v926 < v923 - 3 && *(_DWORD *)v922 == *(_DWORD *)v926 )
                          {
                            v926 = (_QWORD *)((char *)v926 + 4);
                            v922 = (_QWORD *)((char *)v922 + 4);
                          }
                          if ( (unsigned __int64)v926 < v923 - 1 && *(_WORD *)v922 == *(_WORD *)v926 )
                          {
                            v926 = (_QWORD *)((char *)v926 + 2);
                            v922 = (_QWORD *)((char *)v922 + 2);
                          }
                          if ( (unsigned __int64)v926 < v923 && *(_BYTE *)v922 == *(_BYTE *)v926 )
                            LODWORD(v926) = (_DWORD)v926 + 1;
                          v928 = (_DWORD)v926 - (_DWORD)v924;
                        }
                        else
                        {
                          if ( *v924 == *v922 )
                          {
                            v926 = v924 + 1;
                            goto LABEL_1908;
                          }
                          __asm { tzcnt   rcx, rcx }
                          v928 = (unsigned int)_RCX >> 3;
                        }
LABEL_1920:
                        v931 = 0;
                        if ( v920 )
                        {
                          v932 = v1089;
                          v933 = v1081 - (_DWORD)v1089;
                          if ( (__int64)(v1081 - (_QWORD)v1089) <= v916 - v917 )
                            v933 = v916 - v917;
                          if ( -v933 <= 3 )
                          {
LABEL_1926:
                            if ( v931 > v933 )
                            {
                              do
                              {
                                if ( v932[v931 - 1] != *((_BYTE *)v921 + v931 - 1) )
                                  break;
                                --v931;
                              }
                              while ( v931 > v933 );
                              v920 = v1115;
                            }
                          }
                          else
                          {
                            while ( 1 )
                            {
                              v934 = *(_DWORD *)((char *)v921 + v931 - 4) ^ *(_DWORD *)&v932[v931 - 4];
                              if ( v934 )
                                break;
                              v932 = v1089;
                              v931 -= 4;
                              if ( v931 - v933 <= 3 )
                                goto LABEL_1926;
                            }
                            _BitScanReverse(&v935, v934);
                            v931 -= (31 - v935) >> 3;
                          }
                        }
                        v847 = v1054;
                        v850 = v1024;
                        if ( (int)(v928 + 4 - v931) <= v1045 )
                        {
                          v842 = v1089;
                        }
                        else
                        {
                          v1045 = v928 + 4 - v931;
                          v842 = v1089;
                          v1072 = v1054 - v919;
                          v1143 = (unsigned __int64)&v1089[v931];
                        }
                        v914 = v1132;
                      }
                      v936 = *(unsigned __int16 *)(v1176 + 2LL * (unsigned __int16)v917 + 0x20000);
                      v919 -= v936;
                      v917 -= v936;
                    }
                    while ( v847 - v919 <= 0xFFFF );
                    v640 = (__int64)v1121;
                  }
                }
LABEL_1937:
                v937 = v1045;
                v938 = v1072;
                v840 = v1196;
                v839 = v1183;
                v834 = v1063;
                v727 = v1205;
                v729 = v1057;
                v836 = v1081;
              }
              v939 = v727;
              if ( v937 <= v834 )
                break;
              v940 = (char *)v729 + v727;
              if ( v1143 >= (unsigned __int64)(v940 + 3) )
              {
                if ( v836 >= (unsigned __int64)v940 )
                {
                  v941 = v1205;
                }
                else if ( (__int64)(v836 - (_QWORD)v729) >= 18 )
                {
                  v941 = v836 - (_DWORD)v729;
                  v1205 = v836 - (_DWORD)v729;
                }
                else
                {
                  if ( v727 > 18 )
                    v727 = 18;
                  v1205 = v727;
                  if ( (_DWORD *)((char *)v729 + v727) > v840 - 1 )
                  {
                    v727 = v834 + v836 - (_DWORD)v729 - 4;
                    v1205 = v727;
                  }
                  v941 = v1205;
                  v942 = v727 + (_DWORD)v729 - v836;
                  if ( v942 > 0 )
                  {
                    v1081 = v942 + v836;
                    v1063 = v834 - v942;
                  }
                }
                v943 = (char *)v1057;
                v944 = (_BYTE *)(v640 + 1);
                LODWORD(v945) = HIDWORD(v1084);
                v946 = (char *)v1057 - v1161;
                v947 = v640;
                v645 = v1124;
                v948 = (char *)v640;
                if ( a7 && (unsigned __int64)&v944[v946 / 0xFF + 8 + v946] > v1124 )
                  goto LABEL_2083;
                if ( v946 < 0xF )
                {
                  *(_BYTE *)v640 = 16 * v946;
                }
                else
                {
                  v949 = v946 - 15;
                  *(_BYTE *)v640 = -16;
                  while ( v949 >= 0xFF )
                  {
                    *v944++ = -1;
                    v949 -= 255LL;
                  }
                  *v944++ = v949;
                }
                v950 = v1161;
                v951 = &v944[v946];
                do
                {
                  v952 = *(_QWORD *)v950;
                  v950 += 8;
                  *(_QWORD *)v944 = v952;
                  v944 += 8;
                }
                while ( v944 < (_BYTE *)v951 );
                v640 = (__int64)(v951 + 1);
                *v951 = v1033;
                v1121 = v951 + 1;
                v1084 = v951 + 1;
                v953 = v941 - 4LL;
                if ( a7 )
                {
                  if ( v640 + v953 / 0xFF + 6 > v1124 )
                  {
LABEL_2083:
                    v643 = v1161;
                    goto LABEL_2073;
                  }
                }
                v954 = *v948;
                if ( v953 < 0xF )
                {
                  *v948 = v954 + v953;
                }
                else
                {
                  *v948 = v954 + 15;
                  for ( i13 = v941 - 19LL; i13 >= 0x1FE; i13 -= 510LL )
                  {
                    *(_BYTE *)v640 = -1;
                    v956 = (_BYTE *)(v640 + 1);
                    *v956 = -1;
                    v640 = (__int64)(v956 + 1);
                  }
                  if ( i13 >= 0xFF )
                  {
                    LOBYTE(i13) = i13 + 1;
                    *(_BYTE *)v640++ = -1;
                  }
                  *(_BYTE *)v640++ = i13;
                  v1121 = (_WORD *)v640;
                  HIDWORD(v1084) = HIDWORD(v640);
                }
                v729 = (_DWORD *)v1081;
                v836 = v1143;
                LOWORD(v1033) = v1030;
                v727 = v1063;
                v1205 = v1063;
                v1081 = v1143;
                v1161 = (char *)v1057 + v941;
                v1057 = v729;
              }
              else
              {
                if ( v1143 >= (unsigned __int64)v940 )
                {
                  if ( v836 >= (unsigned __int64)v940 )
                  {
                    v959 = v1063;
                  }
                  else
                  {
                    v957 = v727 + (_DWORD)v729 - v836;
                    v958 = v834 - v957;
                    if ( v958 >= 4 )
                    {
                      v959 = v958;
                      v1081 = v957 + v836;
                    }
                    else
                    {
                      v1081 = v1143;
                      v959 = v937;
                      v1030 = v938;
                    }
                  }
                  v960 = (_BYTE *)(v640 + 1);
                  v945 = v640 >> 32;
                  v961 = (char *)v1057 - v1161;
                  v947 = v640;
                  v962 = (char *)v640;
                  if ( !a7 || (unsigned __int64)&v960[v961 / 0xFF + 8 + v961] <= v1124 )
                  {
                    if ( v961 < 0xF )
                    {
                      *(_BYTE *)v640 = 16 * v961;
                    }
                    else
                    {
                      v963 = v961 - 15;
                      *(_BYTE *)v640 = -16;
                      while ( v963 >= 0xFF )
                      {
                        *v960++ = -1;
                        v963 -= 255LL;
                      }
                      *v960++ = v963;
                    }
                    v964 = v1161;
                    v965 = &v960[v961];
                    do
                    {
                      v966 = *(_QWORD *)v964;
                      v964 += 8;
                      *(_QWORD *)v960 = v966;
                      v960 += 8;
                    }
                    while ( v960 < (_BYTE *)v965 );
                    v640 = (__int64)(v965 + 1);
                    v967 = v939 - 4;
                    v1121 = v965 + 1;
                    v1084 = v965 + 1;
                    *v965 = v1033;
                    if ( !a7 || v640 + v967 / 0xFF + 6 <= v1124 )
                    {
                      v968 = *v962;
                      if ( v967 < 0xF )
                      {
                        *v962 = v968 + v967;
                      }
                      else
                      {
                        *v962 = v968 + 15;
                        for ( i14 = v939 - 19; i14 >= 0x1FE; i14 -= 510LL )
                        {
                          *(_BYTE *)v640 = -1;
                          v970 = (_BYTE *)(v640 + 1);
                          *v970 = -1;
                          v640 = (__int64)(v970 + 1);
                        }
                        if ( i14 >= 0xFF )
                        {
                          LOBYTE(i14) = i14 + 1;
                          *(_BYTE *)v640++ = -1;
                        }
                        *(_BYTE *)v640++ = i14;
                        v1121 = (_WORD *)v640;
                        HIDWORD(v1084) = HIDWORD(v640);
                      }
                      LODWORD(v730) = v959;
                      v731 = (_DWORD *)v1081;
                      v729 = (_DWORD *)v1143;
                      v1161 = v940;
                      v727 = v937;
                      v728 = v1030;
                      v1057 = (_DWORD *)v1143;
                      LOWORD(v1033) = v938;
                      v1205 = v937;
                      goto LABEL_1509;
                    }
                  }
                  v643 = v1161;
LABEL_2071:
                  v645 = v1124;
LABEL_2072:
                  v943 = (char *)v1057;
LABEL_2073:
                  v834 = v1205;
                  v1002 = v1033;
LABEL_2074:
                  if ( a7 != 2 )
                    goto LABEL_2100;
                  v1007 = v943 - v643;
                  v640 = __PAIR64__(v945, v947);
                  v1008 = (v943 - v643 + 240) / 0xFFuLL + v943 - v643 + 1;
                  if ( __PAIR64__(v945, v947) + v1008 <= v645 - 3 )
                  {
                    if ( v834 > 255 * (v645 - 3 - __PAIR64__(v945, v947) - v1008) + 18 )
                      v834 = 255 * (v645 - 3 - v947 - v1008) + 18;
                    if ( (__int64)(v834 + v645 - __PAIR64__(v945, v947) - v1008 + 2) >= 12 )
                    {
                      v1009 = (_BYTE *)(__PAIR64__(v945, v947) + 1);
                      if ( v1007 < 0xF )
                      {
                        *(_BYTE *)__PAIR64__(v945, v947) = 16 * v1007;
                      }
                      else
                      {
                        v1010 = v1007 - 15;
                        *(_BYTE *)__PAIR64__(v945, v947) = -16;
                        while ( v1010 >= 0xFF )
                        {
                          *v1009++ = -1;
                          v1010 -= 255LL;
                        }
                        *v1009++ = v1010;
                      }
                      v1011 = &v1009[v1007];
                      do
                      {
                        v1012 = *(_QWORD *)v643;
                        v643 += 8;
                        *(_QWORD *)v1009 = v1012;
                        v1009 += 8;
                      }
                      while ( v1009 < (_BYTE *)v1011 );
                      *v1011 = v1002;
                      v1013 = *(_BYTE *)__PAIR64__(v945, v947);
                      v640 = (__int64)(v1011 + 1);
                      if ( (unsigned __int64)(v834 - 4LL) < 0xF )
                      {
                        *(_BYTE *)__PAIR64__(v945, v947) = v1013 + v834 - 4;
                      }
                      else
                      {
                        *(_BYTE *)__PAIR64__(v945, v947) = v1013 + 15;
                        for ( i15 = v834 - 19LL; i15 >= 0x1FE; i15 -= 510LL )
                        {
                          *(_BYTE *)v640 = -1;
                          v1015 = (_BYTE *)(v640 + 1);
                          *v1015 = -1;
                          v640 = (__int64)(v1015 + 1);
                        }
                        if ( i15 >= 0xFF )
                        {
                          LOBYTE(i15) = i15 + 1;
                          *(_BYTE *)v640++ = -1;
                        }
                        *(_BYTE *)v640++ = i15;
                      }
                      v643 = &v943[v834];
                    }
                  }
                  v1016 = v1194 - v643;
                  v1017 = v1194 - v643;
                  goto LABEL_2103;
                }
                v836 = v1143;
                v1081 = v1143;
              }
              v1030 = v938;
              v834 = v937;
              v732 = v1149;
              v1063 = v937;
            }
            if ( v836 >= (unsigned __int64)v729 + v727 )
            {
              v971 = v1205;
            }
            else
            {
              v971 = v836 - (_DWORD)v729;
              v1205 = v836 - (_DWORD)v729;
            }
            v972 = (_BYTE *)(v640 + 1);
            v643 = v1161;
            v973 = (char *)v1057 - v1161;
            v945 = v640 >> 32;
            v947 = v640;
            if ( a7 && (unsigned __int64)&v972[v973 / 0xFF + 8 + v973] > v1124 )
              goto LABEL_2071;
            if ( v973 < 0xF )
            {
              *(_BYTE *)v640 = 16 * v973;
            }
            else
            {
              v974 = v973 - 15;
              *(_BYTE *)v640 = -16;
              while ( v974 >= 0xFF )
              {
                *v972++ = -1;
                v974 -= 255LL;
              }
              *v972++ = v974;
            }
            v975 = v1161;
            v976 = &v972[v973];
            do
            {
              v977 = *(_QWORD *)v975;
              v975 += 8;
              *(_QWORD *)v972 = v977;
              v972 += 8;
            }
            while ( v972 < (_BYTE *)v976 );
            v978 = (__int64)(v976 + 1);
            *v976 = v1033;
            v979 = v971;
            v980 = v971 - 4LL;
            if ( a7 )
            {
              if ( v978 + v980 / 0xFF + 6 > v1124 )
                goto LABEL_2071;
            }
            v981 = *(_BYTE *)v640;
            if ( v980 < 0xF )
            {
              *(_BYTE *)v640 = v981 + v980;
            }
            else
            {
              *(_BYTE *)v640 = v981 + 15;
              for ( i16 = v971 - 19LL; i16 >= 0x1FE; i16 -= 510LL )
              {
                *(_BYTE *)v978 = -1;
                v983 = (_BYTE *)(v978 + 1);
                *v983 = -1;
                v978 = (__int64)(v983 + 1);
              }
              if ( i16 >= 0xFF )
              {
                LOBYTE(i16) = i16 + 1;
                *(_BYTE *)v978++ = -1;
              }
              *(_BYTE *)v978++ = i16;
            }
            v943 = (char *)v1081;
            v643 = (char *)v1057 + v979;
            v984 = (_BYTE *)(v978 + 1);
            v985 = v1081 - ((_QWORD)v1057 + v979);
            v945 = v978 >> 32;
            v947 = v978;
            if ( a7 && (unsigned __int64)&v984[v985 / 0xFF + 8 + v985] > v1124 )
            {
              v990 = v1030;
            }
            else
            {
              if ( v985 < 0xF )
              {
                *(_BYTE *)v978 = 16 * v985;
              }
              else
              {
                v986 = v985 - 15;
                *(_BYTE *)v978 = -16;
                while ( v986 >= 0xFF )
                {
                  *v984++ = -1;
                  v986 -= 255LL;
                }
                *v984++ = v986;
              }
              v987 = v643;
              v988 = &v984[v985];
              do
              {
                v989 = *(_QWORD *)v987;
                v987 += 8;
                *(_QWORD *)v984 = v989;
                v984 += 8;
              }
              while ( v984 < (_BYTE *)v988 );
              v640 = (__int64)(v988 + 1);
              v990 = v1030;
              v991 = v839 - 4;
              v1121 = v988 + 1;
              v1084 = v988 + 1;
              *v988 = v1030;
              if ( !a7 || v640 + v991 / 0xFF + 6 <= v1124 )
              {
                v992 = *(_BYTE *)v978;
                if ( v991 < 0xF )
                {
                  *(_BYTE *)v978 = v992 + v991;
                }
                else
                {
                  *(_BYTE *)v978 = v992 + 15;
                  for ( i17 = v839 - 19; i17 >= 0x1FE; i17 -= 510LL )
                  {
                    *(_BYTE *)v640 = -1;
                    v994 = (_BYTE *)(v640 + 1);
                    *v994 = -1;
                    v640 = (__int64)(v994 + 1);
                  }
                  if ( i17 >= 0xFF )
                  {
                    LOBYTE(i17) = i17 + 1;
                    *(_BYTE *)v640++ = -1;
                  }
                  *(_BYTE *)v640++ = i17;
                  v1121 = (_WORD *)v640;
                  HIDWORD(v1084) = HIDWORD(v640);
                }
                v642 = (char *)v840;
                v1057 = v840;
                v643 = (char *)v840;
                v1161 = (char *)v840;
                goto LABEL_2066;
              }
              v834 = v1063;
            }
            v645 = v1124;
            v1002 = v990;
            goto LABEL_2074;
          }
          v729 = (_DWORD *)v1081;
          v1057 = (_DWORD *)v1081;
          LOWORD(v1033) = v835;
          v727 = v834;
          v1205 = v834;
        }
        v995 = (_BYTE *)(v640 + 1);
        v643 = v1161;
        v645 = v1124;
        v996 = (char *)v1057 - v1161;
        v945 = v640 >> 32;
        v947 = v640;
        v997 = (char *)v640;
        if ( a7 && (unsigned __int64)&v995[v996 / 0xFF + 8 + v996] > v1124 )
          goto LABEL_2072;
        if ( v996 < 0xF )
        {
          *(_BYTE *)v640 = 16 * v996;
        }
        else
        {
          v998 = v996 - 15;
          *(_BYTE *)v640 = -16;
          while ( v998 >= 0xFF )
          {
            *v995++ = -1;
            v998 -= 255LL;
          }
          *v995++ = v998;
        }
        v999 = v1161;
        v1000 = &v995[v996];
        do
        {
          v1001 = *(_QWORD *)v999;
          v999 += 8;
          *(_QWORD *)v995 = v1001;
          v995 += 8;
        }
        while ( v995 < (_BYTE *)v1000 );
        v640 = (__int64)(v1000 + 1);
        v1002 = v1033;
        v1003 = v733 - 4;
        v1121 = v1000 + 1;
        v1084 = v1000 + 1;
        *v1000 = v1033;
        if ( a7 && v640 + v1003 / 0xFF + 6 > v1124 )
        {
          v834 = v1205;
          v943 = (char *)v1057;
          goto LABEL_2074;
        }
        v1004 = *v997;
        if ( v1003 < 0xF )
        {
          *v997 = v1004 + v1003;
        }
        else
        {
          *v997 = v1004 + 15;
          for ( i18 = v733 - 19; i18 >= 0x1FE; i18 -= 510LL )
          {
            *(_BYTE *)v640 = -1;
            v1006 = (_BYTE *)(v640 + 1);
            *v1006 = -1;
            v640 = (__int64)(v1006 + 1);
          }
          if ( i18 >= 0xFF )
          {
            LOBYTE(i18) = i18 + 1;
            *(_BYTE *)v640++ = -1;
          }
          *(_BYTE *)v640++ = i18;
          v1121 = (_WORD *)v640;
          HIDWORD(v1084) = HIDWORD(v640);
        }
        v642 = (char *)v734;
        v1057 = v734;
        v643 = (char *)v734;
        v1161 = (char *)v734;
LABEL_2066:
        if ( v642 > v1149 )
        {
          v645 = v1124;
          v644 = v1194;
          goto LABEL_2102;
        }
        v8 = a1;
      }
      while ( 1 )
      {
        if ( v655 <= 0 )
          goto LABEL_1506;
        v1052 = v655 - 1;
        if ( v660 < (unsigned int)v650 )
        {
          if ( v660 <= (int)v650 - 4 )
          {
            v682 = v660 - (unsigned int)v646;
            if ( *(_DWORD *)((char *)v652 + v682) == v653 )
            {
              v683 = v1060;
              v684 = (char *)(v1057 + 1);
              v685 = (char *)v1057 + (unsigned int)v650 - v660;
              if ( v685 > v1060 )
                v685 = v1060;
              v686 = (_QWORD *)((char *)v652 + v682 + 4);
              if ( v684 >= v685 - 7 )
              {
                v688 = (char *)(v1057 + 1);
                while ( v688 < v685 - 7 )
                {
                  if ( *v686 != *(_QWORD *)v688 )
                  {
                    __asm { tzcnt   rbx, r8 }
                    v690 = (_DWORD)v688 + ((unsigned int)_RBX >> 3) - (_DWORD)v684;
                    goto LABEL_1413;
                  }
                  v688 += 8;
LABEL_1401:
                  ++v686;
                }
                if ( v688 < v685 - 3 && *(_DWORD *)v686 == *(_DWORD *)v688 )
                {
                  v688 += 4;
                  v686 = (_QWORD *)((char *)v686 + 4);
                }
                if ( v688 < v685 - 1 && *(_WORD *)v686 == *(_WORD *)v688 )
                {
                  v688 += 2;
                  v686 = (_QWORD *)((char *)v686 + 2);
                }
                if ( v688 < v685 && *(_BYTE *)v686 == *v688 )
                  LODWORD(v688) = (_DWORD)v688 + 1;
                v690 = (_DWORD)v688 - (_DWORD)v684;
LABEL_1413:
                v683 = v1060;
              }
              else
              {
                if ( *v686 == *(_QWORD *)v684 )
                {
                  v688 = (char *)(v1057 + 3);
                  goto LABEL_1401;
                }
                __asm { tzcnt   rbx, rcx }
                v690 = (unsigned int)_RBX >> 3;
              }
              v693 = v690 + 4;
              v694 = (char *)v1057 + v690 + 4;
              if ( v694 == v685 && v685 < v683 )
              {
                v695 = (unsigned __int64)(v683 - 7);
                if ( v694 >= v683 - 7 )
                {
                  v698 = v648;
                  v697 = (char *)v1057 + v690 + 4;
LABEL_1421:
                  while ( (unsigned __int64)v697 < v695 )
                  {
                    if ( *v698 != *(_QWORD *)v697 )
                    {
                      __asm { tzcnt   rax, r8 }
                      v700 = ((unsigned int)_RAX >> 3) - (_DWORD)v694 + (_DWORD)v697;
                      goto LABEL_1435;
                    }
                    v697 += 8;
                    ++v698;
                  }
                  if ( v697 < v1060 - 3 && *(_DWORD *)v698 == *(_DWORD *)v697 )
                  {
                    v697 += 4;
                    v698 = (_QWORD *)((char *)v698 + 4);
                  }
                  if ( v697 < v1060 - 1 && *(_WORD *)v698 == *(_WORD *)v697 )
                  {
                    v697 += 2;
                    v698 = (_QWORD *)((char *)v698 + 2);
                  }
                  if ( v697 < v1060 && *(_BYTE *)v698 == *v697 )
                    LODWORD(v697) = (_DWORD)v697 + 1;
                  v700 = (_DWORD)v697 - (_DWORD)v694;
                }
                else
                {
                  if ( *(_QWORD *)v694 == *v648 )
                  {
                    v697 = v694 + 8;
                    v698 = v648 + 1;
                    goto LABEL_1421;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v700 = (unsigned int)_RCX >> 3;
                }
LABEL_1435:
                v693 = v690 + v700 + 4;
              }
              v649 = v1128;
              v653 = v1029;
              if ( v693 > v647 )
              {
                v1205 = v693;
                v1033 = v1104 - v660;
              }
            }
          }
        }
        else
        {
          v672 = v660 - (unsigned int)v650;
          if ( *(_WORD *)((char *)v1057 + v647 - 1) == *(_WORD *)((char *)v648 + v647 + v672 - 1)
            && *(_DWORD *)((char *)v648 + v672) == v653 )
          {
            v673 = v1057 + 1;
            v674 = (_QWORD *)((char *)v648 + v672 + 4);
            if ( v1057 + 1 >= (_DWORD *)(v1060 - 7) )
            {
              v676 = (char *)(v1057 + 1);
              while ( v676 < v1060 - 7 )
              {
                if ( *v674 != *(_QWORD *)v676 )
                {
                  __asm { tzcnt   rax, r8 }
                  v678 = ((unsigned int)_RAX >> 3) - (_DWORD)v673 + (_DWORD)v676;
                  goto LABEL_1387;
                }
                v676 += 8;
LABEL_1375:
                ++v674;
              }
              if ( v676 < v1060 - 3 && *(_DWORD *)v674 == *(_DWORD *)v676 )
              {
                v676 += 4;
                v674 = (_QWORD *)((char *)v674 + 4);
              }
              if ( v676 < v1060 - 1 && *(_WORD *)v674 == *(_WORD *)v676 )
              {
                v676 += 2;
                v674 = (_QWORD *)((char *)v674 + 2);
              }
              if ( v676 < v1060 && *(_BYTE *)v674 == *v676 )
                LODWORD(v676) = (_DWORD)v676 + 1;
              v678 = (_DWORD)v676 - (_DWORD)v673;
            }
            else
            {
              if ( *v674 == *v673 )
              {
                v676 = (char *)(v1057 + 3);
                goto LABEL_1375;
              }
              __asm { tzcnt   rcx, rcx }
              v678 = (unsigned int)_RCX >> 3;
            }
LABEL_1387:
            v653 = v1029;
            v681 = v678 + 4;
            if ( v681 > v647 )
            {
              v1205 = v681;
              v1033 = v1104 - v660;
            }
          }
        }
        v703 = a1;
        v704 = 1;
        if ( *((_WORD *)a1 + (unsigned __int16)v660 + 0x10000) != 1 )
          goto LABEL_1443;
        if ( v654 )
        {
          v1070 = v654;
          if ( v654 != 2 )
            goto LABEL_1443;
        }
        else
        {
          if ( (_BYTE)v653 != HIBYTE(v653) || (unsigned __int16)v653 != HIWORD(v653) )
          {
            v654 = 1;
LABEL_1443:
            v649 = v1128;
            v705 = *((unsigned __int16 *)v703 + (unsigned __int16)v660 + 0x10000);
LABEL_1444:
            v660 -= v705;
            goto LABEL_1445;
          }
          v654 = 2;
          v1070 = 2;
          v1174 = (unsigned int)LZ4HC_countPattern(v1057 + 1, v1060, v653) + 4LL;
          v703 = a1;
        }
        v706 = v660 - 1;
        if ( v660 - 1 < v649 || (unsigned int)v650 - v660 < 3 )
          goto LABEL_1443;
        if ( v706 >= (unsigned int)v650 )
        {
          v704 = 0;
          v707 = (_DWORD *)((char *)v648 + v706 - (unsigned int)v650);
        }
        else
        {
          v707 = (_DWORD *)((char *)v1096 + v706 - v1113);
        }
        if ( *v707 != v1029 )
          goto LABEL_1443;
        v708 = v1060;
        if ( v704 )
          v708 = v1165;
        v709 = (unsigned int)LZ4HC_countPattern(v707 + 1, v708, v1029) + 4LL;
        if ( v704 )
        {
          if ( (char *)v707 + v709 == v708 )
          {
            v710 = LZ4HC_rotatePattern(v709, v1029);
            v648 = v1138;
            v709 += (unsigned int)LZ4HC_countPattern(v1138, v1060, v710);
          }
          else
          {
            v648 = v1138;
          }
          v711 = v1096;
        }
        else
        {
          v648 = v1138;
          v711 = v1138;
        }
        v712 = LZ4HC_reverseCountPattern(v707, v711, v1029);
        v714 = v712;
        if ( !v704 && (_QWORD *)((char *)v707 - v712) == v648 && v1113 < (unsigned int)v650 )
        {
          v715 = LZ4HC_rotatePattern(-v712, v713);
          v716 = LZ4HC_reverseCountPattern(v1165, v1096, v715);
          v714 = v716 + v717;
        }
        v649 = v1128;
        v718 = v706 - v714;
        v660 = v1128;
        if ( v718 > v1128 )
          v660 = v718;
        v719 = v709 + v706 - v660;
        if ( v719 < v1174 || v709 > v1174 )
        {
          if ( (unsigned int)v650 - v660 - 1 >= 3 )
          {
            v720 = v1174;
            if ( v719 < v1174 )
              v720 = v709 + v706 - v660;
            if ( v1205 < v720 )
            {
              if ( (unsigned __int64)(v650 + (char *)v1057 - v660 - (char *)v648) > 0xFFFF )
                goto LABEL_1446;
              v1205 = v720;
              v1033 = v1104 - v660;
            }
            v705 = *((unsigned __int16 *)a1 + (unsigned __int16)v660 + 0x10000);
            if ( v705 > v660 )
            {
LABEL_1446:
              v661 = v1052;
              if ( v1052 <= 0 )
                goto LABEL_1506;
              v651 = v1104;
              v653 = v1029;
              v659 = v1186;
              goto LABEL_1353;
            }
            v654 = v1070;
            goto LABEL_1444;
          }
          v660 = v650;
        }
        else
        {
          v660 = v650;
          if ( (unsigned int)v650 - ((_DWORD)v709 - (_DWORD)v1174 + v706) - 1 >= 3 )
            v660 = v709 - v1174 + v706;
        }
        v654 = v1070;
LABEL_1445:
        LODWORD(v646) = v1113;
        v652 = v1096;
        v653 = v1029;
        v655 = v1052;
        if ( v660 < v649 )
          goto LABEL_1446;
        v647 = v1205;
      }
    }
  }
LABEL_2102:
  v1016 = v644 - v643;
  v1017 = v1016;
  if ( a7 != 2 )
  {
    if ( !a7 )
      goto LABEL_2109;
    goto LABEL_2105;
  }
LABEL_2103:
  v645 += 5LL;
LABEL_2105:
  if ( v640 + (v1016 + 240) / 0xFF + v1016 + 1 > v645 )
  {
    if ( a7 == 1 )
    {
LABEL_2107:
      v638 = 0;
      goto LABEL_2117;
    }
    v1017 = v645 - v640 - 1 - ((v645 - v640 - 1 + 241) >> 8);
  }
LABEL_2109:
  if ( v1017 < 0xF )
  {
    LOBYTE(v1018) = 16 * v1017;
  }
  else
  {
    *(_BYTE *)v640 = -16;
    v1018 = v1017 - 15;
    ++v640;
    while ( v1018 >= 0xFF )
    {
      *(_BYTE *)v640++ = -1;
      v1018 -= 255LL;
    }
  }
  *(_BYTE *)v640 = v1018;
  memmove((void *)(v640 + 1), v643, v1017);
  *a4 = v1017 + (_DWORD)v643 - (_DWORD)Src;
  v638 = v1017 - a3 + v640 + 1;
LABEL_2116:
  if ( v638 <= 0 )
    goto LABEL_2117;
  return (unsigned int)v638;
}

```

## disassembly

```asm
0x1400e71bc  mov     rax, rsp
0x1400e71bf  mov     [rax+20h], r9
0x1400e71c3  mov     [rax+18h], r8
0x1400e71c7  mov     [rax+10h], rdx
0x1400e71cb  mov     [rax+8], rcx
0x1400e71cf  push    rbp
0x1400e71d0  push    rbx
0x1400e71d1  push    rsi
0x1400e71d2  push    rdi
0x1400e71d3  push    r12
0x1400e71d5  push    r13
0x1400e71d7  push    r14
0x1400e71d9  push    r15
0x1400e71db  lea     rbp, [rax-68h]
0x1400e71df  sub     rsp, 128h
0x1400e71e6  mov     r10, [rcx+40000h]
0x1400e71ed  mov     rdi, rcx
0x1400e71f0  mov     ecx, [rcx+40018h]
0x1400e71f6  mov     r13, r9
0x1400e71f9  mov     r15, r8
0x1400e71fc  mov     rbx, rdx
0x1400e71ff  sub     ecx, [rdi+4001Ch]
0x1400e7205  sub     rcx, [rdi+40008h]
0x1400e720c  add     rcx, r10
0x1400e720f  cmp     rcx, 10000h
0x1400e7216  jb      loc_1400E94F8
0x1400e721c  xor     r12d, r12d
0x1400e721f  cmp     [rbp+60h+arg_30], 2
0x1400e7226  mov     [rdi+40028h], r12
0x1400e722d  lea     r11d, [r12+1]
0x1400e7232  jnz     short loc_1400E7241
0x1400e7234  cmp     [rbp+60h+arg_20], r11d
0x1400e723b  jl      loc_1400E94F0
0x1400e7241  movsxd  rax, dword ptr [r9]
0x1400e7244  cmp     eax, 7E000000h
0x1400e7249  ja      loc_1400E94F0
0x1400e724f  movsxd  rcx, [rbp+60h+arg_20]
0x1400e7256  add     rax, r10
0x1400e7259  add     rcx, r15
0x1400e725c  mov     [rdi+40000h], rax
0x1400e7263  movsxd  rdx, dword ptr [r9]
0x1400e7266  mov     r8, rbx
0x1400e7269  cmp     [rbp+60h+arg_30], 2
0x1400e7270  mov     r14, rbx
0x1400e7273  mov     [r13+0], r12d
0x1400e7277  lea     r13, [rcx-5]
0x1400e727b  mov     [rsp+160h+var_128], rbx
0x1400e7280  lea     r9, [rbx+rdx]
0x1400e7284  mov     [rbp+60h+var_D0], rbx
0x1400e7288  mov     rbx, r15
0x1400e728b  mov     [rbp+60h+var_80], r9
0x1400e728f  cmovnz  r13, rcx
0x1400e7293  mov     [rsp+160h+var_F0], rbx
0x1400e7298  mov     [rsp+160h+var_100], rbx
0x1400e729d  mov     [rsp+160h+var_F8], r13
0x1400e72a2  cmp     edx, 0Dh
0x1400e72a5  jl      loc_1400E9253
0x1400e72ab  lea     rax, [r9-0Ch]
0x1400e72af  mov     [rbp+60h+var_98], rax
0x1400e72b3  cmp     [rbp+60h+arg_8], rax
0x1400e72b7  ja      loc_1400E9253
0x1400e72bd  lea     rax, [r9-5]
0x1400e72c1  mov     [rsp+160h+var_108], r12
0x1400e72c6  mov     qword ptr [rsp+160h+var_120], rax
0x1400e72cb  mov     [rbp+60h+var_B8], r12
0x1400e72cf  mov     rdx, [rbp+60h+arg_0]
0x1400e72d3  mov     edi, 3
0x1400e72d8  mov     [rbp+60h+arg_28], edi
0x1400e72de  mov     ecx, [rdx+4001Ch]
0x1400e72e4  mov     rsi, [rdx+40008h]
0x1400e72eb  mov     r12d, ecx
0x1400e72ee  mov     r13d, [rdx+40018h]
0x1400e72f5  mov     r15d, r13d
0x1400e72f8  mov     [rbp+60h+var_D8], rsi
0x1400e72fc  sub     r15d, esi
0x1400e72ff  mov     dword ptr [rbp+60h+var_A0], ecx
0x1400e7302  add     r15d, r8d
0x1400e7305  lea     eax, [rcx+10000h]
0x1400e730b  mov     dword ptr [rsp+160h+var_110], r15d
0x1400e7310  cmp     eax, r15d
0x1400e7313  ja      short loc_1400E731C
0x1400e7315  lea     r12d, [r15-0FFFFh]
0x1400e731c  mov     rdx, [rdx+40010h]
0x1400e7323  mov     rax, rcx
0x1400e7326  mov     r14d, [r8]
0x1400e7329  mov     rcx, r13
0x1400e732c  sub     rcx, rax
0x1400e732f  mov     [rsp+4Ch], r12d
0x1400e7334  xor     eax, eax
0x1400e7336  mov     [rbp+60h+var_B0], rdx
0x1400e733a  add     rcx, rdx
0x1400e733d  mov     [rsp+160h+var_13C], eax
0x1400e7341  mov     r9d, eax
0x1400e7344  mov     [rbp+60h+var_88], rax
0x1400e7348  mov     [rsp+160h+var_138], eax
0x1400e734c  mov     r10d, 100h
0x1400e7352  mov     rax, [rbp+60h+arg_0]
0x1400e7356  mov     [rbp+60h+var_C0], rcx
0x1400e735a  mov     dword ptr [rbp+60h+var_E0], r10d
0x1400e735e  mov     dword ptr [rsp+160h+var_130+4], r14d
0x1400e7363  mov     r8d, [rax+40020h]
0x1400e736a  cmp     r8d, r15d
0x1400e736d  jnb     short loc_1400E73BE
0x1400e736f  mov     r9, rax
0x1400e7372  mov     r14d, 0FFFFh
0x1400e7378  mov     ecx, r8d
0x1400e737b  mov     eax, r8d
0x1400e737e  sub     rax, r13
0x1400e7381  imul    edx, [rax+rsi], 9E3779B1h
0x1400e7388  movzx   eax, r8w
0x1400e738c  shr     rdx, 11h
0x1400e7390  sub     ecx, [r9+rdx*4]
0x1400e7394  cmp     rcx, r14
0x1400e7397  cmova   rcx, r14
0x1400e739b  mov     [r9+rax*2+20000h], cx
0x1400e73a4  mov     [r9+rdx*4], r8d
0x1400e73a8  inc     r8d
0x1400e73ab  cmp     r8d, r15d
0x1400e73ae  jb      short loc_1400E7378
0x1400e73b0  mov     r14d, dword ptr [rsp+160h+var_130+4]
0x1400e73b5  mov     r9d, [rsp+160h+var_13C]
0x1400e73ba  mov     rdx, [rbp+60h+var_B0]
0x1400e73be  mov     r11, [rbp+60h+arg_0]
0x1400e73c2  mov     r8, [rsp+160h+var_128]
0x1400e73c7  mov     [r11+40020h], r15d
0x1400e73ce  imul    ecx, [r8], 9E3779B1h
0x1400e73d5  shr     rcx, 11h
0x1400e73d9  mov     r11d, [r11+rcx*4]
0x1400e73dd  cmp     r11d, r12d
0x1400e73e0  jb      loc_1400E795A
0x1400e73e6  mov     ebx, dword ptr [rbp+60h+var_A0]
0x1400e73e9  test    r10d, r10d
0x1400e73ec  jle     loc_1400E7955
0x1400e73f2  cmp     r11d, r13d
0x1400e73f5  jb      loc_1400E74F8
0x1400e73fb  mov     r10, [rsp+160h+var_128]
0x1400e7400  mov     eax, r11d
0x1400e7403  sub     eax, r13d
0x1400e7406  movsxd  rdx, edi
0x1400e7409  mov     r8d, eax
0x1400e740c  add     rax, rdx
0x1400e740f  movzx   ecx, word ptr [rax+rsi-1]
0x1400e7414  cmp     [rdx+r10-1], cx
0x1400e741a  jnz     loc_1400E76C0
0x1400e7420  cmp     [r8+rsi], r14d
0x1400e7424  jnz     loc_1400E76C0
0x1400e742a  lea     r9, [r10+4]
0x1400e742e  mov     r10, qword ptr [rsp+160h+var_120]
0x1400e7433  lea     rdx, [rsi+4]
0x1400e7437  mov     [rbp+60h+var_A8], r9
0x1400e743b  add     r10, 0FFFFFFFFFFFFFFF9h
0x1400e743f  add     rdx, r8
0x1400e7442  cmp     r9, r10
0x1400e7445  jnb     short loc_1400E745F
0x1400e7447  mov     rcx, [r9]
0x1400e744a  xor     rcx, [rdx]
0x1400e744d  jnz     short loc_1400E7455
0x1400e744f  lea     rcx, [r9+8]
0x1400e7453  jmp     short loc_1400E7473
0x1400e7455  tzcnt   rcx, rcx
0x1400e745a  shr     ecx, 3
0x1400e745d  jmp     short loc_1400E74CE
0x1400e745f  mov     rcx, r9
0x1400e7462  cmp     rcx, r10
0x1400e7465  jnb     short loc_1400E7488
0x1400e7467  mov     r8, [rcx]
0x1400e746a  xor     r8, [rdx]
0x1400e746d  jnz     short loc_1400E7479
0x1400e746f  add     rcx, 8
0x1400e7473  add     rdx, 8
0x1400e7477  jmp     short loc_1400E7462
0x1400e7479  tzcnt   rax, r8
0x1400e747e  shr     eax, 3
0x1400e7481  sub     eax, r9d
0x1400e7484  add     ecx, eax
0x1400e7486  jmp     short loc_1400E74CE
0x1400e7488  mov     r8, qword ptr [rsp+160h+var_120]
0x1400e748d  lea     rax, [r8-3]
0x1400e7491  cmp     rcx, rax
0x1400e7494  jnb     short loc_1400E74A4
0x1400e7496  mov     eax, [rcx]
0x1400e7498  cmp     [rdx], eax
0x1400e749a  jnz     short loc_1400E74A4
0x1400e749c  add     rcx, 4
0x1400e74a0  add     rdx, 4
0x1400e74a4  lea     rax, [r8-1]
0x1400e74a8  cmp     rcx, rax
0x1400e74ab  jnb     short loc_1400E74BD
0x1400e74ad  movzx   eax, word ptr [rcx]
0x1400e74b0  cmp     [rdx], ax
0x1400e74b3  jnz     short loc_1400E74BD
0x1400e74b5  add     rcx, 2
0x1400e74b9  add     rdx, 2
0x1400e74bd  cmp     rcx, r8
0x1400e74c0  jnb     short loc_1400E74CB
0x1400e74c2  mov     al, [rcx]
0x1400e74c4  cmp     [rdx], al
0x1400e74c6  jnz     short loc_1400E74CB
0x1400e74c8  inc     rcx
0x1400e74cb  sub     ecx, r9d
0x1400e74ce  mov     r9d, [rsp+160h+var_13C]
0x1400e74d3  add     ecx, 4
0x1400e74d6  mov     r10, [rsp+160h+var_128]
0x1400e74db  cmp     ecx, edi
0x1400e74dd  jle     loc_1400E76C0
0x1400e74e3  mov     [rbp+60h+arg_28], ecx
0x1400e74e9  mov     ecx, r15d
0x1400e74ec  sub     ecx, r11d
0x1400e74ef  mov     [rsp+160h+var_138], ecx
0x1400e74f3  jmp     loc_1400E76C0
0x1400e74f8  lea     eax, [r13-4]
0x1400e74fc  cmp     r11d, eax
0x1400e74ff  ja      loc_1400E76BB
0x1400e7505  mov     eax, r11d
0x1400e7508  sub     eax, ebx
0x1400e750a  mov     ecx, eax
0x1400e750c  cmp     [rax+rdx], r14d
0x1400e7510  jnz     loc_1400E76BB
0x1400e7516  mov     r9d, r13d
0x1400e7519  lea     r10, [r8+4]
0x1400e751d  sub     r9d, r11d
0x1400e7520  mov     [rbp+60h+var_A8], r10
0x1400e7524  add     r9, r8
0x1400e7527  cmp     r9, qword ptr [rsp+160h+var_120]
0x1400e752c  cmova   r9, qword ptr [rsp+160h+var_120]
0x1400e7532  add     rdx, 4
0x1400e7536  add     rdx, rcx
0x1400e7539  lea     rdi, [r9-7]
0x1400e753d  cmp     r10, rdi
0x1400e7540  jnb     short loc_1400E755B
0x1400e7542  mov     rcx, [rdx]
0x1400e7545  xor     rcx, [r10]
0x1400e7548  jnz     short loc_1400E7550
0x1400e754a  lea     rcx, [r10+8]
0x1400e754e  jmp     short loc_1400E756F
0x1400e7550  tzcnt   r10, rcx
0x1400e7555  shr     r10d, 3
0x1400e7559  jmp     short loc_1400E75CF
0x1400e755b  mov     rcx, r10
0x1400e755e  cmp     rcx, rdi
0x1400e7561  jnb     short loc_1400E7586
0x1400e7563  mov     r8, [rdx]
0x1400e7566  xor     r8, [rcx]
0x1400e7569  jnz     short loc_1400E7575
0x1400e756b  add     rcx, 8
0x1400e756f  add     rdx, 8
0x1400e7573  jmp     short loc_1400E755E
0x1400e7575  tzcnt   rax, r8
0x1400e757a  shr     eax, 3
0x1400e757d  sub     eax, r10d
0x1400e7580  lea     r10d, [rcx+rax]
0x1400e7584  jmp     short loc_1400E75CA
0x1400e7586  lea     rax, [r9-3]
0x1400e758a  cmp     rcx, rax
0x1400e758d  jnb     short loc_1400E759D
0x1400e758f  mov     eax, [rcx]
0x1400e7591  cmp     [rdx], eax
0x1400e7593  jnz     short loc_1400E759D
0x1400e7595  add     rcx, 4
0x1400e7599  add     rdx, 4
0x1400e759d  lea     rax, [r9-1]
0x1400e75a1  cmp     rcx, rax
0x1400e75a4  jnb     short loc_1400E75B6
0x1400e75a6  movzx   eax, word ptr [rcx]
0x1400e75a9  cmp     [rdx], ax
0x1400e75ac  jnz     short loc_1400E75B6
0x1400e75ae  add     rcx, 2
0x1400e75b2  add     rdx, 2
0x1400e75b6  cmp     rcx, r9
0x1400e75b9  jnb     short loc_1400E75C4
0x1400e75bb  mov     al, [rcx]
0x1400e75bd  cmp     [rdx], al
0x1400e75bf  jnz     short loc_1400E75C4
0x1400e75c1  inc     rcx
0x1400e75c4  sub     ecx, r10d
0x1400e75c7  mov     r10d, ecx
0x1400e75ca  mov     r8, [rsp+160h+var_128]
0x1400e75cf  add     r8, 4
0x1400e75d3  movsxd  rax, r10d
0x1400e75d6  add     r8, rax
0x1400e75d9  lea     ecx, [r10+4]
0x1400e75dd  cmp     r8, r9
0x1400e75e0  jnz     loc_1400E7697
0x1400e75e6  cmp     r9, qword ptr [rsp+160h+var_120]
0x1400e75eb  jnb     loc_1400E7697
0x1400e75f1  mov     rdi, qword ptr [rsp+160h+var_120]
0x1400e75f6  add     rdi, 0FFFFFFFFFFFFFFF9h
0x1400e75fa  mov     [rbp+60h+var_A8], r8
0x1400e75fe  cmp     r8, rdi
0x1400e7601  jnb     short loc_1400E761F
0x1400e7603  mov     rcx, [rsi]
0x1400e7606  xor     rcx, [r8]
0x1400e7609  jnz     short loc_1400E7615
0x1400e760b  lea     rcx, [r8+8]
0x1400e760f  lea     rdx, [rsi+8]
0x1400e7613  jmp     short loc_1400E7625
0x1400e7615  tzcnt   rcx, rcx
0x1400e761a  shr     ecx, 3
0x1400e761d  jmp     short loc_1400E7691
0x1400e761f  mov     rdx, rsi
  ... truncated ...
```
