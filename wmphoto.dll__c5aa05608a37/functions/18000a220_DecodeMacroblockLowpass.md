# DecodeMacroblockLowpass

- ea: `0x18000a220`
- end: `0x18000ba87`
- name: `DecodeMacroblockLowpass`
- size: `6247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180007340`
- `0x180008ce0`
- `0x18000f244`

## callees

- `0x18000a220`
- `0x18000ba90`
- `0x18000bae0`
- `0x18000bf68`
- `0x180011ce4`
- `0x180031110`
- `0x1800349c4`
- `0x180035e50`
- `0x180036ba4`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall DecodeMacroblockLowpass(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v4; // rsi
  _DWORD *v5; // r15
  int v6; // r12d
  int v7; // ecx
  unsigned int v8; // edx
  int v9; // edi
  int v10; // ebx
  __int64 v11; // r8
  int v12; // r8d
  unsigned int i; // edx
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  int v16; // r9d
  int v17; // r13d
  int v18; // r12d
  int v19; // r14d
  int Bit16; // eax
  char v21; // cl
  int v22; // r8d
  int v23; // r10d
  int v24; // r9d
  unsigned __int64 v25; // r14
  int v26; // edx
  unsigned __int32 v27; // r11d
  int v28; // eax
  int v29; // r9d
  int v30; // eax
  int v31; // r9d
  int v32; // r8d
  bool v33; // cc
  __int64 (__fastcall *v34)(__int64, _QWORD); // r10
  __int64 v35; // r13
  unsigned int v36; // r8d
  __int64 v37; // rdx
  __int64 v38; // r14
  int v39; // r11d
  __int64 v40; // rdx
  __int64 v41; // rax
  int v42; // ebx
  int v43; // ebx
  __int64 v44; // rdx
  int v45; // ecx
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v50; // ecx
  int v51; // eax
  unsigned int v52; // r13d
  _DWORD *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // r15
  int v56; // r12d
  __int64 v57; // r9
  __int64 v58; // rdi
  int v59; // r8d
  int v60; // ecx
  int v61; // r11d
  unsigned int *v62; // r10
  unsigned __int32 v63; // ebx
  __int64 v64; // rdx
  unsigned int v65; // ebx
  int v66; // r15d
  __int64 v67; // rax
  unsigned __int64 v68; // r9
  int v69; // edi
  unsigned __int32 v70; // edx
  int v71; // edx
  __int64 v72; // r11
  int v73; // r8d
  int v74; // r10d
  unsigned int *v75; // r9
  unsigned __int32 v76; // edx
  __int64 v77; // rax
  int v78; // r8d
  int v79; // edi
  unsigned int *v80; // rax
  int v81; // r15d
  int v82; // r13d
  int v83; // edx
  int v84; // r9d
  __int64 v85; // rdi
  int v86; // r8d
  int v87; // ebx
  unsigned int *v88; // r11
  unsigned __int32 v89; // edx
  int v90; // eax
  __int64 v91; // rax
  int v92; // r8d
  int v93; // r9d
  unsigned int *v94; // rax
  __int64 v95; // r8
  __int64 v96; // rax
  int v97; // r9d
  unsigned __int64 v98; // rdx
  unsigned __int8 v99; // cl
  unsigned int *v100; // rdx
  __int64 v101; // rdx
  int v102; // ecx
  unsigned int v103; // edx
  int v104; // edi
  unsigned __int32 v105; // r8d
  int v106; // ecx
  __int64 v107; // rax
  int v108; // r9d
  int v109; // r10d
  _DWORD *v110; // rbx
  __int64 v111; // rdx
  int v112; // r10d
  __int64 v113; // rcx
  __int64 v114; // r9
  int v115; // r8d
  int v116; // r11d
  unsigned __int64 v117; // r10
  int v118; // r11d
  unsigned int *v119; // r10
  unsigned __int32 v120; // r12d
  __int64 v121; // r10
  int v122; // ecx
  int v123; // r15d
  char v124; // r12
  __int64 m; // rbx
  int v126; // edi
  int v127; // eax
  int v128; // ecx
  unsigned int *v129; // rdx
  int v130; // edi
  int v131; // eax
  int v132; // eax
  int v133; // eax
  int v134; // edx
  __int64 v135; // rax
  int v136; // r8d
  unsigned __int64 v137; // rdx
  char v138; // cl
  unsigned int *v139; // rdx
  int v140; // ecx
  __int64 v141; // r10
  int v142; // r8d
  int v143; // r11d
  unsigned __int64 v144; // r9
  int v145; // r11d
  unsigned int *v146; // r9
  unsigned __int32 v147; // r12d
  __int64 v148; // r9
  int v149; // eax
  unsigned __int64 v150; // r11
  int v151; // edx
  signed __int32 v152; // r8d
  int v153; // ecx
  unsigned int *v154; // rdx
  unsigned __int64 v155; // rcx
  unsigned int *v156; // rcx
  int v157; // r9d
  unsigned int v158; // r8d
  unsigned __int64 v159; // rdx
  int v160; // r8d
  unsigned int *v161; // rdx
  int v162; // edx
  int v163; // r8d
  unsigned __int64 v164; // rdx
  int v165; // ecx
  unsigned int *v166; // rdx
  __int64 v167; // r9
  int v168; // ecx
  unsigned int *v169; // rax
  int v170; // r12d
  unsigned int v171; // r12d
  unsigned __int32 v172; // r8d
  __int64 v173; // r15
  unsigned __int32 v174; // r11d
  int v175; // ecx
  unsigned int *v176; // rdx
  unsigned __int32 v177; // r14d
  unsigned int *v178; // rax
  unsigned __int64 v179; // r9
  int v180; // edx
  signed __int32 v181; // r8d
  signed __int32 v182; // edx
  unsigned int v183; // r8d
  unsigned __int32 v184; // eax
  unsigned __int64 v185; // rcx
  unsigned int *v186; // rcx
  unsigned int v187; // r11d
  signed __int32 v188; // ebx
  __int64 v189; // r9
  int v190; // ecx
  unsigned int *v191; // rax
  int v192; // r12d
  unsigned int v193; // r12d
  unsigned __int32 v194; // r8d
  unsigned __int64 v195; // rcx
  unsigned int *v196; // rcx
  unsigned __int64 v197; // rcx
  unsigned int *v198; // rcx
  unsigned int v199; // r9d
  signed __int32 v200; // r10d
  unsigned int v201; // ecx
  unsigned __int32 v202; // eax
  unsigned int v203; // ecx
  unsigned __int32 v204; // r9d
  unsigned __int32 v205; // eax
  __int64 v206; // r15
  _DWORD *v207; // rdx
  __int64 v208; // rcx
  unsigned int v209; // ecx
  unsigned __int32 v210; // eax
  __int64 v211; // rcx
  unsigned __int64 v212; // rcx
  unsigned int *v213; // rcx
  unsigned __int64 v214; // rcx
  unsigned int *v215; // rcx
  unsigned __int64 v216; // rcx
  unsigned int *v217; // rcx
  unsigned __int64 v218; // rcx
  unsigned int *v219; // rcx
  unsigned __int64 v220; // rdx
  int v221; // ecx
  unsigned int *v222; // rdx
  unsigned __int64 v223; // rdx
  int v224; // ecx
  unsigned int *v225; // rdx
  __int64 v226; // r9
  __int64 v227; // r14
  unsigned __int64 v228; // rax
  __int64 v229; // rax
  unsigned __int32 v230; // edx
  unsigned __int64 v231; // rcx
  unsigned int *v232; // rcx
  unsigned __int64 v233; // rax
  __int64 v234; // rax
  unsigned __int32 v235; // edx
  unsigned int v236; // ecx
  int v237; // r8d
  unsigned __int64 v238; // rdx
  int v239; // ecx
  unsigned int *v240; // rdx
  unsigned __int32 v241; // r12d
  unsigned int *v242; // rax
  __int64 v243; // r14
  __int64 v244; // r10
  unsigned __int64 v245; // rax
  __int64 v246; // rax
  unsigned __int32 v247; // edx
  unsigned __int64 v248; // rdx
  int v249; // ecx
  unsigned int *v250; // rdx
  unsigned int v251; // ecx
  int v252; // r8d
  unsigned __int64 v253; // rdx
  int v254; // ecx
  unsigned int *v255; // rdx
  unsigned __int32 v256; // r12d
  unsigned int *v257; // rax
  int v258; // edi
  int v259; // r15d
  __int64 v260; // r14
  int v261; // ebx
  int v262; // ebx
  int v263; // eax
  __int64 v264; // r9
  int v265; // eax
  int v266; // ebx
  int v267; // eax
  __int64 v268; // rdx
  unsigned __int64 v269; // rcx
  int v270; // r8d
  unsigned __int32 v271; // eax
  unsigned __int64 v272; // rdx
  int v273; // ecx
  unsigned int *v274; // rdx
  unsigned __int64 v275; // rcx
  int v276; // r8d
  unsigned __int32 v277; // eax
  unsigned __int64 v278; // rdx
  int v279; // ecx
  unsigned int *v280; // rdx
  unsigned int v281; // eax
  __int64 v282; // rbx
  int v283; // edi
  char *v284; // rbx
  int v285; // r15d
  int j; // r9d
  int v287; // eax
  int v288; // r8d
  int k; // r9d
  __int64 v290; // r8
  __int64 v291; // rdx
  __int64 v292; // rax
  int v293; // ebx
  int v294; // eax
  int v295; // eax
  int v296; // ebx
  int v297; // eax
  int v298; // ebx
  int v299; // eax
  int v300; // [rsp+20h] [rbp-E0h]
  unsigned int v301; // [rsp+24h] [rbp-DCh]
  int v302; // [rsp+28h] [rbp-D8h]
  int v303; // [rsp+2Ch] [rbp-D4h]
  __int64 v304; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall *v305)(_QWORD); // [rsp+38h] [rbp-C8h]
  int v306; // [rsp+40h] [rbp-C0h]
  int v307; // [rsp+44h] [rbp-BCh]
  _DWORD *v308; // [rsp+48h] [rbp-B8h]
  __int64 v309; // [rsp+50h] [rbp-B0h]
  int v310; // [rsp+58h] [rbp-A8h]
  int v311; // [rsp+5Ch] [rbp-A4h]
  __int64 v312; // [rsp+60h] [rbp-A0h]
  _DWORD *v313; // [rsp+68h] [rbp-98h]
  __int64 *v314; // [rsp+70h] [rbp-90h]
  __int64 v315; // [rsp+78h] [rbp-88h]
  __int64 v316; // [rsp+80h] [rbp-80h]
  __int64 v317; // [rsp+88h] [rbp-78h]
  _DWORD *v318; // [rsp+90h] [rbp-70h]
  _DWORD *v319; // [rsp+98h] [rbp-68h]
  __int64 v320; // [rsp+A0h] [rbp-60h]
  _DWORD v321[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v322; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v323[15]; // [rsp+F8h] [rbp-8h]
  int v324; // [rsp+170h] [rbp+70h]
  _DWORD v325[31]; // [rsp+174h] [rbp+74h]

  v2 = *(_DWORD *)(a1 + 34216);
  v4 = *(_QWORD *)(a2 + 8);
  v5 = (_DWORD *)a2;
  v320 = a1;
  v6 = 2;
  v7 = *(_DWORD *)(a1 + 34240);
  v308 = (_DWORD *)a2;
  v8 = *(_DWORD *)(a2 + 628);
  v302 = v2;
  v311 = v7;
  v301 = v8;
  if ( (unsigned int)(v2 - 1) > 1 )
    v6 = v7;
  v9 = 0;
  v304 = 0;
  v307 = v6;
  v10 = 0;
  memset_0(&v322, 0, 0x80u);
  if ( !*(_DWORD *)(v4 + 48) )
  {
    if ( !*(_DWORD *)(*(_QWORD *)v5 + 48LL) )
      return 0xFFFFFFFFLL;
    if ( !*(_QWORD *)(v4 + 32) )
    {
      LOBYTE(v11) = 1;
      InitBitIO(a1, v4, v11);
      if ( !*(_DWORD *)(v4 + 48) )
        goto LABEL_191;
      if ( !*(_DWORD *)(a1 + 35672) )
      {
        if ( *(_BYTE *)(a1 + 34352) > 1u && (unsigned int)readTileHeaderLP(a1, v4) )
          return 0xFFFFFFFFLL;
        v211 = *(_QWORD *)(a1 + 35664);
        if ( v211 )
        {
          if ( *(_BYTE *)(v211 + 34352) > 1u && (unsigned int)readTileHeaderLP(v211, v4) )
            return 0xFFFFFFFFLL;
        }
      }
    }
    if ( *(_DWORD *)(v4 + 48) )
      goto LABEL_4;
LABEL_191:
    *(_DWORD *)(a1 + 35676) = 1;
    return 0;
  }
LABEL_4:
  v319 = v5 + 54;
  v314 = &v304;
  if ( ((*(_DWORD *)(v4 + 16) ^ *(_DWORD *)(v4 + 24)) & 0x1000LL) != 0 )
  {
    v206 = *(_QWORD *)(v4 + 32);
    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD))(v206 + 88))(v206, *(_QWORD *)(v4 + 40)) )
    {
      if ( *(_QWORD *)(v206 + 40) != *(_QWORD *)(v4 + 40) && ++*(_BYTE *)(v4 + 52) > 1u )
        *(_DWORD *)(v4 + 48) = 0;
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(v206 + 64))(v206, *(_QWORD *)(v4 + 16), 4096);
      v207 = *(_DWORD **)(v4 + 16);
      *(_QWORD *)(v4 + 40) += 4096LL;
      v208 = *(int *)(v4 + 12);
      *(_DWORD *)v4 = *v207;
      *(_QWORD *)(v4 + 16) = (unsigned __int64)(v207 + 1024) & v208;
    }
    v5 = v308;
  }
  if ( *(_DWORD *)(a1 + 168) && *(_BYTE *)(432LL * *(_QWORD *)(a1 + 34392) + *(_QWORD *)(a1 + 34464) + 386) )
    *(_BYTE *)(a1 + 34204) = decodeQPIndex(v4);
  v12 = *(_DWORD *)(a1 + 34240);
  for ( i = 0; (int)i < v12; v323[v14 - 1] = a1 + 33048 + v15 )
  {
    v14 = i & 0xF;
    v15 = (unsigned __int64)i++ << 6;
  }
  if ( *(_DWORD *)(a1 + 34456) )
  {
    v5[54] = 0x7FFF;
    v5[56] = 32;
    v5[58] = 30;
    v5[60] = 28;
    v5[62] = 26;
    v5[64] = 24;
    v5[66] = 22;
    v5[68] = 20;
    v5[70] = 18;
    v5[72] = 16;
    v5[74] = 14;
    v5[76] = 12;
    v5[78] = 10;
    v5[80] = 8;
    v5[82] = 6;
    v5[84] = 4;
  }
  v16 = v302;
  if ( (unsigned int)(v302 - 1) <= 2 )
  {
    v22 = v5[165];
    v23 = 4 * v6 - 5;
    v24 = v5[166];
    if ( v22 <= 0 || v24 < 0 )
    {
      ++*(_DWORD *)(v4 + 8);
      v18 = 0;
      v25 = *(unsigned int *)(v4 + 8);
      v26 = *(_DWORD *)(v4 + 4);
      if ( (unsigned int)v25 >= 0x10 )
      {
        v195 = v25 >> 3;
        LODWORD(v25) = *(_DWORD *)(v4 + 8) & 0xF;
        v196 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + v195));
        *(_DWORD *)(v4 + 8) = v25;
        *(_QWORD *)(v4 + 24) = v196;
        v27 = _byteswap_ulong(*v196) << v25;
      }
      else
      {
        v27 = 2 * v26;
      }
      *(_DWORD *)(v4 + 4) = v27;
      if ( v26 < 0 )
      {
        v173 = *(int *)(v4 + 12);
        v18 = 1;
        v174 = v27 >> (32 - (v307 - 1));
        v175 = ((_BYTE)v307 - 1 + (_BYTE)v25) & 0xF;
        v176 = (unsigned int *)(v173 & (*(_QWORD *)(v4 + 24) + ((unsigned __int64)(unsigned int)(v307 - 1 + v25) >> 3)));
        *(_DWORD *)(v4 + 8) = v175;
        *(_QWORD *)(v4 + 24) = v176;
        v177 = _byteswap_ulong(*v176) << v175;
        *(_DWORD *)(v4 + 4) = v177;
        if ( v174 )
        {
          *(_DWORD *)(v4 + 8) = ((_BYTE)v175 + 1) & 0xF;
          v178 = (unsigned int *)(v173 & ((unsigned __int64)v176 + ((unsigned __int64)(unsigned int)(v175 + 1) >> 3)));
          *(_QWORD *)(v4 + 24) = v178;
          *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v178) << ((v175 + 1) & 0xF);
          v18 = (v177 >> 31) + 2 * v174;
        }
        v5 = v308;
      }
      v300 = v18;
      if ( v24 < v22 )
      {
        v18 = v23 - v18;
        v300 = v18;
      }
    }
    else
    {
      v18 = *(_DWORD *)(v4 + 4) >> (32 - v6);
      v153 = (*(_BYTE *)(v4 + 8) + (_BYTE)v307) & 0xF;
      v154 = (unsigned int *)(*(int *)(v4 + 12)
                            & (*(_QWORD *)(v4 + 24) + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 8) + v307) >> 3)));
      *(_DWORD *)(v4 + 8) = v153;
      *(_QWORD *)(v4 + 24) = v154;
      v300 = v18;
      *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v154) << v153;
    }
    v28 = 0;
    if ( v18 == v23 )
      v28 = 4;
    v29 = v24 - v28;
    v30 = 0;
    v31 = v29 + 1;
    if ( !v18 )
      v30 = 4;
    v32 = v22 - v30 + 1;
    if ( v31 >= -8 )
    {
      if ( v31 > 7 )
        v31 = 7;
    }
    else
    {
      v31 = -8;
    }
    v5[166] = v31;
    if ( v32 < -8 )
    {
      v32 = -8;
    }
    else if ( v32 > 7 )
    {
      v32 = 7;
    }
    v5[165] = v32;
    goto LABEL_32;
  }
  v17 = v311;
  v18 = 0;
  v19 = 0;
  v300 = 0;
  if ( v311 > 0 )
  {
    do
    {
      Bit16 = getBit16(v4, 1);
      v21 = v19++;
      v18 |= Bit16 << v21;
    }
    while ( v19 < v17 );
    v300 = v18;
LABEL_32:
    v16 = v302;
  }
  if ( (int)v5[157] > 14 || (v33 = v5[158] <= 14, v34 = getBit16, v305 = (__int64 (__fastcall *)(_QWORD))getBit16, !v33) )
  {
    v34 = getBit32;
    v305 = (__int64 (__fastcall *)(_QWORD))getBit32;
  }
  v35 = 0;
  v306 = 0;
  if ( v307 > 0 )
  {
    v36 = v301;
    v312 = v323[1];
    v37 = v323[0];
    v309 = v323[0];
    while ( 1 )
    {
      v38 = v323[v35 - 1];
      v317 = v38;
      if ( (v18 & 1) == 0 )
        goto LABEL_38;
      if ( v16 == 1 && (_DWORD)v35 == 1 )
        break;
      v50 = 0;
      if ( v16 != 2 )
        goto LABEL_60;
      v51 = 2;
      if ( (_DWORD)v35 != 1 )
        goto LABEL_60;
LABEL_61:
      v52 = v51 + v50;
      v53 = v5 + 12;
      v54 = 10;
      v55 = *(int *)(v4 + 12);
      if ( v306 )
        v54 = 16;
      v313 = v53;
      v318 = &v53[v54];
      v56 = 1;
      v310 = 1;
      v57 = *(_QWORD *)&v53[v54];
      v58 = *(_QWORD *)(v57 + 64);
      v59 = *(__int16 *)(v58 + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27));
      v60 = *(_WORD *)(v58 + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27)) & 7;
      if ( v59 < 0 )
        v60 = 5;
      v61 = ((_BYTE)v60 + *(_BYTE *)(v4 + 8)) & 0xF;
      v62 = (unsigned int *)(v55
                           & (*(_QWORD *)(v4 + 24) + ((unsigned __int64)(unsigned int)(v60 + *(_DWORD *)(v4 + 8)) >> 3)));
      *(_DWORD *)(v4 + 8) = v61;
      *(_QWORD *)(v4 + 24) = v62;
      v63 = _byteswap_ulong(*v62) << v61;
      *(_DWORD *)(v4 + 4) = v63;
      if ( v59 >> 3 < 0 )
      {
        do
        {
          v233 = (unsigned int)(v61 + 1);
          v61 = ((_BYTE)v61 + 1) & 0xF;
          *(_DWORD *)(v4 + 8) = v61;
          v62 = (unsigned int *)(v55 & ((unsigned __int64)v62 + (v233 >> 3)));
          v234 = (v63 >> 31) + v59 + 0x8000;
          *(_QWORD *)(v4 + 24) = v62;
          v235 = _byteswap_ulong(*v62) << v61;
          *(_DWORD *)(v4 + 4) = v235;
          v63 = v235;
          v59 = *(__int16 *)(v58 + 2 * v234);
        }
        while ( v59 < 0 );
      }
      else
      {
        v59 >>= 3;
      }
      v64 = 4LL * (unsigned int)v59;
      v65 = (unsigned int)v59 >> 2;
      v66 = v59 & 1;
      *(_DWORD *)(v57 + 76) += *(_DWORD *)(*(_QWORD *)(v57 + 40) + v64);
      *(_DWORD *)(v57 + 80) += *(_DWORD *)(*(_QWORD *)(v57 + 48) + v64);
      ++*(_DWORD *)(v4 + 8);
      v67 = ((unsigned int)v59 >> 2) & v59 & 1;
      v68 = *(unsigned int *)(v4 + 8);
      v69 = *(int *)(v4 + 4) >> 31;
      v303 = ((unsigned int)v59 >> 2) & v59 & 1;
      if ( (unsigned int)v68 >= 0x10 )
      {
        v185 = v68 >> 3;
        LODWORD(v68) = *(_DWORD *)(v4 + 8) & 0xF;
        v186 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + v185));
        *(_DWORD *)(v4 + 8) = v68;
        v67 = (unsigned int)v303;
        *(_QWORD *)(v4 + 24) = v186;
        v70 = _byteswap_ulong(*v186) << v68;
      }
      else
      {
        v70 = 2 * *(_DWORD *)(v4 + 4);
      }
      *(_DWORD *)(v4 + 4) = v70;
      if ( (v59 & 2) == 0 )
      {
        v325[0] = v69 | 1;
        goto LABEL_71;
      }
      v141 = *(_QWORD *)&v313[2 * v67 + 22];
      v316 = v141;
      v315 = *(_QWORD *)(v141 + 64);
      v142 = *(__int16 *)(v315 + 2 * ((unsigned __int64)v70 >> 27));
      v143 = *(_WORD *)(v315 + 2 * ((unsigned __int64)v70 >> 27)) & 7;
      if ( v142 < 0 )
        v143 = 5;
      v144 = (unsigned int)(v68 + v143);
      v145 = v144 & 0xF;
      v146 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v144 >> 3)));
      *(_DWORD *)(v4 + 8) = v145;
      *(_QWORD *)(v4 + 24) = v146;
      v147 = _byteswap_ulong(*v146) << v145;
      *(_DWORD *)(v4 + 4) = v147;
      if ( v142 >> 3 < 0 )
      {
        v243 = v315;
        v244 = *(int *)(v4 + 12);
        do
        {
          v245 = (unsigned int)(v145 + 1);
          v145 = ((_BYTE)v145 + 1) & 0xF;
          *(_DWORD *)(v4 + 8) = v145;
          v146 = (unsigned int *)(v244 & ((unsigned __int64)v146 + (v245 >> 3)));
          v246 = (v147 >> 31) + v142 + 0x8000;
          *(_QWORD *)(v4 + 24) = v146;
          v247 = _byteswap_ulong(*v146) << v145;
          *(_DWORD *)(v4 + 4) = v247;
          v147 = v247;
          v142 = *(__int16 *)(v243 + 2 * v246);
        }
        while ( v142 < 0 );
        v38 = v317;
        v141 = v316;
      }
      else
      {
        v142 >>= 3;
      }
      v148 = (unsigned int)v142;
      *(_DWORD *)(v141 + 76) += *(_DWORD *)(*(_QWORD *)(v141 + 40) + v148 * 4);
      if ( (unsigned int)v142 < 2 )
      {
        v149 = v142 + 2;
LABEL_128:
        v56 = v310;
        v325[0] = (v69 ^ v149) - v69;
        goto LABEL_71;
      }
      if ( (unsigned int)v142 >= 6 )
      {
        v189 = *(int *)(v4 + 12);
        v190 = (*(_BYTE *)(v4 + 8) + 4) & 0xF;
        v191 = (unsigned int *)(v189
                              & (*(_QWORD *)(v4 + 24) + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 8) + 4) >> 3)));
        v192 = *(_DWORD *)(v4 + 4) >> 28;
        *(_QWORD *)(v4 + 24) = v191;
        v193 = v192 + 4;
        *(_DWORD *)(v4 + 8) = v190;
        v194 = _byteswap_ulong(*v191) << v190;
        *(_DWORD *)(v4 + 4) = v194;
        if ( v193 == 19 )
        {
          v251 = v190 + 2;
          v252 = (v194 >> 30) + 19;
          v253 = (unsigned __int64)v251 >> 3;
          v254 = v251 & 0xF;
          *(_DWORD *)(v4 + 8) = v254;
          v255 = (unsigned int *)(v189 & ((unsigned __int64)v191 + v253));
          *(_QWORD *)(v4 + 24) = v255;
          v256 = _byteswap_ulong(*v255) << v254;
          *(_DWORD *)(v4 + 4) = v256;
          if ( v252 == 22 )
          {
            *(_DWORD *)(v4 + 8) = ((_BYTE)v254 + 3) & 0xF;
            v257 = (unsigned int *)(v189 & ((unsigned __int64)v255 + ((unsigned __int64)(unsigned int)(v254 + 3) >> 3)));
            *(_QWORD *)(v4 + 24) = v257;
            *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v257) << ((v254 + 3) & 0xF);
            v193 = (v256 >> 29) + 22;
          }
          else
          {
            v193 = v252;
          }
        }
        v149 = (1 << v193) + getBit32(v4, v193) + 2;
        goto LABEL_128;
      }
      _mm_lfence();
      v162 = `DecodeSignificantAbsLevel'::`2'::aFixedLength[v148];
      v56 = v310;
      v163 = *(_DWORD *)(v4 + 4) >> (32 - v162);
      v164 = (unsigned int)(v162 + *(_DWORD *)(v4 + 8));
      v165 = v164 & 0xF;
      v166 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v164 >> 3)));
      *(_DWORD *)(v4 + 8) = v165;
      *(_QWORD *)(v4 + 24) = v166;
      *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v166) << v165;
      v325[0] = (v69 ^ (v163 + `DecodeSignificantAbsLevel'::`2'::aRemap[v148])) - v69;
LABEL_71:
      v71 = 0;
      v324 = 0;
      if ( !v66 )
      {
        if ( (int)(15 - v52) < 5 )
        {
          v179 = (unsigned int)++*(_DWORD *)(v4 + 8);
          v180 = *(_DWORD *)(v4 + 4);
          if ( (unsigned int)v179 >= 0x10 )
          {
            v214 = v179 >> 3;
            LODWORD(v179) = *(_DWORD *)(v4 + 8) & 0xF;
            v215 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + v214));
            *(_DWORD *)(v4 + 8) = v179;
            *(_QWORD *)(v4 + 24) = v215;
            v181 = _byteswap_ulong(*v215) << v179;
          }
          else
          {
            v181 = 2 * v180;
          }
          *(_DWORD *)(v4 + 4) = v181;
          if ( v180 >= 0 )
          {
            v199 = v179 + 1;
            *(_DWORD *)(v4 + 8) = v199;
            if ( v199 >= 0x10 )
            {
              v231 = v199;
              v199 &= 0xFu;
              v232 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v231 >> 3)));
              *(_DWORD *)(v4 + 8) = v199;
              *(_QWORD *)(v4 + 24) = v232;
              v200 = _byteswap_ulong(*v232) << v199;
            }
            else
            {
              v200 = 2 * v181;
            }
            *(_DWORD *)(v4 + 4) = v200;
            if ( v181 < 0 )
            {
              v71 = 2;
            }
            else
            {
              v201 = v199 + 1;
              *(_DWORD *)(v4 + 8) = v199 + 1;
              if ( v199 + 1 >= 0x10 )
              {
                v248 = v201;
                v249 = v201 & 0xF;
                v250 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v248 >> 3)));
                *(_DWORD *)(v4 + 8) = v249;
                *(_QWORD *)(v4 + 24) = v250;
                v202 = _byteswap_ulong(*v250) << v249;
              }
              else
              {
                v202 = 2 * v200;
              }
              *(_DWORD *)(v4 + 4) = v202;
              v71 = (v200 >= 0) + 3;
            }
          }
          else
          {
            v71 = 1;
          }
        }
        else
        {
          v72 = *(int *)(v4 + 12);
          v73 = *(__int16 *)(*(_QWORD *)(*(_QWORD *)v313 + 64LL)
                           + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27)) >> 3;
          v74 = (*(_BYTE *)(v4 + 8)
               + (*(_WORD *)(*(_QWORD *)(*(_QWORD *)v313 + 64LL)
                           + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27))
                & 7))
              & 0xF;
          v75 = (unsigned int *)(v72
                               & (*(_QWORD *)(v4 + 24)
                                + ((unsigned __int64)(*(_DWORD *)(v4 + 8)
                                                    + (*(_WORD *)(*(_QWORD *)(*(_QWORD *)v313 + 64LL)
                                                                + 2
                                                                * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27))
                                                     & 7u)) >> 3)));
          *(_DWORD *)(v4 + 8) = v74;
          *(_QWORD *)(v4 + 24) = v75;
          v76 = _byteswap_ulong(*v75) << v74;
          *(_DWORD *)(v4 + 4) = v76;
          v77 = v73 + 5 * *((_DWORD *)&unk_18004762C - v52);
          v78 = gSignificantRunFixedLength[v77];
          v79 = `DecodeSignificantRun'::`2'::aRemap[v77];
          if ( v78 )
          {
            *(_DWORD *)(v4 + 8) = ((_BYTE)v74 + (_BYTE)v78) & 0xF;
            v80 = (unsigned int *)(v72 & ((unsigned __int64)v75 + ((unsigned __int64)(unsigned int)(v74 + v78) >> 3)));
            *(_QWORD *)(v4 + 24) = v80;
            *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v80) << ((v74 + v78) & 0xF);
            v71 = v79 + (v76 >> (32 - v78));
          }
          else
          {
            v71 = `DecodeSignificantRun'::`2'::aRemap[v77];
          }
        }
        v324 = v71;
      }
      v81 = v52 + v71 + 1;
      if ( v65 )
      {
        v82 = 2;
        do
        {
          v83 = 0;
          v325[v82 - 1] = 0;
          if ( (v65 & 1) == 0 )
          {
            v84 = 15 - v81;
            if ( 15 - v81 < 5 )
            {
              if ( v84 == 1 )
              {
                v83 = 1;
              }
              else
              {
                v150 = (unsigned int)++*(_DWORD *)(v4 + 8);
                v151 = *(_DWORD *)(v4 + 4);
                if ( (unsigned int)v150 >= 0x10 )
                {
                  v197 = v150 >> 3;
                  LODWORD(v150) = *(_DWORD *)(v4 + 8) & 0xF;
                  v198 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + v197));
                  *(_DWORD *)(v4 + 8) = v150;
                  *(_QWORD *)(v4 + 24) = v198;
                  v152 = _byteswap_ulong(*v198) << v150;
                }
                else
                {
                  v152 = 2 * v151;
                }
                *(_DWORD *)(v4 + 4) = v152;
                if ( v151 >= 0 )
                {
                  if ( v84 == 2 )
                    goto LABEL_148;
                  v187 = v150 + 1;
                  *(_DWORD *)(v4 + 8) = v187;
                  if ( v187 >= 0x10 )
                  {
                    v216 = v187;
                    v187 &= 0xFu;
                    v217 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v216 >> 3)));
                    *(_DWORD *)(v4 + 8) = v187;
                    *(_QWORD *)(v4 + 24) = v217;
                    v188 = _byteswap_ulong(*v217) << v187;
                  }
                  else
                  {
                    v188 = 2 * v152;
                  }
                  *(_DWORD *)(v4 + 4) = v188;
                  if ( v152 < 0 )
                  {
LABEL_148:
                    v83 = 2;
                  }
                  else
                  {
                    if ( v84 == 3 )
                      goto LABEL_173;
                    v209 = v187 + 1;
                    *(_DWORD *)(v4 + 8) = v187 + 1;
                    if ( v187 + 1 >= 0x10 )
                    {
                      v223 = v209;
                      v224 = v209 & 0xF;
                      v225 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v223 >> 3)));
                      *(_DWORD *)(v4 + 8) = v224;
                      *(_QWORD *)(v4 + 24) = v225;
                      v210 = _byteswap_ulong(*v225) << v224;
                    }
                    else
                    {
                      v210 = 2 * v188;
                    }
                    *(_DWORD *)(v4 + 4) = v210;
                    if ( v188 < 0 )
