# outputMBRow

- ea: `0x180014bb0`
- end: `0x1800173c0`
- name: `outputMBRow`
- size: `10256`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180025e70`
- `0x1800304a0`
- `0x180040680`
- `0x180040b90`

## callees

- `0x180014bb0`
- `0x1800173c8`
- `0x180017430`
- `0x18002f3f0`
- `0x18003e850`

## pseudocode

```c
__int64 __fastcall outputMBRow(__int64 a1)
{
  int v2; // r14d
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rbx
  int v6; // edi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rsi
  __int64 v9; // rdx
  _QWORD *v10; // r9
  __int64 v11; // r10
  __int64 v12; // r11
  __int64 v13; // r11
  unsigned __int64 v14; // rsi
  __int64 v15; // rbx
  char v16; // r8
  char v17; // dl
  int v18; // eax
  __int64 v19; // r12
  __int64 v20; // r13
  __int64 v21; // rcx
  int v22; // r10d
  int v23; // eax
  int v25; // edx
  int v26; // ecx
  int v27; // r9d
  int v28; // r10d
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rbp
  bool v32; // zf
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r8
  unsigned __int64 v35; // r10
  __int64 v36; // r14
  char *v37; // rcx
  unsigned __int64 v38; // rdx
  int v39; // r9d
  int v40; // ebx
  int v41; // r11d
  __int64 v42; // r8
  int v43; // r11d
  int v44; // edx
  int v45; // ebx
  __int64 v46; // rcx
  int v47; // r9d
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rbp
  char *v51; // rcx
  unsigned __int64 v52; // rdx
  int v53; // r8d
  int v54; // r11d
  int v55; // r8d
  int v56; // r10d
  __int64 v57; // rax
  int v58; // r9d
  __int64 v59; // r8
  __int64 v60; // rbx
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // rcx
  __int64 v63; // rdx
  unsigned __int64 v64; // r8
  __int64 v65; // r10
  unsigned __int64 v66; // r14
  char *v67; // rcx
  unsigned __int64 v68; // rdx
  int v69; // r9d
  int v70; // ebp
  int v71; // r8d
  __int64 v72; // rdx
  int v73; // ebp
  int v74; // r8d
  int v75; // ebp
  int v76; // eax
  int v77; // r8d
  int v78; // eax
  int v79; // r9d
  unsigned __int64 v80; // r8
  int v81; // edx
  unsigned int v82; // edx
  unsigned int v83; // eax
  int v84; // r9d
  int v85; // edx
  int v86; // r8d
  int v87; // r9d
  int v88; // ecx
  int v89; // eax
  unsigned int v90; // edx
  unsigned int v91; // eax
  int v92; // ecx
  int v93; // edx
  int v94; // r8d
  int v95; // ecx
  int v96; // edx
  int v97; // eax
  unsigned int v98; // edx
  unsigned int v99; // eax
  int v100; // ecx
  int v101; // edx
  int v102; // r8d
  int v103; // ecx
  int v104; // edx
  int v105; // eax
  int v106; // eax
  char *v107; // r8
  unsigned __int64 v108; // r9
  char v109; // cl
  unsigned __int64 v110; // r10
  unsigned __int64 v111; // r8
  int v112; // r8d
  int v113; // ebp
  unsigned __int8 v114; // cl
  unsigned int v115; // eax
  unsigned __int8 v116; // r9
  unsigned __int64 v117; // rcx
  __int64 v118; // rbp
  unsigned __int64 v119; // rax
  __int64 v120; // rdx
  unsigned __int64 v121; // r10
  __int64 v122; // r14
  unsigned __int64 v123; // r8
  char *v124; // rcx
  unsigned __int64 v125; // rdx
  int v126; // r8d
  int v127; // r10d
  int v128; // ecx
  int v129; // ebp
  int v130; // edx
  int v131; // r8d
  int v132; // ebp
  int v133; // r9d
  int v134; // r8d
  int v135; // r9d
  __int64 v136; // r10
  __int64 v137; // r14
  unsigned __int64 v138; // rcx
  unsigned __int64 v139; // r8
  unsigned __int64 v140; // rdx
  char *v141; // rcx
  unsigned __int64 v142; // r8
  int v143; // edx
  int v144; // edi
  int v145; // r14d
  int v146; // r8d
  int v147; // r9d
  unsigned __int64 v148; // rdx
  __int64 v149; // rcx
  __int64 v150; // rcx
  unsigned __int64 v151; // rdx
  unsigned __int64 v152; // r8
  unsigned __int64 v153; // rcx
  char *v154; // rdx
  unsigned __int64 v155; // r9
  int v156; // r8d
  int v157; // eax
  int v158; // r14d
  int v159; // r8d
  int v160; // r14d
  int v161; // edx
  __int64 v162; // r9
  int v163; // ecx
  unsigned __int64 v164; // r8
  unsigned __int64 v165; // r14
  __int64 v166; // rax
  char *v167; // rcx
  unsigned __int64 v168; // r8
  int v169; // edx
  int v170; // edi
  int v171; // r9d
  int v172; // r8d
  __int64 v173; // rdx
  __int64 v174; // rcx
  int v175; // r8d
  int v176; // r14d
  int v177; // r14d
  unsigned __int64 v178; // rcx
  unsigned __int64 v179; // rdx
  unsigned __int64 v180; // r14
  __int64 v181; // rax
  char *v182; // rcx
  unsigned __int64 v183; // rdx
  int v184; // r9d
  int v185; // edi
  int v186; // r10d
  __int64 v187; // r8
  int v188; // edi
  int v189; // edx
  int v190; // r10d
  __int64 v191; // rcx
  unsigned __int64 v192; // rdx
  unsigned __int64 v193; // r9
  __int64 v194; // rax
  char *v195; // rcx
  unsigned __int64 v196; // rdx
  int v197; // r9d
  int v198; // r14d
  int v199; // r10d
  __int64 v200; // r8
  int v201; // r14d
  int v202; // edx
  int v203; // r10d
  __int64 v204; // rcx
  unsigned __int64 v205; // rcx
  __int64 v206; // r14
  unsigned __int64 v207; // rdx
  unsigned __int64 v208; // r9
  __int64 v209; // rax
  char *v210; // rcx
  unsigned __int64 v211; // rdx
  int v212; // r8d
  int v213; // r10d
  int v214; // ecx
  int v215; // r14d
  int v216; // r9d
  int v217; // r8d
  __int64 v218; // r10
  int v219; // r9d
  int v220; // r14d
  int v221; // r8d
  int v222; // edx
  __int64 v223; // rcx
  unsigned __int64 v224; // rcx
  unsigned __int64 v225; // rdx
  unsigned __int64 v226; // r9
  char *v227; // rcx
  unsigned __int64 v228; // rdx
  int v229; // r9d
  int v230; // r8d
  int v231; // eax
  int v232; // ebp
  int v233; // edx
  int v234; // r8d
  __int64 v235; // rcx
  unsigned __int64 v236; // rcx
  unsigned __int64 v237; // rdx
  unsigned __int64 v238; // r14
  char *v239; // rbp
  unsigned __int64 v240; // rdx
  int v241; // r10d
  __int64 v242; // rcx
  int v243; // r9d
  __int64 v244; // r8
  int v245; // r14d
  int v246; // r10d
  int v247; // r10d
  int v248; // r10d
  unsigned __int64 v249; // rcx
  unsigned __int64 v250; // rdx
  unsigned __int64 v251; // r9
  char *v252; // rcx
  unsigned __int64 v253; // rdx
  int v254; // r9d
  int v255; // r14d
  int v256; // r8d
  int v257; // r14d
  int v258; // edx
  int v259; // r8d
  __int64 v260; // rcx
  unsigned __int64 v261; // rdx
  unsigned __int64 v262; // r8
  unsigned __int64 v263; // rcx
  __int64 v264; // rax
  char *v265; // rdx
  unsigned __int64 v266; // rdx
  int v267; // r9d
  int v268; // r14d
  int v269; // r14d
  int v270; // r8d
  int v271; // edx
  __int64 v272; // r9
  unsigned __int64 v273; // r14
  unsigned __int64 v274; // rax
  __int64 v275; // rcx
  unsigned __int64 v276; // rdx
  __int64 v277; // r11
  unsigned __int64 v278; // r8
  int v279; // edx
  __int64 v280; // rbx
  __int16 v281; // ax
  __int16 v282; // cx
  int v283; // r10d
  int v284; // r10d
  unsigned __int64 v285; // r8
  unsigned __int64 v286; // rdx
  char v287; // r10
  unsigned __int64 v288; // rcx
  char *v289; // rdx
  unsigned __int64 v290; // rdx
  int v291; // r9d
  int v292; // r14d
  int v293; // r8d
  int v294; // r14d
  int v295; // edx
  int v296; // r8d
  __int64 v297; // r9
  __int64 v298; // rax
  unsigned __int64 v299; // rdx
  char v300; // r10
  unsigned __int64 v301; // rcx
  char *v302; // rdx
  unsigned __int64 v303; // rdx
  int v304; // r9d
  int v305; // r14d
  int v306; // r14d
  int v307; // r8d
  int v308; // edx
  __int64 v309; // r9
  __int64 v310; // rax
  unsigned __int64 v311; // rcx
  unsigned __int64 v312; // rdx
  unsigned __int64 v313; // r8
  __int64 v314; // rax
  char *v315; // r9
  __int64 v316; // rbx
  __int64 v317; // rbx
  int v318; // edx
  int v319; // ecx
  __int16 v320; // ax
  int v321; // ebp
  int v322; // ebp
  unsigned __int64 v323; // rcx
  unsigned __int64 v324; // rdx
  unsigned __int64 v325; // r14
  __int64 v326; // rax
  char *v327; // rcx
  unsigned __int64 v328; // rdx
  int v329; // r9d
  int v330; // ebp
  int v331; // r8d
  int v332; // ebp
  int v333; // r8d
  int v334; // edx
  __int64 v335; // rcx
  int v336; // edx
  unsigned __int64 v337; // rcx
  unsigned __int64 v338; // rdx
  unsigned __int64 v339; // r14
  char *v340; // rcx
  unsigned __int64 v341; // rdx
  int v342; // r9d
  int v343; // r8d
  int v344; // r8d
  int v345; // edx
  int v346; // r9d
  int v347; // r8d
  int v348; // r9d
  unsigned __int64 v349; // rcx
  unsigned __int64 v350; // rdx
  unsigned __int64 v351; // r8
  __int64 v352; // r14
  char *v353; // r9
  __int64 v354; // r11
  int v355; // edx
  int v356; // eax
  int v357; // ecx
  int v358; // r11d
  __int64 v359; // r14
  unsigned __int64 j; // rcx
  unsigned __int64 v361; // rdi
  __int64 v362; // rbp
  unsigned __int64 v363; // r10
  unsigned __int64 v364; // rdx
  unsigned __int64 i; // rdx
  unsigned __int64 v366; // rbx
  unsigned __int64 v367; // rcx
  char v368; // r14
  char *v369; // rdi
  __int64 v370; // r9
  unsigned __int64 v371; // r10
  char v372; // dl
  unsigned __int64 v373; // [rsp+40h] [rbp-A8h]
  unsigned __int64 v374; // [rsp+48h] [rbp-A0h]
  unsigned __int64 v375; // [rsp+50h] [rbp-98h]
  __int64 v376; // [rsp+58h] [rbp-90h]
  char *v377; // [rsp+60h] [rbp-88h]
  unsigned __int64 v378; // [rsp+60h] [rbp-88h]
  char *v379; // [rsp+60h] [rbp-88h]
  char *v380; // [rsp+60h] [rbp-88h]
  __int64 v381; // [rsp+60h] [rbp-88h]
  char *v382; // [rsp+60h] [rbp-88h]
  __int64 v383; // [rsp+60h] [rbp-88h]
  __int64 v384; // [rsp+68h] [rbp-80h]
  int v385; // [rsp+68h] [rbp-80h]
  char *v386; // [rsp+68h] [rbp-80h]
  char *v387; // [rsp+68h] [rbp-80h]
  int v388; // [rsp+70h] [rbp-78h]
  int v389; // [rsp+70h] [rbp-78h]
  unsigned int *v390; // [rsp+78h] [rbp-70h]
  __int64 v391; // [rsp+78h] [rbp-70h]
  __int64 v392; // [rsp+80h] [rbp-68h]
  int v393; // [rsp+80h] [rbp-68h]
  __int64 v394; // [rsp+88h] [rbp-60h]
  char *v395; // [rsp+90h] [rbp-58h]
  char v396; // [rsp+F0h] [rbp+8h]
  int v397; // [rsp+F0h] [rbp+8h]
  int v398; // [rsp+F0h] [rbp+8h]
  __int64 v399; // [rsp+F0h] [rbp+8h]
  int v400; // [rsp+F0h] [rbp+8h]
  unsigned __int64 v401; // [rsp+F0h] [rbp+8h]
  char v402; // [rsp+F0h] [rbp+8h]
  char v403; // [rsp+F0h] [rbp+8h]
  unsigned __int64 v404; // [rsp+F0h] [rbp+8h]
  unsigned __int64 v405; // [rsp+F0h] [rbp+8h]
  int v406; // [rsp+F0h] [rbp+8h]
  __int64 v407; // [rsp+F0h] [rbp+8h]
  int v408; // [rsp+F0h] [rbp+8h]
  __int64 v409; // [rsp+F0h] [rbp+8h]
  char v410; // [rsp+F8h] [rbp+10h]
  int v411; // [rsp+F8h] [rbp+10h]
  __int64 v412; // [rsp+F8h] [rbp+10h]
  __int64 v413; // [rsp+F8h] [rbp+10h]
  __int64 v414; // [rsp+F8h] [rbp+10h]
  char v415; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v416; // [rsp+F8h] [rbp+10h]
  int v417; // [rsp+F8h] [rbp+10h]
  char v418; // [rsp+F8h] [rbp+10h]
  __int64 v419; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v420; // [rsp+F8h] [rbp+10h]
  unsigned __int64 v421; // [rsp+F8h] [rbp+10h]
  __int64 v422; // [rsp+F8h] [rbp+10h]
  __int64 v423; // [rsp+F8h] [rbp+10h]
  int v424; // [rsp+100h] [rbp+18h]
  __int64 v425; // [rsp+100h] [rbp+18h]
  char *v426; // [rsp+100h] [rbp+18h]
  unsigned __int64 v427; // [rsp+100h] [rbp+18h]
  unsigned __int64 v428; // [rsp+100h] [rbp+18h]
  __int64 v429; // [rsp+100h] [rbp+18h]
  unsigned __int64 v430; // [rsp+100h] [rbp+18h]
  char *v431; // [rsp+100h] [rbp+18h]
  int v432; // [rsp+100h] [rbp+18h]
  unsigned __int64 v433; // [rsp+100h] [rbp+18h]
  __int64 v434; // [rsp+100h] [rbp+18h]
  __int64 v435; // [rsp+100h] [rbp+18h]
  int v436; // [rsp+100h] [rbp+18h]
  char *v437; // [rsp+100h] [rbp+18h]
  char *v438; // [rsp+100h] [rbp+18h]
  __int64 v439; // [rsp+100h] [rbp+18h]
  __int64 v440; // [rsp+100h] [rbp+18h]
  char *v441; // [rsp+100h] [rbp+18h]
  char *v442; // [rsp+100h] [rbp+18h]
  int v443; // [rsp+108h] [rbp+20h]
  char *v444; // [rsp+108h] [rbp+20h]
  __int64 v445; // [rsp+108h] [rbp+20h]
  int v446; // [rsp+108h] [rbp+20h]
  char *v447; // [rsp+108h] [rbp+20h]
  char *v448; // [rsp+108h] [rbp+20h]
  char v449; // [rsp+108h] [rbp+20h]
  char *v450; // [rsp+108h] [rbp+20h]
  char *v451; // [rsp+108h] [rbp+20h]

  if ( *(_DWORD *)(a1 + 34216) )
    v2 = *(_DWORD *)(a1 + 24);
  else
    v2 = 0;
  v3 = 16;
  v4 = *(_QWORD *)(a1 + 34344);
  v5 = 34864;
  v424 = *(_DWORD *)(a1 + 34224);
  v6 = v424 != 0 ? 3 : 0;
  v7 = 16LL * *(_QWORD *)(a1 + 34528) - 16;
  if ( *(_QWORD *)(v4 + 56) - v7 + 1 < 0x10 )
    v3 = *(_QWORD *)(v4 + 56) - v7 + 1;
  v374 = v3;
  v8 = 0;
  if ( v7 <= *(_QWORD *)(v4 + 48) )
    v8 = *(_DWORD *)(v4 + 48) & 0xF;
  v373 = v8;
  if ( *(_DWORD *)(a1 + 34356) )
    v5 = 35368;
  if ( v2 == 5 )
    v443 = (*(_BYTE *)(a1 + 60) & 2) - (*(_BYTE *)(a1 + 60) & 1) + 1;
  else
    v443 = *(_DWORD *)(a1 + 48) != 0 ? 2 : 0;
  v9 = 72;
  if ( *(int *)(a1 + 124) >= 4 )
    v9 = 88;
  if ( (unsigned int)checkImageBuffer(a1, *(_QWORD *)(v9 + a1), v3 - v8) )
    return 0xFFFFFFFFLL;
  v13 = *(_QWORD *)(v12 + a1);
  v14 = v10[5] + 1LL;
  v15 = *(_QWORD *)(v5 + a1);
  v16 = *(_BYTE *)(a1 + 32992);
  v17 = *(_BYTE *)(a1 + 32993);
  v18 = *(_DWORD *)(a1 + 28);
  v19 = *(_QWORD *)(a1 + 34848);
  v20 = v10[8];
  v375 = v10[4];
  v388 = v18;
  v384 = v13;
  v21 = v10[9] + v11 * (*(_QWORD *)(a1 + 34528) - 1LL);
  v392 = v15;
  v410 = v16;
  v396 = v17;
  v376 = v21;
  if ( *(_DWORD *)(a1 + 34356) )
  {
    interpolateUV(a1);
    v13 = v384;
    v18 = v388;
    v16 = v410;
    v17 = v396;
    v21 = v376;
  }
  switch ( v18 )
  {
    case 1:
      v25 = v424;
      v26 = *(_DWORD *)(a1 + 34224);
      v27 = 1024;
      if ( !v424 )
        v27 = 128;
      v397 = v27;
      v411 = *(_DWORD *)(a1 + 34224) != 0 ? 3 : 0;
      v28 = v411 + v27;
      if ( v2 == 7 )
      {
        v29 = v443;
        v30 = *(_QWORD *)(a1 + 35664);
        v31 = 2LL - v443;
        if ( v30 && *(_BYTE *)(a1 + 184) )
        {
          v137 = *(_QWORD *)(v30 + 34848);
          v413 = v137;
          if ( v26 )
          {
            v151 = v373;
            if ( v373 < v374 )
            {
              v152 = v375;
              do
              {
                v153 = v152;
                v430 = v152;
                v381 = *(_QWORD *)(v376 + 8 * v151);
                if ( v152 < v14 )
                {
                  v154 = &idxCC[16 * v151];
                  v386 = v154;
                  do
                  {
                    v155 = 16 * (v153 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v154[v153 & 0xF];
                    v156 = *(_DWORD *)(v15 + 4 * v155);
                    v157 = *(_DWORD *)(v19 + 4 * v155) - (-*(_DWORD *)(v13 + 4 * v155) >> 1) + v28;
                    v158 = -*(_DWORD *)(v13 + 4 * v155) - ((v156 + 1) >> 1) + v157;
                    v159 = (v158 + v156) >> v6;
                    v160 = v158 >> v6;
                    v161 = (v28 + *(_DWORD *)(v413 + 4 * v155)) >> v6;
                    v162 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v430) + v381;
                    v391 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v430);
                    v163 = v157 >> v6;
                    if ( ((v161 | (v157 >> v6) | v159 | v160) & 0xFFFFFF00) != 0 )
                    {
                      if ( v160 >= 0 )
                      {
                        if ( v160 > 255 )
                          LOBYTE(v160) = -1;
                      }
                      else
                      {
                        LOBYTE(v160) = 0;
                      }
                      *(_BYTE *)(v162 + v31) = v160;
                      if ( v163 >= 0 )
                      {
                        if ( v163 > 255 )
                          LOBYTE(v163) = -1;
                      }
                      else
                      {
                        LOBYTE(v163) = 0;
                      }
                      *(_BYTE *)(v162 + 1) = v163;
                      if ( v159 >= 0 )
                      {
                        if ( v159 > 255 )
                          LOBYTE(v159) = -1;
                      }
                      else
                      {
                        LOBYTE(v159) = 0;
                      }
                      *(_BYTE *)(v162 + v443) = v159;
                      if ( v161 >= 0 )
                      {
                        if ( v161 > 255 )
                          LOBYTE(v161) = -1;
                      }
                      else
                      {
                        LOBYTE(v161) = 0;
                      }
                    }
                    else
                    {
                      *(_BYTE *)(v162 + v31) = v160;
                      *(_BYTE *)(v162 + 1) = v163;
                      *(_BYTE *)(v162 + v443) = v159;
                    }
                    *(_BYTE *)(v381 + v391 + 3) = v161;
                    v154 = v386;
                    v153 = v430 + 1;
                    v430 = v153;
                  }
                  while ( v153 < v14 );
                  v151 = v373;
                  v152 = v375;
                }
                v373 = ++v151;
              }
              while ( v151 < v374 );
            }
          }
          else
          {
            v138 = v373;
            if ( v373 < v374 )
            {
              v139 = v375;
              do
              {
                v140 = v139;
                v428 = v139;
                v399 = *(_QWORD *)(v376 + 8 * v138);
                if ( v139 < v14 )
                {
                  v141 = &idxCC[16 * v138];
                  v380 = v141;
                  do
                  {
                    v142 = 16 * (v140 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v141[v140 & 0xF];
                    v143 = *(_DWORD *)(v15 + 4 * v142);
                    v144 = v28 + *(_DWORD *)(v137 + 4 * v142);
                    v145 = v28 + *(_DWORD *)(v19 + 4 * v142) - (-*(_DWORD *)(v13 + 4 * v142) >> 1);
                    v146 = -*(_DWORD *)(v13 + 4 * v142) - ((v143 + 1) >> 1) + v145;
                    v147 = v143 + v146;
                    v148 = v428;
                    v429 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v428);
                    v149 = v399 + v429;
                    if ( ((v144 | v145 | v146 | v147) & 0xFFFFFF00) != 0 )
                    {
                      if ( v146 >= 0 )
                      {
                        if ( v146 > 255 )
                          LOBYTE(v146) = -1;
                      }
                      else
                      {
                        LOBYTE(v146) = 0;
                      }
                      *(_BYTE *)(v149 + v31) = v146;
                      if ( v145 >= 0 )
                      {
                        if ( v145 > 255 )
                          LOBYTE(v145) = -1;
                      }
                      else
                      {
                        LOBYTE(v145) = 0;
                      }
                      *(_BYTE *)(v149 + 1) = v145;
                      if ( v147 >= 0 )
                      {
                        if ( v147 > 255 )
                          LOBYTE(v147) = -1;
                      }
                      else
                      {
                        LOBYTE(v147) = 0;
                      }
                      *(_BYTE *)(v149 + v443) = v147;
                      if ( v144 >= 0 )
                      {
                        if ( v144 > 255 )
                          LOBYTE(v144) = -1;
                      }
                      else
                      {
                        LOBYTE(v144) = 0;
                      }
                    }
                    else
                    {
                      *(_BYTE *)(v149 + v31) = v146;
                      *(_BYTE *)(v149 + 1) = v145;
                      *(_BYTE *)(v149 + v443) = v147;
                    }
                    v150 = v429;
                    v140 = v148 + 1;
                    v137 = v413;
                    v428 = v140;
                    *(_BYTE *)(v150 + v399 + 3) = v144;
                    v141 = v380;
                  }
                  while ( v140 < v14 );
                  v138 = v373;
                  v139 = v375;
                }
                v373 = ++v138;
              }
              while ( v138 < v374 );
            }
          }
        }
        else
        {
          v32 = v26 == 0;
          v33 = v373;
          if ( v32 )
          {
            if ( v373 < v374 )
            {
              v164 = v375;
              do
              {
                v165 = v164;
                v166 = *(_QWORD *)(v376 + 8 * v33);
                if ( v164 < v14 )
                {
                  v167 = &idxCC[16 * v33];
                  v431 = v167;
                  v414 = v29 + v166;
                  do
                  {
                    v168 = 16 * (v165 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v167[v165 & 0xF];
                    v169 = *(_DWORD *)(v15 + 4 * v168);
                    v170 = v28 + *(_DWORD *)(v19 + 4 * v168) - (-*(_DWORD *)(v13 + 4 * v168) >> 1);
                    v171 = v170 + -*(_DWORD *)(v13 + 4 * v168) - ((v169 + 1) >> 1);
                    v172 = v169 + v171;
                    v173 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v165);
                    v174 = v173 + v166;
                    if ( ((v170 | v171 | v172) & 0xFFFFFF00) != 0 )
                    {
                      if ( v171 >= 0 )
                      {
                        if ( v171 > 255 )
                          LOBYTE(v171) = -1;
                      }
                      else
                      {
                        LOBYTE(v171) = 0;
                      }
                      *(_BYTE *)(v174 + v31) = v171;
                      if ( v170 >= 0 )
                      {
                        if ( v170 > 255 )
                          LOBYTE(v170) = -1;
                      }
                      else
                      {
                        LOBYTE(v170) = 0;
                      }
                      *(_BYTE *)(v174 + 1) = v170;
                      if ( v172 >= 0 )
                      {
                        if ( v172 > 255 )
                          LOBYTE(v172) = -1;
                      }
                      else
                      {
                        LOBYTE(v172) = 0;
                      }
                    }
                    else
                    {
                      *(_BYTE *)(v174 + v31) = v171;
                      *(_BYTE *)(v174 + 1) = v170;
                    }
                    ++v165;
                    v167 = v431;
                    *(_BYTE *)(v414 + v173) = v172;
                  }
                  while ( v165 < v14 );
                  v33 = v373;
                  v29 = v443;
                  v164 = v375;
                }
                v373 = ++v33;
              }
              while ( v33 < v374 );
            }
          }
          else if ( v373 < v374 )
          {
            v34 = v375;
            do
            {
              v35 = v34;
              v425 = *(_QWORD *)(v376 + 8 * v33);
              if ( v34 < v14 )
              {
                v36 = *(_QWORD *)(v376 + 8 * v33) + v29;
                v37 = &idxCC[16 * v33];
                v377 = v37;
                do
                {
                  v38 = 16 * (v35 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v37[v35 & 0xF];
                  v39 = *(_DWORD *)(v15 + 4 * v38);
                  v40 = v397 + v411 + *(_DWORD *)(v19 + 4 * v38) - (-*(_DWORD *)(v13 + 4 * v38) >> 1);
                  v41 = -*(_DWORD *)(v13 + 4 * v38) - ((v39 + 1) >> 1) + v40;
                  v42 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v35);
                  LODWORD(v38) = v39 + v41;
                  v43 = v41 >> v6;
                  v44 = (int)v38 >> v6;
                  v45 = v40 >> v6;
                  v46 = v42 + v425;
                  if ( ((v45 | v44 | v43) & 0xFFFFFF00) != 0 )
                  {
                    if ( v43 < 0 )
                    {
                      LOBYTE(v43) = 0;
                    }
                    else if ( v43 > 255 )
                    {
                      LOBYTE(v43) = -1;
                    }
                    *(_BYTE *)(v46 + v31) = v43;
                    if ( v45 < 0 )
                    {
                      LOBYTE(v45) = 0;
                    }
                    else if ( v45 > 255 )
                    {
                      LOBYTE(v45) = -1;
                    }
                    *(_BYTE *)(v46 + 1) = v45;
                    if ( v44 < 0 )
                    {
                      LOBYTE(v44) = 0;
                    }
                    else if ( v44 > 255 )
                    {
                      LOBYTE(v44) = -1;
                    }
                  }
                  else
                  {
                    *(_BYTE *)(v46 + v31) = v43;
                    *(_BYTE *)(v46 + 1) = v45;
                  }
                  v13 = v384;
                  ++v35;
                  v15 = v392;
                  v37 = v377;
                  *(_BYTE *)(v36 + v42) = v44;
                }
                while ( v35 < v14 );
                v33 = v373;
                v29 = v443;
                v34 = v375;
              }
              v373 = ++v33;
            }
            while ( v33 < v374 );
          }
        }
        break;
      }
      if ( v2 )
      {
        if ( v2 == 4 )
        {
          v117 = v373;
          v118 = *(_QWORD *)(a1 + 34872);
          v445 = v118;
          if ( v373 < v374 )
          {
            v119 = v374;
            v120 = v376;
            v121 = v375;
            do
            {
              v122 = *(_QWORD *)(v120 + 8 * v117);
              v123 = v121;
              v427 = v121;
              if ( v121 < v14 )
              {
                v124 = &idxCC[16 * v117];
                v379 = v124;
                do
                {
                  v125 = 16 * (v123 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v124[v123 & 0xF];
                  v126 = v27 - *(_DWORD *)(v19 + 4 * v125);
                  v127 = *(_DWORD *)(v15 + 4 * v125);
                  v128 = *(_DWORD *)(v13 + 4 * v125);
                  LODWORD(v125) = v411 + *(_DWORD *)(v118 + 4 * v125) - ((v126 + 1) >> 1);
                  v129 = v126 + v125 - (v128 >> 1);
                  v130 = (int)v125 >> v6;
                  v131 = v128 - ((1 - v127) >> 1) + v129;
                  v132 = v129 >> v6;
                  v133 = v131;
                  v134 = (v131 - v127) >> v6;
                  v135 = v133 >> v6;
                  v136 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v427);
                  if ( ((v135 | v132 | v130 | v134) & 0xFFFFFF00) != 0 )
                  {
                    if ( v135 >= 0 )
                    {
                      if ( v135 > 255 )
                        LOBYTE(v135) = -1;
                    }
                    else
                    {
                      LOBYTE(v135) = 0;
                    }
                    *(_BYTE *)(v136 + v122) = v135;
                    if ( v132 >= 0 )
                    {
                      if ( v132 > 255 )
                        LOBYTE(v132) = -1;
                    }
                    else
                    {
                      LOBYTE(v132) = 0;
                    }
                    *(_BYTE *)(v136 + v122 + 1) = v132;
                    if ( v134 >= 0 )
                    {
                      if ( v134 > 255 )
                        LOBYTE(v134) = -1;
                    }
                    else
                    {
                      LOBYTE(v134) = 0;
                    }
                    *(_BYTE *)(v136 + v122 + 2) = v134;
                    if ( v130 >= 0 )
                    {
                      if ( v130 > 255 )
                        LOBYTE(v130) = -1;
                    }
                    else
                    {
                      LOBYTE(v130) = 0;
                    }
                  }
                  else
                  {
                    *(_BYTE *)(v136 + v122) = v135;
                    *(_BYTE *)(v136 + v122 + 1) = v132;
                    *(_BYTE *)(v136 + v122 + 2) = v134;
                  }
                  v27 = v397;
                  v124 = v379;
                  v123 = v427 + 1;
                  v118 = v445;
                  *(_BYTE *)(v122 + v136 + 3) = v130;
                  v427 = v123;
                }
                while ( v123 < v14 );
                v117 = v373;
                v119 = v374;
                v120 = v376;
                v121 = v375;
              }
              v373 = ++v117;
            }
            while ( v117 < v119 );
          }
          break;
        }
        if ( v2 != 6 )
        {
          if ( v2 == 8 )
          {
            v61 = v373;
            v62 = v374;
            if ( v373 < v374 )
            {
              v63 = v376;
              v64 = v375;
              do
              {
                v65 = *(_QWORD *)(v63 + 8 * v61);
                v66 = v64;
                if ( v64 < v14 )
                {
                  v67 = &idxCC[16 * v61];
                  v444 = v67;
                  do
                  {
                    v68 = 16 * (v66 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v67[v66 & 0xF];
                    v69 = *(_DWORD *)(v15 + 4 * v68);
                    v70 = *(_DWORD *)(v19 + 4 * v68);
                    v71 = -*(_DWORD *)(v13 + 4 * v68);
                    v72 = *(_QWORD *)(a1 + 33024) + *(_QWORD *)(v20 + 8 * v66);
                    v73 = v411 + v70 - (v71 >> 1);
                    v74 = v73 - ((v69 + 1) >> 1) + v71;
                    v75 = v73 >> v6;
                    v76 = v69 + v74;
                    v77 = v74 >> v6;
                    v78 = v76 >> v6;
                    if ( v77 > 0 )
                    {
                      v79 = v77 >> 7;
                      if ( v77 >> 7 <= 1 )
                        LOBYTE(v79) = 1;
                      else
                        LOBYTE(v77) = v77 | 0x80;
                    }
                    else
                    {
                      LOBYTE(v79) = 0;
                      LOBYTE(v77) = 0;
                    }
                    *(_BYTE *)(v72 + v65) = v77;
                    if ( v75 > 0 )
                    {
                      v112 = v75 >> 7;
                      if ( v75 >> 7 <= 1 )
                        LOBYTE(v112) = 1;
                      else
                        LOBYTE(v75) = v75 | 0x80;
                    }
                    else
                    {
                      LOBYTE(v112) = 0;
                      LOBYTE(v75) = 0;
                    }
                    *(_BYTE *)(v65 + v72 + 1) = v75;
                    if ( v78 > 0 )
                    {
                      v113 = v78 >> 7;
                      if ( v78 >> 7 <= 1 )
                        LOBYTE(v113) = 1;
                      else
                        LOBYTE(v78) = v78 | 0x80;
                    }
                    else
                    {
                      LOBYTE(v113) = 0;
                      LOBYTE(v78) = 0;
                    }
                    *(_BYTE *)(v65 + v72 + 2) = v78;
                    v114 = v79;
                    v115 = (unsigned __int8)v79;
                    if ( (unsigned __int8)v79 <= (unsigned __int8)v112 )
                      v115 = (unsigned __int8)v112;
                    if ( v115 <= (unsigned __int8)v113 )
                    {
                      v114 = v113;
                    }
                    else if ( (unsigned __int8)v79 <= (unsigned __int8)v112 )
                    {
                      v114 = v112;
                    }
                    *(_BYTE *)(v65 + v72 + 3) = v114;
                    if ( v114 > (unsigned __int8)v79 )
                      *(_BYTE *)(v72 + v65) = (2 * *(unsigned __int8 *)(v72 + v65) + 1) >> (v114 - v79 + 1);
                    v116 = *(_BYTE *)(v65 + v72 + 3);
                    if ( v116 > (unsigned __int8)v112 )
                      *(_BYTE *)(v65 + v72 + 1) = (2 * *(unsigned __int8 *)(v65 + v72 + 1) + 1) >> (v116 - v112 + 1);
                    if ( v116 > (unsigned __int8)v113 )
                      *(_BYTE *)(v65 + v72 + 2) = (2 * *(unsigned __int8 *)(v65 + v72 + 2) + 1) >> (v116 - v113 + 1);
                    v67 = v444;
                    ++v66;
                  }
                  while ( v66 < v14 );
                  v61 = v373;
                  v62 = v374;
                  v63 = v376;
                  v64 = v375;
                }
                v373 = ++v61;
              }
              while ( v61 < v62 );
            }
            break;
          }
          return 0xFFFFFFFFLL;
        }
      }
LABEL_179:
      v23 = outputNChannel(a1, v373, v375, v14, v374, v25 != 0 ? 3 : 0, v28);
      goto LABEL_21;
    case 2:
      v25 = v424;
      v415 = v16;
      v446 = v424 != 0 ? 4 : 0;
      v175 = 0x8000 >> v16 << v6;
      v432 = v175;
      v28 = v175 + v446;
      v400 = v175 + v446;
      if ( v2 )
      {
        v176 = v2 - 4;
        if ( !v176 )
        {
          v205 = v373;
          v206 = *(_QWORD *)(a1 + 34872);
          v383 = v206;
          if ( v373 < v374 )
          {
            v207 = v375;
            do
            {
              v208 = v207;
              v401 = v207;
              v209 = *(_QWORD *)(v376 + 8 * v205);
              if ( v207 < v14 )
              {
                v210 = &idxCC[16 * v205];
                v387 = v210;
                do
                {
                  v211 = 16 * (v208 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v210[v208 & 0xF];
                  v212 = v175 - *(_DWORD *)(v19 + 4 * v211);
                  v213 = *(_DWORD *)(v15 + 4 * v211);
                  v214 = *(_DWORD *)(v13 + 4 * v211);
                  LODWORD(v211) = v446 + *(_DWORD *)(v206 + 4 * v211) - ((v212 + 1) >> 1);
                  v215 = v212 + v211 - (v214 >> 1);
                  v216 = v214 - ((1 - v213) >> 1) + v215;
                  v217 = v216 - v213;
                  v218 = *(_QWORD *)(a1 + 33024);
                  v219 = v216 >> v6 << v415;
                  v220 = v215 >> v6 << v415;
                  v221 = v217 >> v6 << v415;
                  v222 = (int)v211 >> v6 << v415;
                  v223 = 2 * v209 + 2LL * *(_QWORD *)(v20 + 8 * v401);
                  if ( ((v221 | v219 | v220 | v222) & 0xFFFF0000) != 0 )
                  {
                    if ( v219 >= 0 )
                    {
                      if ( v219 > 0xFFFF )
                        LOWORD(v219) = -1;
                    }
                    else
                    {
                      LOWORD(v219) = 0;
                    }
                    *(_WORD *)(v223 + v218) = v219;
                    if ( v220 >= 0 )
                    {
                      if ( v220 > 0xFFFF )
                        LOWORD(v220) = -1;
                    }
                    else
                    {
                      LOWORD(v220) = 0;
                    }
                    *(_WORD *)(v223 + v218 + 2) = v220;
                    if ( v221 >= 0 )
                    {
                      if ( v221 > 0xFFFF )
                        LOWORD(v221) = -1;
                    }
                    else
                    {
                      LOWORD(v221) = 0;
                    }
                    *(_WORD *)(v223 + v218 + 4) = v221;
                    if ( v222 >= 0 )
                    {
                      if ( v222 > 0xFFFF )
                        LOWORD(v222) = -1;
                    }
                    else
                    {
                      LOWORD(v222) = 0;
                    }
                  }
                  else
                  {
                    *(_WORD *)(v223 + v218) = v219;
                    *(_WORD *)(v223 + v218 + 2) = v220;
                    *(_WORD *)(v223 + v218 + 4) = v221;
                  }
                  v175 = v432;
                  v208 = v401 + 1;
                  v206 = v383;
                  *(_WORD *)(v223 + v218 + 6) = v222;
                  v210 = v387;
                  v401 = v208;
                }
                while ( v208 < v14 );
                v205 = v373;
                v207 = v375;
              }
              v373 = ++v205;
            }
            while ( v205 < v374 );
          }
          break;
        }
        v177 = v176 - 2;
        if ( v177 )
        {
          if ( v177 == 1 )
          {
            v178 = v373;
            if ( *(_DWORD *)(a1 + 34224) )
            {
              if ( v373 < v374 )
              {
                v192 = v375;
                do
                {
                  v193 = v192;
                  v433 = v192;
                  v194 = *(_QWORD *)(v376 + 8 * v178);
                  if ( v192 < v14 )
                  {
                    v195 = &idxCC[16 * v178];
                    v382 = v195;
                    do
                    {
                      v196 = 16 * (v193 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v195[v193 & 0xF];
                      v197 = *(_DWORD *)(v15 + 4 * v196);
                      v198 = v28 + *(_DWORD *)(v19 + 4 * v196) - (-*(_DWORD *)(v13 + 4 * v196) >> 1);
                      v199 = -*(_DWORD *)(v13 + 4 * v196) - ((v197 + 1) >> 1) + v198;
                      v200 = *(_QWORD *)(a1 + 33024);
                      v201 = v198 >> v6 << v415;
                      v202 = (v197 + v199) >> v6 << v415;
                      v203 = v199 >> v6 << v415;
                      v204 = 2 * v194 + 2LL * *(_QWORD *)(v20 + 8 * v433);
                      if ( ((v201 | v202 | v203) & 0xFFFF0000) != 0 )
                      {
                        if ( v203 >= 0 )
                        {
                          if ( v203 > 0xFFFF )
                            LOWORD(v203) = -1;
                        }
                        else
                        {
                          LOWORD(v203) = 0;
                        }
                        *(_WORD *)(v204 + v200) = v203;
                        if ( v201 >= 0 )
                        {
                          if ( v201 > 0xFFFF )
                            LOWORD(v201) = -1;
                        }
                        else
                        {
                          LOWORD(v201) = 0;
                        }
                        *(_WORD *)(v204 + v200 + 2) = v201;
                        if ( v202 >= 0 )
                        {
                          if ( v202 > 0xFFFF )
                            LOWORD(v202) = -1;
                        }
                        else
                        {
                          LOWORD(v202) = 0;
                        }
                      }
                      else
                      {
                        *(_WORD *)(v204 + v200) = v203;
                        *(_WORD *)(v204 + v200 + 2) = v201;
                      }
                      v28 = v400;
                      v193 = v433 + 1;
                      *(_WORD *)(v204 + v200 + 4) = v202;
                      v195 = v382;
                      v433 = v193;
                    }
                    while ( v193 < v14 );
                    v178 = v373;
                    v192 = v375;
                  }
                  v373 = ++v178;
                }
                while ( v178 < v374 );
              }
            }
            else if ( v373 < v374 )
            {
              v179 = v375;
              do
              {
                v180 = v179;
                v181 = *(_QWORD *)(v376 + 8 * v178);
                if ( v179 < v14 )
                {
                  v182 = &idxCC[16 * v178];
                  v447 = v182;
                  do
                  {
                    v183 = 16 * (v180 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v182[v180 & 0xF];
                    v184 = *(_DWORD *)(v15 + 4 * v183);
                    v185 = v28 + *(_DWORD *)(v19 + 4 * v183) - (-*(_DWORD *)(v13 + 4 * v183) >> 1);
                    v186 = -*(_DWORD *)(v13 + 4 * v183) - ((v184 + 1) >> 1) + v185;
                    v187 = *(_QWORD *)(a1 + 33024);
                    v188 = v185 << v415;
                    v189 = (v184 + v186) << v415;
                    v190 = v186 << v415;
                    v191 = 2 * v181 + 2LL * *(_QWORD *)(v20 + 8 * v180);
                    if ( ((v188 | v189 | v190) & 0xFFFF0000) != 0 )
                    {
                      if ( v190 >= 0 )
                      {
                        if ( v190 > 0xFFFF )
                          LOWORD(v190) = -1;
                      }
                      else
                      {
                        LOWORD(v190) = 0;
                      }
                      *(_WORD *)(v191 + v187) = v190;
                      if ( v188 >= 0 )
                      {
                        if ( v188 > 0xFFFF )
                          LOWORD(v188) = -1;
                      }
                      else
                      {
                        LOWORD(v188) = 0;
                      }
                      *(_WORD *)(v191 + v187 + 2) = v188;
                      if ( v189 >= 0 )
                      {
                        if ( v189 > 0xFFFF )
                          LOWORD(v189) = -1;
                      }
                      else
                      {
                        LOWORD(v189) = 0;
                      }
                    }
                    else
                    {
                      *(_WORD *)(v191 + v187) = v190;
                      *(_WORD *)(v191 + v187 + 2) = v188;
                    }
                    v28 = v400;
                    ++v180;
                    *(_WORD *)(v191 + v187 + 4) = v189;
                    v182 = v447;
                  }
                  while ( v180 < v14 );
                  v178 = v373;
                  v179 = v375;
                }
                v373 = ++v178;
              }
              while ( v178 < v374 );
            }
            break;
          }
          return 0xFFFFFFFFLL;
        }
      }
      goto LABEL_179;
    case 3:
      v22 = *(_DWORD *)(a1 + 34224) != 0 ? 3 : 0;
      if ( v2 )
      {
        if ( v2 == 7 )
        {
          v224 = v373;
          if ( v373 < v374 )
          {
            v225 = v375;
            v402 = v16;
            do
            {
              v226 = v225;
              v416 = v225;
              v434 = *(_QWORD *)(v376 + 8 * v224);
              if ( v225 < v14 )
              {
                v227 = &idxCC[16 * v224];
                v448 = v227;
                do
                {
                  v228 = 16 * (v226 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v227[v226 & 0xF];
                  v229 = *(_DWORD *)(v15 + 4 * v228);
                  v230 = -*(_DWORD *)(v13 + 4 * v228);
                  LODWORD(v228) = v22 + *(_DWORD *)(v19 + 4 * v228) - (v230 >> 1);
                  v231 = v230 - ((v229 + 1) >> 1) + v228;
                  v232 = v231 >> v6 << v402;
                  v233 = (int)v228 >> v6 << v402;
                  v234 = (v229 + v231) >> v6 << v402;
                  v235 = *(_QWORD *)(a1 + 33024) + 2LL * *(_QWORD *)(v20 + 8 * v416);
                  if ( v232 >= -32768 )
                  {
                    if ( v232 > 0x7FFF )
                      LOWORD(v232) = 0x7FFF;
                  }
                  else
                  {
                    LOWORD(v232) = 0x8000;
                  }
                  *(_WORD *)(v235 + 2 * v434) = v232;
                  if ( v233 >= -32768 )
                  {
                    if ( v233 > 0x7FFF )
                      LOWORD(v233) = 0x7FFF;
                  }
                  else
                  {
                    LOWORD(v233) = 0x8000;
                  }
                  *(_WORD *)(v235 + 2 * v434 + 2) = v233;
                  if ( v234 >= -32768 )
                  {
                    if ( v234 > 0x7FFF )
                      LOWORD(v234) = 0x7FFF;
                  }
                  else
                  {
                    LOWORD(v234) = 0x8000;
                  }
                  v226 = v416 + 1;
                  *(_WORD *)(v235 + 2 * v434 + 4) = v234;
                  v227 = v448;
                  v416 = v226;
                }
                while ( v226 < v14 );
                v224 = v373;
                v225 = v375;
              }
              v373 = ++v224;
            }
            while ( v224 < v374 );
          }
          break;
        }
        return 0xFFFFFFFFLL;
      }
      goto LABEL_20;
    case 4:
      v47 = 0;
      if ( *(_DWORD *)(a1 + 34224) )
        v47 = 3;
      v398 = v47;
      if ( v2 )
      {
        if ( v2 == 7 )
        {
          v48 = v373;
          if ( v373 < v374 )
          {
            v49 = v375;
            do
            {
              v50 = v49;
              v412 = *(_QWORD *)(v376 + 8 * v48);
              if ( v49 < v14 )
              {
                v51 = &idxCC[16 * v48];
                v426 = v51;
                do
                {
                  v52 = 16 * (v50 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v51[v50 & 0xF];
                  v53 = *(_DWORD *)(v13 + 4 * v52);
                  v54 = *(_DWORD *)(v15 + 4 * v52);
                  v55 = -v53;
                  v56 = v47 + *(_DWORD *)(v19 + 4 * v52) - (v55 >> 1);
                  v57 = *(_QWORD *)(v20 + 8 * v50++);
                  v58 = v55 - ((v54 + 1) >> 1) + v56;
                  v59 = *(_QWORD *)(a1 + 33024);
                  v60 = 2 * v412 + 2 * v57;
                  *(_WORD *)(v60 + v59) = ((v58 >> v6 >> 31) ^ (v58 >> v6) & 0x7FFF) - (v58 >> v6 >> 31);
                  LODWORD(v52) = v54 + v58;
                  v13 = v384;
                  v47 = v398;
                  v51 = v426;
                  *(_WORD *)(v60 + v59 + 2) = ((v56 >> v6 >> 31) ^ (v56 >> v6) & 0x7FFF) - (v56 >> v6 >> 31);
                  *(_WORD *)(v60 + v59 + 4) = (((int)v52 >> v6 >> 31) ^ ((int)v52 >> v6) & 0x7FFF)
                                            - ((int)v52 >> v6 >> 31);
                  v15 = v392;
                }
                while ( v50 < v14 );
                v48 = v373;
                v49 = v375;
              }
              v373 = ++v48;
            }
            while ( v48 < v374 );
          }
          break;
        }
        return 0xFFFFFFFFLL;
      }
      goto LABEL_357;
    case 6:
      v47 = *(_DWORD *)(a1 + 34224) != 0 ? 3 : 0;
      v417 = v47;
      if ( v2 )
      {
        if ( v2 == 7 )
        {
          v236 = v373;
          if ( v373 < v374 )
          {
            v237 = v375;
            v403 = v16;
            do
            {
              v238 = v237;
              v435 = *(_QWORD *)(v376 + 8 * v236);
              if ( v237 < v14 )
              {
                v239 = &idxCC[16 * v236];
                do
                {
                  v240 = 16 * (v238 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v239[v238 & 0xF];
                  v241 = *(_DWORD *)(v15 + 4 * v240);
                  v242 = *(_QWORD *)(v20 + 8 * v238);
                  v243 = *(_DWORD *)(v19 + 4 * v240) - (-*(_DWORD *)(v13 + 4 * v240) >> 1) + v47;
                  ++v238;
                  LODWORD(v240) = -*(_DWORD *)(v13 + 4 * v240) - ((v241 + 1) >> 1) + v243;
                  v244 = *(_QWORD *)(a1 + 33024) + 4 * v242;
                  *(_DWORD *)(v244 + 4 * v435) = (int)v240 >> v6 << v403;
                  *(_DWORD *)(v244 + 4 * v435 + 4) = v243 >> v6 << v403;
                  v47 = v417;
                  *(_DWORD *)(v244 + 4 * v435 + 8) = (v241 + (int)v240) >> v6 << v403;
                }
                while ( v238 < v14 );
                v236 = v373;
                v237 = v375;
              }
              v373 = ++v236;
            }
            while ( v236 < v374 );
          }
          break;
        }
        return 0xFFFFFFFFLL;
      }
LABEL_357:
      v23 = outputNChannel(a1, v373, v375, v14, v374, v424 != 0 ? 3 : 0, v47);
LABEL_21:
      if ( !v23 )
        break;
      return 0xFFFFFFFFLL;
    case 7:
      if ( !v2 )
      {
LABEL_20:
        v23 = outputNChannel(a1, v373, v375, v14, v374, v424 != 0 ? 3 : 0, *(_DWORD *)(a1 + 34224) != 0 ? 3 : 0);
        goto LABEL_21;
      }
      if ( v2 != 7 )
        return 0xFFFFFFFFLL;
      v110 = v373;
      if ( v373 < v374 )
      {
        v245 = *(_DWORD *)(a1 + 34224) != 0 ? 3 : 0;
        v109 = v16;
        v111 = v375;
        v418 = v109;
        while ( 1 )
        {
          v108 = v111;
          v378 = v111;
          if ( v111 < v14 )
            break;
LABEL_112:
          v373 = ++v110;
          if ( v110 >= v374 )
            goto LABEL_22;
        }
        v394 = 4LL * *(_QWORD *)(v376 + 8 * v110);
        v107 = &idxCC[16 * v110];
        v436 = v17;
        v246 = 1 << v109;
        v395 = v107;
        v449 = 23 - v109;
        while ( 1 )
        {
          v80 = 16 * (v108 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v107[v108 & 0xF];
          v81 = *(_DWORD *)(v15 + 4 * v80);
          v393 = *(_DWORD *)(v19 + 4 * v80) - (-*(_DWORD *)(v13 + 4 * v80) >> 1) + v245;
          LODWORD(v80) = -*(_DWORD *)(v13 + 4 * v80) - ((v81 + 1) >> 1) + v393;
          v385 = v81 + v80;
          LODWORD(v80) = (int)v80 >> v6;
          v390 = (unsigned int *)(*(_QWORD *)(a1 + 33024) + v394 + 4LL * *(_QWORD *)(v20 + 8 * v378));
          v389 = (int)v80 >> 31;
          v82 = abs32(v80);
          v83 = v82 >> v418;
          v84 = v83;
          v85 = v246 | (v246 - 1) & v82;
          if ( !v83 )
            v84 = 1;
          v86 = v246 ^ v85;
          if ( v83 )
            v86 = v85;
          v87 = 127 - v436 + v84;
          if ( v86 >= v246 )
            break;
          while ( 1 )
          {
            v88 = v86;
            if ( v87 <= 1 || v86 <= 0 )
              break;
            --v87;
            v86 *= 2;
            if ( v86 >= v246 )
              goto LABEL_115;
          }
          if ( v86 >= v246 )
            goto LABEL_116;
LABEL_87:
          v89 = 0;
          if ( v88 >= v246 )
            v89 = v87;
          *v390 = v389 & 0x80000000 | (v86 << v449) | (v89 << 23);
          v90 = abs32(v393 >> v6);
          v91 = v90 >> v418;
          v92 = v91;
          v93 = v246 | (v246 - 1) & v90;
          if ( !v91 )
            v92 = 1;
          v94 = v246 ^ v93;
          if ( v91 )
            v94 = v93;
          v95 = 127 - v436 + v92;
          if ( v94 >= v246 )
          {
LABEL_118:
            v96 = v94;
LABEL_119:
            v94 ^= v246;
            goto LABEL_97;
          }
          while ( 1 )
          {
            v96 = v94;
            if ( v95 <= 1 || v94 <= 0 )
              break;
            --v95;
            v94 *= 2;
            if ( v94 >= v246 )
              goto LABEL_118;
          }
          if ( v94 >= v246 )
            goto LABEL_119;
LABEL_97:
          v97 = 0;
          if ( v96 >= v246 )
            v97 = v95;
          v390[1] = (v393 >> v6 >> 31) & 0x80000000 | (v94 << v449) | (v97 << 23);
          v98 = abs32(v385 >> v6);
          v99 = v98 >> v418;
          v100 = v99;
          v101 = v246 | (v246 - 1) & v98;
          if ( !v99 )
            v100 = 1;
          v102 = v101 ^ v246;
          if ( v99 )
            v102 = v101;
          v103 = 127 - v436 + v100;
          if ( v102 >= v246 )
          {
LABEL_121:
            v104 = v102;
          }
          else
          {
            while ( 1 )
            {
              v104 = v102;
              if ( v103 <= 1 || v102 <= 0 )
                break;
              --v103;
              v102 *= 2;
              if ( v102 >= v246 )
                goto LABEL_121;
            }
            if ( v102 < v246 )
              goto LABEL_108;
          }
          v102 ^= v246;
LABEL_108:
          v105 = 0;
          if ( v104 >= v246 )
            v105 = v103;
          v106 = (v102 << v449) | (v105 << 23);
          v107 = v395;
          v108 = ++v378;
          v390[2] = (v385 >> v6 >> 31) & 0x80000000 | v106;
          if ( v378 >= v14 )
          {
            v17 = v396;
            v109 = v418;
            v110 = v373;
            v111 = v375;
            goto LABEL_112;
          }
        }
LABEL_115:
        v88 = v86;
LABEL_116:
        v86 ^= v246;
        goto LABEL_87;
      }
      break;
    case 8:
      v247 = 128;
      if ( !v424 )
        v247 = 16;
      v248 = (*(_DWORD *)(a1 + 34224) != 0 ? 3 : 0) + v247;
      if ( !v2 )
      {
        v273 = v373;
        v274 = v374;
        if ( v373 < v374 )
        {
          v275 = v376;
          v276 = v375;
          do
          {
            v277 = *(_QWORD *)(v275 + 8 * v273);
            v278 = v276;
            if ( v276 < v14 )
            {
              do
              {
                v279 = (v248
                      + *(_DWORD *)(v19
                                  + 4
                                  * (16 * (v278 & 0xFFFFFFFFFFFFFFF0uLL)
                                   + (unsigned __int8)idxCC[16 * v273 + (v278 & 0xF)]))) >> v6;
                v280 = *(_QWORD *)(a1 + 33024) + 2LL * *(_QWORD *)(v20 + 8 * v278);
                if ( v279 >= 0 )
                {
                  if ( v279 <= 31 )
                  {
                    v281 = (v248
                          + *(_DWORD *)(v19
                                      + 4
                                      * (16 * (v278 & 0xFFFFFFFFFFFFFFF0uLL)
                                       + (unsigned __int8)idxCC[16 * v273 + (v278 & 0xF)]))) >> v6;
                    v282 = v281;
                  }
                  else
                  {
                    LOWORD(v279) = 31;
                    v281 = 31;
                    v282 = 31;
                  }
                }
                else
                {
                  LOWORD(v279) = 0;
                  v281 = 0;
                  v282 = 0;
                }
                ++v278;
                *(_WORD *)(v280 + 2 * v277) = v282 + 32 * (v281 + 32 * v279);
              }
              while ( v278 < v14 );
              v274 = v374;
              v275 = v376;
              v276 = v375;
            }
            ++v273;
          }
          while ( v273 < v274 );
        }
        break;
      }
      if ( v2 == 7 )
      {
        if ( *(_DWORD *)(a1 + 52) )
        {
          v261 = v373;
          if ( v373 < v374 )
          {
            v262 = v375;
            do
            {
              v263 = v262;
              v405 = v262;
              v264 = *(_QWORD *)(v376 + 8 * v261);
              if ( v262 < v14 )
              {
                v265 = &idxCC[16 * v261];
                v438 = v265;
                do
                {
                  v266 = 16 * (v263 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v265[v263 & 0xF];
                  v267 = *(_DWORD *)(v15 + 4 * v266);
                  v268 = v248 + *(_DWORD *)(v19 + 4 * v266) - (-*(_DWORD *)(v13 + 4 * v266) >> 1);
                  LODWORD(v266) = -*(_DWORD *)(v13 + 4 * v266) - ((v267 + 1) >> 1) + v268;
                  v269 = v268 >> v6;
                  v270 = (v267 + (int)v266) >> v6;
                  v271 = (int)v266 >> v6;
                  v272 = 2 * v264 + 2LL * *(_QWORD *)(v20 + 8 * v405);
                  if ( v270 >= 0 )
                  {
                    if ( v270 > 31 )
                      LOWORD(v270) = 31;
                  }
                  else
                  {
                    LOWORD(v270) = 0;
                  }
                  if ( v269 >= 0 )
                  {
                    if ( v269 > 31 )
                      LOWORD(v269) = 31;
                  }
                  else
                  {
                    LOWORD(v269) = 0;
                  }
                  if ( v271 >= 0 )
                  {
                    if ( v271 > 31 )
                      LOWORD(v271) = 31;
                  }
                  else
                  {
                    LOWORD(v271) = 0;
                  }
                  v263 = v405 + 1;
                  v405 = v263;
                  *(_WORD *)(v272 + *(_QWORD *)(a1 + 33024)) = v270 + 32 * (v269 + 32 * v271);
                  v265 = v438;
                }
                while ( v263 < v14 );
                v261 = v373;
                v262 = v375;
              }
              v373 = ++v261;
            }
            while ( v261 < v374 );
          }
        }
        else
        {
          v249 = v373;
          if ( v373 < v374 )
          {
            v250 = v375;
            do
            {
              v251 = v250;
              v404 = v250;
              v419 = *(_QWORD *)(v376 + 8 * v249);
              if ( v250 < v14 )
              {
                v252 = &idxCC[16 * v249];
                v437 = v252;
                do
                {
                  v253 = 16 * (v251 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v252[v251 & 0xF];
                  v254 = *(_DWORD *)(v15 + 4 * v253);
                  v255 = v248 + *(_DWORD *)(v19 + 4 * v253) - (-*(_DWORD *)(v13 + 4 * v253) >> 1);
                  v256 = v255 + -*(_DWORD *)(v13 + 4 * v253) - ((v254 + 1) >> 1);
                  v257 = v255 >> v6;
                  v258 = (v254 + v256) >> v6;
                  v259 = v256 >> v6;
                  v260 = *(_QWORD *)(a1 + 33024) + 2LL * *(_QWORD *)(v20 + 8 * v404);
                  if ( v259 >= 0 )
                  {
                    if ( v259 > 31 )
                      LOWORD(v259) = 31;
                  }
                  else
                  {
                    LOWORD(v259) = 0;
                  }
                  if ( v257 >= 0 )
                  {
                    if ( v257 > 31 )
                      LOWORD(v257) = 31;
                  }
                  else
                  {
                    LOWORD(v257) = 0;
                  }
                  if ( v258 >= 0 )
                  {
                    if ( v258 > 31 )
                      LOWORD(v258) = 31;
                  }
                  else
                  {
                    LOWORD(v258) = 0;
                  }
                  v251 = v404 + 1;
                  v404 = v251;
                  *(_WORD *)(v260 + 2 * v419) = v259 + 32 * (v257 + 32 * v258);
                  v252 = v437;
                }
                while ( v251 < v14 );
                v249 = v373;
                v250 = v375;
              }
              v373 = ++v249;
            }
            while ( v249 < v374 );
          }
        }
        break;
      }
      return 0xFFFFFFFFLL;
    case 10:
      v283 = 256;
      if ( !v424 )
        v283 = 32;
      v284 = (*(_DWORD *)(a1 + 34224) != 0 ? 3 : 0) + v283;
      v406 = v284;
      if ( !v2 )
      {
        v311 = v373;
        if ( v373 < v374 )
        {
          v312 = v375;
          do
          {
            v313 = v312;
            v314 = *(_QWORD *)(v376 + 8 * v311);
            if ( v312 < v14 )
            {
              v315 = &idxCC[16 * v311];
              v316 = 2 * v314;
              v407 = 2 * v314;
              do
              {
                v317 = v316 + 2LL * *(_QWORD *)(v20 + 8 * v313);
                v318 = (v284
                      + *(_DWORD *)(v19 + 4 * (16 * (v313 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v315[v313 & 0xF]))) >> v6;
                v319 = v318 >> 1;
                if ( v318 >> 1 >= 0 )
                {
                  v320 = (v284
                        + *(_DWORD *)(v19 + 4
                                          * (16 * (v313 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v315[v313 & 0xF]))) >> v6 >> 1;
                  if ( v319 > 31 )
                    v320 = 31;
                }
                else
                {
                  v320 = 0;
                }
                if ( v318 >= 0 )
                {
                  if ( v318 > 63 )
                    LOWORD(v318) = 63;
                }
                else
                {
                  LOWORD(v318) = 0;
                }
                if ( v319 >= 0 )
                {
                  if ( v319 > 31 )
                    LOWORD(v319) = 31;
                }
                else
                {
                  LOWORD(v319) = 0;
                }
                ++v313;
                *(_WORD *)(v317 + *(_QWORD *)(a1 + 33024)) = v320 + 32 * (v318 + ((_WORD)v319 << 6));
                v316 = v407;
              }
              while ( v313 < v14 );
              v311 = v373;
              v312 = v375;
            }
            v373 = ++v311;
          }
          while ( v311 < v374 );
        }
        break;
      }
      if ( v2 == 7 )
      {
        v285 = v373;
        if ( *(_DWORD *)(a1 + 52) )
        {
          if ( v373 < v374 )
          {
            v299 = v375;
            v300 = 4;
            if ( !v424 )
              v300 = 1;
            do
            {
              v301 = v299;
              v421 = v299;
              if ( v299 < v14 )
              {
                v302 = &idxCC[16 * v285];
                v451 = v302;
                v440 = 2LL * *(_QWORD *)(v376 + 8 * v285);
                do
                {
                  v303 = 16 * (v301 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v302[v301 & 0xF];
                  v304 = *(_DWORD *)(v15 + 4 * v303);
                  v305 = v406 + *(_DWORD *)(v19 + 4 * v303) - (-*(_DWORD *)(v13 + 4 * v303) >> 1);
                  LODWORD(v303) = -*(_DWORD *)(v13 + 4 * v303) - ((v304 + 1) >> 1) + v305;
                  v306 = v305 >> v6;
                  v307 = ((int)v303 + v304) >> v300;
                  v308 = (int)v303 >> v300;
                  v309 = v440 + 2LL * *(_QWORD *)(v20 + 8 * v421);
                  v310 = *(_QWORD *)(a1 + 33024);
                  if ( v307 >= 0 )
                  {
                    if ( v307 > 31 )
                      LOWORD(v307) = 31;
                  }
                  else
                  {
                    LOWORD(v307) = 0;
                  }
                  if ( v306 >= 0 )
                  {
                    if ( v306 > 63 )
                      LOWORD(v306) = 63;
                    v310 = *(_QWORD *)(a1 + 33024);
                  }
                  else
                  {
                    LOWORD(v306) = 0;
                  }
                  if ( v308 >= 0 )
                  {
                    if ( v308 > 31 )
                      LOWORD(v308) = 31;
                  }
                  else
                  {
                    LOWORD(v308) = 0;
                  }
                  v301 = v421 + 1;
                  v421 = v301;
                  *(_WORD *)(v309 + v310) = v307 + 32 * (v306 + ((_WORD)v308 << 6));
                  v302 = v451;
                }
                while ( v301 < v14 );
                v285 = v373;
                v299 = v375;
              }
              v373 = ++v285;
            }
            while ( v285 < v374 );
          }
        }
        else if ( v373 < v374 )
        {
          v286 = v375;
          v287 = 4;
          if ( !v424 )
            v287 = 1;
          do
          {
            v288 = v286;
            v420 = v286;
            if ( v286 < v14 )
            {
              v289 = &idxCC[16 * v285];
              v450 = v289;
              v439 = 2LL * *(_QWORD *)(v376 + 8 * v285);
              do
              {
                v290 = 16 * (v288 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v289[v288 & 0xF];
                v291 = *(_DWORD *)(v15 + 4 * v290);
                v292 = v406 + *(_DWORD *)(v19 + 4 * v290) - (-*(_DWORD *)(v13 + 4 * v290) >> 1);
                v293 = v292 + -*(_DWORD *)(v13 + 4 * v290) - ((v291 + 1) >> 1);
                v294 = v292 >> v6;
                v295 = (v293 + v291) >> v287;
                v296 = v293 >> v287;
                v297 = v439 + 2LL * *(_QWORD *)(v20 + 8 * v420);
                v298 = *(_QWORD *)(a1 + 33024);
                if ( v296 >= 0 )
                {
                  if ( v296 > 31 )
                    LOWORD(v296) = 31;
                }
                else
                {
                  LOWORD(v296) = 0;
                }
                if ( v294 >= 0 )
                {
                  if ( v294 > 63 )
                    LOWORD(v294) = 63;
                  v298 = *(_QWORD *)(a1 + 33024);
                }
                else
                {
                  LOWORD(v294) = 0;
                }
                if ( v295 >= 0 )
                {
                  if ( v295 > 31 )
                    LOWORD(v295) = 31;
                }
                else
                {
                  LOWORD(v295) = 0;
                }
                v288 = v420 + 1;
                v420 = v288;
                *(_WORD *)(v297 + v298) = v296 + 32 * (v294 + ((_WORD)v295 << 6));
                v289 = v450;
              }
              while ( v288 < v14 );
              v285 = v373;
              v286 = v375;
            }
            v373 = ++v285;
          }
          while ( v285 < v374 );
        }
        break;
      }
      return 0xFFFFFFFFLL;
    case 9:
      v321 = 4096;
      if ( !v424 )
        v321 = 512;
      v322 = (*(_DWORD *)(a1 + 34224) != 0 ? 3 : 0) + v321;
      v408 = v322;
      if ( !v2 )
      {
        v349 = v373;
        if ( v373 < v374 )
        {
          v350 = v375;
          do
          {
            v351 = v350;
            if ( v350 < v14 )
            {
              v352 = 4LL * *(_QWORD *)(v376 + 8 * v349);
              v353 = &idxCC[16 * v349];
              do
              {
                v354 = v352 + 4LL * *(_QWORD *)(v20 + 8 * v351);
                v355 = (v322
                      + *(_DWORD *)(v19 + 4 * (16 * (v351 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v353[v351 & 0xF]))) >> v6;
                if ( v355 >= 0 )
                {
                  if ( v355 <= 1023 )
                  {
                    v356 = (v322
                          + *(_DWORD *)(v19
                                      + 4 * (16 * (v351 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v353[v351 & 0xF]))) >> v6;
                    v357 = v356;
                  }
                  else
                  {
                    v355 = 1023;
                    v356 = 1023;
                    v357 = 1023;
                  }
                }
                else
                {
                  v355 = 0;
                  v356 = 0;
                  v357 = 0;
                }
                ++v351;
                *(_DWORD *)(v354 + *(_QWORD *)(a1 + 33024)) = v357 + ((v356 + (v355 << 10)) << 10);
              }
              while ( v351 < v14 );
              v349 = v373;
              v350 = v375;
            }
            v373 = ++v349;
          }
          while ( v349 < v374 );
        }
        break;
      }
      if ( v2 == 7 )
      {
        if ( *(_DWORD *)(a1 + 52) || *(_DWORD *)(a1 + 48) )
        {
          v337 = v373;
          if ( v373 < v374 )
          {
            v338 = v375;
            do
            {
              v339 = v338;
              v409 = *(_QWORD *)(v376 + 8 * v337);
              if ( v338 < v14 )
              {
                v340 = &idxCC[16 * v337];
                v442 = v340;
                do
                {
                  v341 = 16 * (v339 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v340[v339 & 0xF];
                  v342 = *(_DWORD *)(v15 + 4 * v341);
                  v343 = -*(_DWORD *)(v13 + 4 * v341);
                  LODWORD(v341) = v322 + *(_DWORD *)(v19 + 4 * v341) - (v343 >> 1);
                  v344 = v341 + v343 - ((v342 + 1) >> 1);
                  v345 = (int)v341 >> v6;
                  v346 = v344 + v342;
                  v347 = v344 >> v6;
                  v348 = v346 >> v6;
                  v422 = *(_QWORD *)(a1 + 33024) + 4LL * *(_QWORD *)(v20 + 8 * v339);
                  if ( v348 >= 0 )
                  {
                    if ( v348 > 1023 )
                      v348 = 1023;
                  }
                  else
                  {
                    v348 = 0;
                  }
                  if ( v345 >= 0 )
                  {
                    if ( v345 > 1023 )
                      v345 = 1023;
                  }
                  else
                  {
                    v345 = 0;
                  }
                  if ( v347 >= 0 )
                  {
                    if ( v347 > 1023 )
                      v347 = 1023;
                  }
                  else
                  {
                    v347 = 0;
                  }
                  ++v339;
                  *(_DWORD *)(v422 + 4 * v409) = v348 + ((v345 + ((v347 + 3072) << 10)) << 10);
                  v340 = v442;
                }
                while ( v339 < v14 );
                v337 = v373;
                v338 = v375;
              }
              v373 = ++v337;
            }
            while ( v337 < v374 );
          }
        }
        else
        {
          v323 = v373;
          if ( v373 < v374 )
          {
            v324 = v375;
            do
            {
              v325 = v324;
              v326 = *(_QWORD *)(v376 + 8 * v323);
              if ( v324 < v14 )
              {
                v327 = &idxCC[16 * v323];
                v441 = v327;
                do
                {
                  v328 = 16 * (v325 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v327[v325 & 0xF];
                  v329 = *(_DWORD *)(v15 + 4 * v328);
                  v330 = *(_DWORD *)(v19 + 4 * v328) - (-*(_DWORD *)(v13 + 4 * v328) >> 1) + v322;
                  v331 = v330 + -*(_DWORD *)(v13 + 4 * v328) - ((v329 + 1) >> 1);
                  v332 = v330 >> v6;
                  LODWORD(v328) = v331 + v329;
                  v333 = v331 >> v6;
                  v334 = (int)v328 >> v6;
                  v335 = 4 * v326 + 4LL * *(_QWORD *)(v20 + 8 * v325);
                  if ( v333 >= 0 )
                  {
                    if ( v333 > 1023 )
                      v333 = 1023;
                  }
                  else
                  {
                    v333 = 0;
                  }
                  if ( v332 >= 0 )
                  {
                    if ( v332 > 1023 )
                      v332 = 1023;
                  }
                  else
                  {
                    v332 = 0;
                  }
                  if ( v334 >= 0 )
                  {
                    if ( v334 > 1023 )
                      v334 = 1023;
                  }
                  else
                  {
                    v334 = 0;
                  }
                  ++v325;
                  v336 = v332 + (v334 << 10);
                  v322 = v408;
                  *(_DWORD *)(v335 + *(_QWORD *)(a1 + 33024)) = v333 + (v336 << 10);
                  v327 = v441;
                }
                while ( v325 < v14 );
                v323 = v373;
                v324 = v375;
              }
              v373 = ++v323;
            }
            while ( v323 < v374 );
          }
        }
        break;
      }
      return 0xFFFFFFFFLL;
    case 0:
      v358 = 4;
      if ( !v424 )
        v358 = 1;
      if ( !v2 && !*(_DWORD *)(a1 + 34216) )
      {
        v359 = *(_QWORD *)(a1 + 40);
        v423 = v359;
        if ( *(int *)(a1 + 124) >= 4 )
        {
          for ( i = v373; i < v374; v373 = i )
          {
            v366 = v375;
            v367 = v359 + *(_QWORD *)(v21 + 8 * i);
            if ( v375 < v14 )
            {
              v368 = 7 - (v367 & 7);
              v369 = &idxCC[16 * i];
              do
              {
                v370 = *(_QWORD *)(a1 + 33024);
                v371 = (v367 >> 3) + *(_QWORD *)(v20 + 8 * v366);
                v372 = *(_BYTE *)(a1 + 32996)
                     + (*(_BYTE *)(v371 + v370) >> v368)
                     + (*(_DWORD *)(v19 + 4 * (16 * (v366 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)v369[v366 & 0xF])) >= v358);
                ++v366;
                *(_BYTE *)(v371 + v370) ^= (v372 & 1) << v368;
              }
              while ( v366 < v14 );
              v359 = v423;
              i = v373;
            }
            v21 = v376;
            ++i;
          }
        }
        else
        {
          for ( j = v373; j < v374; v373 = j )
          {
            v361 = v375;
            v362 = v359 + *(_QWORD *)(v376 + 8 * j);
            if ( v375 < v14 )
            {
              do
              {
                v363 = *(_QWORD *)(v20 + 8 * v361);
                v364 = 16 * (v361 & 0xFFFFFFFFFFFFFFF0uLL) + (unsigned __int8)idxCC[16 * j + (v361 & 0xF)];
                ++v361;
                *(_BYTE *)(*(_QWORD *)(a1 + 33024) + (v363 >> 3) + v362) ^= ((*(_BYTE *)(a1 + 32996)
                                                                            + (*(_BYTE *)(*(_QWORD *)(a1 + 33024)
                                                                                        + (v363 >> 3)
                                                                                        + v362) >> (7 - (v363 & 7)))
                                                                            + (*(_DWORD *)(v19 + 4 * v364) >= v358))
                                                                           & 1) << (7 - (v363 & 7));
              }
              while ( v361 < v14 );
              j = v373;
            }
            ++j;
          }
        }
        break;
      }
      return 0xFFFFFFFFLL;
  }
LABEL_22:
  if ( *(_BYTE *)(a1 + 184) )
    return (unsigned int)-((unsigned int)outputMBRowAlpha(a1) != 0);
  else
    return 0;
}

```

## disassembly

```asm
0x180014bb0  push    rbx
0x180014bb2  push    rbp
0x180014bb3  push    rsi
0x180014bb4  push    rdi
0x180014bb5  push    r14
0x180014bb7  push    r15
0x180014bb9  sub     rsp, 0B8h
0x180014bc0  cmp     dword ptr [rcx+85A8h], 0
0x180014bc7  mov     r15, rcx
0x180014bca  jnz     loc_180014DF4
0x180014bd0  xor     r14d, r14d
0x180014bd3  mov     eax, [rcx+85B0h]
0x180014bd9  mov     r8d, 10h
0x180014bdf  mov     r9, [rcx+8628h]
0x180014be6  mov     r11d, 8A20h
0x180014bec  mov     rdx, [rcx+86E0h]
0x180014bf3  mov     ebx, 8830h
0x180014bf8  mov     dword ptr [rsp+0E8h+arg_10], eax
0x180014bff  neg     eax
0x180014c01  mov     rax, [r9+38h]
0x180014c05  sbb     edi, edi
0x180014c07  shl     rdx, 4
0x180014c0b  and     edi, 3
0x180014c0e  add     rdx, 0FFFFFFFFFFFFFFF0h
0x180014c12  sub     rax, rdx
0x180014c15  inc     rax
0x180014c18  cmp     rax, r8
0x180014c1b  cmovb   r8, rax
0x180014c1f  mov     rax, [r9+30h]
0x180014c23  and     eax, 0Fh
0x180014c26  mov     [rsp+0E8h+var_A0], r8
0x180014c2b  xor     esi, esi
0x180014c2d  cmp     rdx, [r9+30h]
0x180014c31  cmovbe  esi, eax
0x180014c34  mov     eax, [rcx+8634h]
0x180014c3a  test    eax, eax
0x180014c3c  mov     [rsp+0E8h+var_A8], rsi
0x180014c41  mov     ecx, 8828h
0x180014c46  cmovz   r11d, ecx
0x180014c4a  mov     ecx, 8A28h
0x180014c4f  cmovnz  ebx, ecx
0x180014c52  cmp     r14d, 5
0x180014c56  jz      loc_180014DFD
0x180014c5c  mov     eax, [r15+30h]
0x180014c60  neg     eax
0x180014c62  sbb     r10d, r10d
0x180014c65  and     r10d, 2
0x180014c69  mov     dword ptr [rsp+0E8h+arg_18], r10d
0x180014c71  xor     ebp, ebp
0x180014c73  mov     [rsp+0E8h+var_38], r12
0x180014c7b  cmp     r14d, 5
0x180014c7f  mov     [rsp+0E8h+var_40], r13
0x180014c87  mov     eax, 80h
0x180014c8c  mov     r10d, 40h ; '@'
0x180014c92  setz    bpl
0x180014c96  mov     edx, 48h ; 'H'
0x180014c9b  add     rbp, 2
0x180014c9f  mov     rcx, r15
0x180014ca2  cmp     r14d, 1
0x180014ca6  cmovnz  r10d, eax
0x180014caa  cmp     dword ptr [r15+7Ch], 4
0x180014caf  mov     eax, 58h ; 'X'
0x180014cb4  cmovge  edx, eax
0x180014cb7  sub     r8, rsi
0x180014cba  mov     rdx, [rdx+r15]
0x180014cbe  call    checkImageBuffer
0x180014cc3  test    eax, eax
0x180014cc5  jnz     loc_180014DCF
0x180014ccb  mov     rcx, [r9+20h]
0x180014ccf  mov     rsi, [r9+28h]
0x180014cd3  mov     r11, [r11+r15]
0x180014cd7  inc     rsi
0x180014cda  mov     rbx, [rbx+r15]
0x180014cde  movzx   r8d, byte ptr [r15+80E0h]
0x180014ce6  movzx   edx, byte ptr [r15+80E1h]
0x180014cee  mov     eax, [r15+1Ch]
0x180014cf2  mov     r12, [r15+8820h]
0x180014cf9  mov     r13, [r9+40h]
0x180014cfd  mov     [rsp+0E8h+var_98], rcx
0x180014d02  mov     rcx, [r15+86E0h]
0x180014d09  dec     rcx
0x180014d0c  mov     [rsp+0E8h+var_78], eax
0x180014d10  imul    rcx, r10
0x180014d14  mov     [rsp+0E8h+var_80], r11
0x180014d19  add     rcx, [r9+48h]
0x180014d1d  cmp     dword ptr [r15+8634h], 0
0x180014d25  mov     [rsp+0E8h+var_68], rbx
0x180014d2d  mov     byte ptr [rsp+0E8h+arg_8], r8b
0x180014d35  mov     byte ptr [rsp+0E8h+arg_0], dl
0x180014d3c  mov     [rsp+0E8h+var_90], rcx
0x180014d41  jnz     loc_18001553D
0x180014d47  cmp     eax, 1
0x180014d4a  jz      loc_180014E1A
0x180014d50  cmp     eax, 2
0x180014d53  jz      loc_180015D27
0x180014d59  cmp     eax, 3
0x180014d5c  jnz     loc_180014FF0
0x180014d62  mov     eax, [r15+85B0h]
0x180014d69  neg     eax
0x180014d6b  sbb     r10d, r10d
0x180014d6e  and     r10d, 3
0x180014d72  test    r14d, r14d
0x180014d75  jnz     short loc_180014DC5
0x180014d77  mov     [rsp+0E8h+var_B8], r10d
0x180014d7c  mov     edx, dword ptr [rsp+0E8h+arg_10]
0x180014d83  mov     r8, [rsp+0E8h+var_98]
0x180014d88  neg     edx
0x180014d8a  mov     rdx, [rsp+0E8h+var_A8]
0x180014d8f  mov     r9, rsi
0x180014d92  sbb     rax, rax
0x180014d95  mov     rcx, r15
0x180014d98  and     eax, 3
0x180014d9b  mov     [rsp+0E8h+var_C0], rax
0x180014da0  mov     rax, [rsp+0E8h+var_A0]
0x180014da5  mov     [rsp+0E8h+var_C8], rax
0x180014daa  call    outputNChannel
0x180014daf  test    eax, eax
0x180014db1  jnz     short loc_180014DCF
0x180014db3  cmp     byte ptr [r15+0B8h], 0
0x180014dbb  ja      loc_1800173AF
0x180014dc1  xor     eax, eax
0x180014dc3  jmp     short loc_180014DD4
0x180014dc5  cmp     r14d, 7
0x180014dc9  jz      loc_18001624D
0x180014dcf  mov     eax, 0FFFFFFFFh
0x180014dd4  mov     r13, [rsp+0E8h+var_40]
0x180014ddc  mov     r12, [rsp+0E8h+var_38]
0x180014de4  add     rsp, 0B8h
0x180014deb  pop     r15
0x180014ded  pop     r14
0x180014def  pop     rdi
0x180014df0  pop     rsi
0x180014df1  pop     rbp
0x180014df2  pop     rbx
0x180014df3  retn
0x180014df4  mov     r14d, [rcx+18h]
0x180014df8  jmp     loc_180014BD3
0x180014dfd  movzx   eax, byte ptr [r15+3Ch]
0x180014e02  mov     ecx, eax
0x180014e04  and     eax, 1
0x180014e07  and     ecx, 2
0x180014e0a  sub     ecx, eax
0x180014e0c  inc     ecx
0x180014e0e  mov     dword ptr [rsp+0E8h+arg_18], ecx
0x180014e15  jmp     loc_180014C71
0x180014e1a  mov     edx, dword ptr [rsp+0E8h+arg_10]
0x180014e21  mov     r10d, 80h
0x180014e27  mov     ecx, [r15+85B0h]
0x180014e2e  test    edx, edx
0x180014e30  mov     r9d, 400h
0x180014e36  mov     eax, ecx
0x180014e38  cmovz   r9d, r10d
0x180014e3c  neg     eax
0x180014e3e  mov     dword ptr [rsp+0E8h+arg_0], r9d
0x180014e46  sbb     eax, eax
0x180014e48  and     eax, 3
0x180014e4b  mov     dword ptr [rsp+0E8h+arg_8], eax
0x180014e52  lea     r10d, [rax+r9]
0x180014e56  cmp     r14d, 7
0x180014e5a  jnz     loc_18001517E
0x180014e60  movsxd  rdx, dword ptr [rsp+0E8h+arg_18]
0x180014e68  mov     rax, [r15+8B50h]
0x180014e6f  sub     rbp, rdx
0x180014e72  test    rax, rax
0x180014e75  jnz     loc_18001586A
0x180014e7b  test    ecx, ecx
0x180014e7d  mov     rcx, [rsp+0E8h+var_A8]
0x180014e82  jz      loc_180015BDB
0x180014e88  cmp     rcx, [rsp+0E8h+var_A0]
0x180014e8d  jnb     loc_180014DB3
0x180014e93  mov     r8, [rsp+0E8h+var_98]
0x180014e98  lea     r9, idxCC
0x180014e9f  nop
0x180014ea0  mov     rax, [rsp+0E8h+var_90]
0x180014ea5  mov     r10, r8
0x180014ea8  mov     rax, [rax+rcx*8]
0x180014eac  mov     [rsp+0E8h+arg_10], rax
0x180014eb4  cmp     r8, rsi
0x180014eb7  jnb     loc_180014F8F
0x180014ebd  shl     rcx, 4
0x180014ec1  lea     r14, [rax+rdx]
0x180014ec5  add     rcx, r9
0x180014ec8  mov     [rsp+0E8h+var_88], rcx
0x180014ecd  nop     dword ptr [rax]
0x180014ed0  mov     rax, r10
0x180014ed3  and     eax, 0Fh
0x180014ed6  movzx   edx, byte ptr [rax+rcx]
0x180014eda  mov     rax, r10
0x180014edd  and     rax, 0FFFFFFFFFFFFFFF0h
0x180014ee1  shl     rax, 4
0x180014ee5  add     rdx, rax
0x180014ee8  mov     r9d, [rbx+rdx*4]
0x180014eec  mov     r8d, [r11+rdx*4]
0x180014ef0  mov     ebx, [r12+rdx*4]
0x180014ef4  neg     r8d
0x180014ef7  mov     ecx, r8d
0x180014efa  sar     ecx, 1
0x180014efc  lea     eax, [r9+1]
0x180014f00  sub     ebx, ecx
0x180014f02  sar     eax, 1
0x180014f04  mov     ecx, dword ptr [rsp+0E8h+arg_8]
0x180014f0b  sub     r8d, eax
0x180014f0e  add     ecx, dword ptr [rsp+0E8h+arg_0]
0x180014f15  add     ebx, ecx
0x180014f17  mov     ecx, edi
0x180014f19  lea     r11d, [r8+rbx]
0x180014f1d  mov     r8, [r13+r10*8+0]
0x180014f22  add     r8, [r15+8100h]
0x180014f29  lea     edx, [r9+r11]
0x180014f2d  sar     r11d, cl
0x180014f30  sar     edx, cl
0x180014f32  mov     eax, r11d
0x180014f35  sar     ebx, cl
0x180014f37  or      eax, edx
0x180014f39  mov     rcx, [rsp+0E8h+arg_10]
0x180014f41  or      eax, ebx
0x180014f43  add     rcx, r8
0x180014f46  test    eax, 0FFFFFF00h
0x180014f4b  jnz     short loc_180014FA7
0x180014f4d  mov     [rcx+rbp], r11b
0x180014f51  mov     [rcx+1], bl
0x180014f54  mov     r11, [rsp+0E8h+var_80]
0x180014f59  inc     r10
0x180014f5c  mov     rbx, [rsp+0E8h+var_68]
0x180014f64  mov     rcx, [rsp+0E8h+var_88]
0x180014f69  mov     [r14+r8], dl
0x180014f6d  cmp     r10, rsi
0x180014f70  jb      loc_180014ED0
0x180014f76  mov     rcx, [rsp+0E8h+var_A8]
0x180014f7b  lea     r9, idxCC
0x180014f82  movsxd  rdx, dword ptr [rsp+0E8h+arg_18]
0x180014f8a  mov     r8, [rsp+0E8h+var_98]
0x180014f8f  inc     rcx
0x180014f92  mov     [rsp+0E8h+var_A8], rcx
0x180014f97  cmp     rcx, [rsp+0E8h+var_A0]
0x180014f9c  jb      loc_180014EA0
0x180014fa2  jmp     loc_180014DB3
0x180014fa7  test    r11d, r11d
0x180014faa  js      short loc_180014FE7
0x180014fac  mov     eax, 0FFh
0x180014fb1  cmp     r11d, eax
0x180014fb4  cmovg   r11d, eax
0x180014fb8  mov     [rcx+rbp], r11b
0x180014fbc  test    ebx, ebx
0x180014fbe  js      short loc_180014FEC
0x180014fc0  mov     eax, 0FFh
0x180014fc5  cmp     ebx, eax
0x180014fc7  cmovg   ebx, eax
0x180014fca  mov     [rcx+1], bl
0x180014fcd  test    edx, edx
0x180014fcf  js      short loc_180014FE0
0x180014fd1  mov     eax, 0FFh
0x180014fd6  cmp     edx, eax
0x180014fd8  cmovg   edx, eax
0x180014fdb  jmp     loc_180014F54
0x180014fe0  xor     edx, edx
0x180014fe2  jmp     loc_180014F54
0x180014fe7  xor     r11d, r11d
0x180014fea  jmp     short loc_180014FB8
0x180014fec  xor     ebx, ebx
0x180014fee  jmp     short loc_180014FCA
0x180014ff0  cmp     eax, 4
0x180014ff3  jnz     loc_1800163DD
0x180014ff9  xor     r9d, r9d
0x180014ffc  mov     eax, 3
0x180015001  cmp     [r15+85B0h], r9d
0x180015008  cmovnz  r9d, eax
0x18001500c  mov     dword ptr [rsp+0E8h+arg_0], r9d
0x180015014  test    r14d, r14d
0x180015017  jz      loc_1800163D3
0x18001501d  cmp     r14d, 7
0x180015021  jnz     loc_180014DCF
0x180015027  mov     rcx, [rsp+0E8h+var_A8]
0x18001502c  cmp     rcx, [rsp+0E8h+var_A0]
0x180015031  jnb     loc_180014DB3
0x180015037  mov     rdx, [rsp+0E8h+var_98]
0x18001503c  lea     r8, idxCC
0x180015043  mov     r14d, 7FFFh
0x180015049  mov     rax, [rsp+0E8h+var_90]
0x18001504e  mov     rbp, rdx
0x180015051  mov     rax, [rax+rcx*8]
0x180015055  mov     [rsp+0E8h+arg_8], rax
0x18001505d  cmp     rdx, rsi
0x180015060  jnb     loc_180015166
0x180015066  shl     rcx, 4
0x18001506a  add     rcx, r8
0x18001506d  mov     [rsp+0E8h+arg_10], rcx
0x180015075  nop     word ptr [rax+rax+00000000h]
0x180015080  mov     rax, rbp
0x180015083  and     eax, 0Fh
0x180015086  movzx   edx, byte ptr [rax+rcx]
0x18001508a  mov     rax, rbp
0x18001508d  and     rax, 0FFFFFFFFFFFFFFF0h
0x180015091  shl     rax, 4
0x180015095  add     rdx, rax
0x180015098  mov     r8d, [r11+rdx*4]
0x18001509c  mov     r11d, [rbx+rdx*4]
0x1800150a0  neg     r8d
0x1800150a3  mov     r10d, [r12+rdx*4]
0x1800150a7  mov     ecx, r8d
  ... truncated ...
```
