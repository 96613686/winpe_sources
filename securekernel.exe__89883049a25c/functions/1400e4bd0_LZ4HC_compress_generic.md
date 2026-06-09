# LZ4HC_compress_generic

- ea: `0x1400e4bd0`
- end: `0x1400e71b5`
- name: `LZ4HC_compress_generic`
- size: `9701`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400ee3c8`

## callees

- `0x1400e4bd0`
- `0x1400e71bc`
- `0x1400ee148`
- `0x1400ee238`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall LZ4HC_compress_generic(__int64 a1, char *a2, __int64 a3, int *a4, int a5, __int64 a6, int a7)
{
  __int64 v10; // rbx
  __int64 result; // rax
  __int64 v12; // rax
  char *v13; // r8
  __int64 v14; // rdx
  char *v15; // r14
  __int64 v16; // rdi
  char *v17; // r9
  unsigned __int64 v18; // r15
  __int64 v19; // rcx
  _QWORD *v20; // rbp
  int v21; // r14d
  __int64 v22; // r13
  unsigned int v23; // esi
  unsigned int v24; // r15d
  _QWORD *v25; // rdx
  unsigned int v26; // r12d
  int v27; // r9d
  unsigned int v28; // r8d
  int v29; // r10d
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  _DWORD *v32; // r8
  unsigned int v33; // r11d
  _DWORD *v34; // r10
  __int64 v35; // r8
  _QWORD *v36; // r9
  _QWORD *v37; // rdx
  _QWORD *v39; // rcx
  unsigned int v41; // ecx
  signed int v44; // ecx
  _QWORD *v45; // r10
  _QWORD *v46; // r9
  _QWORD *v47; // rdx
  _QWORD *v49; // rcx
  signed int v51; // ebx
  _QWORD *v54; // r8
  int v55; // ecx
  _QWORD *v57; // rcx
  _QWORD *v58; // rdx
  unsigned int v60; // ecx
  unsigned int v63; // r14d
  int v64; // r15d
  _DWORD *v65; // rbx
  _DWORD *v66; // rbp
  unsigned __int64 v67; // rsi
  __int64 v68; // r8
  __int64 v69; // rcx
  _QWORD *v70; // rdx
  unsigned int v71; // eax
  __int64 v72; // r8
  unsigned int v73; // r11d
  __int64 v74; // rcx
  int v75; // eax
  int v76; // r11d
  unsigned int v77; // eax
  unsigned __int64 v78; // rcx
  unsigned __int64 v79; // rdx
  unsigned int v80; // ecx
  int v81; // r13d
  __int16 v82; // r11
  _DWORD *v83; // rdx
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rsi
  __int64 v86; // rbp
  char *v87; // r10
  _QWORD *v88; // r15
  char *v89; // rbx
  char *v90; // r12
  unsigned int v91; // esi
  unsigned int v92; // r9d
  unsigned int v93; // r14d
  char *v94; // r10
  unsigned int v95; // ebp
  _DWORD *v96; // rdx
  unsigned int v97; // r8d
  unsigned __int64 v98; // rdx
  unsigned __int64 v99; // rcx
  unsigned int v100; // r13d
  int v101; // eax
  int v102; // r8d
  int v103; // edx
  _DWORD *v104; // r10
  int v105; // r9d
  __int64 v106; // rax
  int v107; // r8d
  int j; // eax
  unsigned __int64 v109; // r15
  _QWORD *v110; // rbx
  _QWORD *v111; // rdx
  _QWORD *v113; // rcx
  unsigned int v114; // eax
  unsigned int v116; // ecx
  int v119; // ecx
  char *v120; // r14
  char *v121; // r10
  char *v122; // rsi
  _QWORD *v123; // rdx
  char *v125; // rcx
  signed int v127; // ebp
  int v130; // ebx
  char *v131; // r10
  char *v133; // rcx
  _QWORD *v134; // rdx
  unsigned int v136; // ecx
  char *v139; // rsi
  int v140; // edx
  int v141; // r9d
  int i; // eax
  int v143; // ebx
  unsigned int v144; // eax
  __int64 v145; // r9
  unsigned int v146; // eax
  unsigned int v147; // ecx
  unsigned int v148; // r15d
  int v149; // r14d
  char *v150; // rsi
  unsigned __int64 v151; // rbp
  __int64 v152; // r8
  __int64 v153; // rcx
  char *v154; // rdx
  unsigned int v155; // eax
  char *v156; // r8
  unsigned int v157; // esi
  bool v158; // zf
  __int64 v159; // r8
  __int64 v160; // rcx
  unsigned __int64 v161; // rcx
  unsigned __int64 v162; // rdx
  int v163; // r12d
  __int16 v164; // r9
  unsigned __int64 v165; // rbx
  int v166; // edx
  int v167; // ecx
  __int64 v168; // r10
  char *v169; // r15
  char *v170; // r12
  unsigned int v171; // edx
  unsigned int v172; // ebp
  _QWORD *v173; // r14
  char *v174; // rbx
  unsigned int v175; // r15d
  char *v176; // r9
  unsigned int v177; // r8d
  unsigned int v178; // esi
  unsigned __int64 v179; // rdx
  unsigned __int64 v180; // rcx
  unsigned int v181; // r13d
  int v182; // eax
  int v183; // r8d
  int v184; // r11d
  int v185; // ecx
  _DWORD *v186; // r10
  int v187; // r9d
  __int64 v188; // rax
  int v189; // r8d
  int n; // eax
  _QWORD *v191; // rdx
  _QWORD *v192; // r11
  _QWORD *v194; // rcx
  unsigned int v195; // eax
  unsigned int v197; // ecx
  int v200; // ecx
  __int64 v201; // r9
  unsigned int v202; // eax
  char *v203; // rbp
  char *v204; // r10
  char *v205; // rbx
  _QWORD *v206; // rdx
  char *v208; // rcx
  signed int v210; // esi
  int v213; // r11d
  char *v214; // r10
  char *v216; // rcx
  _QWORD *v217; // rdx
  unsigned int v219; // ecx
  int v222; // edx
  int v223; // r9d
  int m; // eax
  int v225; // r11d
  unsigned int v226; // eax
  unsigned int v227; // ecx
  unsigned int v228; // r15d
  int v229; // ebp
  char *v230; // rsi
  unsigned __int64 v231; // r14
  __int64 v232; // r8
  __int64 v233; // rcx
  char *v234; // r13
  char *v235; // rdx
  unsigned int v236; // eax
  __int64 v237; // r8
  unsigned int v238; // r11d
  __int64 v239; // rcx
  int v240; // eax
  int v241; // r11d
  unsigned __int64 v242; // rcx
  unsigned __int64 v243; // rdx
  int v244; // ebp
  __int16 v245; // r14
  unsigned __int64 v246; // r10
  int v247; // ecx
  _BYTE *v248; // rcx
  __int64 v249; // rbx
  unsigned int v250; // esi
  char *v251; // r9
  unsigned __int64 v252; // r8
  unsigned __int64 v253; // rax
  char *v254; // rdx
  _WORD *v255; // rdi
  __int64 v256; // rax
  unsigned __int64 v257; // rcx
  char v258; // al
  unsigned __int64 ii; // rax
  _BYTE *v260; // rdi
  int v261; // ecx
  __int16 v262; // r15
  _BYTE *v263; // rcx
  char *v264; // r9
  unsigned __int64 v265; // r8
  unsigned __int64 v266; // rax
  char *v267; // rdx
  _WORD *v268; // rdi
  __int64 v269; // rax
  unsigned __int64 v270; // rcx
  char v271; // al
  unsigned __int64 kk; // rax
  _BYTE *v273; // rdi
  _BYTE *v274; // rcx
  unsigned __int64 v275; // r8
  unsigned __int64 v276; // rax
  char *v277; // rdx
  _WORD *v278; // r9
  __int64 v279; // rax
  __int64 v280; // rcx
  __int16 v281; // bp
  unsigned __int64 v282; // r8
  char v283; // al
  unsigned __int64 mm; // rax
  _BYTE *v285; // rcx
  _BYTE *v286; // r8
  char *v287; // r11
  unsigned __int64 v288; // r9
  unsigned __int64 v289; // rax
  __int64 *v290; // rdx
  _WORD *v291; // rdi
  __int64 v292; // rax
  __int16 v293; // r13
  unsigned __int64 v294; // r8
  char v295; // al
  unsigned __int64 nn; // rax
  _BYTE *v297; // rdi
  _BYTE *v298; // rcx
  unsigned __int64 v299; // r8
  char *v300; // r9
  unsigned __int64 v301; // rax
  char *v302; // rdx
  _WORD *v303; // rdi
  __int64 v304; // rax
  unsigned __int64 v305; // rcx
  char v306; // al
  unsigned __int64 k; // rcx
  _BYTE *v308; // rdi
  unsigned __int64 v309; // r8
  unsigned __int64 v310; // r9
  _BYTE *v311; // rcx
  unsigned __int64 v312; // rax
  _WORD *v313; // rdi
  __int64 v314; // rax
  char v315; // cl
  unsigned __int64 jj; // rax
  _BYTE *v317; // rdi
  size_t v318; // r9
  size_t v319; // rbx
  unsigned __int64 v320; // rax
  int v321; // [rsp+28h] [rbp-130h]
  int v322; // [rsp+40h] [rbp-118h]
  int v323; // [rsp+40h] [rbp-118h]
  int v324; // [rsp+44h] [rbp-114h]
  int v325; // [rsp+44h] [rbp-114h]
  unsigned int v326; // [rsp+48h] [rbp-110h]
  int v327; // [rsp+48h] [rbp-110h]
  _DWORD *v328; // [rsp+50h] [rbp-108h]
  unsigned int v329; // [rsp+58h] [rbp-100h]
  unsigned int v330; // [rsp+58h] [rbp-100h]
  unsigned int v331; // [rsp+5Ch] [rbp-FCh]
  unsigned int v332; // [rsp+5Ch] [rbp-FCh]
  unsigned int v333; // [rsp+60h] [rbp-F8h]
  unsigned int v334; // [rsp+60h] [rbp-F8h]
  unsigned int v335; // [rsp+64h] [rbp-F4h]
  unsigned int v336; // [rsp+64h] [rbp-F4h]
  unsigned __int64 v337; // [rsp+68h] [rbp-F0h]
  int v338; // [rsp+70h] [rbp-E8h]
  __int16 v339; // [rsp+74h] [rbp-E4h]
  _QWORD *v340; // [rsp+78h] [rbp-E0h]
  char *v341; // [rsp+78h] [rbp-E0h]
  _QWORD *v342; // [rsp+78h] [rbp-E0h]
  _QWORD *v343; // [rsp+80h] [rbp-D8h]
  char *v344; // [rsp+80h] [rbp-D8h]
  unsigned __int64 v345; // [rsp+88h] [rbp-D0h]
  int v346; // [rsp+94h] [rbp-C4h]
  int v347; // [rsp+98h] [rbp-C0h]
  int v348; // [rsp+98h] [rbp-C0h]
  __int16 v349; // [rsp+98h] [rbp-C0h]
  unsigned __int64 v350; // [rsp+A0h] [rbp-B8h]
  __int64 v351; // [rsp+A8h] [rbp-B0h]
  char *v352; // [rsp+A8h] [rbp-B0h]
  char *v353; // [rsp+A8h] [rbp-B0h]
  char *v354; // [rsp+B0h] [rbp-A8h]
  _DWORD *v355; // [rsp+B8h] [rbp-A0h]
  __int16 v356; // [rsp+B8h] [rbp-A0h]
  __int16 v357; // [rsp+B8h] [rbp-A0h]
  unsigned __int64 v358; // [rsp+C0h] [rbp-98h]
  unsigned __int64 v359; // [rsp+C0h] [rbp-98h]
  unsigned int v360; // [rsp+C0h] [rbp-98h]
  unsigned int v361; // [rsp+C8h] [rbp-90h]
  int v362; // [rsp+C8h] [rbp-90h]
  unsigned __int64 v363; // [rsp+D0h] [rbp-88h]
  unsigned __int64 v364; // [rsp+D8h] [rbp-80h]
  __int64 v365; // [rsp+E0h] [rbp-78h]
  char *v366; // [rsp+E0h] [rbp-78h]
  int v367; // [rsp+E8h] [rbp-70h]
  char *v368; // [rsp+E8h] [rbp-70h]
  _DWORD *v369; // [rsp+F0h] [rbp-68h]
  unsigned __int64 v370; // [rsp+F0h] [rbp-68h]
  char *v371; // [rsp+F8h] [rbp-60h]
  __int64 v372; // [rsp+F8h] [rbp-60h]
  char *v373; // [rsp+108h] [rbp-50h]
  int v375; // [rsp+168h] [rbp+10h]
  int v376; // [rsp+170h] [rbp+18h]
  unsigned int v378; // [rsp+188h] [rbp+30h]

  v376 = a3;
  v375 = (int)a2;
  v10 = a1;
  if ( *(_QWORD *)(a1 + 262184) )
    return LZ4HC_compress_generic_dictCtx((unsigned int *)a1, a2, a3, a4, a5, v321, a7);
  if ( a7 == 2 && a5 < 1 )
    return 0;
  v12 = *a4;
  if ( (unsigned int)v12 > 0x7E000000 )
    return 0;
  *(_QWORD *)(a1 + 0x40000) += v12;
  v13 = a2;
  v14 = *a4;
  v15 = a2;
  v16 = a3;
  v328 = a2;
  v17 = &a2[v14];
  v354 = a2;
  v373 = &a2[v14];
  v18 = a3 + a5 - 5;
  v351 = a3;
  if ( a7 != 2 )
    v18 = a3 + a5;
  v346 = HIDWORD(a3);
  v350 = v18;
  *a4 = 0;
  if ( (int)v14 >= 13 )
  {
    v364 = (unsigned __int64)(v17 - 12);
    if ( a2 <= v17 - 12 )
    {
      v345 = 0;
      v337 = (unsigned __int64)(v17 - 5);
      v363 = 0;
      while ( 1 )
      {
        v19 = *(unsigned int *)(v10 + 262172);
        v20 = *(_QWORD **)(v10 + 262152);
        v21 = 3;
        v22 = *(unsigned int *)(v10 + 262168);
        v23 = v22 + (_DWORD)v13 - (_DWORD)v20;
        v338 = 3;
        v343 = v20;
        v335 = v23;
        v24 = *(_DWORD *)(v10 + 262172);
        v361 = v24;
        if ( (int)v19 + 0x10000 <= v23 )
          v24 = v23 - 0xFFFF;
        v25 = *(_QWORD **)(v10 + 262160);
        v26 = *(_DWORD *)v13;
        v27 = 0;
        v28 = *(_DWORD *)(v10 + 262176);
        v329 = v24;
        v340 = v25;
        v355 = (_DWORD *)((char *)v25 + v22 - v19);
        v324 = 0;
        v29 = 256;
        v347 = 256;
        v358 = 0;
        v378 = 0;
        if ( v28 < v23 )
        {
          do
          {
            v30 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v20 + v28 - v22)) >> 17;
            v31 = v28 - *(_DWORD *)(v10 + 4 * v30);
            if ( v31 > 0xFFFF )
              LOWORD(v31) = -1;
            *(_WORD *)(v10 + 2LL * (unsigned __int16)v28 + 0x20000) = v31;
            *(_DWORD *)(v10 + 4 * v30) = v28++;
          }
          while ( v28 < v23 );
          v25 = v340;
        }
        v32 = v328;
        *(_DWORD *)(v10 + 262176) = v23;
        v33 = *(_DWORD *)(v10 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *v328) >> 17));
        if ( v33 >= v24 )
        {
          while ( 1 )
          {
            if ( v29 <= 0 )
            {
LABEL_146:
              v16 = v351;
              v10 = a1;
              goto LABEL_147;
            }
            if ( v33 < (unsigned int)v22 )
            {
              if ( v33 > (int)v22 - 4 )
              {
                v34 = v328;
              }
              else if ( *(_DWORD *)((char *)v25 + v33 - v361) == v26 )
              {
                v45 = v32 + 1;
                v46 = (_QWORD *)((char *)v32 + (unsigned int)v22 - v33);
                if ( (unsigned __int64)v46 > v337 )
                  v46 = (_QWORD *)v337;
                v47 = (_QWORD *)((char *)v25 + v33 - v361 + 4);
                if ( v45 >= (_QWORD *)((char *)v46 - 7) )
                {
                  v49 = v32 + 1;
                  while ( v49 < (_QWORD *)((char *)v46 - 7) )
                  {
                    if ( *v47 != *v49 )
                    {
                      __asm { tzcnt   rbx, r8 }
                      v51 = (_DWORD)v49 + ((unsigned int)_RBX >> 3) - (_DWORD)v45;
                      goto LABEL_69;
                    }
                    ++v49;
LABEL_57:
                    ++v47;
                  }
                  if ( v49 < (_QWORD *)((char *)v46 - 3) && *(_DWORD *)v47 == *(_DWORD *)v49 )
                  {
                    v49 = (_QWORD *)((char *)v49 + 4);
                    v47 = (_QWORD *)((char *)v47 + 4);
                  }
                  if ( v49 < (_QWORD *)((char *)v46 - 1) && *(_WORD *)v47 == *(_WORD *)v49 )
                  {
                    v49 = (_QWORD *)((char *)v49 + 2);
                    v47 = (_QWORD *)((char *)v47 + 2);
                  }
                  if ( v49 < v46 && *(_BYTE *)v47 == *(_BYTE *)v49 )
                    LODWORD(v49) = (_DWORD)v49 + 1;
                  v51 = (_DWORD)v49 - (_DWORD)v45;
LABEL_69:
                  v32 = v328;
                }
                else
                {
                  if ( *v45 == *v47 )
                  {
                    v49 = v32 + 3;
                    goto LABEL_57;
                  }
                  __asm { tzcnt   rbx, rcx }
                  v51 = (unsigned int)_RBX >> 3;
                }
                v54 = (_QWORD *)((char *)v32 + v51 + 4);
                v55 = v51 + 4;
                if ( v54 == v46 && (unsigned __int64)v46 < v337 )
                {
                  if ( (unsigned __int64)v54 >= v337 - 7 )
                  {
                    v58 = v20;
                    v57 = v54;
LABEL_77:
                    while ( (unsigned __int64)v57 < v337 - 7 )
                    {
                      if ( *v58 != *v57 )
                      {
                        __asm { tzcnt   rax, r9 }
                        v60 = ((unsigned int)_RAX >> 3) - (_DWORD)v54 + (_DWORD)v57;
                        goto LABEL_91;
                      }
                      ++v57;
                      ++v58;
                    }
                    if ( (unsigned __int64)v57 < v337 - 3 && *(_DWORD *)v58 == *(_DWORD *)v57 )
                    {
                      v57 = (_QWORD *)((char *)v57 + 4);
                      v58 = (_QWORD *)((char *)v58 + 4);
                    }
                    if ( (unsigned __int64)v57 < v337 - 1 && *(_WORD *)v58 == *(_WORD *)v57 )
                    {
                      v57 = (_QWORD *)((char *)v57 + 2);
                      v58 = (_QWORD *)((char *)v58 + 2);
                    }
                    if ( (unsigned __int64)v57 < v337 && *(_BYTE *)v58 == *(_BYTE *)v57 )
                      LODWORD(v57) = (_DWORD)v57 + 1;
                    v60 = (_DWORD)v57 - (_DWORD)v54;
                  }
                  else
                  {
                    if ( *v20 == *v54 )
                    {
                      v57 = v54 + 1;
                      v58 = v20 + 1;
                      goto LABEL_77;
                    }
                    __asm { tzcnt   rcx, rcx }
                    v60 = (unsigned int)_RCX >> 3;
                  }
LABEL_91:
                  v55 = v51 + v60 + 4;
                }
                v27 = v324;
                v34 = v328;
                v10 = a1;
                if ( v55 > v21 )
                {
                  v338 = v55;
                  v378 = v23 - v33;
                }
              }
              else
              {
                v34 = v328;
              }
            }
            else
            {
              v34 = v328;
              v35 = v33 - (unsigned int)v22;
              if ( *(_WORD *)((char *)v328 + v21 - 1) == *(_WORD *)((char *)v20 + v21 + v35 - 1)
                && *(_DWORD *)((char *)v20 + v35) == v26 )
              {
                v36 = v328 + 1;
                v37 = (_QWORD *)((char *)v20 + v35 + 4);
                if ( (unsigned __int64)(v328 + 1) >= v337 - 7 )
                {
                  v39 = v328 + 1;
                  while ( (unsigned __int64)v39 < v337 - 7 )
                  {
                    if ( *v39 != *v37 )
                    {
                      __asm { tzcnt   rax, r8 }
                      v41 = ((unsigned int)_RAX >> 3) - (_DWORD)v36 + (_DWORD)v39;
                      goto LABEL_43;
                    }
                    ++v39;
LABEL_31:
                    ++v37;
                  }
                  if ( (unsigned __int64)v39 < v337 - 3 && *(_DWORD *)v37 == *(_DWORD *)v39 )
                  {
                    v39 = (_QWORD *)((char *)v39 + 4);
                    v37 = (_QWORD *)((char *)v37 + 4);
                  }
                  if ( (unsigned __int64)v39 < v337 - 1 && *(_WORD *)v37 == *(_WORD *)v39 )
                  {
                    v39 = (_QWORD *)((char *)v39 + 2);
                    v37 = (_QWORD *)((char *)v37 + 2);
                  }
                  if ( (unsigned __int64)v39 < v337 && *(_BYTE *)v37 == *(_BYTE *)v39 )
                    LODWORD(v39) = (_DWORD)v39 + 1;
                  v41 = (_DWORD)v39 - (_DWORD)v36;
                }
                else
                {
                  if ( *v36 == *v37 )
                  {
                    v39 = v328 + 3;
                    goto LABEL_31;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v41 = (unsigned int)_RCX >> 3;
                }
LABEL_43:
                v27 = v324;
                v44 = v41 + 4;
                v34 = v328;
                if ( v44 > v21 )
                {
                  v338 = v44;
                  v378 = v23 - v33;
                }
              }
            }
            if ( *(_WORD *)(v10 + 2LL * (unsigned __int16)v33 + 0x20000) != 1 )
              goto LABEL_143;
            if ( v27 )
            {
              v324 = v27;
              if ( v27 != 2 )
                goto LABEL_143;
            }
            else
            {
              if ( (_BYTE)v26 != HIBYTE(v26) || (unsigned __int16)v26 != HIWORD(v26) )
              {
                v27 = 1;
                v324 = 1;
                goto LABEL_143;
              }
              v324 = 2;
              v358 = (unsigned int)LZ4HC_countPattern(v34 + 1, v337, v26) + 4LL;
              v27 = 2;
            }
            v63 = v33 - 1;
            if ( v33 - 1 < v24 || (unsigned int)v22 - v33 < 3 )
              goto LABEL_143;
            if ( v63 >= (unsigned int)v22 )
            {
              v64 = 0;
              v65 = (_DWORD *)((char *)v20 + v63 - (unsigned int)v22);
            }
            else
            {
              v64 = 1;
              v65 = (_DWORD *)((char *)v340 + v63 - v361);
            }
            if ( *v65 != v26 )
              break;
            v66 = (_DWORD *)v337;
            if ( v64 )
              v66 = v355;
            v67 = (unsigned int)LZ4HC_countPattern(v65 + 1, v66, v26) + 4LL;
            if ( v64 )
            {
              if ( (_DWORD *)((char *)v65 + v67) == v66 )
              {
                v68 = v26;
                v69 = 8 * (v67 & 3);
                if ( v69 )
                  v68 = (unsigned int)__ROL4__(v26, v69);
                v20 = v343;
                v67 += (unsigned int)LZ4HC_countPattern(v343, v337, v68);
              }
              else
              {
                v20 = v343;
              }
              v70 = v340;
            }
            else
            {
              v20 = v343;
              v70 = v343;
            }
            v71 = LZ4HC_reverseCountPattern(v65, v70, v26);
            v73 = v71;
            if ( !v64 && (_QWORD *)((char *)v65 - v71) == v20 && v361 < (unsigned int)v22 )
            {
              v74 = 8LL * (-v71 & 3);
              if ( v74 )
                v72 = (unsigned int)__ROL4__(v72, v74);
              v75 = LZ4HC_reverseCountPattern(v355, v340, v72);
              v73 = v75 + v76;
            }
            v24 = v329;
            v77 = v63 - v73;
            v33 = v329;
            if ( v77 > v329 )
              v33 = v77;
            v78 = v67 + v63 - v33;
            if ( v78 < v358 || v67 > v358 )
            {
              if ( (unsigned int)v22 - v33 - 1 >= 3 )
              {
                v32 = v328;
                v79 = v358;
                if ( v78 < v358 )
                  v79 = v67 + v63 - v33;
                if ( v338 >= v79 )
                {
                  v23 = v335;
                }
                else
                {
                  if ( (unsigned __int64)v328 + v22 - v33 - (_QWORD)v20 > 0xFFFF )
                    goto LABEL_146;
                  v23 = v335;
                  v338 = v79;
                  v378 = v335 - v33;
                }
                v10 = a1;
                v80 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v33 + 0x20000);
                if ( v80 > v33 )
                  goto LABEL_146;
                v27 = v324;
                goto LABEL_144;
              }
              v33 = v22;
            }
            else
            {
              v33 = v22;
              if ( (unsigned int)v22 - ((_DWORD)v67 - (_DWORD)v358 + v63) - 1 >= 3 )
                v33 = v67 - v358 + v63;
            }
            v23 = v335;
            v27 = v324;
            v10 = a1;
LABEL_145:
            v25 = v340;
            v29 = v347 - 1;
            v21 = v338;
            v32 = v328;
            --v347;
            if ( v33 < v24 )
              goto LABEL_146;
          }
          v24 = v329;
          v10 = a1;
LABEL_143:
          v80 = *(unsigned __int16 *)(v10 + 2LL * (unsigned __int16)v33 + 0x20000);
LABEL_144:
          v33 -= v80;
          goto LABEL_145;
        }
LABEL_147:
        v81 = v338;
        if ( v338 < 4 )
        {
          v15 = v354;
          v13 = (char *)v32 + 1;
          v328 = v13;
          goto LABEL_619;
        }
        v82 = v378;
        v83 = v32;
        v84 = __PAIR64__(v338, v378) >> 32;
        while ( 1 )
        {
          v85 = v364;
          v367 = v84;
          v369 = v83;
          while ( 1 )
          {
            v86 = v81;
            v365 = v81;
            v87 = (char *)v32 + v81;
            v371 = v87;
            if ( (unsigned __int64)v87 > v85 )
            {
              v164 = 0;
              v163 = 0;
              v339 = 0;
              v325 = 0;
            }
            else
            {
              v88 = *(_QWORD **)(v10 + 262152);
              v89 = (char *)*(unsigned int *)(v10 + 262168);
              v90 = v87 - 2;
              v345 = (unsigned __int64)(v87 - 2);
              v91 = (_DWORD)v87 - 2 + (_DWORD)v89 - (_DWORD)v88;
              v325 = v81;
              v341 = (char *)v88;
              v92 = *(_DWORD *)(a1 + 262172);
              v93 = v92;
              v331 = (unsigned int)v89;
              v356 = (_WORD)v87 - 2 + (_WORD)v89 - (_WORD)v88;
              v336 = v92;
              if ( v92 + 0x10000 <= v91 )
                v93 = v91 - 0xFFFF;
              v94 = *(char **)(a1 + 262160);
              v95 = *(_DWORD *)v90;
              v96 = v89;
              v339 = 0;
              v333 = v93;
              v344 = v94;
              v326 = *(_DWORD *)v90;
              v97 = *(_DWORD *)(a1 + 262176);
              if ( v97 < v91 )
              {
                do
                {
                  v98 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v88 + v97 - (_QWORD)v89)) >> 17;
                  v99 = v97 - *(_DWORD *)(a1 + 4 * v98);
                  if ( v99 > 0xFFFF )
                    LOWORD(v99) = -1;
                  *(_WORD *)(a1 + 2LL * (unsigned __int16)v97 + 0x20000) = v99;
                  *(_DWORD *)(a1 + 4 * v98) = v97++;
                }
                while ( v97 < v91 );
                v95 = v326;
                v96 = v89;
              }
              *(_DWORD *)(a1 + 262176) = v91;
              v100 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)v90) >> 17));
              if ( v100 >= v93 )
              {
                v101 = 256;
                v352 = (char *)v96 + (_QWORD)v94 - v92;
                v102 = (_DWORD)v90 - (_DWORD)v328;
                v348 = 256;
                v103 = 0;
                v322 = 0;
                v359 = 0;
                while ( 1 )
                {
                  if ( v101 <= 0 )
                    goto LABEL_314;
                  if ( v100 >= (unsigned int)v89 )
                    break;
                  if ( v100 > (int)v89 - 4 )
                    goto LABEL_262;
                  v120 = &v94[v100 - v92];
                  if ( *(_DWORD *)v120 != v95 )
                  {
                    v93 = v333;
LABEL_262:
                    v109 = v337;
                    goto LABEL_263;
                  }
                  v121 = v90 + 4;
                  v122 = &v90[(unsigned int)v89 - v100];
                  v123 = v120 + 4;
                  if ( (unsigned __int64)v122 > v337 )
                    v122 = (char *)v337;
                  if ( v121 >= v122 - 7 )
                  {
                    v125 = v90 + 4;
                    while ( v125 < v122 - 7 )
                    {
                      if ( *v123 != *(_QWORD *)v125 )
                      {
                        __asm { tzcnt   rbp, r8 }
                        v127 = (_DWORD)v125 + ((unsigned int)_RBP >> 3) - (_DWORD)v121;
                        goto LABEL_223;
                      }
                      v125 += 8;
LABEL_211:
                      ++v123;
                    }
                    if ( v125 < v122 - 3 && *(_DWORD *)v123 == *(_DWORD *)v125 )
                    {
                      v125 += 4;
                      v123 = (_QWORD *)((char *)v123 + 4);
                    }
                    if ( v125 < v122 - 1 && *(_WORD *)v123 == *(_WORD *)v125 )
                    {
                      v125 += 2;
                      v123 = (_QWORD *)((char *)v123 + 2);
                    }
                    if ( v125 < v122 && *(_BYTE *)v123 == *v125 )
                      LODWORD(v125) = (_DWORD)v125 + 1;
                    v127 = (_DWORD)v125 - (_DWORD)v121;
LABEL_223:
                    v102 = (_DWORD)v90 - (_DWORD)v328;
                  }
                  else
                  {
                    if ( *(_QWORD *)v121 == *v123 )
                    {
                      v125 = v90 + 12;
                      goto LABEL_211;
                    }
                    __asm { tzcnt   rbp, rcx }
                    v127 = (unsigned int)_RBP >> 3;
                  }
                  v130 = v127 + 4;
                  v131 = &v90[v127 + 4];
                  if ( v131 == v122 && (unsigned __int64)v122 < v337 )
                  {
                    if ( (unsigned __int64)v131 >= v337 - 7 )
                    {
                      v134 = v88;
                      v133 = &v90[v127 + 4];
LABEL_231:
                      while ( (unsigned __int64)v133 < v337 - 7 )
                      {
                        if ( *v134 != *(_QWORD *)v133 )
                        {
                          __asm { tzcnt   rax, r8 }
                          v136 = ((unsigned int)_RAX >> 3) - (_DWORD)v131 + (_DWORD)v133;
                          goto LABEL_245;
                        }
                        v133 += 8;
                        ++v134;
                      }
                      if ( (unsigned __int64)v133 < v337 - 3 && *(_DWORD *)v134 == *(_DWORD *)v133 )
                      {
                        v133 += 4;
                        v134 = (_QWORD *)((char *)v134 + 4);
                      }
                      if ( (unsigned __int64)v133 < v337 - 1 && *(_WORD *)v134 == *(_WORD *)v133 )
                      {
                        v133 += 2;
                        v134 = (_QWORD *)((char *)v134 + 2);
                      }
                      if ( (unsigned __int64)v133 < v337 && *(_BYTE *)v134 == *v133 )
                        LODWORD(v133) = (_DWORD)v133 + 1;
                      v136 = (_DWORD)v133 - (_DWORD)v131;
                    }
                    else
                    {
                      if ( *v88 == *(_QWORD *)v131 )
                      {
                        v133 = v131 + 8;
                        v134 = v88 + 1;
                        goto LABEL_231;
                      }
                      __asm { tzcnt   rcx, rcx }
                      v136 = (unsigned int)_RCX >> 3;
                    }
LABEL_245:
                    v102 = (_DWORD)v90 - (_DWORD)v328;
                    v130 = v127 + v136 + 4;
                  }
                  v139 = v344;
                  v140 = 0;
                  if ( v102 )
                  {
                    v141 = (_DWORD)v328 - (_DWORD)v90;
                    if ( (char *)v328 - v90 <= v344 - v120 )
                      v141 = (_DWORD)v344 - (_DWORD)v120;
                    for ( i = -v141; i > 3; i = v140 - v141 )
                    {
                      if ( *(_DWORD *)&v120[v140 - 4] != *(_DWORD *)&v90[v140 - 4] )
                      {
                        _BitScanReverse(&v144, *(_DWORD *)&v120[v140 - 4] ^ *(_DWORD *)&v90[v140 - 4]);
                        v140 -= (31 - v144) >> 3;
                        goto LABEL_256;
                      }
                      v140 -= 4;
                    }
                    for ( ; v140 > v141; --v140 )
                    {
                      if ( v90[v140 - 1] != v120[v140 - 1] )
                        break;
                    }
                  }
LABEL_256:
                  v95 = v326;
                  v143 = v130 - v140;
                  v93 = v333;
                  v109 = v337;
                  if ( v143 > v325 )
                  {
                    v325 = v143;
                    v339 = v356 - v100;
                    v345 = (unsigned __int64)&v90[v140];
                  }
                  LODWORD(v89) = v331;
                  v103 = v322;
LABEL_264:
                  v145 = a1;
                  if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v100 + 0x20000) != 1 )
                    goto LABEL_269;
                  if ( v103 )
                  {
                    v322 = v103;
                    if ( v103 != 2 )
                      goto LABEL_269;
                  }
                  else
                  {
                    if ( (_BYTE)v95 != HIBYTE(v95) || (unsigned __int16)v95 != HIWORD(v95) )
                    {
                      v103 = 1;
                      v322 = 1;
LABEL_269:
                      LODWORD(v89) = v331;
                      v93 = v333;
                      v147 = *(unsigned __int16 *)(v145 + 2LL * (unsigned __int16)v100 + 0x20000);
                      goto LABEL_270;
                    }
                    v322 = 2;
                    v146 = LZ4HC_countPattern(v90 + 4, v109, v95);
                    v103 = 2;
                    v359 = v146 + 4LL;
                    v145 = a1;
                  }
                  v148 = v100 - 1;
                  if ( v100 - 1 < v93 || (unsigned int)v89 - v100 < 3 )
                    goto LABEL_269;
                  if ( v148 >= (unsigned int)v89 )
                  {
                    v149 = 0;
                    v89 = &v341[v148 - (unsigned int)v89];
                  }
                  else
                  {
                    v149 = 1;
                    v89 = &v139[v148 - v336];
                  }
                  if ( *(_DWORD *)v89 != v95 )
                    goto LABEL_269;
                  v150 = (char *)v337;
                  if ( v149 )
                    v150 = v352;
                  v151 = (unsigned int)LZ4HC_countPattern(v89 + 4, v150, v95) + 4LL;
                  if ( v149 )
                  {
                    if ( &v89[v151] == v150 )
                    {
                      v152 = v326;
                      v153 = 8 * (v151 & 3);
                      if ( v153 )
                        v152 = (unsigned int)__ROL4__(v326, v153);
                      v151 += (unsigned int)LZ4HC_countPattern(v341, v337, v152);
                    }
                    v154 = v344;
                  }
                  else
                  {
                    v154 = v341;
                  }
                  v155 = LZ4HC_reverseCountPattern(v89, v154, v326);
                  v156 = v341;
                  v157 = v155;
                  if ( v149 )
                  {
                    LODWORD(v89) = v331;
                  }
                  else
                  {
                    v158 = &v89[-v155] == v341;
                    LODWORD(v89) = v331;
                    if ( v158 && v336 < v331 )
                    {
                      v159 = v326;
                      v160 = 8LL * (-v155 & 3);
                      if ( v160 )
                        v159 = (unsigned int)__ROL4__(v326, v160);
                      v157 = LZ4HC_reverseCountPattern(v352, v344, v159) + v155;
                      v156 = v341;
                    }
                  }
                  v93 = v333;
                  v100 = v333;
                  if ( v148 - v157 > v333 )
                    v100 = v148 - v157;
                  v161 = v151 + v148 - v100;
                  if ( v161 >= v359 && v151 <= v359 )
                  {
                    v100 = (unsigned int)v89;
                    if ( (unsigned int)v89 - (v148 + (_DWORD)v151 - (_DWORD)v359) - 1 >= 3 )
                      v100 = v148 + v151 - v359;
                    goto LABEL_313;
                  }
                  if ( (unsigned int)v89 - v100 - 1 < 3 )
                  {
                    v100 = (unsigned int)v89;
LABEL_313:
                    v103 = v322;
                    goto LABEL_271;
                  }
                  if ( (_DWORD)v90 != (_DWORD)v328 )
                    goto LABEL_313;
                  v162 = v359;
                  if ( v161 < v359 )
                    v162 = v151 + v148 - v100;
                  if ( v325 < v162 )
                  {
                    if ( (unsigned __int64)&v90[(unsigned int)v89 - (unsigned __int64)v100 - (_QWORD)v156] > 0xFFFF )
                      goto LABEL_314;
                    v325 = v162;
                    v339 = v356 - v100;
                    v345 = (unsigned __int64)v90;
                  }
                  v147 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v100 + 0x20000);
                  if ( v147 > v100 )
                    goto LABEL_314;
                  v103 = v322;
LABEL_270:
                  v100 -= v147;
LABEL_271:
                  v95 = v326;
                  v101 = v348 - 1;
                  v88 = v341;
                  LOWORD(v91) = v356;
                  v102 = (_DWORD)v90 - (_DWORD)v328;
                  v92 = v336;
                  v94 = v344;
                  --v348;
                  if ( v100 < v93 )
                    goto LABEL_314;
                }
                v104 = (_DWORD *)((char *)v88 + v100 - (unsigned int)v89);
                if ( *(_WORD *)((char *)v328 + v325 - 1) != *(_WORD *)((char *)v104 + v325 - (__int64)v102 - 1)
                  || *v104 != v95 )
                {
                  v103 = v322;
                  goto LABEL_262;
                }
                v105 = 0;
                if ( v102 )
                {
                  v106 = -(__int64)(v100 - (unsigned int)v89);
                  v107 = (_DWORD)v328 - (_DWORD)v90;
                  if ( (char *)v328 - v90 <= v106 )
                    v107 = v106;
                  for ( j = -v107; j > 3; j = v105 - v107 )
                  {
                    if ( *(_DWORD *)&v90[v105 - 4] != *(_DWORD *)((char *)v104 + v105 - 4) )
                    {
                      _BitScanReverse(&v114, *(_DWORD *)&v90[v105 - 4] ^ *(_DWORD *)((char *)v104 + v105 - 4));
                      v105 -= (31 - v114) >> 3;
                      goto LABEL_176;
                    }
                    v105 -= 4;
                  }
                  if ( v105 > v107 )
                  {
                    do
                    {
                      if ( v90[v105 - 1] != *((_BYTE *)v104 + v105 - 1) )
                        break;
                      --v105;
                    }
                    while ( v105 > v107 );
                    v93 = v333;
                  }
                }
LABEL_176:
                v109 = v337;
                v110 = v90 + 4;
                v111 = v104 + 1;
                if ( (unsigned __int64)(v90 + 4) >= v337 - 7 )
                {
                  v113 = v90 + 4;
                  while ( (unsigned __int64)v113 < v337 - 7 )
                  {
                    if ( *v111 != *v113 )
                    {
                      __asm { tzcnt   rax, r8 }
                      v116 = ((unsigned int)_RAX >> 3) - (_DWORD)v110 + (_DWORD)v113;
                      goto LABEL_197;
                    }
                    ++v113;
LABEL_185:
                    ++v111;
                  }
                  if ( (unsigned __int64)v113 < v337 - 3 && *(_DWORD *)v111 == *(_DWORD *)v113 )
                  {
                    v113 = (_QWORD *)((char *)v113 + 4);
                    v111 = (_QWORD *)((char *)v111 + 4);
                  }
                  if ( (unsigned __int64)v113 < v337 - 1 && *(_WORD *)v111 == *(_WORD *)v113 )
                  {
                    v113 = (_QWORD *)((char *)v113 + 2);
                    v111 = (_QWORD *)((char *)v111 + 2);
                  }
                  if ( (unsigned __int64)v113 < v337 && *(_BYTE *)v111 == *(_BYTE *)v113 )
                    LODWORD(v113) = (_DWORD)v113 + 1;
                  v116 = (_DWORD)v113 - (_DWORD)v110;
                }
                else
                {
                  if ( *v110 == *v111 )
                  {
                    v113 = v90 + 12;
                    goto LABEL_185;
                  }
                  __asm { tzcnt   rcx, rcx }
                  v116 = (unsigned int)_RCX >> 3;
                }
LABEL_197:
                LODWORD(v89) = v331;
                v103 = v322;
                v119 = v116 - v105 + 4;
                if ( v119 > v325 )
                {
                  v325 = v119;
                  v345 = (unsigned __int64)&v90[v105];
                  v339 = v91 - v100;
                }
LABEL_263:
                v139 = v344;
                goto LABEL_264;
              }
LABEL_314:
              LODWORD(v84) = v367;
              v83 = v369;
              v87 = v371;
              v86 = v365;
              v163 = v325;
              v81 = v338;
              v32 = v328;
              v164 = v339;
              v85 = v364;
            }
            if ( v163 <= v81 )
            {
              v15 = v354;
              v298 = (_BYTE *)(v16 + 1);
              v18 = v350;
              v249 = v16 >> 32;
              v299 = (char *)v32 - v354;
              v250 = v16;
              v300 = (char *)v16;
              if ( a7 && (unsigned __int64)&v298[v299 + 8 + v299 / 0xFF] > v350 )
                goto LABEL_625;
              if ( v299 < 0xF )
              {
                *(_BYTE *)v16 = 16 * v299;
              }
              else
              {
                v301 = v299 - 15;
                *(_BYTE *)v16 = -16;
                while ( v301 >= 0xFF )
                {
                  *v298++ = -1;
                  v301 -= 255LL;
                }
                *v298++ = v301;
              }
              v302 = v354;
              v303 = &v298[v299];
              do
              {
                v304 = *(_QWORD *)v302;
                v302 += 8;
                *(_QWORD *)v298 = v304;
                v298 += 8;
              }
              while ( v298 < (_BYTE *)v303 );
              v305 = v86 - 4;
              *v303 = v378;
              v16 = (__int64)(v303 + 1);
              v351 = v16;
              v346 = HIDWORD(v16);
              if ( a7 )
              {
                if ( v16 + v305 / 0xFF + 6 > v350 )
                  goto LABEL_625;
              }
              v306 = *v300;
              if ( v305 < 0xF )
              {
                *v300 = v306 + v305;
              }
              else
              {
                *v300 = v306 + 15;
                for ( k = v86 - 19; k >= 0x1FE; k -= 510LL )
                {
                  *(_BYTE *)v16 = -1;
                  v308 = (_BYTE *)(v16 + 1);
                  *v308 = -1;
                  v16 = (__int64)(v308 + 1);
                }
                if ( k >= 0xFF )
                {
                  LOBYTE(k) = k + 1;
                  *(_BYTE *)v16++ = -1;
                }
                *(_BYTE *)v16++ = k;
                v351 = v16;
                v346 = HIDWORD(v16);
              }
              v13 = v87;
              v328 = v87;
              v15 = v87;
              v354 = v87;
              goto LABEL_619;
            }
            v165 = v345;
            if ( v83 < v32 && v345 < (unsigned __int64)v32 + (int)v84 )
            {
              v32 = v83;
              v328 = v83;
              LOWORD(v378) = v82;
              v81 = v84;
              v338 = v84;
            }
            if ( (__int64)(v345 - (_QWORD)v32) >= 3 )
              break;
            v32 = (_DWORD *)v345;
            v328 = (_DWORD *)v345;
            v10 = a1;
            v81 = v163;
            LOWORD(v378) = v164;
            v338 = v163;
          }
LABEL_322:
          if ( (__int64)(v165 - (_QWORD)v32) < 18 )
          {
            v166 = v81;
            if ( v81 > 18 )
              v166 = 18;
            if ( (unsigned __int64)v32 + v166 > v165 + v163 - 4LL )
              v166 = v163 + v165 - (_DWORD)v32 - 4;
            v167 = v166 + (_DWORD)v32 - v165;
            if ( v167 > 0 )
            {
              v165 += v167;
              v163 -= v167;
              v345 = v165;
              v325 = v163;
            }
          }
          v168 = v163;
          v372 = v163;
          v169 = (char *)(v163 + v165);
          v366 = v169;
          if ( (unsigned __int64)v169 > v85 )
          {
            v245 = 0;
            v244 = 0;
          }
          else
          {
            v327 = v163;
            v363 = (unsigned __int64)(v169 - 3);
            v170 = v169 - 3;
            v171 = *(_DWORD *)(a1 + 262172);
            v172 = v171;
            v173 = *(_QWORD **)(a1 + 262152);
            v174 = (char *)*(unsigned int *)(a1 + 262168);
            v175 = (_DWORD)v174 + (_DWORD)v169 - 3 - (_DWORD)v173;
            v342 = v173;
            v334 = *(_DWORD *)(a1 + 262168);
            v349 = v175;
            v360 = v171;
            if ( v171 + 0x10000 <= v175 )
              v172 = v175 - 0xFFFF;
            v176 = *(char **)(a1 + 262160);
            v177 = *(_DWORD *)(a1 + 262176);
            v178 = *(_DWORD *)v170;
            v332 = v172;
            v353 = v176;
            v330 = *(_DWORD *)v170;
            v357 = 0;
            if ( v177 < v175 )
            {
              do
              {
                v179 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)((char *)v173 + v177 - (_QWORD)v174)) >> 17;
                v180 = v177 - *(_DWORD *)(a1 + 4 * v179);
                if ( v180 > 0xFFFF )
                  LOWORD(v180) = -1;
                *(_WORD *)(a1 + 2LL * (unsigned __int16)v177 + 0x20000) = v180;
                *(_DWORD *)(a1 + 4 * v179) = v177++;
              }
              while ( v177 < v175 );
              v178 = v330;
              v171 = v360;
            }
            *(_DWORD *)(a1 + 262176) = v175;
            v181 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)v170) >> 17));
            if ( v181 >= v172 )
            {
              v182 = 256;
              v368 = &v174[(_QWORD)v176 - v171];
              v183 = (_DWORD)v170 - v345;
              v362 = 256;
              v184 = 0;
              v323 = 0;
              v370 = 0;
              v185 = 1;
              while ( 1 )
              {
                if ( v182 <= 0 )
                  goto LABEL_493;
                if ( v181 < (unsigned int)v174 )
                {
                  if ( v181 <= (int)v174 - 4 )
                  {
                    v203 = &v176[v181 - v171];
                    if ( *(_DWORD *)v203 == v178 )
                    {
                      v204 = v170 + 4;
                      v205 = &v170[(unsigned int)v174 - v181];
                      v206 = v203 + 4;
                      if ( (unsigned __int64)v205 > v337 )
                        v205 = (char *)v337;
                      if ( v204 >= v205 - 7 )
                      {
                        v208 = v170 + 4;
                        while ( v208 < v205 - 7 )
                        {
                          if ( *v206 != *(_QWORD *)v208 )
                          {
                            __asm { tzcnt   rsi, r8 }
                            v210 = (_DWORD)v208 + ((unsigned int)_RSI >> 3) - (_DWORD)v204;
                            goto LABEL_406;
                          }
                          v208 += 8;
LABEL_394:
                          ++v206;
                        }
                        if ( v208 < v205 - 3 && *(_DWORD *)v206 == *(_DWORD *)v208 )
                        {
                          v208 += 4;
                          v206 = (_QWORD *)((char *)v206 + 4);
                        }
                        if ( v208 < v205 - 1 && *(_WORD *)v206 == *(_WORD *)v208 )
                        {
                          v208 += 2;
                          v206 = (_QWORD *)((char *)v206 + 2);
                        }
                        if ( v208 < v205 && *(_BYTE *)v206 == *v208 )
                          LODWORD(v208) = (_DWORD)v208 + 1;
                        v210 = (_DWORD)v208 - (_DWORD)v204;
LABEL_406:
                        v183 = (_DWORD)v170 - v345;
                      }
                      else
                      {
                        if ( *v206 == *(_QWORD *)v204 )
                        {
                          v208 = v170 + 12;
                          goto LABEL_394;
                        }
                        __asm { tzcnt   rsi, rcx }
                        v210 = (unsigned int)_RSI >> 3;
                      }
                      v213 = v210 + 4;
                      v214 = &v170[v210 + 4];
                      if ( v214 == v205 && (unsigned __int64)v205 < v337 )
                      {
                        if ( (unsigned __int64)v214 >= v337 - 7 )
                        {
                          v217 = v173;
                          v216 = &v170[v210 + 4];
LABEL_414:
                          while ( (unsigned __int64)v216 < v337 - 7 )
                          {
                            if ( *v217 != *(_QWORD *)v216 )
                            {
                              __asm { tzcnt   rax, r8 }
                              v219 = ((unsigned int)_RAX >> 3) - (_DWORD)v214 + (_DWORD)v216;
                              goto LABEL_428;
                            }
                            v216 += 8;
                            ++v217;
                          }
                          if ( (unsigned __int64)v216 < v337 - 3 && *(_DWORD *)v217 == *(_DWORD *)v216 )
                          {
                            v216 += 4;
                            v217 = (_QWORD *)((char *)v217 + 4);
                          }
                          if ( (unsigned __int64)v216 < v337 - 1 && *(_WORD *)v217 == *(_WORD *)v216 )
                          {
                            v216 += 2;
                            v217 = (_QWORD *)((char *)v217 + 2);
                          }
                          if ( (unsigned __int64)v216 < v337 && *(_BYTE *)v217 == *v216 )
                            LODWORD(v216) = (_DWORD)v216 + 1;
                          v219 = (_DWORD)v216 - (_DWORD)v214;
                        }
                        else
                        {
                          if ( *(_QWORD *)v214 == *v173 )
                          {
                            v216 = v214 + 8;
                            v217 = v173 + 1;
                            goto LABEL_414;
                          }
                          __asm { tzcnt   rcx, rcx }
                          v219 = (unsigned int)_RCX >> 3;
                        }
LABEL_428:
                        v183 = (_DWORD)v170 - v345;
                        v213 = v210 + v219 + 4;
                      }
                      v222 = 0;
                      if ( v183 )
                      {
                        v223 = v345 - (_DWORD)v170;
                        if ( (__int64)(v345 - (_QWORD)v170) <= v353 - v203 )
                          v223 = (_DWORD)v353 - (_DWORD)v203;
                        for ( m = -v223; m > 3; m = v222 - v223 )
                        {
                          if ( *(_DWORD *)&v170[v222 - 4] != *(_DWORD *)&v203[v222 - 4] )
                          {
                            _BitScanReverse(&v226, *(_DWORD *)&v170[v222 - 4] ^ *(_DWORD *)&v203[v222 - 4]);
                            v222 -= (31 - v226) >> 3;
                            goto LABEL_440;
                          }
                          v222 -= 4;
                        }
                        if ( v222 > v223 )
                        {
                          do
                          {
                            if ( v170[v222 - 1] != v203[v222 - 1] )
                              break;
                            --v222;
                          }
                          while ( v222 > v223 );
                          LOWORD(v175) = v349;
                        }
                      }
LABEL_440:
                      LODWORD(v174) = v334;
                      v225 = v213 - v222;
                      v185 = 1;
                      v178 = v330;
                      v172 = v332;
                      if ( v225 > v327 )
                      {
                        v327 = v225;
                        v357 = v175 - v181;
                        v363 = (unsigned __int64)&v170[v222];
                      }
                      v184 = v323;
                    }
                    else
                    {
                      v172 = v332;
                    }
                  }
                }
                else
                {
                  v186 = (_DWORD *)((char *)v173 + v181 - (unsigned int)v174);
                  if ( *(_WORD *)(v327 + v345 - 1) == *(_WORD *)((char *)v186 + v327 - (__int64)v183 - 1)
                    && *v186 == v178 )
                  {
                    v187 = 0;
                    if ( v183 )
                    {
                      v188 = -(__int64)(v181 - (unsigned int)v174);
                      v189 = v345 - (_DWORD)v170;
                      if ( (__int64)(v345 - (_QWORD)v170) <= v188 )
                        v189 = v188;
                      for ( n = -v189; n > 3; n = v187 - v189 )
                      {
                        if ( *(_DWORD *)((char *)v186 + v187 - 4) != *(_DWORD *)&v170[v187 - 4] )
                        {
                          _BitScanReverse(&v195, *(_DWORD *)((char *)v186 + v187 - 4) ^ *(_DWORD *)&v170[v187 - 4]);
                          v187 -= (31 - v195) >> 3;
                          goto LABEL_354;
                        }
                        v187 -= 4;
                      }
                      if ( v187 > v189 )
                      {
                        do
                        {
                          if ( v170[v187 - 1] != *((_BYTE *)v186 + v187 - 1) )
                            break;
                          --v187;
                        }
                        while ( v187 > v189 );
                        v173 = v342;
                      }
                    }
LABEL_354:
                    v191 = v186 + 1;
                    v192 = v170 + 4;
                    if ( (unsigned __int64)(v170 + 4) >= v337 - 7 )
                    {
                      v194 = v170 + 4;
                      while ( (unsigned __int64)v194 < v337 - 7 )
                      {
                        if ( *v191 != *v194 )
                        {
                          __asm { tzcnt   rax, r8 }
                          v197 = ((unsigned int)_RAX >> 3) - (_DWORD)v192 + (_DWORD)v194;
                          goto LABEL_375;
                        }
                        ++v194;
LABEL_363:
                        ++v191;
                      }
                      if ( (unsigned __int64)v194 < v337 - 3 && *(_DWORD *)v191 == *(_DWORD *)v194 )
                      {
                        v194 = (_QWORD *)((char *)v194 + 4);
                        v191 = (_QWORD *)((char *)v191 + 4);
                      }
                      if ( (unsigned __int64)v194 < v337 - 1 && *(_WORD *)v191 == *(_WORD *)v194 )
                      {
                        v194 = (_QWORD *)((char *)v194 + 2);
                        v191 = (_QWORD *)((char *)v191 + 2);
                      }
                      if ( (unsigned __int64)v194 < v337 && *(_BYTE *)v191 == *(_BYTE *)v194 )
                        LODWORD(v194) = (_DWORD)v194 + 1;
                      v197 = (_DWORD)v194 - (_DWORD)v192;
                    }
                    else
                    {
                      if ( *v191 == *v192 )
                      {
                        v194 = v170 + 12;
                        goto LABEL_363;
                      }
                      __asm { tzcnt   rcx, rcx }
                      v197 = (unsigned int)_RCX >> 3;
                    }
LABEL_375:
                    v184 = v323;
                    v200 = v197 - v187 + 4;
                    if ( v200 > v327 )
                    {
                      v327 = v200;
                      v357 = v175 - v181;
                      v363 = (unsigned __int64)&v170[v187];
                    }
                  }
                  v185 = 1;
                }
                v201 = a1;
                if ( *(_WORD *)(a1 + 2LL * (unsigned __int16)v181 + 0x20000) != 1 )
                  goto LABEL_446;
                if ( v184 )
                {
                  v323 = v184;
                  if ( v184 != 2 )
                    goto LABEL_446;
                }
                else
                {
                  if ( (_BYTE)v178 != HIBYTE(v178) || (unsigned __int16)v178 != HIWORD(v178) )
                  {
                    v184 = 1;
                    v323 = 1;
LABEL_446:
                    LODWORD(v174) = v334;
                    v172 = v332;
                    v227 = *(unsigned __int16 *)(v201 + 2LL * (unsigned __int16)v181 + 0x20000);
                    goto LABEL_447;
                  }
                  v323 = 2;
                  v202 = LZ4HC_countPattern(v170 + 4, v337, v178);
                  v201 = a1;
                  v185 = v184 - 1;
                  v370 = v202 + 4LL;
                }
                v228 = v181 - 1;
                if ( v181 - 1 < v172 || (unsigned int)v174 - v228 - v185 < 3 )
                  goto LABEL_446;
                if ( v228 >= (unsigned int)v174 )
                {
                  v229 = 0;
                  v174 = (char *)v173 + v228 - (unsigned int)v174;
                }
                else
                {
                  v229 = v185;
                  v174 = &v353[v228 - v360];
                }
                if ( *(_DWORD *)v174 != v178 )
                  goto LABEL_446;
                v230 = (char *)v337;
                if ( v229 )
                  v230 = v368;
                v231 = (unsigned int)LZ4HC_countPattern(v174 + 4, v230, v330) + 4LL;
                if ( v229 )
                {
                  if ( &v174[v231] == v230 )
                  {
                    v232 = v330;
                    v233 = 8 * (v231 & 3);
                    if ( v233 )
                      v232 = (unsigned int)__ROL4__(v330, v233);
                    v234 = (char *)v342;
                    v231 += (unsigned int)LZ4HC_countPattern(v342, v337, v232);
                  }
                  else
                  {
                    v234 = (char *)v342;
                  }
                  v235 = v353;
                }
                else
                {
                  v234 = (char *)v342;
                  v235 = (char *)v342;
                }
                v178 = v330;
                v236 = LZ4HC_reverseCountPattern(v174, v235, v330);
                v238 = v236;
                if ( v229 )
                {
                  LODWORD(v174) = v334;
                }
                else
                {
                  v158 = &v174[-v236] == v234;
                  LODWORD(v174) = v334;
                  if ( v158 && v360 < v334 )
                  {
                    v239 = 8LL * (-v236 & 3);
                    if ( v239 )
                      v237 = (unsigned int)__ROL4__(v237, v239);
                    v240 = LZ4HC_reverseCountPattern(v368, v353, v237);
                    v238 = v240 + v241;
                  }
                }
                v172 = v332;
                v181 = v332;
                if ( v228 - v238 > v332 )
                  v181 = v228 - v238;
                v242 = v231 + v228 - v181;
                if ( v242 >= v370 && v231 <= v370 )
                {
                  v181 = (unsigned int)v174;
                  if ( (unsigned int)v174 - ((_DWORD)v231 - (_DWORD)v370 + v228) - 1 >= 3 )
                    v181 = v231 - v370 + v228;
                  goto LABEL_491;
                }
                if ( (unsigned int)v174 - v181 - 1 < 3 )
                {
                  v181 = (unsigned int)v174;
LABEL_491:
                  v173 = v342;
                  v184 = v323;
                  goto LABEL_448;
                }
                if ( (_DWORD)v170 != (_DWORD)v345 )
                  goto LABEL_491;
                v173 = v342;
                v243 = v370;
                if ( v242 < v370 )
                  v243 = v242;
                if ( v327 < v243 )
                {
                  if ( (unsigned __int64)&v170[(unsigned int)v174 - (unsigned __int64)v181 - (_QWORD)v342] > 0xFFFF )
                    goto LABEL_493;
                  v327 = v243;
                  v357 = v349 - v181;
                  v363 = (unsigned __int64)v170;
                }
                v227 = *(unsigned __int16 *)(a1 + 2LL * (unsigned __int16)v181 + 0x20000);
                if ( v227 > v181 )
                  goto LABEL_493;
                v184 = v323;
LABEL_447:
                v181 -= v227;
LABEL_448:
                v185 = 1;
                LOWORD(v175) = v349;
                v182 = v362 - 1;
                v183 = (_DWORD)v170 - v345;
                v171 = v360;
                v176 = v353;
                --v362;
                if ( v181 < v172 )
                  goto LABEL_493;
              }
            }
            v363 = (unsigned __int64)v170;
LABEL_493:
            v244 = v327;
            v245 = v357;
            v169 = v366;
            v168 = v372;
            v163 = v325;
            v81 = v338;
            v32 = v328;
            v165 = v345;
            v85 = v364;
          }
          if ( v244 <= v163 )
            break;
          v246 = (unsigned __int64)v32 + v81;
          if ( v363 >= v246 + 3 )
          {
            if ( v165 < v246 )
            {
              if ( (__int64)(v165 - (_QWORD)v32) >= 18 )
              {
                v81 = v165 - (_DWORD)v32;
              }
              else
              {
                if ( v81 > 18 )
                  v81 = 18;
                if ( (_DWORD *)((char *)v32 + v81) > (_DWORD *)v169 - 1 )
                  v81 = v163 + v165 - (_DWORD)v32 - 4;
                v247 = v81 + (_DWORD)v32 - v165;
                if ( v247 > 0 )
                {
                  v345 = v247 + v165;
                  v163 -= v247;
                }
              }
            }
            v248 = (_BYTE *)(v16 + 1);
            LODWORD(v249) = v346;
            v250 = v16;
            v18 = v350;
            v251 = (char *)v16;
            v252 = (char *)v32 - v354;
            if ( a7 && (unsigned __int64)&v248[v252 + 8 + v252 / 0xFF] > v350 )
            {
              v15 = v354;
              goto LABEL_625;
            }
            if ( v252 < 0xF )
            {
              *(_BYTE *)v16 = 16 * v252;
            }
            else
            {
              v253 = v252 - 15;
              *(_BYTE *)v16 = -16;
              while ( v253 >= 0xFF )
              {
                *v248++ = -1;
                v253 -= 255LL;
              }
              *v248++ = v253;
            }
            v254 = v354;
            v255 = &v248[v252];
            do
            {
              v256 = *(_QWORD *)v254;
              v254 += 8;
              *(_QWORD *)v248 = v256;
              v248 += 8;
            }
            while ( v248 < (_BYTE *)v255 );
            *v255 = v378;
            v16 = (__int64)(v255 + 1);
            v346 = HIDWORD(v16);
            v257 = v81 - 4LL;
            if ( a7 && v16 + v257 / 0xFF + 6 > v350 )
            {
              v15 = v354;
              goto LABEL_625;
            }
            v258 = *v251;
            if ( v257 < 0xF )
            {
              *v251 = v258 + v257;
            }
            else
            {
              *v251 = v258 + 15;
              for ( ii = v81 - 19LL; ii >= 0x1FE; ii -= 510LL )
              {
                *(_BYTE *)v16 = -1;
                v260 = (_BYTE *)(v16 + 1);
                *v260 = -1;
                v16 = (__int64)(v260 + 1);
              }
              if ( ii >= 0xFF )
              {
                LOBYTE(ii) = ii + 1;
                *(_BYTE *)v16++ = -1;
              }
              *(_BYTE *)v16++ = ii;
              v346 = HIDWORD(v16);
            }
            v85 = v364;
            v32 = (_DWORD *)v345;
            v354 = (char *)v328 + v81;
            LOWORD(v378) = v339;
            v165 = v363;
            v81 = v163;
            v338 = v163;
            v345 = v363;
            v163 = v244;
            v328 = v32;
            v339 = v245;
            v325 = v244;
            goto LABEL_322;
          }
          if ( v363 < v246 )
          {
            v165 = v363;
            v345 = v363;
            v339 = v245;
            v163 = v244;
            v325 = v244;
            goto LABEL_322;
          }
          if ( v165 >= v246 )
            goto LABEL_533;
          v261 = v81 + (_DWORD)v32 - v165;
          v163 -= v261;
          if ( v163 >= 4 )
          {
            v345 = v261 + v165;
LABEL_533:
            v262 = v339;
            goto LABEL_534;
          }
          v345 = v363;
          v262 = v245;
          v163 = v244;
LABEL_534:
          v263 = (_BYTE *)(v16 + 1);
          v250 = v16;
          v249 = v16 >> 32;
          v264 = (char *)v16;
          v265 = (char *)v32 - v354;
          if ( a7 && (unsigned __int64)&v263[v265 + 8 + v265 / 0xFF] > v350 )
          {
            v15 = v354;
            goto LABEL_624;
          }
          if ( v265 < 0xF )
          {
            *(_BYTE *)v16 = 16 * v265;
          }
          else
          {
            v266 = v265 - 15;
            *(_BYTE *)v16 = -16;
            while ( v266 >= 0xFF )
            {
              *v263++ = -1;
              v266 -= 255LL;
            }
            *v263++ = v266;
          }
          v267 = v354;
          v268 = &v263[v265];
          do
          {
            v269 = *(_QWORD *)v267;
            v267 += 8;
            *(_QWORD *)v263 = v269;
            v263 += 8;
          }
          while ( v263 < (_BYTE *)v268 );
          v270 = v81 - 4LL;
          *v268 = v378;
          v16 = (__int64)(v268 + 1);
          v346 = HIDWORD(v16);
          if ( a7 && v16 + v270 / 0xFF + 6 > v350 )
          {
            v15 = v354;
LABEL_624:
            v18 = v350;
LABEL_625:
            v281 = v378;
LABEL_626:
            v287 = (char *)v328;
LABEL_627:
            if ( a7 != 2 )
              goto LABEL_660;
            v309 = v287 - v15;
            v16 = __PAIR64__(v249, v250);
            v310 = (v287 - v15 + 240) / 0xFFuLL + v287 - v15 + 1;
            if ( v310 + __PAIR64__(v249, v250) <= v18 - 3 )
            {
              if ( v81 > 255 * (v18 - 3 - v310 - __PAIR64__(v249, v250)) + 18 )
                v81 = 255 * (v18 - 3 - v310 - v250) + 18;
              if ( (__int64)(v81 + v18 - v310 - __PAIR64__(v249, v250) + 2) >= 12 )
              {
                v311 = (_BYTE *)(__PAIR64__(v249, v250) + 1);
                if ( v309 < 0xF )
                {
                  *(_BYTE *)__PAIR64__(v249, v250) = 16 * v309;
                }
                else
                {
                  v312 = v309 - 15;
                  *(_BYTE *)__PAIR64__(v249, v250) = -16;
                  while ( v312 >= 0xFF )
                  {
                    *v311++ = -1;
                    v312 -= 255LL;
                  }
                  *v311++ = v312;
                }
                v313 = &v311[v309];
                do
                {
                  v314 = *(_QWORD *)v15;
                  v15 += 8;
                  *(_QWORD *)v311 = v314;
                  v311 += 8;
                }
                while ( v311 < (_BYTE *)v313 );
                *v313 = v281;
                v315 = *(_BYTE *)__PAIR64__(v249, v250);
                v16 = (__int64)(v313 + 1);
                if ( (unsigned __int64)(v81 - 4LL) < 0xF )
                {
                  *(_BYTE *)__PAIR64__(v249, v250) = v315 + v81 - 4;
                }
                else
                {
                  *(_BYTE *)__PAIR64__(v249, v250) = v315 + 15;
                  for ( jj = v81 - 19LL; jj >= 0x1FE; jj -= 510LL )
                  {
                    *(_BYTE *)v16 = -1;
                    v317 = (_BYTE *)(v16 + 1);
                    *v317 = -1;
                    v16 = (__int64)(v317 + 1);
                  }
                  if ( jj >= 0xFF )
                  {
                    LOBYTE(jj) = jj + 1;
                    *(_BYTE *)v16++ = -1;
                  }
                  *(_BYTE *)v16++ = jj;
                }
                v15 = &v287[v81];
              }
            }
            v318 = v373 - v15;
            v319 = v373 - v15;
            goto LABEL_656;
          }
          v271 = *v264;
          if ( v270 < 0xF )
          {
            *v264 = v271 + v270;
          }
          else
          {
            *v264 = v271 + 15;
            for ( kk = v81 - 19LL; kk >= 0x1FE; kk -= 510LL )
            {
              *(_BYTE *)v16 = -1;
              v273 = (_BYTE *)(v16 + 1);
              *v273 = -1;
              v16 = (__int64)(v273 + 1);
            }
            if ( kk >= 0xFF )
            {
              LOBYTE(kk) = kk + 1;
              *(_BYTE *)v16++ = -1;
            }
            *(_BYTE *)v16++ = kk;
            v346 = HIDWORD(v16);
          }
          v81 = v244;
          v83 = (_DWORD *)v345;
          v32 = (_DWORD *)v363;
          v10 = a1;
          v82 = v262;
          v328 = (_DWORD *)v363;
          LODWORD(v84) = v163;
          v354 = (char *)v246;
          LOWORD(v378) = v245;
          v338 = v244;
        }
        if ( v165 < (unsigned __int64)v32 + v81 )
          v81 = v165 - (_DWORD)v32;
        v15 = v354;
        v274 = (_BYTE *)(v16 + 1);
        v249 = v16 >> 32;
        v275 = (char *)v32 - v354;
        v250 = v16;
        if ( a7 && (unsigned __int64)&v274[v275 + 8 + v275 / 0xFF] > v350 )
          goto LABEL_624;
        if ( v275 < 0xF )
        {
          *(_BYTE *)v16 = 16 * v275;
        }
        else
        {
          v276 = v275 - 15;
          *(_BYTE *)v16 = -16;
          while ( v276 >= 0xFF )
          {
            *v274++ = -1;
            v276 -= 255LL;
          }
          *v274++ = v276;
        }
        v277 = v354;
        v278 = &v274[v275];
        do
        {
          v279 = *(_QWORD *)v277;
          v277 += 8;
          *(_QWORD *)v274 = v279;
          v274 += 8;
        }
        while ( v274 < (_BYTE *)v278 );
        v280 = (__int64)(v278 + 1);
        v281 = v378;
        *v278 = v378;
        v282 = v81 - 4LL;
        if ( a7 && v280 + v282 / 0xFF + 6 > v350 )
        {
          v18 = v350;
          goto LABEL_626;
        }
        v283 = *(_BYTE *)v16;
        if ( v282 < 0xF )
        {
          *(_BYTE *)v16 = v283 + v282;
        }
        else
        {
          *(_BYTE *)v16 = v283 + 15;
          for ( mm = v81 - 19LL; mm >= 0x1FE; mm -= 510LL )
          {
            *(_BYTE *)v280 = -1;
            v285 = (_BYTE *)(v280 + 1);
            *v285 = -1;
            v280 = (__int64)(v285 + 1);
          }
          if ( mm >= 0xFF )
          {
            LOBYTE(mm) = mm + 1;
            *(_BYTE *)v280++ = -1;
          }
          *(_BYTE *)v280++ = mm;
        }
        v286 = (_BYTE *)(v280 + 1);
        v287 = (char *)v345;
        v15 = (char *)v328 + v81;
        v288 = v345 - (_QWORD)v15;
        v249 = v280 >> 32;
        v250 = v280;
        if ( a7 && (unsigned __int64)&v286[v288 / 0xFF + 8 + v288] > v350 )
        {
          v293 = v339;
LABEL_622:
          v18 = v350;
          v281 = v293;
          v81 = v163;
          goto LABEL_627;
        }
        if ( v288 < 0xF )
        {
          *(_BYTE *)v280 = 16 * v288;
        }
        else
        {
          v289 = v288 - 15;
          *(_BYTE *)v280 = -16;
          while ( v289 >= 0xFF )
          {
            *v286++ = -1;
            v289 -= 255LL;
          }
          *v286++ = v289;
        }
        v290 = (__int64 *)((char *)v328 + v81);
        v291 = &v286[v288];
        do
        {
          v292 = *v290++;
          *(_QWORD *)v286 = v292;
          v286 += 8;
        }
        while ( v286 < (_BYTE *)v291 );
        v293 = v339;
        v294 = v168 - 4;
        *v291 = v339;
        v16 = (__int64)(v291 + 1);
        v351 = v16;
        v346 = HIDWORD(v16);
        if ( a7 && v16 + v294 / 0xFF + 6 > v350 )
          goto LABEL_622;
        v295 = *(_BYTE *)v280;
        if ( v294 < 0xF )
        {
          *(_BYTE *)v280 = v295 + v294;
        }
        else
        {
          *(_BYTE *)v280 = v295 + 15;
          for ( nn = v168 - 19; nn >= 0x1FE; nn -= 510LL )
          {
            *(_BYTE *)v16 = -1;
            v297 = (_BYTE *)(v16 + 1);
            *v297 = -1;
            v16 = (__int64)(v297 + 1);
          }
          if ( nn >= 0xFF )
          {
            LOBYTE(nn) = nn + 1;
            *(_BYTE *)v16++ = -1;
          }
          *(_BYTE *)v16++ = nn;
          v351 = v16;
          v346 = HIDWORD(v16);
        }
        v13 = v169;
        v328 = v169;
        v15 = v169;
        v354 = v169;
LABEL_619:
        if ( (unsigned __int64)v13 > v364 )
        {
          v18 = v350;
          v17 = v373;
          break;
        }
        v10 = a1;
      }
    }
  }
  v318 = v17 - v15;
  v319 = v318;
  if ( a7 == 2 )
  {
LABEL_656:
    v18 += 5LL;
    goto LABEL_658;
  }
  if ( a7 )
  {
LABEL_658:
    if ( v16 + (v318 + 240) / 0xFF + v318 + 1 > v18 )
    {
      if ( a7 == 1 )
      {
LABEL_660:
        result = 0;
LABEL_669:
        *(_BYTE *)(a1 + 262183) = 1;
        return result;
      }
      v319 = v18 - v16 - 1 - ((v18 - v16 - 1 + 241) >> 8);
    }
  }
  if ( v319 < 0xF )
  {
    LOBYTE(v320) = 16 * v319;
  }
  else
  {
    *(_BYTE *)v16 = -16;
    v320 = v319 - 15;
    ++v16;
    while ( v320 >= 0xFF )
    {
      *(_BYTE *)v16++ = -1;
      v320 -= 255LL;
    }
  }
  *(_BYTE *)v16 = v320;
  memmove((void *)(v16 + 1), v15, v319);
  *a4 = v319 + (_DWORD)v15 - v375;
  result = (unsigned int)(v319 - v376 + v16 + 1);
  if ( (int)result <= 0 )
    goto LABEL_669;
  return result;
}

```