LABEL_173:
                      v83 = 3;
                    else
                      v83 = 4;
                  }
                }
                else
                {
                  v83 = 1;
                }
              }
            }
            else
            {
              v85 = *(int *)(v4 + 12);
              v86 = *(__int16 *)(*(_QWORD *)(*(_QWORD *)v313 + 64LL)
                               + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27)) >> 3;
              v87 = (*(_BYTE *)(v4 + 8)
                   + (*(_WORD *)(*(_QWORD *)(*(_QWORD *)v313 + 64LL)
                               + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27))
                    & 7))
                  & 0xF;
              v88 = (unsigned int *)(v85
                                   & (*(_QWORD *)(v4 + 24)
                                    + ((unsigned __int64)(*(_DWORD *)(v4 + 8)
                                                        + (*(_WORD *)(*(_QWORD *)(*(_QWORD *)v313 + 64LL)
                                                                    + 2
                                                                    * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27))
                                                         & 7u)) >> 3)));
              *(_DWORD *)(v4 + 8) = v87;
              *(_QWORD *)(v4 + 24) = v88;
              v89 = _byteswap_ulong(*v88) << v87;
              v90 = gSignificantRunBin[v84];
              *(_DWORD *)(v4 + 4) = v89;
              v91 = v86 + 5 * v90;
              v92 = gSignificantRunFixedLength[v91];
              v93 = `DecodeSignificantRun'::`2'::aRemap[v91];
              if ( v92 )
              {
                *(_DWORD *)(v4 + 8) = ((_BYTE)v87 + (_BYTE)v92) & 0xF;
                v94 = (unsigned int *)(v85 & ((unsigned __int64)v88 + ((unsigned __int64)(unsigned int)(v87 + v92) >> 3)));
                *(_QWORD *)(v4 + 24) = v94;
                *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v94) << ((v87 + v92) & 0xF);
                v83 = v93 + (v89 >> (32 - v92));
              }
              else
              {
                v83 = `DecodeSignificantRun'::`2'::aRemap[v91];
              }
            }
            v325[v82 - 1] = v83;
          }
          v81 += v83 + 1;
          if ( v81 >= 15 )
          {
            v157 = *(_DWORD *)(v4 + 4);
            v158 = *(_DWORD *)(v4 + 8) + 1;
            *(_DWORD *)(v4 + 8) = v158;
            if ( v81 == 15 )
            {
              if ( v158 >= 0x10 )
              {
                v212 = v158;
                v158 &= 0xFu;
                v213 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v212 >> 3)));
                *(_DWORD *)(v4 + 8) = v158;
                *(_QWORD *)(v4 + 24) = v213;
                v182 = _byteswap_ulong(*v213) << v158;
              }
              else
              {
                v182 = 2 * v157;
              }
              *(_DWORD *)(v4 + 4) = v182;
              if ( v157 >= 0 )
              {
                v97 = 0;
              }
              else
              {
                v183 = v158 + 1;
                *(_DWORD *)(v4 + 8) = v183;
                if ( v183 >= 0x10 )
                {
                  v218 = v183;
                  v183 &= 0xFu;
                  v219 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v218 >> 3)));
                  *(_DWORD *)(v4 + 8) = v183;
                  *(_QWORD *)(v4 + 24) = v219;
                  v184 = _byteswap_ulong(*v219) << v183;
                }
                else
                {
                  v184 = 2 * v182;
                }
                *(_DWORD *)(v4 + 4) = v184;
                if ( v182 < 0 )
                {
                  v203 = v183 + 1;
                  v204 = v184 >> 31;
                  *(_DWORD *)(v4 + 8) = v183 + 1;
                  if ( v183 + 1 >= 0x10 )
                  {
                    v220 = v203;
                    v221 = v203 & 0xF;
                    v222 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v220 >> 3)));
                    *(_DWORD *)(v4 + 8) = v221;
                    *(_QWORD *)(v4 + 24) = v222;
                    v205 = _byteswap_ulong(*v222) << v221;
                  }
                  else
                  {
                    v205 = 2 * v184;
                  }
                  v97 = 2 * v204 + 1;
                  *(_DWORD *)(v4 + 4) = v205;
                }
                else
                {
                  v97 = 2;
                }
              }
            }
            else
            {
              v159 = v158;
              v160 = v158 & 0xF;
              v161 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v159 >> 3)));
              *(_DWORD *)(v4 + 8) = v160;
              *(_QWORD *)(v4 + 24) = v161;
              v97 = (unsigned int)v157 >> 31;
              *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v161) << v160;
            }
          }
          else
          {
            v95 = *(_QWORD *)&v318[2 * v303 + 2];
            v96 = *(int *)(v4 + 12);
            v97 = *(__int16 *)(*(_QWORD *)(v95 + 64) + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27)) >> 3;
            v98 = *(_DWORD *)(v4 + 8)
                + (*(_WORD *)(*(_QWORD *)(v95 + 64) + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27)) & 7u);
            v99 = (*(_BYTE *)(v4 + 8)
                 + (*(_WORD *)(*(_QWORD *)(v95 + 64) + 2 * ((unsigned __int64)*(unsigned int *)(v4 + 4) >> 27)) & 7))
                & 0xF;
            *(_DWORD *)(v4 + 8) = v99;
            v100 = (unsigned int *)(v96 & (*(_QWORD *)(v4 + 24) + (v98 >> 3)));
            *(_QWORD *)(v4 + 24) = v100;
            *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v100) << v99;
            v101 = 4LL * v97;
            *(_DWORD *)(v95 + 76) += *(_DWORD *)(*(_QWORD *)(v95 + 40) + v101);
            *(_DWORD *)(v95 + 80) += *(_DWORD *)(*(_QWORD *)(v95 + 48) + v101);
          }
          v102 = *(_DWORD *)(v4 + 4);
          v103 = *(_DWORD *)(v4 + 8) + 1;
          v65 = v97 >> 1;
          v303 &= v97 >> 1;
          v104 = v102 >> 31;
          *(_DWORD *)(v4 + 8) = v103;
          if ( v103 >= 0x10 )
          {
            v155 = v103;
            v103 &= 0xFu;
            v156 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v155 >> 3)));
            *(_DWORD *)(v4 + 8) = v103;
            *(_QWORD *)(v4 + 24) = v156;
            v105 = _byteswap_ulong(*v156) << v103;
          }
          else
          {
            v105 = 2 * v102;
          }
          *(_DWORD *)(v4 + 4) = v105;
          if ( (v97 & 1) != 0 )
          {
            v114 = *(_QWORD *)&v313[2 * v303 + 22];
            v315 = v114;
            v316 = *(_QWORD *)(v114 + 64);
            v115 = *(__int16 *)(v316 + 2 * ((unsigned __int64)v105 >> 27));
            v116 = v115 & 7;
            if ( v115 < 0 )
              v116 = 5;
            v117 = v103 + v116;
            v118 = ((_BYTE)v103 + (_BYTE)v116) & 0xF;
            v119 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + (v117 >> 3)));
            *(_DWORD *)(v4 + 8) = v118;
            *(_QWORD *)(v4 + 24) = v119;
            v120 = _byteswap_ulong(*v119) << v118;
            *(_DWORD *)(v4 + 4) = v120;
            if ( v115 >> 3 < 0 )
            {
              v226 = v316;
              v227 = *(int *)(v4 + 12);
              do
              {
                v228 = (unsigned int)(v118 + 1);
                v118 = ((_BYTE)v118 + 1) & 0xF;
                *(_DWORD *)(v4 + 8) = v118;
                v119 = (unsigned int *)(v227 & ((unsigned __int64)v119 + (v228 >> 3)));
                v229 = (v120 >> 31) + v115 + 0x8000;
                *(_QWORD *)(v4 + 24) = v119;
                v230 = _byteswap_ulong(*v119) << v118;
                *(_DWORD *)(v4 + 4) = v230;
                v120 = v230;
                v115 = *(__int16 *)(v226 + 2 * v229);
              }
              while ( v115 < 0 );
              v38 = v317;
              v114 = v315;
            }
            else
            {
              v115 >>= 3;
            }
            v121 = (unsigned int)v115;
            *(_DWORD *)(v114 + 76) += *(_DWORD *)(*(_QWORD *)(v114 + 40) + v121 * 4);
            if ( (unsigned int)v115 >= 2 )
            {
              if ( (unsigned int)v115 < 6 )
              {
                _mm_lfence();
                v134 = `DecodeSignificantAbsLevel'::`2'::aFixedLength[v121];
                v135 = *(int *)(v4 + 12);
                v56 = v310;
                v136 = *(_DWORD *)(v4 + 4) >> (32 - v134);
                v137 = (unsigned int)(v134 + *(_DWORD *)(v4 + 8));
                v138 = v137 & 0xF;
                *(_DWORD *)(v4 + 8) = v137 & 0xF;
                v139 = (unsigned int *)(v135 & (*(_QWORD *)(v4 + 24) + (v137 >> 3)));
                *(_QWORD *)(v4 + 24) = v139;
                LODWORD(v135) = _byteswap_ulong(*v139) << v138;
                v140 = v136 + `DecodeSignificantAbsLevel'::`2'::aRemap[v121];
                *(_DWORD *)(v4 + 4) = v135;
                v106 = (v104 ^ v140) - v104;
                goto LABEL_89;
              }
              v167 = *(int *)(v4 + 12);
              v168 = (*(_BYTE *)(v4 + 8) + 4) & 0xF;
              v169 = (unsigned int *)(v167
                                    & (*(_QWORD *)(v4 + 24)
                                     + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v4 + 8) + 4) >> 3)));
              v170 = *(_DWORD *)(v4 + 4) >> 28;
              *(_QWORD *)(v4 + 24) = v169;
              v171 = v170 + 4;
              *(_DWORD *)(v4 + 8) = v168;
              v172 = _byteswap_ulong(*v169) << v168;
              *(_DWORD *)(v4 + 4) = v172;
              if ( v171 == 19 )
              {
                v236 = v168 + 2;
                v237 = (v172 >> 30) + 19;
                v238 = (unsigned __int64)v236 >> 3;
                v239 = v236 & 0xF;
                *(_DWORD *)(v4 + 8) = v239;
                v240 = (unsigned int *)(v167 & ((unsigned __int64)v169 + v238));
                *(_QWORD *)(v4 + 24) = v240;
                v241 = _byteswap_ulong(*v240) << v239;
                *(_DWORD *)(v4 + 4) = v241;
                if ( v237 == 22 )
                {
                  *(_DWORD *)(v4 + 8) = ((_BYTE)v239 + 3) & 0xF;
                  v242 = (unsigned int *)(v167
                                        & ((unsigned __int64)v240 + ((unsigned __int64)(unsigned int)(v239 + 3) >> 3)));
                  *(_QWORD *)(v4 + 24) = v242;
                  *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v242) << ((v239 + 3) & 0xF);
                  v171 = (v241 >> 29) + 22;
                }
                else
                {
                  v171 = v237;
                }
              }
              v122 = getBit32(v4, v171) + (1 << v171) + 2;
            }
            else
            {
              v122 = v115 + 2;
            }
            v56 = v310;
            v106 = (v104 ^ v122) - v104;
          }
          else
          {
            v106 = v104 | 1;
          }
LABEL_89:
          v107 = v82;
          ++v56;
          v82 += 2;
          v310 = v56;
          v325[v107] = v106;
        }
        while ( v65 );
      }
      v39 = v302;
      LODWORD(v35) = v306;
      if ( (unsigned int)(v302 - 1) <= 1 && v306 )
      {
        v282 = 0;
        v283 = 6;
        if ( v302 == 1 )
          v282 = 4;
        v284 = (char *)&unk_180049710 + v282;
        if ( v302 != 1 )
          v283 = 14;
        v285 = 0;
        *(_DWORD *)v314 += v56;
        memset_0(v321, 0, sizeof(v321));
        for ( j = 0; j < v56; v321[v288 & 0xF] = v325[v287] )
        {
          v287 = 2 * j++;
          v288 = v285 + v325[v287 - 1];
          v285 = v288 + 1;
        }
        for ( k = 0; k < v283; ++k )
        {
          v290 = k;
          v291 = *(int *)&v284[4 * ((__int64)k >> 1)];
          v292 = k & 1;
          *(_DWORD *)(v323[v292] + 4 * v291) = v321[v290];
        }
        v36 = v301;
        v18 = v300;
        v5 = v308;
        v34 = (__int64 (__fastcall *)(__int64, _QWORD))v305;
        v37 = v309;
LABEL_38:
        v39 = v302;
        goto LABEL_39;
      }
      v108 = 0;
      v109 = 1;
      *(_DWORD *)v314 += v56;
      if ( v56 > 0 )
      {
        v110 = v319;
        do
        {
          v111 = 2 * v108;
          v112 = v325[v111 - 1] + v109;
          *(_DWORD *)(v38 + 4LL * (unsigned int)v110[2 * v112 + 1]) = v325[v111];
          if ( ++v110[2 * v112] > v110[2 * v112 - 2] )
          {
            v113 = *(_QWORD *)&v110[2 * v112];
            *(_QWORD *)&v110[2 * v112] = *(_QWORD *)&v110[2 * v112 - 2];
            *(_QWORD *)&v110[2 * v112 - 2] = v113;
          }
          v109 = v112 + 1;
          ++v108;
        }
        while ( v108 < v56 );
      }
      v36 = v301;
      v18 = v300;
      v5 = v308;
      v34 = (__int64 (__fastcall *)(__int64, _QWORD))v305;
      v37 = v309;