## disassembly

```asm
0x1400e4bd0  mov     rax, rsp
0x1400e4bd3  mov     [rax+20h], r9
0x1400e4bd7  mov     [rax+18h], r8
0x1400e4bdb  mov     [rax+10h], rdx
0x1400e4bdf  mov     [rax+8], rcx
0x1400e4be3  push    rbx
0x1400e4be4  push    rbp
0x1400e4be5  push    rsi
0x1400e4be6  push    rdi
0x1400e4be7  push    r12
0x1400e4be9  push    r13
0x1400e4beb  push    r14
0x1400e4bed  push    r15
0x1400e4bef  sub     rsp, 118h
0x1400e4bf6  cmp     qword ptr [rcx+40028h], 0
0x1400e4bfe  mov     r11, r9
0x1400e4c01  mov     rsi, r8
0x1400e4c04  mov     r10, rdx
0x1400e4c07  mov     rbx, rcx
0x1400e4c0a  jnz     loc_1400E7185
0x1400e4c10  cmp     [rsp+158h+arg_30], 2
0x1400e4c18  mov     r12d, 1
0x1400e4c1e  jnz     short loc_1400E4C31
0x1400e4c20  cmp     [rsp+158h+arg_20], r12d
0x1400e4c28  jge     short loc_1400E4C31
0x1400e4c2a  xor     eax, eax
0x1400e4c2c  jmp     loc_1400E71A0
0x1400e4c31  movsxd  rax, dword ptr [r9]
0x1400e4c34  cmp     eax, 7E000000h
0x1400e4c39  ja      short loc_1400E4C2A
0x1400e4c3b  add     [rcx+40000h], rax
0x1400e4c42  mov     r8, r10
0x1400e4c45  movsxd  rdx, dword ptr [r9]
0x1400e4c48  mov     r14, r10
0x1400e4c4b  movsxd  rcx, [rsp+158h+arg_20]
0x1400e4c53  mov     rdi, rsi
0x1400e4c56  add     rcx, rsi
0x1400e4c59  mov     [rsp+158h+var_108], r10
0x1400e4c5e  cmp     [rsp+158h+arg_30], 2
0x1400e4c66  mov     r12, 8080808080808081h
0x1400e4c70  lea     r9, [r10+rdx]
0x1400e4c74  mov     [rsp+158h+var_A8], r10
0x1400e4c7c  mov     [rsp+158h+var_50], r9
0x1400e4c84  lea     r15, [rcx-5]
0x1400e4c88  mov     [rsp+158h+var_B0], rsi
0x1400e4c90  cmovnz  r15, rcx
0x1400e4c94  mov     [rsp+158h+var_C8], rsi
0x1400e4c9c  mov     [rsp+158h+var_B8], r15
0x1400e4ca4  mov     dword ptr [r11], 0
0x1400e4cab  cmp     edx, 0Dh
0x1400e4cae  jl      loc_1400E709D
0x1400e4cb4  lea     rax, [r9-0Ch]
0x1400e4cb8  mov     [rsp+158h+var_80], rax
0x1400e4cc0  cmp     r10, rax
0x1400e4cc3  ja      loc_1400E709D
0x1400e4cc9  lea     rax, [r9-5]
0x1400e4ccd  mov     [rsp+158h+var_D0], 0
0x1400e4cd9  mov     [rsp+158h+var_F0], rax
0x1400e4cde  xor     eax, eax
0x1400e4ce0  mov     [rsp+158h+var_88], rax
0x1400e4ce8  mov     ecx, [rbx+4001Ch]
0x1400e4cee  mov     esi, r8d
0x1400e4cf1  mov     rbp, [rbx+40008h]
0x1400e4cf8  mov     r14d, 3
0x1400e4cfe  mov     r13d, [rbx+40018h]
0x1400e4d05  sub     esi, ebp
0x1400e4d07  add     esi, r13d
0x1400e4d0a  mov     [rsp+158h+var_E8], r14d
0x1400e4d0f  lea     eax, [rcx+10000h]
0x1400e4d15  mov     [rsp+158h+var_D8], rbp
0x1400e4d1d  mov     [rsp+158h+var_F4], esi
0x1400e4d21  mov     r15d, ecx
0x1400e4d24  mov     dword ptr [rsp+158h+var_90], ecx
0x1400e4d2b  cmp     eax, esi
0x1400e4d2d  ja      short loc_1400E4D36
0x1400e4d2f  lea     r15d, [rsi-0FFFFh]
0x1400e4d36  mov     rdx, [rbx+40010h]
0x1400e4d3d  mov     rax, rcx
0x1400e4d40  mov     r12d, [r8]
0x1400e4d43  xor     r9d, r9d
0x1400e4d46  mov     r8d, [rbx+40020h]
0x1400e4d4d  mov     rcx, r13
0x1400e4d50  sub     rcx, rax
0x1400e4d53  mov     [rsp+158h+var_100], r15d
0x1400e4d58  add     rcx, rdx
0x1400e4d5b  mov     [rsp+158h+var_E0], rdx
0x1400e4d60  xor     eax, eax
0x1400e4d62  mov     [rsp+158h+var_A0], rcx
0x1400e4d6a  mov     [rsp+158h+var_114], r9d
0x1400e4d6f  mov     r10d, 100h
0x1400e4d75  mov     [rsp+158h+var_C0], r10d
0x1400e4d7d  mov     [rsp+158h+var_98], r9
0x1400e4d85  mov     [rsp+158h+arg_28], eax
0x1400e4d8c  cmp     r8d, esi
0x1400e4d8f  jnb     short loc_1400E4DD7
0x1400e4d91  mov     r15d, 0FFFFh
0x1400e4d97  mov     ecx, r8d
0x1400e4d9a  mov     eax, r8d
0x1400e4d9d  sub     rax, r13
0x1400e4da0  imul    edx, [rax+rbp], 9E3779B1h
0x1400e4da7  movzx   eax, r8w
0x1400e4dab  shr     rdx, 11h
0x1400e4daf  sub     ecx, [rbx+rdx*4]
0x1400e4db2  cmp     rcx, r15
0x1400e4db5  cmova   rcx, r15
0x1400e4db9  mov     [rbx+rax*2+20000h], cx
0x1400e4dc1  mov     [rbx+rdx*4], r8d
0x1400e4dc5  inc     r8d
0x1400e4dc8  cmp     r8d, esi
0x1400e4dcb  jb      short loc_1400E4D97
0x1400e4dcd  mov     r15d, [rsp+158h+var_100]
0x1400e4dd2  mov     rdx, [rsp+158h+var_E0]
0x1400e4dd7  mov     r8, [rsp+158h+var_108]
0x1400e4ddc  mov     [rbx+40020h], esi
0x1400e4de2  imul    ecx, [r8], 9E3779B1h
0x1400e4de9  shr     rcx, 11h
0x1400e4ded  mov     r11d, [rbx+rcx*4]
0x1400e4df1  cmp     r11d, r15d
0x1400e4df4  jb      loc_1400E53D6
0x1400e4dfa  mov     edi, dword ptr [rsp+158h+var_90]
0x1400e4e01  mov     ecx, 1
0x1400e4e06  test    r10d, r10d
0x1400e4e09  jle     loc_1400E53C6
0x1400e4e0f  cmp     r11d, r13d
0x1400e4e12  jb      loc_1400E4F1A
0x1400e4e18  mov     r10, [rsp+158h+var_108]
0x1400e4e1d  mov     eax, r11d
0x1400e4e20  sub     eax, r13d
0x1400e4e23  movsxd  rdx, r14d
0x1400e4e26  mov     r8d, eax
0x1400e4e29  add     rax, rdx
0x1400e4e2c  movzx   ecx, word ptr [rax+rbp-1]
0x1400e4e31  cmp     [rdx+r10-1], cx
0x1400e4e37  jnz     loc_1400E50F1
0x1400e4e3d  cmp     [r8+rbp], r12d
0x1400e4e41  jnz     loc_1400E50F1
0x1400e4e47  lea     r9, [r10+4]
0x1400e4e4b  mov     r10, [rsp+158h+var_F0]
0x1400e4e50  lea     rdx, [rbp+4]
0x1400e4e54  mov     [rsp+158h+var_78], r9
0x1400e4e5c  add     r10, 0FFFFFFFFFFFFFFF9h
0x1400e4e60  add     rdx, r8
0x1400e4e63  cmp     r9, r10
0x1400e4e66  jnb     short loc_1400E4E80
0x1400e4e68  mov     rcx, [rdx]
0x1400e4e6b  xor     rcx, [r9]
0x1400e4e6e  jnz     short loc_1400E4E76
0x1400e4e70  lea     rcx, [r9+8]
0x1400e4e74  jmp     short loc_1400E4E94
0x1400e4e76  tzcnt   rcx, rcx
0x1400e4e7b  shr     ecx, 3
0x1400e4e7e  jmp     short loc_1400E4EEF
0x1400e4e80  mov     rcx, r9
0x1400e4e83  cmp     rcx, r10
0x1400e4e86  jnb     short loc_1400E4EA9
0x1400e4e88  mov     r8, [rdx]
0x1400e4e8b  xor     r8, [rcx]
0x1400e4e8e  jnz     short loc_1400E4E9A
0x1400e4e90  add     rcx, 8
0x1400e4e94  add     rdx, 8
0x1400e4e98  jmp     short loc_1400E4E83
0x1400e4e9a  tzcnt   rax, r8
0x1400e4e9f  shr     eax, 3
0x1400e4ea2  sub     eax, r9d
0x1400e4ea5  add     ecx, eax
0x1400e4ea7  jmp     short loc_1400E4EEF
0x1400e4ea9  mov     r8, [rsp+158h+var_F0]
0x1400e4eae  lea     rax, [r8-3]
0x1400e4eb2  cmp     rcx, rax
0x1400e4eb5  jnb     short loc_1400E4EC5
0x1400e4eb7  mov     eax, [rcx]
0x1400e4eb9  cmp     [rdx], eax
0x1400e4ebb  jnz     short loc_1400E4EC5
0x1400e4ebd  add     rcx, 4
0x1400e4ec1  add     rdx, 4
0x1400e4ec5  lea     rax, [r8-1]
0x1400e4ec9  cmp     rcx, rax
0x1400e4ecc  jnb     short loc_1400E4EDE
0x1400e4ece  movzx   eax, word ptr [rcx]
0x1400e4ed1  cmp     [rdx], ax
0x1400e4ed4  jnz     short loc_1400E4EDE
0x1400e4ed6  add     rcx, 2
0x1400e4eda  add     rdx, 2
0x1400e4ede  cmp     rcx, r8
0x1400e4ee1  jnb     short loc_1400E4EEC
0x1400e4ee3  mov     al, [rcx]
0x1400e4ee5  cmp     [rdx], al
0x1400e4ee7  jnz     short loc_1400E4EEC
0x1400e4ee9  inc     rcx
0x1400e4eec  sub     ecx, r9d
0x1400e4eef  mov     r9d, [rsp+158h+var_114]
0x1400e4ef4  add     ecx, 4
0x1400e4ef7  mov     r10, [rsp+158h+var_108]
0x1400e4efc  cmp     ecx, r14d
0x1400e4eff  jle     loc_1400E50F1
0x1400e4f05  mov     [rsp+158h+var_E8], ecx
0x1400e4f09  mov     ecx, esi
0x1400e4f0b  sub     ecx, r11d
0x1400e4f0e  mov     [rsp+158h+arg_28], ecx
0x1400e4f15  jmp     loc_1400E50F1
0x1400e4f1a  lea     eax, [r13-4]
0x1400e4f1e  cmp     r11d, eax
0x1400e4f21  ja      loc_1400E50E5
0x1400e4f27  mov     eax, r11d
0x1400e4f2a  sub     eax, edi
0x1400e4f2c  mov     ecx, eax
0x1400e4f2e  cmp     [rax+rdx], r12d
0x1400e4f32  jnz     loc_1400E50EC
0x1400e4f38  mov     r9d, r13d
0x1400e4f3b  lea     r10, [r8+4]
0x1400e4f3f  sub     r9d, r11d
0x1400e4f42  mov     [rsp+158h+var_78], r10
0x1400e4f4a  add     r9, r8
0x1400e4f4d  cmp     r9, [rsp+158h+var_F0]
0x1400e4f52  cmova   r9, [rsp+158h+var_F0]
0x1400e4f58  add     rdx, 4
0x1400e4f5c  add     rdx, rcx
0x1400e4f5f  lea     rbx, [r9-7]
0x1400e4f63  cmp     r10, rbx
0x1400e4f66  jnb     short loc_1400E4F80
0x1400e4f68  mov     rcx, [rdx]
0x1400e4f6b  xor     rcx, [r10]
0x1400e4f6e  jnz     short loc_1400E4F76
0x1400e4f70  lea     rcx, [r10+8]
0x1400e4f74  jmp     short loc_1400E4F94
0x1400e4f76  tzcnt   rbx, rcx
0x1400e4f7b  shr     ebx, 3
0x1400e4f7e  jmp     short loc_1400E4FF1
0x1400e4f80  mov     rcx, r10
0x1400e4f83  cmp     rcx, rbx
0x1400e4f86  jnb     short loc_1400E4FA9
0x1400e4f88  mov     r8, [rcx]
0x1400e4f8b  xor     r8, [rdx]
0x1400e4f8e  jnz     short loc_1400E4F9A
0x1400e4f90  add     rcx, 8
0x1400e4f94  add     rdx, 8
0x1400e4f98  jmp     short loc_1400E4F83
0x1400e4f9a  tzcnt   rbx, r8
0x1400e4f9f  shr     ebx, 3
0x1400e4fa2  sub     ebx, r10d
0x1400e4fa5  add     ebx, ecx
0x1400e4fa7  jmp     short loc_1400E4FEC
0x1400e4fa9  lea     rax, [r9-3]
0x1400e4fad  cmp     rcx, rax
0x1400e4fb0  jnb     short loc_1400E4FC0
0x1400e4fb2  mov     eax, [rcx]
0x1400e4fb4  cmp     [rdx], eax
0x1400e4fb6  jnz     short loc_1400E4FC0
0x1400e4fb8  add     rcx, 4
0x1400e4fbc  add     rdx, 4
0x1400e4fc0  lea     rax, [r9-1]
0x1400e4fc4  cmp     rcx, rax
0x1400e4fc7  jnb     short loc_1400E4FD9
0x1400e4fc9  movzx   eax, word ptr [rcx]
0x1400e4fcc  cmp     [rdx], ax
0x1400e4fcf  jnz     short loc_1400E4FD9
0x1400e4fd1  add     rcx, 2
0x1400e4fd5  add     rdx, 2
0x1400e4fd9  cmp     rcx, r9
0x1400e4fdc  jnb     short loc_1400E4FE7
0x1400e4fde  mov     al, [rcx]
0x1400e4fe0  cmp     [rdx], al
0x1400e4fe2  jnz     short loc_1400E4FE7
0x1400e4fe4  inc     rcx
0x1400e4fe7  sub     ecx, r10d
0x1400e4fea  mov     ebx, ecx
0x1400e4fec  mov     r8, [rsp+158h+var_108]
0x1400e4ff1  add     r8, 4
0x1400e4ff5  movsxd  rax, ebx
0x1400e4ff8  add     r8, rax
0x1400e4ffb  lea     ecx, [rbx+4]
0x1400e4ffe  cmp     r8, r9
0x1400e5001  jnz     loc_1400E50BC
0x1400e5007  cmp     r9, [rsp+158h+var_F0]
0x1400e500c  jnb     loc_1400E50BC
0x1400e5012  mov     r10, [rsp+158h+var_F0]
0x1400e5017  add     r10, 0FFFFFFFFFFFFFFF9h
0x1400e501b  mov     [rsp+158h+var_78], r8
0x1400e5023  cmp     r8, r10
0x1400e5026  jnb     short loc_1400E5045
0x1400e5028  mov     rcx, [r8]
0x1400e502b  xor     rcx, [rbp+0]
0x1400e502f  jnz     short loc_1400E503B
0x1400e5031  lea     rcx, [r8+8]
0x1400e5035  lea     rdx, [rbp+8]
0x1400e5039  jmp     short loc_1400E504B
0x1400e503b  tzcnt   rcx, rcx
0x1400e5040  shr     ecx, 3
0x1400e5043  jmp     short loc_1400E50B7
0x1400e5045  mov     rdx, rbp
0x1400e5048  mov     rcx, r8
0x1400e504b  cmp     rcx, r10
0x1400e504e  jnb     short loc_1400E5071
0x1400e5050  mov     r9, [rcx]
0x1400e5053  xor     r9, [rdx]
0x1400e5056  jnz     short loc_1400E5062
0x1400e5058  add     rcx, 8
0x1400e505c  add     rdx, 8
0x1400e5060  jmp     short loc_1400E504B
0x1400e5062  tzcnt   rax, r9
  ... truncated ...
```