LABEL_39:
      if ( v36 )
      {
        if ( (unsigned int)(v39 - 1) > 1 || !(_DWORD)v35 )
        {
          v123 = 1 << v36;
          v124 = 31 - v36;
          for ( m = 1; m != 16; ++m )
          {
            v126 = *(_DWORD *)(v38 + 4 * m);
            if ( v126 )
            {
              v130 = __ROL4__(v126, v36);
              v131 = v34(v4, v36);
              v36 = v301;
              *(_DWORD *)(v38 + 4 * m) = (v130 ^ v131) - (v130 & (v123 - 1));
            }
            else
            {
              v127 = ((*(_DWORD *)(v4 + 4) >> v124) & 1)
                   + (((int)(*(_DWORD *)(v4 + 4) >> v124) >> 1) ^ -((*(_DWORD *)(v4 + 4) >> v124) & 1));
              *(_DWORD *)(v38 + 4 * m) = v127;
              v128 = ((_BYTE)v36 + *(_BYTE *)(v4 + 8) + (v127 != 0)) & 0xF;
              v129 = (unsigned int *)(*(int *)(v4 + 12)
                                    & (*(_QWORD *)(v4 + 24)
                                     + ((unsigned __int64)(v36 + *(_DWORD *)(v4 + 8) + (v127 != 0)) >> 3)));
              *(_DWORD *)(v4 + 8) = v128;
              *(_QWORD *)(v4 + 24) = v129;
              *(_DWORD *)(v4 + 4) = _byteswap_ulong(*v129) << v128;
            }
            v34 = (__int64 (__fastcall *)(__int64, _QWORD))v305;
          }
          v18 = v300;
LABEL_110:
          v5 = v308;
          goto LABEL_40;
        }
        v258 = 1;
        v259 = 4;
        if ( v39 != 1 )
          v259 = 8;
        while ( 1 )
        {
          if ( v258 >= v259 )
            goto LABEL_110;
          v260 = 4LL * v258;
          v261 = *(_DWORD *)(v260 + v37);
          if ( v261 > 0 )
            break;
          if ( v261 >= 0 )
          {
            v295 = v34(v4, v36);
            v264 = v309;
            *(_DWORD *)(v260 + v309) = v295;
            if ( v295 )
            {
              v269 = (unsigned int)++*(_DWORD *)(v4 + 8);
              v270 = *(_DWORD *)(v4 + 4);
              if ( (unsigned int)v269 >= 0x10 )
              {
                v272 = v269 >> 3;
                v273 = *(_DWORD *)(v4 + 8) & 0xF;
                v274 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + v272));
                *(_DWORD *)(v4 + 8) = v273;
                *(_QWORD *)(v4 + 24) = v274;
                v271 = _byteswap_ulong(*v274) << v273;
              }
              else
              {
                v271 = 2 * v270;
              }
              *(_DWORD *)(v4 + 4) = v271;
              if ( v270 < 0 )
              {
                v265 = -*(_DWORD *)(v260 + v264);
                goto LABEL_238;
              }
            }
          }
          else
          {
            v293 = v261 << v36;
            *(_DWORD *)(v260 + v37) = v293;
            v294 = v34(v4, v36);
            *(_DWORD *)(v260 + v309) = v293 - v294;
          }
LABEL_239:
          v266 = *(_DWORD *)(v260 + v312);
          if ( v266 > 0 )
          {
            v296 = v266 << v301;
            *(_DWORD *)(v260 + v312) = v296;
            v297 = v305(v4);
            *(_DWORD *)(v260 + v312) = v296 + v297;
          }
          else if ( v266 < 0 )
          {
            v298 = v266 << v301;
            *(_DWORD *)(v260 + v312) = v298;
            v299 = v305(v4);
            *(_DWORD *)(v260 + v312) = v298 - v299;
          }
          else
          {
            v267 = ((__int64 (__fastcall *)(__int64, _QWORD))v305)(v4, v301);
            v268 = v312;
            *(_DWORD *)(v260 + v312) = v267;
            if ( v267 )
            {
              v275 = (unsigned int)++*(_DWORD *)(v4 + 8);
              v276 = *(_DWORD *)(v4 + 4);
              if ( (unsigned int)v275 >= 0x10 )
              {
                v278 = v275 >> 3;
                v279 = *(_DWORD *)(v4 + 8) & 0xF;
                v280 = (unsigned int *)(*(int *)(v4 + 12) & (*(_QWORD *)(v4 + 24) + v278));
                *(_DWORD *)(v4 + 8) = v279;
                *(_QWORD *)(v4 + 24) = v280;
                v281 = *v280;
                v268 = v312;
                v277 = _byteswap_ulong(v281) << v279;
              }
              else
              {
                v277 = 2 * v276;
              }
              *(_DWORD *)(v4 + 4) = v277;
              if ( v276 < 0 )
                *(_DWORD *)(v260 + v268) = -*(_DWORD *)(v260 + v268);
            }
          }
          v36 = v301;
          ++v258;
          v34 = (__int64 (__fastcall *)(__int64, _QWORD))v305;
          v37 = v309;
        }
        v262 = v261 << v36;
        *(_DWORD *)(v260 + v37) = v262;
        v263 = v34(v4, v36);
        v264 = v309;
        v265 = v262 + v263;
LABEL_238:
        *(_DWORD *)(v260 + v264) = v265;
        goto LABEL_239;
      }
LABEL_40:
      v36 = v5[158];
      v16 = v302;
      v35 = (unsigned int)(v35 + 1);
      v34 = (__int64 (__fastcall *)(__int64, _QWORD))v305;
      v37 = v309;
      v18 >>= 1;
      v314 = (__int64 *)((char *)&v304 + 4);
      v301 = v36;
      v300 = v18;
      v306 = v35;
      if ( (int)v35 >= v307 )
      {
        v10 = HIDWORD(v304);
        v9 = v304;
        goto LABEL_42;
      }
    }
    v50 = 9;
LABEL_60:
    v51 = 1;
    goto LABEL_61;
  }
LABEL_42:
  v40 = (int)v5[159];
  v41 = v40 - 1;
  LODWORD(v304) = dword_180049D10[v41] * v9;
  if ( v16 == 1 )
  {
    v43 = dword_180049C70[v41] * v10;
  }
  else if ( v16 == 2 )
  {
    v43 = dword_180049C78[v40] * v10;
  }
  else
  {
    v42 = dword_180049D1C[16 * v40 - 16 + v311] * v10;
    HIDWORD(v304) = v42;
    if ( (_DWORD)v40 != 3 )
      goto LABEL_47;
    v43 = v42 >> 4;
  }
  HIDWORD(v304) = v43;
LABEL_47:
  v44 = 0;
  do
  {
    v45 = v5[v44 + 155];
    v46 = (*((_DWORD *)&v304 + v44) - 70) >> 2;
    if ( v46 > -8 )
    {
      if ( v46 >= 8 )
      {
        v132 = v46 - 4;
        if ( v132 > 15 )
          v132 = 15;
        v45 += v132;
        if ( v45 > 8 )
        {
          v133 = v5[v44 + 157];
          if ( v133 >= 15 )
          {
            v5[v44 + 157] = 15;
            v45 = 8;
          }
          else
          {
            v45 = 0;
            v5[v44 + 157] = v133 + 1;
          }
        }
      }
    }
    else
    {
      v47 = v46 + 4;
      if ( v47 < -16 )
        v47 = -16;
      v45 += v47;
      if ( v45 < -8 )
      {
        v48 = v5[v44 + 157];
        if ( v48 )
        {
          v45 = 0;
          v5[v44 + 157] = v48 - 1;
        }
        else
        {
          v45 = -8;
        }
      }
    }
    v5[v44 + 155] = v45;
    if ( !v16 )
      break;
    v44 = (unsigned int)(v44 + 1);
  }
  while ( (int)v44 < 2 );
  if ( !*(_DWORD *)(v320 + 34460) )
    return 0;
  return (unsigned int)-((unsigned int)AdaptLowpassDec(v5) != 0);
}

```

## disassembly

```asm
0x18000a220  push    rbp
0x18000a222  push    rbx
0x18000a223  push    rsi
0x18000a224  push    rdi
0x18000a225  push    r12
0x18000a227  push    r13
0x18000a229  push    r15
0x18000a22b  lea     rbp, [rsp-100h]
0x18000a233  sub     rsp, 200h
0x18000a23a  mov     rax, cs:__security_cookie
0x18000a241  xor     rax, rsp
0x18000a244  mov     [rbp+130h+var_40], rax
0x18000a24b  mov     eax, [rcx+85A8h]
0x18000a251  mov     r13, rcx
0x18000a254  mov     rsi, [rdx+8]
0x18000a258  mov     r15, rdx
0x18000a25b  mov     [rbp+130h+var_190], rcx
0x18000a25f  mov     r12d, 2
0x18000a265  mov     ecx, [rcx+85C0h]
0x18000a26b  mov     r8d, 80h; Size
0x18000a271  mov     [rsp+230h+var_1E8], rdx
0x18000a276  mov     edx, [rdx+274h]
0x18000a27c  mov     [rsp+230h+var_208], eax
0x18000a280  dec     eax
0x18000a282  cmp     eax, 1
0x18000a285  mov     [rsp+230h+var_1D4], ecx
0x18000a289  mov     [rsp+230h+var_20C], edx
0x18000a28d  cmova   r12d, ecx
0x18000a291  xor     edi, edi
0x18000a293  xor     edx, edx; Val
0x18000a295  mov     [rsp+230h+var_200], rdi
0x18000a29a  lea     rcx, [rbp+130h+var_140]; void *
0x18000a29e  mov     [rsp+230h+var_1EC], r12d
0x18000a2a3  xor     ebx, ebx
0x18000a2a5  call    memset_0
0x18000a2aa  cmp     [rsi+30h], ebx
0x18000a2ad  jz      loc_18000B17B
0x18000a2b3  lea     rax, [r15+0D8h]
0x18000a2ba  mov     [rsp+230h+arg_10], r14
0x18000a2c2  mov     [rbp+130h+var_198], rax
0x18000a2c6  lea     r14, [r13+8118h]
0x18000a2cd  lea     rax, [rsp+230h+var_200]
0x18000a2d2  mov     [rsp+230h+var_1C0], rax
0x18000a2d7  mov     eax, [rsi+18h]
0x18000a2da  xor     eax, [rsi+10h]
0x18000a2dd  bt      rax, 0Ch
0x18000a2e2  jb      loc_18000B32E
0x18000a2e8  cmp     [r13+0A8h], ebx
0x18000a2ef  jnz     loc_18000A378
0x18000a2f5  mov     r8d, [r13+85C0h]
0x18000a2fc  xor     edx, edx
0x18000a2fe  test    r8d, r8d
0x18000a301  jle     short loc_18000A31D
0x18000a303  mov     ecx, edx
0x18000a305  mov     eax, edx
0x18000a307  and     ecx, 0Fh
0x18000a30a  shl     rax, 6
0x18000a30e  inc     edx
0x18000a310  add     rax, r14
0x18000a313  mov     [rbp+rcx*8+130h+var_140], rax
0x18000a318  cmp     edx, r8d
0x18000a31b  jl      short loc_18000A303
0x18000a31d  cmp     [r13+8698h], ebx
0x18000a324  jnz     loc_18000B096
0x18000a32a  mov     r9d, [rsp+230h+var_208]
0x18000a32f  lea     eax, [r9-1]
0x18000a333  cmp     eax, 2
0x18000a336  jbe     short loc_18000A3AE
0x18000a338  mov     r13d, [rsp+230h+var_1D4]
0x18000a33d  xor     r12d, r12d
0x18000a340  xor     r14d, r14d
0x18000a343  mov     [rsp+230h+var_210], r12d
0x18000a348  test    r13d, r13d
0x18000a34b  jle     loc_18000A46B
0x18000a351  mov     edx, 1
0x18000a356  mov     rcx, rsi
0x18000a359  call    _getBit16
0x18000a35e  mov     ecx, r14d
0x18000a361  inc     r14d
0x18000a364  shl     eax, cl
0x18000a366  or      r12d, eax
0x18000a369  cmp     r14d, r13d
0x18000a36c  jl      short loc_18000A351
0x18000a36e  mov     [rsp+230h+var_210], r12d
0x18000a373  jmp     loc_18000A466
0x18000a378  imul    rcx, [r13+8658h], 1B0h
0x18000a383  mov     rax, [r13+86A0h]
0x18000a38a  movzx   edx, byte ptr [rcx+rax+182h]
0x18000a392  test    dl, dl
0x18000a394  jz      loc_18000A2F5
0x18000a39a  mov     rcx, rsi
0x18000a39d  call    decodeQPIndex
0x18000a3a2  mov     [r14+484h], al
0x18000a3a9  jmp     loc_18000A2F5
0x18000a3ae  mov     r8d, [r15+294h]
0x18000a3b5  lea     r10d, ds:0FFFFFFFFFFFFFFFBh[r12*4]
0x18000a3bd  mov     r9d, [r15+298h]
0x18000a3c4  test    r8d, r8d
0x18000a3c7  jg      loc_18000ADC0
0x18000a3cd  inc     dword ptr [rsi+8]
0x18000a3d0  xor     r12d, r12d
0x18000a3d3  mov     r14d, [rsi+8]
0x18000a3d7  mov     edx, [rsi+4]
0x18000a3da  mov     [rsp+230h+var_210], r12d
0x18000a3df  cmp     r14d, 10h
0x18000a3e3  jnb     loc_18000B23B
0x18000a3e9  lea     r11d, [rdx+rdx]
0x18000a3ed  mov     [rsi+4], r11d
0x18000a3f1  test    edx, edx
0x18000a3f3  js      loc_18000AF99
0x18000a3f9  mov     [rsp+230h+var_210], r12d
0x18000a3fe  cmp     r9d, r8d
0x18000a401  jge     short loc_18000A410
0x18000a403  mov     eax, r10d
0x18000a406  sub     eax, r12d
0x18000a409  mov     r12d, eax
0x18000a40c  mov     [rsp+230h+var_210], eax
0x18000a410  xor     eax, eax
0x18000a412  mov     ecx, 4
0x18000a417  cmp     r12d, r10d
0x18000a41a  cmovz   eax, ecx
0x18000a41d  sub     r9d, eax
0x18000a420  xor     eax, eax
0x18000a422  inc     r9d
0x18000a425  test    r12d, r12d
0x18000a428  cmovz   eax, ecx
0x18000a42b  sub     r8d, eax
0x18000a42e  mov     eax, 7
0x18000a433  inc     r8d
0x18000a436  cmp     r9d, 0FFFFFFF8h
0x18000a43a  jge     loc_18000AE38
0x18000a440  mov     r9d, 0FFFFFFF8h
0x18000a446  mov     [r15+298h], r9d
0x18000a44d  cmp     r8d, 0FFFFFFF8h
0x18000a451  jl      loc_18000AE55
0x18000a457  cmp     r8d, eax
0x18000a45a  jle     short loc_18000A45F
0x18000a45c  mov     r8d, eax
0x18000a45f  mov     [r15+294h], r8d
0x18000a466  mov     r9d, [rsp+230h+var_208]
0x18000a46b  cmp     dword ptr [r15+274h], 0Eh
0x18000a473  jg      loc_18000B8D7
0x18000a479  cmp     dword ptr [r15+278h], 0Eh
0x18000a481  lea     r10, _getBit16
0x18000a488  mov     [rsp+230h+var_1F8], r10
0x18000a48d  jg      loc_18000B8D7
0x18000a493  xor     r13d, r13d
0x18000a496  lea     r11, __ImageBase
0x18000a49d  mov     r14d, 0Fh
0x18000a4a3  mov     [rsp+230h+var_1F0], r13d
0x18000a4a8  cmp     [rsp+230h+var_1EC], ebx
0x18000a4ac  jle     loc_18000A551
0x18000a4b2  mov     rdx, [rbp+130h+var_130]
0x18000a4b6  mov     ebx, 40h ; '@'
0x18000a4bb  mov     r8d, [rsp+230h+var_20C]
0x18000a4c0  mov     r11d, 5
0x18000a4c6  mov     [rsp+230h+var_1D0], rdx
0x18000a4cb  mov     rdx, [rbp+130h+var_138]
0x18000a4cf  mov     [rsp+230h+var_1E0], rdx
0x18000a4d4  mov     r14, [rbp+r13*8+130h+var_140]
0x18000a4d9  mov     [rbp+130h+var_1A8], r14
0x18000a4dd  test    r12b, 1
0x18000a4e1  jnz     loc_18000A643
0x18000a4e7  mov     r11d, [rsp+230h+var_208]
0x18000a4ec  test    r8d, r8d
0x18000a4ef  jnz     loc_18000AB58
0x18000a4f5  mov     r8d, [r15+278h]
0x18000a4fc  lea     rax, [rsp+230h+var_200+4]
0x18000a501  mov     r9d, [rsp+230h+var_208]
0x18000a506  inc     r13d
0x18000a509  mov     r10, [rsp+230h+var_1F8]
0x18000a50e  mov     ebx, 40h ; '@'
0x18000a513  mov     rdx, [rsp+230h+var_1E0]
0x18000a518  mov     r11d, 5
0x18000a51e  sar     r12d, 1
0x18000a521  mov     [rsp+230h+var_1C0], rax
0x18000a526  mov     [rsp+230h+var_20C], r8d
0x18000a52b  mov     [rsp+230h+var_210], r12d
0x18000a530  mov     [rsp+230h+var_1F0], r13d
0x18000a535  cmp     r13d, [rsp+230h+var_1EC]
0x18000a53a  jl      short loc_18000A4D4
0x18000a53c  mov     ebx, dword ptr [rsp+230h+var_200+4]
0x18000a540  lea     r11, __ImageBase
0x18000a547  mov     edi, dword ptr [rsp+230h+var_200]
0x18000a54b  mov     r14d, 0Fh
0x18000a551  movsxd  rdx, dword ptr [r15+27Ch]
0x18000a558  lea     rcx, [rdx-1]
0x18000a55c  lea     rax, ds:0[rcx*4]
0x18000a564  imul    edi, [rax+r11+49D10h]
0x18000a56d  mov     dword ptr [rsp+230h+var_200], edi
0x18000a571  cmp     r9d, 1
0x18000a575  jz      loc_18000ACCD
0x18000a57b  cmp     r9d, 2
0x18000a57f  jz      loc_18000BA79
0x18000a585  movsxd  rax, [rsp+230h+var_1D4]
0x18000a58a  shl     rcx, 4
0x18000a58e  add     rcx, rax
0x18000a591  imul    ebx, ds:rva dword_180049D1C[r11+rcx*4]
0x18000a59a  mov     dword ptr [rsp+230h+var_200+4], ebx
0x18000a59e  cmp     edx, 3
0x18000a5a1  jnz     short loc_18000A5AA
0x18000a5a3  sar     ebx, 4
0x18000a5a6  mov     dword ptr [rsp+230h+var_200+4], ebx
0x18000a5aa  xor     edx, edx
0x18000a5ac  mov     r10d, 0FFFFFFF0h
0x18000a5b2  mov     eax, dword ptr [rsp+rdx*4+230h+var_200]
0x18000a5b6  mov     ecx, [r15+rdx*4+26Ch]
0x18000a5be  sub     eax, 46h ; 'F'
0x18000a5c1  sar     eax, 2
0x18000a5c4  cmp     eax, 0FFFFFFF8h
0x18000a5c7  jg      loc_18000AC19
0x18000a5cd  add     eax, 4
0x18000a5d0  cmp     eax, r10d
0x18000a5d3  cmovl   eax, r10d
0x18000a5d7  add     ecx, eax
0x18000a5d9  cmp     ecx, 0FFFFFFF8h
0x18000a5dc  jge     short loc_18000A5F3
0x18000a5de  mov     eax, [r15+rdx*4+274h]
0x18000a5e6  test    eax, eax
0x18000a5e8  jnz     loc_18000AE44
0x18000a5ee  mov     ecx, 0FFFFFFF8h
0x18000a5f3  mov     [r15+rdx*4+26Ch], ecx
0x18000a5fb  test    r9d, r9d
0x18000a5fe  jz      short loc_18000A607
0x18000a600  inc     edx
0x18000a602  cmp     edx, 2
0x18000a605  jl      short loc_18000A5B2
0x18000a607  mov     rax, [rbp+130h+var_190]
0x18000a60b  mov     r14, [rsp+230h+arg_10]
0x18000a613  cmp     dword ptr [rax+869Ch], 0
0x18000a61a  jnz     loc_18000B013
0x18000a620  xor     eax, eax
0x18000a622  mov     rcx, [rbp+130h+var_40]
0x18000a629  xor     rcx, rsp; StackCookie
0x18000a62c  call    __security_check_cookie
0x18000a631  add     rsp, 200h
0x18000a638  pop     r15
0x18000a63a  pop     r13
0x18000a63c  pop     r12
0x18000a63e  pop     rdi
0x18000a63f  pop     rsi
0x18000a640  pop     rbx
0x18000a641  pop     rbp
0x18000a642  retn
0x18000a643  cmp     r9d, 1
0x18000a647  jz      loc_18000B8E8
0x18000a64d  xor     ecx, ecx
0x18000a64f  cmp     r9d, 2
0x18000a653  jz      loc_18000B8FC
0x18000a659  mov     eax, 1
0x18000a65e  cmp     [rsp+230h+var_1F0], 0
0x18000a663  lea     r13d, [rax+rcx]
0x18000a667  lea     rcx, [r15+30h]
0x18000a66b  mov     eax, 28h ; '('
0x18000a670  movsxd  r15, dword ptr [rsi+0Ch]
0x18000a674  cmova   rax, rbx
0x18000a678  add     rax, rcx
0x18000a67b  mov     [rsp+230h+var_1C8], rcx
0x18000a680  mov     [rbp+130h+var_1A0], rax
0x18000a684  mov     r12d, 1
0x18000a68a  mov     [rsp+230h+var_1D8], r12d
0x18000a68f  mov     r9, [rax]
0x18000a692  mov     eax, [rsi+4]
0x18000a695  shr     rax, 1Bh
0x18000a699  mov     rdi, [r9+40h]
0x18000a69d  movsx   r8d, word ptr [rdi+rax*2]
0x18000a6a2  mov     ecx, r8d
0x18000a6a5  mov     eax, r8d
0x18000a6a8  and     ecx, 7
0x18000a6ab  test    r8d, r8d
0x18000a6ae  cmovs   ecx, r11d
0x18000a6b2  mov     r11d, [rsi+8]
0x18000a6b6  add     r11d, ecx
0x18000a6b9  sar     eax, 3
0x18000a6bc  mov     r10d, r11d
0x18000a6bf  and     r11d, 0Fh
0x18000a6c3  shr     r10, 3
0x18000a6c7  mov     ecx, r11d
0x18000a6ca  add     r10, [rsi+18h]
0x18000a6ce  and     r10, r15
0x18000a6d1  mov     [rsi+8], r11d
0x18000a6d5  mov     [rsi+18h], r10
0x18000a6d9  mov     ebx, [r10]
0x18000a6dc  bswap   ebx
0x18000a6de  shl     ebx, cl
0x18000a6e0  mov     [rsi+4], ebx
0x18000a6e3  test    eax, eax
0x18000a6e5  js      loc_18000B5E1
0x18000a6eb  mov     r8d, eax
0x18000a6ee  mov     eax, r8d
0x18000a6f1  mov     ebx, r8d
0x18000a6f4  lea     rdx, ds:0[rax*4]
0x18000a6fc  shr     ebx, 2
0x18000a6ff  mov     rax, [r9+28h]
0x18000a703  mov     r15d, r8d
0x18000a706  and     r15d, r12d
0x18000a709  mov     ecx, [rax+rdx]
0x18000a70c  add     [r9+4Ch], ecx
0x18000a710  mov     rax, [r9+30h]
0x18000a714  mov     ecx, [rax+rdx]
  ... truncated ...
```
