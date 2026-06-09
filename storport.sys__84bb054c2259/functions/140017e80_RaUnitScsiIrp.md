# RaUnitScsiIrp

- ea: `0x140017e80`
- end: `0x14001ab30`
- name: `RaUnitScsiIrp`
- size: `11440`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140012590`
- `0x1400147f4`
- `0x140014bd4`
- `0x140014fe4`
- `0x1400173f0`
- `0x140017b80`
- `0x140017e80`
- `0x14001ab40`
- `0x140033b18`
- `0x140063e4c`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x1400848c4`
- `0x140093dc0`
- `0x140095098`
- `0x1400bdb38`
- `0x1400bf1c8`
- `0x1400c1a34`
- `0x1400c1dc8`
- `0x1400c2588`
- `0x14014b400`
- `0x1401971e4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140017f6a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140018208`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400184f1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400185c3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400186a8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001893e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140018bda`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140019ad6`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140019e49`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001a006`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001a177`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140017f6a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140018208`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400184f1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400185c3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400186a8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001893e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140018bda`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140019ad6`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140019e49`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001a006`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001a177`
- `ntoskrnl!KeSetEvent` at `0x140017f2f`
- `ntoskrnl!KeSetEvent` at `0x1400188a6`
- `ntoskrnl!KeSetEvent` at `0x140018a07`
- `ntoskrnl!KeSetEvent` at `0x140018b76`
- `ntoskrnl!KeSetEvent` at `0x140018d38`
- `ntoskrnl!KeSetEvent` at `0x140019b58`
- `ntoskrnl!KeSetEvent` at `0x140019c70`
- `ntoskrnl!KeSetEvent` at `0x14001a085`
- `ntoskrnl!KeSetEvent` at `0x140017f2f`
- `ntoskrnl!KeSetEvent` at `0x1400188a6`
- `ntoskrnl!KeSetEvent` at `0x140018a07`
- `ntoskrnl!KeSetEvent` at `0x140018b76`
- `ntoskrnl!KeSetEvent` at `0x140018d38`
- `ntoskrnl!KeSetEvent` at `0x140019b58`
- `ntoskrnl!KeSetEvent` at `0x140019c70`
- `ntoskrnl!KeSetEvent` at `0x14001a085`
- `ntoskrnl!IofCompleteRequest` at `0x140017f9a`
- `ntoskrnl!IofCompleteRequest` at `0x140018521`
- `ntoskrnl!IofCompleteRequest` at `0x1400185f3`
- `ntoskrnl!IofCompleteRequest` at `0x1400186d9`
- `ntoskrnl!IofCompleteRequest` at `0x1400189a3`
- `ntoskrnl!IofCompleteRequest` at `0x140018c07`
- `ntoskrnl!IofCompleteRequest` at `0x140018ca3`
- `ntoskrnl!IofCompleteRequest` at `0x14001a1d2`
- `ntoskrnl!IofCompleteRequest` at `0x140017f9a`
- `ntoskrnl!IofCompleteRequest` at `0x140018521`
- `ntoskrnl!IofCompleteRequest` at `0x1400185f3`
- `ntoskrnl!IofCompleteRequest` at `0x1400186d9`
- `ntoskrnl!IofCompleteRequest` at `0x1400189a3`
- `ntoskrnl!IofCompleteRequest` at `0x140018c07`
- `ntoskrnl!IofCompleteRequest` at `0x140018ca3`
- `ntoskrnl!IofCompleteRequest` at `0x14001a1d2`

## pseudocode

```c
__int64 __fastcall RaUnitScsiIrp(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v5; // rbx
  unsigned __int64 v6; // r8
  signed __int32 v7; // eax
  signed __int32 v8; // ett
  int v9; // eax
  char *v10; // r13
  int v11; // esi
  unsigned __int8 *v12; // r15
  bool v13; // zf
  int v14; // edx
  char *v15; // rcx
  char v16; // al
  unsigned __int8 *v18; // rcx
  unsigned __int8 v19; // al
  __int64 v20; // rdx
  char v21; // al
  char v22; // dl
  _DWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r15
  int v26; // esi
  int v27; // r12d
  PDEVICE_OBJECT v28; // rcx
  _BYTE *v29; // rsi
  unsigned int v30; // r10d
  unsigned int v31; // r8d
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  int v34; // r11d
  __int64 v35; // r9
  unsigned __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned __int64 v40; // rsi
  int *v41; // rbx
  int v42; // ebx
  int v43; // r8d
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  unsigned __int64 v47; // rsi
  int *v48; // rbx
  int v49; // ebx
  int v50; // r8d
  unsigned int v51; // r15d
  bool v52; // bl
  unsigned __int64 v53; // r8
  signed __int32 v54; // eax
  signed __int32 v55; // ett
  int v56; // r11d
  __int64 v57; // rcx
  __int64 v58; // rax
  int v59; // eax
  bool v60; // al
  _DWORD *v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  int v65; // edx
  char *v66; // rcx
  char v67; // al
  int v68; // edx
  char *v69; // rcx
  char v70; // al
  unsigned __int64 v71; // r8
  signed __int32 v72; // eax
  signed __int32 v73; // ett
  PDEVICE_OBJECT v74; // rcx
  unsigned __int64 v75; // r8
  signed __int32 v76; // eax
  signed __int32 v77; // ett
  char *v78; // rdx
  unsigned __int8 *v79; // rax
  __int64 v80; // rcx
  unsigned __int64 v81; // rsi
  int *v82; // rbx
  int v83; // ebx
  int v84; // r8d
  _DWORD *Reserved; // rax
  unsigned __int64 v86; // r8
  signed __int32 v87; // eax
  signed __int32 v88; // ett
  int v89; // edx
  __int64 v90; // rcx
  char *v91; // r8
  char v92; // al
  _DWORD *v93; // rax
  _DWORD *v94; // rax
  int *v95; // rax
  int v96; // ecx
  _DWORD *v97; // rax
  int v98; // edx
  unsigned __int8 *v99; // rax
  __int64 v100; // rcx
  _DWORD *v101; // rax
  unsigned __int64 v102; // r8
  signed __int32 v103; // eax
  signed __int32 v104; // ett
  __int64 v105; // rdx
  _BYTE *v106; // rdx
  char v107; // bl
  unsigned __int8 v108; // r9
  unsigned __int64 v109; // rcx
  char v110; // di
  char v111; // r10
  char v112; // r11
  char v113; // r8
  unsigned __int8 *v114; // r9
  char v115; // r11
  unsigned __int8 v116; // r8
  unsigned __int64 v117; // rcx
  char v118; // bl
  char v119; // r9
  char v120; // r10
  __int64 v121; // rdx
  unsigned __int8 *v122; // r9
  char v123; // r11
  unsigned __int8 v124; // r8
  unsigned __int64 v125; // rcx
  char v126; // bl
  char v127; // dl
  char v128; // r10
  char v129; // r9
  _BYTE *v130; // rax
  char *v131; // r9
  unsigned int v132; // eax
  char v133; // al
  _BYTE *v134; // rdx
  char v135; // bl
  unsigned __int8 v136; // r9
  char v137; // cl
  char v138; // di
  char v139; // r8
  char v140; // r11
  char v141; // r10
  _BYTE *v142; // rcx
  _BYTE *v143; // rax
  char *v144; // r10
  unsigned int v145; // eax
  unsigned __int64 v146; // rcx
  char v147; // al
  unsigned __int8 *v148; // r9
  char v149; // si
  unsigned __int8 v150; // r8
  unsigned __int64 v151; // rcx
  char v152; // r11
  __int64 v153; // rdx
  char v154; // r10
  char v155; // r9
  _BYTE *v156; // rax
  char *v157; // r9
  unsigned int v158; // eax
  char v159; // al
  unsigned __int8 *v160; // r9
  char v161; // r12
  unsigned __int8 v162; // r8
  unsigned __int64 v163; // rcx
  char v164; // r11
  __int64 v165; // rdx
  char v166; // r10
  char v167; // r9
  _BYTE *v168; // rax
  char *v169; // r9
  unsigned int v170; // eax
  char v171; // al
  char *v172; // r9
  char v173; // r11
  unsigned __int8 v174; // r8
  char v175; // cl
  char v176; // bl
  __int64 v177; // rdx
  char v178; // r10
  char v179; // r9
  char *v180; // rcx
  char *v181; // rax
  char *v182; // r9
  unsigned int v183; // eax
  unsigned __int64 v184; // rcx
  char v185; // al
  unsigned __int64 v186; // rcx
  _BYTE *v187; // rsi
  unsigned __int8 v188; // r8
  char v189; // r11
  __int64 v190; // rdx
  char v191; // r10
  char v192; // r9
  _BYTE *v193; // rax
  char *v194; // r9
  unsigned int v195; // eax
  char v196; // al
  unsigned __int8 *v197; // r10
  _BYTE *v198; // rdx
  char v199; // r12
  unsigned __int8 v200; // r9
  unsigned __int64 v201; // rcx
  char v202; // bl
  char v203; // r8
  char v204; // r11
  char v205; // r10
  _BYTE *v206; // rax
  char *v207; // r10
  unsigned int v208; // eax
  char v209; // al
  char *v210; // r9
  char v211; // r15
  unsigned __int8 v212; // r8
  unsigned int v213; // r13d
  char v214; // r10
  _BYTE *v215; // r12
  char v216; // r11
  __int64 v217; // rdx
  char v218; // r10
  char v219; // r9
  _BYTE *v220; // rcx
  _BYTE *v221; // rax
  char *v222; // r9
  unsigned int v223; // eax
  unsigned __int64 v224; // rcx
  char v225; // al
  unsigned __int8 *v226; // r9
  int v227; // ecx
  int v228; // ecx
  int v229; // ecx
  int v230; // ecx
  int v231; // ecx
  int v232; // ecx
  int v233; // ecx
  int v234; // ecx
  unsigned int v235; // esi
  int v236; // ecx
  int v237; // ecx
  unsigned int v238; // esi
  unsigned int v239; // r10d
  __int64 v240; // rcx
  unsigned __int64 v241; // r11
  __int64 v242; // rdi
  int v243; // ecx
  _BYTE *v244; // rax
  char *v245; // r10
  unsigned int v246; // eax
  char v247; // al
  unsigned int v248; // esi
  unsigned int v249; // r10d
  __int64 v250; // rcx
  unsigned __int64 v251; // rbx
  __int64 v252; // rdi
  int v253; // ecx
  _BYTE *v254; // rax
  char *v255; // r9
  unsigned int v256; // eax
  char v257; // al
  signed __int32 v258; // eax
  signed __int32 v259; // ett
  char *v260; // rdx
  char v261; // al
  _DWORD *v262; // rax
  __int64 v263; // rdx
  unsigned int v264; // esi
  unsigned int v265; // r10d
  __int64 v266; // rcx
  unsigned __int64 v267; // rbx
  __int64 v268; // rdi
  int v269; // ecx
  _DWORD *v270; // rax
  __int64 v271; // r8
  unsigned int v272; // esi
  unsigned int v273; // r10d
  __int64 v274; // rcx
  unsigned __int64 v275; // r11
  __int64 v276; // rdi
  int v277; // ecx
  unsigned int v278; // r15d
  unsigned int v279; // r11d
  __int64 v280; // rcx
  unsigned __int64 v281; // r10
  __int64 v282; // rbx
  int v283; // ecx
  __int64 v284; // rcx
  char *v285; // rdx
  char v286; // al
  _DWORD *v287; // rax
  unsigned int v288; // r15d
  unsigned int v289; // r11d
  __int64 v290; // rcx
  unsigned __int64 v291; // r10
  __int64 v292; // rbx
  int v293; // ecx
  signed __int32 v294; // eax
  signed __int32 v295; // ett
  char v296; // al
  unsigned int v297; // esi
  unsigned int v298; // r10d
  __int64 v299; // rcx
  unsigned __int64 v300; // rbx
  __int64 v301; // rdi
  int v302; // ecx
  __int64 v303; // rcx
  char *v304; // rdx
  char v305; // al
  _DWORD *v306; // rax
  unsigned int v307; // r12d
  __int64 v308; // rcx
  unsigned __int64 v309; // r10
  __int64 v310; // r11
  int v311; // ecx
  unsigned int v312; // r15d
  unsigned int v313; // ebx
  __int64 v314; // rcx
  unsigned __int64 v315; // r11
  __int64 v316; // rsi
  int v317; // ecx
  int v318; // ebx
  __int64 v319; // rcx
  unsigned __int64 v320; // r11
  __int64 v321; // r12
  int v322; // ecx
  __int64 v323; // r8
  __int64 v324; // rax
  unsigned __int64 v325; // r8
  char v326; // cl
  __int64 v327; // r8
  __int64 v328; // rcx
  __int64 v329; // rcx
  unsigned int v330; // edi
  unsigned __int64 v331; // r8
  __int128 v332; // [rsp+68h] [rbp-11h] BYREF
  __int128 v333; // [rsp+78h] [rbp-1h] BYREF
  __int128 v334; // [rsp+88h] [rbp+Fh] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v334 = 0;
  v5 = *(_QWORD *)(v2 + 8);
  if ( !v5 )
  {
    v12 = 0;
    *(_BYTE *)(a2 + 141) = -84;
    v13 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v13 )
      goto LABEL_12;
    v332 = 0;
    IoGetActivityIdIrp(a2, &v332);
    v15 = *(char **)(a2 + 184);
    v16 = *v15;
    if ( *v15 == 15 )
    {
      if ( byte_140177431 >= 0 )
        goto LABEL_12;
      v323 = *((_QWORD *)v15 + 1);
      if ( *(_BYTE *)(v323 + 2) != 40 )
      {
        LODWORD(v109) = *(unsigned __int8 *)(v323 + 72);
        v106 = *(_BYTE **)(v323 + 32);
        v108 = *(_BYTE *)(v323 + 11);
        v107 = *(_BYTE *)(v323 + 4);
        if ( *(_BYTE *)(v323 + 2) )
          goto LABEL_12;
        goto LABEL_248;
      }
      if ( *(_DWORD *)(v323 + 20) )
        goto LABEL_12;
      v238 = *(_DWORD *)(v323 + 56);
      if ( !v238 )
        goto LABEL_12;
      v108 = 0;
      v106 = 0;
      v107 = 0;
      v239 = 0;
      while ( 1 )
      {
        v240 = *(unsigned int *)(v323 + 4LL * v239 + 120);
        if ( (unsigned int)v240 >= 0x80 )
        {
          v241 = *(unsigned int *)(v323 + 16);
          if ( (unsigned int)v240 < (unsigned int)v241 )
          {
            v242 = (unsigned int)v240;
            v243 = *(_DWORD *)(v240 + v323);
            if ( v243 == 64 )
            {
              if ( v242 + 40 <= v241 )
              {
                if ( *(_BYTE *)(v242 + v323 + 10) )
LABEL_245:
                  v12 = (unsigned __int8 *)(v242 + v323 + 24);
LABEL_246:
                v106 = *(_BYTE **)(v242 + v323 + 16);
                v107 = *(_BYTE *)(v242 + v323 + 8);
                v108 = *(_BYTE *)(v242 + v323 + 9);
                goto LABEL_681;
              }
            }
            else
            {
              v227 = v243 - 65;
              if ( v227 )
              {
                if ( v227 == 1 && v242 + 40 <= v241 )
                {
                  if ( *(_DWORD *)(v242 + v323 + 12) )
                    v12 = (unsigned __int8 *)(v242 + v323 + 32);
                  v106 = *(_BYTE **)(v242 + v323 + 24);
                  v107 = *(_BYTE *)(v242 + v323 + 8);
                  v108 = *(_BYTE *)(v242 + v323 + 9);
LABEL_681:
                  if ( !v12 )
                    goto LABEL_12;
                  LODWORD(v109) = *v12;
LABEL_248:
                  LOBYTE(v109) = v109 - 8;
                  if ( (v109 & 0x5D) != 0 )
                    goto LABEL_12;
                  v110 = *(_BYTE *)(v323 + 3);
                  if ( v110 == 1 || !v106 || !v108 )
                    goto LABEL_251;
                  v113 = 0;
                  v112 = 0;
                  v111 = 0;
                  v109 = (unsigned __int64)&v106[v108];
                  v244 = v106 + 8;
                  if ( (unsigned __int8)((*v106 & 0x7F) - 114) <= 1u )
                  {
                    if ( (unsigned __int64)v244 <= v109 )
                    {
                      v112 = v106[2];
                      v113 = v106[1] & 0xF;
                      v111 = v106[3];
                      goto LABEL_502;
                    }
                  }
                  else if ( (unsigned __int64)v244 <= v109 )
                  {
                    v245 = v106 + 13;
                    v113 = v106[2] & 0xF;
                    v246 = v108;
                    if ( (unsigned int)(unsigned __int8)v106[7] + 8 <= v108 )
                      v246 = (unsigned __int8)v106[7] + 8;
                    v109 = (unsigned __int64)&v106[v246];
                    if ( (unsigned __int64)v245 <= v109 )
                      v112 = v106[12];
                    if ( (unsigned __int64)(v106 + 14) > v109 )
                      v111 = 0;
                    else
                      v111 = *v245;
LABEL_502:
                    v247 = 1;
LABEL_687:
                    if ( !v247 )
                    {
LABEL_251:
                      v111 = 0;
                      v112 = 0;
                      v113 = 0;
                    }
                    McTemplateK0pduuuuup_EtwWriteTransfer(
                      v109,
                      (_DWORD)v106,
                      (unsigned int)&v332,
                      a2,
                      *(_DWORD *)(a2 + 48),
                      v110,
                      v107,
                      v113,
                      v112,
                      v111,
                      a2);
                    goto LABEL_12;
                  }
                  v247 = 0;
                  goto LABEL_687;
                }
              }
              else if ( v242 + 56 <= v241 )
              {
                if ( *(_BYTE *)(v242 + v323 + 10) )
                  goto LABEL_245;
                goto LABEL_246;
              }
            }
          }
        }
        if ( ++v239 >= v238 )
          goto LABEL_681;
      }
    }
    if ( v16 != 14 )
    {
      if ( v16 != 27 )
        goto LABEL_12;
      if ( v15[1] == 7 && !*((_DWORD *)v15 + 2) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v93 = *(_DWORD **)(a2 + 56);
          if ( v93 )
            LODWORD(v12) = *v93;
          McTemplateK0pqd_EtwWriteTransfer((_DWORD)v15, v14, (unsigned int)&v332, a2, (char)v12, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_12;
      }
LABEL_28:
      if ( (byte_140177432 & 0x20) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v15, EventPnpRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_12;
    }
LABEL_24:
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v15, EventNonReadWriteRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_12;
  }
  v6 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
  v7 = *(_DWORD *)(v6 + *(_QWORD *)(a1 + 40));
  while ( (v7 & 1) == 0 )
  {
    v8 = v7;
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + *(_QWORD *)(a1 + 40)), v7 + 2, v7);
    if ( v8 == v7 )
      goto LABEL_5;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 1032));
LABEL_5:
  v9 = *(_DWORD *)(a1 + 56);
  v10 = 0;
  *(_QWORD *)&v332 = 0;
  if ( v9 != 6 )
  {
    if ( v9 == 5 )
    {
      v324 = *(_QWORD *)(a2 + 184);
      if ( *(_BYTE *)v324 == 27 )
      {
        v11 = 0;
        goto LABEL_30;
      }
      if ( *(_BYTE *)v324 == 14 && *(_DWORD *)(v324 + 24) == 266276 )
        goto LABEL_830;
    }
    else
    {
      if ( v9 != 7 )
        goto LABEL_31;
      v18 = *(unsigned __int8 **)(a2 + 184);
      v19 = *v18;
      v20 = v18[1];
      if ( *v18 == 15 )
      {
        v21 = RaidSrbFunctionFromIrp(a2, v20);
        if ( v22 == -16 || v21 == 1 )
          goto LABEL_830;
      }
      else
      {
        if ( v19 == 27 )
        {
          v11 = 0;
          goto LABEL_30;
        }
        if ( v19 == 14 )
        {
          if ( *((_DWORD *)v18 + 6) == 266264 )
          {
            v11 = 0;
            goto LABEL_30;
          }
        }
        else if ( __PAIR16__(v20, v19) == 534 )
        {
LABEL_830:
          v11 = 0;
LABEL_30:
          if ( v11 < 0 )
            goto LABEL_7;
LABEL_31:
          v23 = *(_DWORD **)(a1 + 24);
          if ( *v23 == 1314275652 )
          {
            v24 = (__int64)v23 + 282;
          }
          else if ( *v23 == 1094997074 )
          {
            v24 = (__int64)v23 + 466;
          }
          else
          {
            v24 = 98;
          }
          if ( *(_BYTE *)(v5 + 2) != 40 )
          {
            v27 = *(_DWORD *)(v5 + 12);
            v25 = 0;
            v26 = *(unsigned __int8 *)(v5 + 2);
            goto LABEL_39;
          }
          if ( *(_BYTE *)v24 != 1 )
          {
            *(_BYTE *)(v5 + 3) = 6;
            *(_QWORD *)(a2 + 56) = 0;
            v75 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
            v76 = *(_DWORD *)(v75 + *(_QWORD *)(a1 + 40));
            while ( (v76 & 1) == 0 )
            {
              v77 = v76;
              v76 = _InterlockedCompareExchange((volatile signed __int32 *)(v75 + *(_QWORD *)(a1 + 40)), v76 - 2, v76);
              if ( v77 == v76 )
                goto LABEL_140;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
              KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
LABEL_140:
            v13 = StorEtwLoggingEnabled == 0;
            *(_BYTE *)(a2 + 141) = -84;
            *(_DWORD *)(a2 + 48) = -1073741637;
            if ( v13 )
              goto LABEL_143;
            v332 = 0;
            IoGetActivityIdIrp(a2, &v332);
            v79 = *(unsigned __int8 **)(a2 + 184);
            v80 = *v79;
            if ( (_BYTE)v80 == 15 )
            {
              if ( byte_140177431 >= 0 )
                goto LABEL_143;
              v121 = *((_QWORD *)v79 + 1);
              if ( *(_BYTE *)(v121 + 2) != 40 )
              {
                LODWORD(v117) = *(unsigned __int8 *)(v121 + 72);
                v10 = *(char **)(v121 + 32);
                v116 = *(_BYTE *)(v121 + 11);
                v115 = *(_BYTE *)(v121 + 4);
                if ( *(_BYTE *)(v121 + 2) )
                  goto LABEL_143;
                goto LABEL_256;
              }
              if ( *(_DWORD *)(v121 + 20) )
                goto LABEL_143;
              v248 = *(_DWORD *)(v121 + 56);
              if ( !v248 )
                goto LABEL_143;
              v115 = 0;
              v114 = 0;
              v116 = 0;
              v249 = 0;
              while ( 1 )
              {
                v250 = *(unsigned int *)(v121 + 4LL * v249 + 120);
                if ( (unsigned int)v250 >= 0x80 )
                {
                  v251 = *(unsigned int *)(v121 + 16);
                  if ( (unsigned int)v250 < (unsigned int)v251 )
                  {
                    v252 = (unsigned int)v250;
                    v253 = *(_DWORD *)(v121 + v250);
                    if ( v253 == 64 )
                    {
                      if ( v252 + 40 <= v251 )
                      {
                        if ( *(_BYTE *)(v121 + v252 + 10) )
LABEL_253:
                          v114 = (unsigned __int8 *)(v252 + v121 + 24);
LABEL_254:
                        v10 = *(char **)(v121 + v252 + 16);
                        v115 = *(_BYTE *)(v121 + v252 + 8);
                        v116 = *(_BYTE *)(v121 + v252 + 9);
                        goto LABEL_694;
                      }
                    }
                    else
                    {
                      v228 = v253 - 65;
                      if ( v228 )
                      {
                        if ( v228 == 1 && v252 + 40 <= v251 )
                        {
                          if ( *(_DWORD *)(v121 + v252 + 12) )
                            v114 = (unsigned __int8 *)(v252 + v121 + 32);
                          v10 = *(char **)(v121 + v252 + 24);
                          v115 = *(_BYTE *)(v121 + v252 + 8);
                          v116 = *(_BYTE *)(v121 + v252 + 9);
LABEL_694:
                          if ( !v114 )
                            goto LABEL_143;
                          LODWORD(v117) = *v114;
LABEL_256:
                          LOBYTE(v117) = v117 - 8;
                          if ( (v117 & 0x5D) != 0 )
                            goto LABEL_143;
                          v118 = *(_BYTE *)(v121 + 3);
                          if ( v118 == 1 || !v10 || !v116 )
                            goto LABEL_259;
                          LOBYTE(v121) = 0;
                          v120 = 0;
                          v119 = 0;
                          v117 = (unsigned __int64)&v10[v116];
                          v254 = v10 + 8;
                          if ( (unsigned __int8)((*v10 & 0x7F) - 114) <= 1u )
                          {
                            if ( (unsigned __int64)v254 <= v117 )
                            {
                              LODWORD(v121) = (unsigned __int8)v10[1];
                              v120 = v10[2];
                              LOBYTE(v121) = v121 & 0xF;
                              v119 = v10[3];
                              goto LABEL_521;
                            }
                          }
                          else if ( (unsigned __int64)v254 <= v117 )
                          {
                            v255 = v10 + 13;
                            LODWORD(v121) = (unsigned __int8)v10[2];
                            LOBYTE(v121) = v121 & 0xF;
                            v256 = v116;
                            if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v116 )
                              v256 = (unsigned __int8)v10[7] + 8;
                            v117 = (unsigned __int64)&v10[v256];
                            if ( (unsigned __int64)v255 <= v117 )
                              v120 = v10[12];
                            if ( (unsigned __int64)(v10 + 14) > v117 )
                              v119 = 0;
                            else
                              v119 = *v255;
LABEL_521:
                            v257 = 1;
LABEL_700:
                            if ( !v257 )
                            {
LABEL_259:
                              v119 = 0;
                              v120 = 0;
                              LOBYTE(v121) = 0;
                            }
                            McTemplateK0pduuuuup_EtwWriteTransfer(
                              v117,
                              v121,
                              (unsigned int)&v332,
                              a2,
                              *(_DWORD *)(a2 + 48),
                              v118,
                              v115,
                              v121,
                              v120,
                              v119,
                              a2);
                            goto LABEL_143;
                          }
                          v257 = 0;
                          goto LABEL_700;
                        }
                      }
                      else if ( v252 + 56 <= v251 )
                      {
                        if ( *(_BYTE *)(v121 + v252 + 10) )
                          goto LABEL_253;
                        goto LABEL_254;
                      }
                    }
                  }
                }
                if ( ++v249 >= v248 )
                  goto LABEL_694;
              }
            }
            if ( (_BYTE)v80 != 14 )
            {
              if ( (_BYTE)v80 != 27 )
                goto LABEL_143;
              if ( v79[1] == 7 && !*((_DWORD *)v79 + 2) )
              {
                if ( (byte_140177432 & 0x40) == 0 )
                  goto LABEL_143;
                v97 = *(_DWORD **)(a2 + 56);
                if ( !v97 )
                {
LABEL_851:
                  McTemplateK0pqd_EtwWriteTransfer(
                    v80,
                    (_DWORD)v78,
                    (unsigned int)&v332,
                    a2,
                    (char)v10,
                    *(_DWORD *)(a2 + 48));
                  goto LABEL_143;
                }
LABEL_850:
                LODWORD(v10) = *v97;
                goto LABEL_851;
              }
LABEL_210:
              if ( (byte_140177432 & 0x20) != 0 )
                McTemplateK0pd_EtwWriteTransfer(v80, EventPnpRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
              goto LABEL_143;
            }
LABEL_196:
            if ( (byte_140177432 & 8) != 0 )
              McTemplateK0pd_EtwWriteTransfer(v80, EventNonReadWriteRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
            goto LABEL_143;
          }
          if ( *(_DWORD *)(v5 + 8) == 1397899864 && !*(_DWORD *)(v5 + 48) )
          {
            v25 = v5;
            v26 = *(_DWORD *)(v5 + 20);
            v27 = *(_DWORD *)(v5 + 24);
            if ( !*(_QWORD *)(v5 + 72) )
            {
LABEL_39:
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qqD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
                  a1,
                  a2,
                  v26);
              }
              if ( (v27 & 0x100000) != 0 )
              {
                if ( (v28 = *(PDEVICE_OBJECT *)(a1 + 24), (Reserved = v28[14].Reserved) != 0) && (Reserved[5] & 1) == 0
                  || (BYTE3(v28->Queue.Wcb.DeviceRoutine) & 4) != 0
                  || *((_DWORD *)&v28->Reserved + 3) != 1 )
                {
                  *(_BYTE *)(v5 + 3) = 36;
                  *(_QWORD *)(a2 + 56) = 0;
                  v86 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
                  v87 = *(_DWORD *)(v86 + *(_QWORD *)(a1 + 40));
                  while ( (v87 & 1) == 0 )
                  {
                    v88 = v87;
                    v87 = _InterlockedCompareExchange(
                            (volatile signed __int32 *)(v86 + *(_QWORD *)(a1 + 40)),
                            v87 - 2,
                            v87);
                    if ( v88 == v87 )
                      goto LABEL_179;
                  }
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
                    KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
LABEL_179:
                  v13 = StorEtwLoggingEnabled == 0;
                  *(_BYTE *)(a2 + 141) = -84;
                  *(_DWORD *)(a2 + 48) = -1073741823;
                  if ( v13 )
                    goto LABEL_187;
                  v332 = 0;
                  IoGetActivityIdIrp(a2, &v332);
                  v91 = *(char **)(a2 + 184);
                  v92 = *v91;
                  if ( *v91 != 15 )
                  {
                    if ( v92 == 14 )
                    {
                      if ( (byte_140177432 & 8) != 0 )
                        McTemplateK0pd_EtwWriteTransfer(
                          v90,
                          EventNonReadWriteRequestComplete,
                          &v332,
                          a2,
                          *(_DWORD *)(a2 + 48));
                    }
                    else if ( v92 == 27 )
                    {
                      if ( v91[1] == 7 && !*((_DWORD *)v91 + 2) )
                      {
                        if ( (byte_140177432 & 0x40) != 0 )
                        {
                          v270 = *(_DWORD **)(a2 + 56);
                          if ( v270 )
                            LODWORD(v10) = *v270;
                          McTemplateK0pqd_EtwWriteTransfer(
                            v90,
                            v89,
                            (unsigned int)&v332,
                            a2,
                            (char)v10,
                            *(_DWORD *)(a2 + 48));
                        }
                      }
                      else if ( (byte_140177432 & 0x20) != 0 )
                      {
                        McTemplateK0pd_EtwWriteTransfer(v90, EventPnpRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
                      }
                    }
                    goto LABEL_187;
                  }
                  if ( byte_140177431 >= 0 )
                  {
LABEL_187:
                    IofCompleteRequest((PIRP)a2, 0);
                    return 3221225473LL;
                  }
                  v271 = *((_QWORD *)v91 + 1);
                  if ( *(_BYTE *)(v271 + 2) != 40 )
                  {
                    v137 = *(_BYTE *)(v271 + 72);
                    v134 = *(_BYTE **)(v271 + 32);
                    v136 = *(_BYTE *)(v271 + 11);
                    v135 = *(_BYTE *)(v271 + 4);
                    if ( !*(_BYTE *)(v271 + 2) )
                      goto LABEL_280;
                    goto LABEL_187;
                  }
                  if ( *(_DWORD *)(v271 + 20) )
                    goto LABEL_187;
                  v272 = *(_DWORD *)(v271 + 56);
                  if ( !v272 )
                    goto LABEL_187;
                  v136 = 0;
                  v134 = 0;
                  v135 = 0;
                  v273 = 0;
                  while ( 1 )
                  {
                    v274 = *(unsigned int *)(v271 + 4LL * v273 + 120);
                    if ( (unsigned int)v274 >= 0x80 )
                    {
                      v275 = *(unsigned int *)(v271 + 16);
                      if ( (unsigned int)v274 < (unsigned int)v275 )
                      {
                        v276 = (unsigned int)v274;
                        v277 = *(_DWORD *)(v274 + v271);
                        if ( v277 == 64 )
                        {
                          if ( v276 + 40 <= v275 )
                          {
                            if ( *(_BYTE *)(v276 + v271 + 10) )
LABEL_277:
                              v10 = (char *)(v276 + v271 + 24);
LABEL_278:
                            v134 = *(_BYTE **)(v276 + v271 + 16);
                            v135 = *(_BYTE *)(v276 + v271 + 8);
                            v136 = *(_BYTE *)(v276 + v271 + 9);
                            goto LABEL_715;
                          }
                        }
                        else
                        {
                          v230 = v277 - 65;
                          if ( v230 )
                          {
                            if ( v230 == 1 && v276 + 40 <= v275 )
                            {
                              if ( *(_DWORD *)(v276 + v271 + 12) )
                                v10 = (char *)(v276 + v271 + 32);
                              v134 = *(_BYTE **)(v276 + v271 + 24);
                              v135 = *(_BYTE *)(v276 + v271 + 8);
                              v136 = *(_BYTE *)(v276 + v271 + 9);
LABEL_715:
                              if ( !v10 )
                                goto LABEL_187;
                              v137 = *v10;
LABEL_280:
                              if ( ((v137 - 8) & 0x5D) != 0 )
                                goto LABEL_187;
                              v138 = *(_BYTE *)(v271 + 3);
                              if ( v138 == 1 || !v134 || !v136 )
                                goto LABEL_566;
                              v139 = 0;
                              v140 = 0;
                              v141 = 0;
                              v142 = &v134[v136];
                              v143 = v134 + 8;
                              if ( (unsigned __int8)((*v134 & 0x7F) - 114) <= 1u )
                              {
                                if ( v143 <= v142 )
                                {
                                  v140 = v134[2];
                                  v139 = v134[1] & 0xF;
                                  v141 = v134[3];
                                  goto LABEL_292;
                                }
                              }
                              else if ( v143 <= v142 )
                              {
                                v144 = v134 + 13;
                                v139 = v134[2] & 0xF;
                                v145 = v136;
                                if ( (unsigned int)(unsigned __int8)v134[7] + 8 <= v136 )
                                  v145 = (unsigned __int8)v134[7] + 8;
                                v146 = (unsigned __int64)&v134[v145];
                                if ( (unsigned __int64)v144 <= v146 )
                                  v140 = v134[12];
                                if ( (unsigned __int64)(v134 + 14) > v146 )
                                  v141 = 0;
                                else
                                  v141 = *v144;
LABEL_292:
                                v147 = 1;
LABEL_721:
                                if ( !v147 )
                                {
LABEL_566:
                                  v141 = 0;
                                  v140 = 0;
                                  v139 = 0;
                                }
                                McTemplateK0pduuuuup_EtwWriteTransfer(
                                  *(_DWORD *)(a2 + 48),
                                  (_DWORD)v134,
                                  (unsigned int)&v332,
                                  a2,
                                  *(_DWORD *)(a2 + 48),
                                  v138,
                                  v135,
                                  v139,
                                  v140,
                                  v141,
                                  a2);
                                goto LABEL_187;
                              }
                              v147 = 0;
                              goto LABEL_721;
                            }
                          }
                          else if ( v276 + 56 <= v275 )
                          {
                            if ( *(_BYTE *)(v276 + v271 + 10) )
                              goto LABEL_277;
                            goto LABEL_278;
                          }
                        }
                      }
                    }
                    if ( ++v273 >= v272 )
                      goto LABEL_715;
                  }
                }
              }
              if ( v26 )
              {
                switch ( v26 )
                {
                  case 10:
                    return StorUnitExecuteNvmeSrb(a1, a2);
                  case 7:
                    v45 = *(_QWORD *)(a2 + 184);
                    v46 = *(_QWORD *)(v45 + 8);
                    *(_BYTE *)(v45 + 3) |= 1u;
                    *(_BYTE *)(v46 + 3) = 0;
                    *(_QWORD *)(*(_QWORD *)(a2 + 184) + 24LL) = 0;
                    if ( *(_BYTE *)(v46 + 2) == 40 )
                    {
                      v47 = *(unsigned int *)(v46 + 20);
                      v48 = (int *)(v46 + 24);
                    }
                    else
                    {
                      v47 = *(unsigned __int8 *)(v46 + 2);
                      v48 = (int *)(v46 + 12);
                    }
                    v49 = *v48;
                    if ( (qword_140176450 & 0x20) != 0 )
                      DbgLogRequest(
                        *(_QWORD *)(a1 + 24),
                        3,
                        a2,
                        (unsigned __int8)BYTE2(*(_DWORD *)(a1 + 104))
                      | ((((unsigned __int8)*(_DWORD *)(a1 + 104) << 8) | (unsigned __int8)BYTE1(*(_DWORD *)(a1 + 104))) << 8),
                        0,
                        0,
                        0);
                    v50 = ((v49 & 0x80000) != 0 ? 4 : 0) | 2;
                    if ( (v49 & 0x10) == 0 )
                      v50 = (v49 & 0x80000) != 0 ? 4 : 0;
                    if ( EnableSolitaryIO
                      || (v49 & 0x102) != 0x102
                      && (v49 & 0x10) == 0
                      && (v49 & 0x80000) == 0
                      && ((unsigned int)v47 > 0x20 || (v329 = 0x1000D0000LL, !_bittest64(&v329, v47))) )
                    {
                      v50 |= 1u;
                    }
                    RaidStartIoPacket(a1, a2, v50);
                    v51 = 259;
LABEL_94:
                    v52 = 0;
                    goto LABEL_95;
                  case 8:
                    v61 = *(_DWORD **)(a1 + 24);
                    if ( *v61 == 1094997074 )
                    {
                      v62 = (__int64)v61 + 451;
                    }
                    else if ( *v61 == 1314275652 )
                    {
                      v62 = (__int64)v61 + 267;
                    }
                    else
                    {
                      v62 = 91;
                    }
                    v63 = *(_QWORD *)(a2 + 184);
                    v64 = *(_QWORD *)(v63 + 8);
                    if ( *(_BYTE *)v62 )
                    {
                      *(_BYTE *)(v63 + 3) |= 1u;
                      *(_BYTE *)(v64 + 3) = 0;
                      *(_QWORD *)(*(_QWORD *)(a2 + 184) + 24LL) = 0;
                      if ( *(_BYTE *)(v64 + 2) == 40 )
                      {
                        v81 = *(unsigned int *)(v64 + 20);
                        v82 = (int *)(v64 + 24);
                      }
                      else
                      {
                        v81 = *(unsigned __int8 *)(v64 + 2);
                        v82 = (int *)(v64 + 12);
                      }
                      v83 = *v82;
                      if ( (qword_140176450 & 0x20) != 0 )
                        DbgLogRequest(
                          *(_QWORD *)(a1 + 24),
                          3,
                          a2,
                          (unsigned __int8)BYTE2(*(_DWORD *)(a1 + 104))
                        | ((((unsigned __int8)*(_DWORD *)(a1 + 104) << 8) | (unsigned __int8)BYTE1(*(_DWORD *)(a1 + 104))) << 8),
                          0,
                          0,
                          0);
                      v84 = ((v83 & 0x80000) != 0 ? 4 : 0) | 2;
                      if ( (v83 & 0x10) == 0 )
                        v84 = (v83 & 0x80000) != 0 ? 4 : 0;
                      if ( EnableSolitaryIO
                        || (v83 & 0x102) != 0x102
                        && (v83 & 0x10) == 0
                        && (v83 & 0x80000) == 0
                        && ((unsigned int)v81 > 0x20 || (v328 = 0x1000D0000LL, !_bittest64(&v328, v81))) )
                      {
                        v84 |= 1u;
                      }
                      RaidStartIoPacket(a1, a2, v84);
                      v51 = 259;
                      goto LABEL_122;
                    }
                    v13 = StorEtwLoggingEnabled == 0;
                    *(_BYTE *)(v64 + 3) = 1;
                    *(_QWORD *)(a2 + 56) = 0;
                    *(_BYTE *)(a2 + 141) = -84;
                    *(_DWORD *)(a2 + 48) = 0;
                    if ( v13 )
                      goto LABEL_121;
                    v332 = 0;
                    IoGetActivityIdIrp(a2, &v332);
                    v66 = *(char **)(a2 + 184);
                    v67 = *v66;
                    if ( *v66 != 15 )
                    {
                      if ( v67 == 14 )
                      {
                        if ( (byte_140177432 & 8) != 0 )
                          McTemplateK0pd_EtwWriteTransfer(
                            v66,
                            EventNonReadWriteRequestComplete,
                            &v332,
                            a2,
                            *(_DWORD *)(a2 + 48));
                      }
                      else if ( v67 == 27 )
                      {
                        if ( v66[1] != 7 || *((_DWORD *)v66 + 2) )
                        {
                          if ( (byte_140177432 & 0x20) != 0 )
                            McTemplateK0pd_EtwWriteTransfer(
                              v66,
                              EventPnpRequestComplete,
                              &v332,
                              a2,
                              *(_DWORD *)(a2 + 48));
                        }
                        else if ( (byte_140177432 & 0x40) != 0 )
                        {
                          v95 = *(int **)(a2 + 56);
                          if ( v95 )
                            v96 = *v95;
                          else
                            v96 = 0;
                          McTemplateK0pqd_EtwWriteTransfer(v96, v65, (unsigned int)&v332, a2, v96, *(_DWORD *)(a2 + 48));
                        }
                      }
                      goto LABEL_121;
                    }
                    if ( byte_140177431 >= 0 )
                      goto LABEL_121;
                    v327 = *((_QWORD *)v66 + 1);
                    if ( *(_BYTE *)(v327 + 2) != 40 )
                    {
                      LODWORD(v201) = *(unsigned __int8 *)(v327 + 72);
                      v198 = *(_BYTE **)(v327 + 32);
                      v200 = *(_BYTE *)(v327 + 11);
                      v199 = *(_BYTE *)(v327 + 4);
                      if ( !*(_BYTE *)(v327 + 2) )
                        goto LABEL_358;
                      goto LABEL_121;
                    }
                    if ( *(_DWORD *)(v327 + 20) )
                      goto LABEL_121;
                    v312 = *(_DWORD *)(v327 + 56);
                    if ( !v312 )
                      goto LABEL_121;
                    v199 = 0;
                    v198 = 0;
                    v200 = 0;
                    v197 = 0;
                    v313 = 0;
                    while ( 1 )
                    {
                      v314 = *(unsigned int *)(v327 + 4LL * v313 + 120);
                      if ( (unsigned int)v314 >= 0x80 )
                      {
                        v315 = *(unsigned int *)(v327 + 16);
                        if ( (unsigned int)v314 < (unsigned int)v315 )
                        {
                          v316 = (unsigned int)v314;
                          v317 = *(_DWORD *)(v314 + v327);
                          if ( v317 == 64 )
                          {
                            if ( v316 + 40 <= v315 )
                            {
                              if ( *(_BYTE *)(v316 + v327 + 10) )
LABEL_355:
                                v197 = (unsigned __int8 *)(v316 + v327 + 24);
LABEL_356:
                              v198 = *(_BYTE **)(v316 + v327 + 16);
                              v199 = *(_BYTE *)(v316 + v327 + 8);
                              v200 = *(_BYTE *)(v316 + v327 + 9);
                              goto LABEL_790;
                            }
                          }
                          else
                          {
                            v236 = v317 - 65;
                            if ( v236 )
                            {
                              if ( v236 == 1 && v316 + 40 <= v315 )
                              {
                                if ( *(_DWORD *)(v316 + v327 + 12) )
                                  v197 = (unsigned __int8 *)(v316 + v327 + 32);
                                v198 = *(_BYTE **)(v316 + v327 + 24);
                                v199 = *(_BYTE *)(v316 + v327 + 8);
                                v200 = *(_BYTE *)(v316 + v327 + 9);
LABEL_790:
                                if ( !v197 )
                                  goto LABEL_121;
                                LODWORD(v201) = *v197;
LABEL_358:
                                LOBYTE(v201) = v201 - 8;
                                if ( (v201 & 0x5D) != 0 )
                                  goto LABEL_121;
                                v202 = *(_BYTE *)(v327 + 3);
                                if ( v202 == 1 || !v198 || !v200 )
                                  goto LABEL_666;
                                v203 = 0;
                                v204 = 0;
                                v205 = 0;
                                v201 = (unsigned __int64)&v198[v200];
                                v206 = v198 + 8;
                                if ( (unsigned __int8)((*v198 & 0x7F) - 114) <= 1u )
                                {
                                  if ( (unsigned __int64)v206 <= v201 )
                                  {
                                    v204 = v198[2];
                                    v203 = v198[1] & 0xF;
                                    v205 = v198[3];
                                    goto LABEL_370;
                                  }
                                }
                                else if ( (unsigned __int64)v206 <= v201 )
                                {
                                  v207 = v198 + 13;
                                  v203 = v198[2] & 0xF;
                                  v208 = v200;
                                  if ( (unsigned int)(unsigned __int8)v198[7] + 8 <= v200 )
                                    v208 = (unsigned __int8)v198[7] + 8;
                                  v201 = (unsigned __int64)&v198[v208];
                                  if ( (unsigned __int64)v207 <= v201 )
                                    v204 = v198[12];
                                  if ( (unsigned __int64)(v198 + 14) > v201 )
                                    v205 = 0;
                                  else
                                    v205 = *v207;
LABEL_370:
                                  v209 = 1;
LABEL_796:
                                  if ( !v209 )
                                  {
LABEL_666:
                                    v205 = 0;
                                    v204 = 0;
                                    v203 = 0;
                                  }
                                  McTemplateK0pduuuuup_EtwWriteTransfer(
                                    v201,
                                    (_DWORD)v198,
                                    (unsigned int)&v332,
                                    a2,
                                    *(_DWORD *)(a2 + 48),
                                    v202,
                                    v199,
                                    v203,
                                    v204,
                                    v205,
                                    a2);
LABEL_121:
                                  IofCompleteRequest((PIRP)a2, 0);
                                  v51 = 0;
LABEL_122:
                                  v52 = v51 != 259;
LABEL_95:
                                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                  {
                                    WPP_SF_qqD(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      20,
                                      WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
                                      a1,
                                      a2,
                                      v51);
                                  }
                                  if ( v52 )
                                  {
                                    v53 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
                                    v54 = *(_DWORD *)(v53 + *(_QWORD *)(a1 + 40));
                                    while ( (v54 & 1) == 0 )
                                    {
                                      v55 = v54;
                                      v54 = _InterlockedCompareExchange(
                                              (volatile signed __int32 *)(v53 + *(_QWORD *)(a1 + 40)),
                                              v54 - 2,
                                              v54);
                                      if ( v55 == v54 )
                                        return v51;
                                    }
                                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
                                      KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
                                  }
                                  return v51;
                                }
                                v209 = 0;
                                goto LABEL_796;
                              }
                            }
                            else if ( v316 + 56 <= v315 )
                            {
                              if ( *(_BYTE *)(v316 + v327 + 10) )
                                goto LABEL_355;
                              goto LABEL_356;
                            }
                          }
                        }
                      }
                      if ( ++v313 >= v312 )
                        goto LABEL_790;
                    }
                }
                v52 = 1;
                switch ( v26 )
                {
                  case 1:
                    v51 = RaUnitClaimDeviceSrb(a1, a2);
                    goto LABEL_95;
                  case 2:
                  case 9:
                    v51 = RaidUnitSubmitRequest(a1, a2);
                    goto LABEL_94;
                  case 4:
                    v51 = RaUnitReleaseQueueSrb(a1, a2);
                    goto LABEL_95;
                  case 6:
                    v51 = RaUnitReleaseDeviceSrb(a1, a2);
                    goto LABEL_95;
                  case 16:
                  case 19:
                  case 32:
                    v51 = RaidUnitSubmitResetRequest(a1, a2);
                    goto LABEL_95;
                  case 18:
                    v51 = RaUnitResetBusSrb(a1, a2);
                    goto LABEL_95;
                  case 21:
                    v51 = RaUnitFlushQueueSrb(a1, a2);
                    goto LABEL_95;
                  case 23:
                    v13 = StorEtwLoggingEnabled == 0;
                    v51 = -1073741808;
                    *(_DWORD *)(a2 + 48) = -1073741808;
                    *(_BYTE *)(a2 + 141) = -84;
                    if ( v13 )
                      goto LABEL_639;
                    v332 = 0;
                    IoGetActivityIdIrp(a2, &v332);
                    v304 = *(char **)(a2 + 184);
                    v305 = *v304;
                    if ( *v304 == 15 )
                    {
                      if ( byte_140177431 >= 0 )
                        goto LABEL_639;
                      v190 = *((_QWORD *)v304 + 1);
                      if ( *(_BYTE *)(v190 + 2) != 40 )
                      {
                        LODWORD(v186) = *(unsigned __int8 *)(v190 + 72);
                        v187 = *(_BYTE **)(v190 + 32);
                        v188 = *(_BYTE *)(v190 + 11);
                        LOBYTE(v10) = *(_BYTE *)(v190 + 4);
                        if ( *(_BYTE *)(v190 + 2) )
                          goto LABEL_639;
                        goto LABEL_342;
                      }
                      if ( !*(_DWORD *)(v190 + 20) )
                      {
                        v307 = *(_DWORD *)(v190 + 56);
                        if ( v307 )
                        {
                          v188 = 0;
                          v226 = 0;
                          v235 = 0;
                          while ( 1 )
                          {
                            v308 = *(unsigned int *)(v190 + 4LL * v235 + 120);
                            if ( (unsigned int)v308 >= 0x80 )
                            {
                              v309 = *(unsigned int *)(v190 + 16);
                              if ( (unsigned int)v308 < (unsigned int)v309 )
                              {
                                v310 = (unsigned int)v308;
                                v311 = *(_DWORD *)(v190 + v308);
                                if ( v311 == 64 )
                                {
                                  if ( v310 + 40 <= v309 )
                                  {
LABEL_389:
                                    if ( *(_BYTE *)(v190 + v310 + 10) )
                                      v226 = (unsigned __int8 *)(v310 + v190 + 24);
                                    LOBYTE(v10) = *(_BYTE *)(v190 + v310 + 8);
                                    v187 = *(_BYTE **)(v190 + v310 + 16);
                                    v188 = *(_BYTE *)(v190 + v310 + 9);
                                    goto LABEL_464;
                                  }
                                }
                                else
                                {
                                  v234 = v311 - 65;
                                  if ( v234 )
                                  {
                                    if ( v234 == 1 && v310 + 40 <= v309 )
                                    {
                                      if ( *(_DWORD *)(v190 + v310 + 12) )
                                        v226 = (unsigned __int8 *)(v310 + v190 + 32);
                                      LOBYTE(v10) = *(_BYTE *)(v190 + v310 + 8);
                                      v187 = *(_BYTE **)(v190 + v310 + 24);
                                      v188 = *(_BYTE *)(v190 + v310 + 9);
LABEL_464:
                                      if ( !v226 )
                                        break;
                                      LODWORD(v186) = *v226;
LABEL_342:
                                      LOBYTE(v186) = v186 - 8;
                                      if ( (v186 & 0x5D) != 0 )
                                        break;
                                      v189 = *(_BYTE *)(v190 + 3);
                                      if ( v189 == 1 || !v187 || !v188 )
                                        goto LABEL_655;
                                      LOBYTE(v190) = 0;
                                      v191 = 0;
                                      v192 = 0;
                                      v186 = (unsigned __int64)&v187[v188];
                                      v193 = v187 + 8;
                                      if ( (unsigned __int8)((*v187 & 0x7F) - 114) <= 1u )
                                      {
                                        if ( (unsigned __int64)v193 <= v186 )
                                        {
                                          LODWORD(v190) = (unsigned __int8)v187[1];
                                          v191 = v187[2];
                                          LOBYTE(v190) = v190 & 0xF;
                                          v192 = v187[3];
                                          goto LABEL_354;
                                        }
                                      }
                                      else if ( (unsigned __int64)v193 <= v186 )
                                      {
                                        v194 = v187 + 13;
                                        LODWORD(v190) = (unsigned __int8)v187[2];
                                        LOBYTE(v190) = v190 & 0xF;
                                        v195 = v188;
                                        if ( (unsigned int)(unsigned __int8)v187[7] + 8 <= v188 )
                                          v195 = (unsigned __int8)v187[7] + 8;
                                        v186 = (unsigned __int64)&v187[v195];
                                        if ( (unsigned __int64)v194 <= v186 )
                                          v191 = v187[12];
                                        if ( (unsigned __int64)(v187 + 14) > v186 )
                                          v192 = 0;
                                        else
                                          v192 = *v194;
LABEL_354:
                                        v196 = 1;
LABEL_782:
                                        if ( !v196 )
                                        {
LABEL_655:
                                          v192 = 0;
                                          v191 = 0;
                                          LOBYTE(v190) = 0;
                                        }
                                        McTemplateK0pduuuuup_EtwWriteTransfer(
                                          v186,
                                          v190,
                                          (unsigned int)&v332,
                                          a2,
                                          *(_DWORD *)(a2 + 48),
                                          v189,
                                          (char)v10,
                                          v190,
                                          v191,
                                          v192,
                                          a2);
                                        break;
                                      }
                                      v196 = 0;
                                      goto LABEL_782;
                                    }
                                  }
                                  else if ( v310 + 56 <= v309 )
                                  {
                                    goto LABEL_389;
                                  }
                                }
                              }
                            }
                            if ( ++v235 >= v307 )
                            {
                              v187 = 0;
                              goto LABEL_464;
                            }
                          }
                        }
                      }
                    }
                    else if ( v305 == 14 )
                    {
                      if ( (byte_140177432 & 8) != 0 )
                        McTemplateK0pd_EtwWriteTransfer(
                          v303,
                          EventNonReadWriteRequestComplete,
                          &v332,
                          a2,
                          *(_DWORD *)(a2 + 48));
                    }
                    else if ( v305 == 27 )
                    {
                      if ( v304[1] == 7 && !*((_DWORD *)v304 + 2) )
                      {
                        if ( (byte_140177432 & 0x40) != 0 )
                        {
                          v306 = *(_DWORD **)(a2 + 56);
                          if ( v306 )
                            LODWORD(v10) = *v306;
                          McTemplateK0pqd_EtwWriteTransfer(
                            v303,
                            (_DWORD)v304,
                            (unsigned int)&v332,
                            a2,
                            (char)v10,
                            *(_DWORD *)(a2 + 48));
                        }
                      }
                      else if ( (byte_140177432 & 0x20) != 0 )
                      {
                        McTemplateK0pd_EtwWriteTransfer(v303, EventPnpRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
                      }
                    }
LABEL_639:
                    IofCompleteRequest((PIRP)a2, 0);
                    goto LABEL_95;
                  case 24:
                    v51 = RaUnitLockQueueSrb(a1, a2);
                    goto LABEL_95;
                  case 25:
                    v51 = RaUnitUnlockQueueSrb(a1, a2);
                    goto LABEL_95;
                  case 26:
                    v51 = RaUnitQuiesceDeviceSrb(a1, a2);
                    v52 = v51 != 259;
                    goto LABEL_95;
                  default:
                    v51 = RaUnitUnknownSrb(v28, a2);
                    goto LABEL_95;
                }
              }
              if ( *(_BYTE *)(v5 + 2) != 40 )
              {
                v29 = (_BYTE *)(v5 + 72);
                goto LABEL_56;
              }
              v29 = 0;
              if ( *(_BYTE *)(v25 + 2) == 40 && !*(_DWORD *)(v25 + 20) )
              {
                v30 = *(_DWORD *)(v25 + 56);
                if ( v30 )
                {
                  v31 = 0;
                  while ( 1 )
                  {
                    v32 = *(unsigned int *)(v25 + 4LL * v31 + 120);
                    if ( (unsigned int)v32 < 0x80 )
                      goto LABEL_53;
                    v33 = *(unsigned int *)(v25 + 16);
                    if ( (unsigned int)v32 >= (unsigned int)v33 )
                      goto LABEL_53;
                    v34 = *(_DWORD *)(v32 + v25);
                    v35 = v32 + v25;
                    if ( v34 == 64 )
                      break;
                    v56 = v34 - 65;
                    if ( !v56 )
                    {
                      v36 = v32 + 56;
LABEL_52:
                      if ( v36 <= v33 )
                      {
                        if ( *(_BYTE *)(v35 + 10) )
                          v29 = (_BYTE *)(v35 + 24);
                        goto LABEL_56;
                      }
                      goto LABEL_53;
                    }
                    if ( v56 == 1 && v32 + 40 <= v33 )
                    {
                      if ( *(_DWORD *)(v35 + 12) )
                        v29 = (_BYTE *)(v35 + 32);
                      goto LABEL_56;
                    }
LABEL_53:
                    if ( ++v31 >= v30 )
                      goto LABEL_56;
                  }
                  v36 = v32 + 40;
                  goto LABEL_52;
                }
              }
LABEL_56:
              if ( !v29 )
              {
LABEL_60:
                if ( !DisableIEEE1667 || !v29 )
                  goto LABEL_61;
                if ( *v29 == 0xA2 )
                {
                  if ( v29[1] != 0xEE )
                  {
LABEL_61:
                    if ( StorEtwLoggingEnabled && (byte_140177431 & 0x1E) != 0 && ((*v29 - 8) & 0x5D) == 0 )
                    {
                      IoGetActivityIdIrp(a2, &v334);
                      StorEtwIORequestDispatch(a2);
                    }
                    v38 = *(_QWORD *)(a2 + 184);
                    v39 = *(_QWORD *)(v38 + 8);
                    *(_BYTE *)(v38 + 3) |= 1u;
                    *(_BYTE *)(v39 + 3) = 0;
                    *(_QWORD *)(*(_QWORD *)(a2 + 184) + 24LL) = 0;
                    if ( *(_BYTE *)(v39 + 2) == 40 )
                    {
                      v40 = *(unsigned int *)(v39 + 20);
                      v41 = (int *)(v39 + 24);
                    }
                    else
                    {
                      v40 = *(unsigned __int8 *)(v39 + 2);
                      v41 = (int *)(v39 + 12);
                    }
                    v42 = *v41;
                    if ( (qword_140176450 & 0x20) != 0 )
                      DbgLogRequest(
                        *(_QWORD *)(a1 + 24),
                        3,
                        a2,
                        (unsigned __int8)BYTE2(*(_DWORD *)(a1 + 104))
                      | ((((unsigned __int8)*(_DWORD *)(a1 + 104) << 8) | (unsigned __int8)BYTE1(*(_DWORD *)(a1 + 104))) << 8),
                        0,
                        0,
                        0);
                    v43 = ((v42 & 0x80000) != 0 ? 4 : 0) | 2;
                    if ( (v42 & 0x10) == 0 )
                      v43 = (v42 & 0x80000) != 0 ? 4 : 0;
                    if ( EnableSolitaryIO
                      || (v42 & 0x102) != 0x102
                      && (v42 & 0x10) == 0
                      && (v42 & 0x80000) == 0
                      && ((unsigned int)v40 > 0x20 || (v44 = 0x1000D0000LL, !_bittest64(&v44, v40))) )
                    {
                      v43 |= 1u;
                    }
                    RaidStartIoPacket(a1, a2, v43);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_qqD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        19,
                        WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
                        a1,
                        a2,
                        259);
                    }
                    return 259;
                  }
                }
                else if ( *v29 != 0xB5 || v29[1] != 0xEE )
                {
                  goto LABEL_61;
                }
                *(_BYTE *)(v5 + 3) = 4;
                *(_QWORD *)(a2 + 56) = 0;
                v331 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
                v294 = *(_DWORD *)(v331 + *(_QWORD *)(a1 + 40));
                while ( (v294 & 1) == 0 )
                {
                  v295 = v294;
                  v294 = _InterlockedCompareExchange(
                           (volatile signed __int32 *)(v331 + *(_QWORD *)(a1 + 40)),
                           v294 - 2,
                           v294);
                  if ( v295 == v294 )
                    goto LABEL_607;
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
                  KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
LABEL_607:
                v13 = StorEtwLoggingEnabled == 0;
                *(_BYTE *)(a2 + 141) = -84;
                *(_DWORD *)(a2 + 48) = -1073741637;
                if ( v13 )
                  goto LABEL_143;
                v332 = 0;
                IoGetActivityIdIrp(a2, &v332);
                v78 = *(char **)(a2 + 184);
                v296 = *v78;
                if ( *v78 == 15 )
                {
                  if ( byte_140177431 >= 0 )
                    goto LABEL_143;
                  v177 = *((_QWORD *)v78 + 1);
                  if ( *(_BYTE *)(v177 + 2) != 40 )
                  {
                    v175 = *(_BYTE *)(v177 + 72);
                    v10 = *(char **)(v177 + 32);
                    v174 = *(_BYTE *)(v177 + 11);
                    v173 = *(_BYTE *)(v177 + 4);
                    if ( !*(_BYTE *)(v177 + 2) )
                      goto LABEL_328;
                    goto LABEL_143;
                  }
                  if ( *(_DWORD *)(v177 + 20) )
                    goto LABEL_143;
                  v297 = *(_DWORD *)(v177 + 56);
                  if ( !v297 )
                    goto LABEL_143;
                  v173 = 0;
                  v172 = 0;
                  v174 = 0;
                  v298 = 0;
                  while ( 1 )
                  {
                    v299 = *(unsigned int *)(v177 + 4LL * v298 + 120);
                    if ( (unsigned int)v299 >= 0x80 )
                    {
                      v300 = *(unsigned int *)(v177 + 16);
                      if ( (unsigned int)v299 < (unsigned int)v300 )
                      {
                        v301 = (unsigned int)v299;
                        v302 = *(_DWORD *)(v299 + v177);
                        if ( v302 == 64 )
                        {
                          if ( v301 + 40 <= v300 )
                          {
                            if ( *(_BYTE *)(v301 + v177 + 10) )
LABEL_325:
                              v172 = (char *)(v301 + v177 + 24);
LABEL_326:
                            v10 = *(char **)(v301 + v177 + 16);
                            v173 = *(_BYTE *)(v301 + v177 + 8);
                            v174 = *(_BYTE *)(v301 + v177 + 9);
                            goto LABEL_762;
                          }
                        }
                        else
                        {
                          v233 = v302 - 65;
                          if ( v233 )
                          {
                            if ( v233 == 1 && v301 + 40 <= v300 )
                            {
                              if ( *(_DWORD *)(v301 + v177 + 12) )
                                v172 = (char *)(v301 + v177 + 32);
                              v10 = *(char **)(v301 + v177 + 24);
                              v173 = *(_BYTE *)(v301 + v177 + 8);
                              v174 = *(_BYTE *)(v301 + v177 + 9);
LABEL_762:
                              if ( !v172 )
                                goto LABEL_143;
                              v175 = *v172;
LABEL_328:
                              if ( ((v175 - 8) & 0x5D) != 0 )
                                goto LABEL_143;
                              v176 = *(_BYTE *)(v177 + 3);
                              if ( v176 == 1 || !v10 || !v174 )
                                goto LABEL_629;
                              LOBYTE(v177) = 0;
                              v178 = 0;
                              v179 = 0;
                              v180 = &v10[v174];
                              v181 = v10 + 8;
                              if ( (unsigned __int8)((*v10 & 0x7F) - 114) <= 1u )
                              {
                                if ( v181 <= v180 )
                                {
                                  LODWORD(v177) = (unsigned __int8)v10[1];
                                  v178 = v10[2];
                                  LOBYTE(v177) = v177 & 0xF;
                                  v179 = v10[3];
                                  goto LABEL_340;
                                }
                              }
                              else if ( v181 <= v180 )
                              {
                                v182 = v10 + 13;
                                LODWORD(v177) = (unsigned __int8)v10[2];
                                LOBYTE(v177) = v177 & 0xF;
                                v183 = v174;
                                if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v174 )
                                  v183 = (unsigned __int8)v10[7] + 8;
                                v184 = (unsigned __int64)&v10[v183];
                                if ( (unsigned __int64)v182 <= v184 )
                                  v178 = v10[12];
                                if ( (unsigned __int64)(v10 + 14) > v184 )
                                  v179 = 0;
                                else
                                  v179 = *v182;
LABEL_340:
                                v185 = 1;
LABEL_768:
                                if ( !v185 )
                                {
LABEL_629:
                                  v179 = 0;
                                  v178 = 0;
                                  LOBYTE(v177) = 0;
                                }
                                McTemplateK0pduuuuup_EtwWriteTransfer(
                                  *(_DWORD *)(a2 + 48),
                                  v177,
                                  (unsigned int)&v332,
                                  a2,
                                  *(_DWORD *)(a2 + 48),
                                  v176,
                                  v173,
                                  v177,
                                  v178,
                                  v179,
                                  a2);
LABEL_143:
                                IofCompleteRequest((PIRP)a2, 0);
                                return 3221225659LL;
                              }
                              v185 = 0;
                              goto LABEL_768;
                            }
                          }
                          else if ( v301 + 56 <= v300 )
                          {
                            if ( *(_BYTE *)(v301 + v177 + 10) )
                              goto LABEL_325;
                            goto LABEL_326;
                          }
                        }
                      }
                    }
                    if ( ++v298 >= v297 )
                      goto LABEL_762;
                  }
                }
                if ( v296 != 14 )
                {
                  if ( v296 != 27 )
                    goto LABEL_143;
                  if ( v78[1] == 7 && !*((_DWORD *)v78 + 2) )
                  {
                    if ( (byte_140177432 & 0x40) == 0 )
                      goto LABEL_143;
                    v97 = *(_DWORD **)(a2 + 56);
                    if ( !v97 )
                      goto LABEL_851;
                    goto LABEL_850;
                  }
                  goto LABEL_210;
                }
                goto LABEL_196;
              }
              if ( *v29 == 27 && (v29[4] & 1) == 0 )
              {
                v57 = *(_QWORD *)(a1 + 24);
                if ( *(_DWORD *)v57 == 1094997074 )
                {
                  v58 = v57 + 588;
                }
                else
                {
                  v58 = v57 + 404;
                  if ( *(_DWORD *)v57 != 1314275652 )
                    v58 = 228;
                }
                if ( (*(_DWORD *)v58 & 2) == 0 )
                {
                  v60 = *(_DWORD *)(a1 + 544) >= 5;
LABEL_128:
                  if ( v60 )
                    goto LABEL_129;
                  goto LABEL_58;
                }
                if ( (*(_BYTE *)(a1 + 505) & 4) != 0 || (*(_BYTE *)(v57 + 107) & 0x10) != 0 )
                  goto LABEL_58;
                v59 = *(_DWORD *)(a1 + 544);
                if ( v59 == 5 )
                {
                  v60 = *(_DWORD *)(a1 + 1044) != 0;
                  goto LABEL_128;
                }
                if ( v59 == 6 && *(_DWORD *)(a1 + 552) == 5 )
                {
LABEL_129:
                  v13 = StorEtwLoggingEnabled == 0;
                  *(_BYTE *)(v5 + 3) = 1;
                  *(_QWORD *)(a2 + 56) = 0;
                  *(_BYTE *)(a2 + 141) = -84;
                  *(_DWORD *)(a2 + 48) = 0;
                  if ( !v13 )
                  {
                    v332 = 0;
                    IoGetActivityIdIrp(a2, &v332);
                    v69 = *(char **)(a2 + 184);
                    v70 = *v69;
                    if ( *v69 != 15 )
                    {
                      if ( v70 == 14 )
                      {
                        if ( (byte_140177432 & 8) != 0 )
                          McTemplateK0pd_EtwWriteTransfer(
                            v69,
                            EventNonReadWriteRequestComplete,
                            &v332,
                            a2,
                            *(_DWORD *)(a2 + 48));
                      }
                      else if ( v70 == 27 )
                      {
                        if ( v69[1] != 7 || *((_DWORD *)v69 + 2) )
                        {
                          if ( (byte_140177432 & 0x20) != 0 )
                            McTemplateK0pd_EtwWriteTransfer(
                              v69,
                              EventPnpRequestComplete,
                              &v332,
                              a2,
                              *(_DWORD *)(a2 + 48));
                        }
                        else if ( (byte_140177432 & 0x40) != 0 )
                        {
                          v94 = *(_DWORD **)(a2 + 56);
                          if ( v94 )
                            LODWORD(v10) = *v94;
                          McTemplateK0pqd_EtwWriteTransfer(
                            (_DWORD)v69,
                            v68,
                            (unsigned int)&v332,
                            a2,
                            (char)v10,
                            *(_DWORD *)(a2 + 48));
                        }
                      }
                      goto LABEL_132;
                    }
                    if ( byte_140177431 < 0 )
                    {
                      v153 = *((_QWORD *)v69 + 1);
                      if ( *(_BYTE *)(v153 + 2) != 40 )
                      {
                        LODWORD(v151) = *(unsigned __int8 *)(v153 + 72);
                        v10 = *(char **)(v153 + 32);
                        v150 = *(_BYTE *)(v153 + 11);
                        v149 = *(_BYTE *)(v153 + 4);
                        if ( !*(_BYTE *)(v153 + 2) )
                          goto LABEL_296;
                        goto LABEL_132;
                      }
                      if ( *(_DWORD *)(v153 + 20) )
                        goto LABEL_132;
                      v278 = *(_DWORD *)(v153 + 56);
                      if ( !v278 )
                        goto LABEL_132;
                      v149 = 0;
                      v148 = 0;
                      v150 = 0;
                      v279 = 0;
                      while ( 1 )
                      {
                        v280 = *(unsigned int *)(v153 + 4LL * v279 + 120);
                        if ( (unsigned int)v280 >= 0x80 )
                        {
                          v281 = *(unsigned int *)(v153 + 16);
                          if ( (unsigned int)v280 < (unsigned int)v281 )
                          {
                            v282 = (unsigned int)v280;
                            v283 = *(_DWORD *)(v153 + v280);
                            if ( v283 == 64 )
                            {
                              if ( v282 + 40 <= v281 )
                              {
                                if ( *(_BYTE *)(v153 + v282 + 10) )
LABEL_293:
                                  v148 = (unsigned __int8 *)(v282 + v153 + 24);
LABEL_294:
                                v10 = *(char **)(v153 + v282 + 16);
                                v149 = *(_BYTE *)(v153 + v282 + 8);
                                v150 = *(_BYTE *)(v153 + v282 + 9);
                                goto LABEL_731;
                              }
                            }
                            else
                            {
                              v231 = v283 - 65;
                              if ( v231 )
                              {
                                if ( v231 == 1 && v282 + 40 <= v281 )
                                {
                                  if ( *(_DWORD *)(v153 + v282 + 12) )
                                    v148 = (unsigned __int8 *)(v282 + v153 + 32);
                                  v10 = *(char **)(v153 + v282 + 24);
                                  v149 = *(_BYTE *)(v153 + v282 + 8);
                                  v150 = *(_BYTE *)(v153 + v282 + 9);
LABEL_731:
                                  if ( !v148 )
                                    break;
                                  LODWORD(v151) = *v148;
LABEL_296:
                                  LOBYTE(v151) = v151 - 8;
                                  if ( (v151 & 0x5D) != 0 )
                                    break;
                                  v152 = *(_BYTE *)(v153 + 3);
                                  if ( v152 == 1 || !v10 || !v150 )
                                    goto LABEL_577;
                                  LOBYTE(v153) = 0;
                                  v154 = 0;
                                  v155 = 0;
                                  v151 = (unsigned __int64)&v10[v150];
                                  v156 = v10 + 8;
                                  if ( (unsigned __int8)((*v10 & 0x7F) - 114) <= 1u )
                                  {
                                    if ( (unsigned __int64)v156 <= v151 )
                                    {
                                      LODWORD(v153) = (unsigned __int8)v10[1];
                                      v154 = v10[2];
                                      LOBYTE(v153) = v153 & 0xF;
                                      v155 = v10[3];
                                      goto LABEL_308;
                                    }
                                  }
                                  else if ( (unsigned __int64)v156 <= v151 )
                                  {
                                    v157 = v10 + 13;
                                    LODWORD(v153) = (unsigned __int8)v10[2];
                                    LOBYTE(v153) = v153 & 0xF;
                                    v158 = v150;
                                    if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v150 )
                                      v158 = (unsigned __int8)v10[7] + 8;
                                    v151 = (unsigned __int64)&v10[v158];
                                    if ( (unsigned __int64)v157 <= v151 )
                                      v154 = v10[12];
                                    if ( (unsigned __int64)(v10 + 14) > v151 )
                                      v155 = 0;
                                    else
                                      v155 = *v157;
LABEL_308:
                                    v159 = 1;
LABEL_737:
                                    if ( !v159 )
                                    {
LABEL_577:
                                      v155 = 0;
                                      v154 = 0;
                                      LOBYTE(v153) = 0;
                                    }
                                    McTemplateK0pduuuuup_EtwWriteTransfer(
                                      v151,
                                      v153,
                                      (unsigned int)&v332,
                                      a2,
                                      *(_DWORD *)(a2 + 48),
                                      v152,
                                      v149,
                                      v153,
                                      v154,
                                      v155,
                                      a2);
                                    break;
                                  }
                                  v159 = 0;
                                  goto LABEL_737;
                                }
                              }
                              else if ( v282 + 56 <= v281 )
                              {
                                if ( *(_BYTE *)(v153 + v282 + 10) )
                                  goto LABEL_293;
                                goto LABEL_294;
                              }
                            }
                          }
                        }
                        if ( ++v279 >= v278 )
                          goto LABEL_731;
                      }
                    }
                  }
LABEL_132:
                  IofCompleteRequest((PIRP)a2, 0);
                  v71 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
                  v72 = *(_DWORD *)(v71 + *(_QWORD *)(a1 + 40));
                  while ( (v72 & 1) == 0 )
                  {
                    v73 = v72;
                    v72 = _InterlockedCompareExchange(
                            (volatile signed __int32 *)(v71 + *(_QWORD *)(a1 + 40)),
                            v72 - 2,
                            v72);
                    if ( v73 == v72 )
                      goto LABEL_135;
                  }
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
                    KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
LABEL_135:
                  v74 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                  {
                    return 0;
                  }
                  v105 = 16;
LABEL_846:
                  WPP_SF_qq(v74->AttachedDevice, v105, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, a1, a2);
                  return 0;
                }
              }
LABEL_58:
              v37 = *(_QWORD *)(a1 + 24);
              if ( (*(_DWORD *)(v37 + 128) & 4) == 0 && !*(_DWORD *)(v37 + 312) )
                goto LABEL_60;
              v326 = 0;
              if ( (v27 & 0x800) != 0 && (*(_DWORD *)(a1 + 512) & 0x40) != 0 )
              {
                if ( *v29 == 53 )
                {
LABEL_834:
                  v326 = 1;
                  goto LABEL_835;
                }
                if ( *v29 == 27 )
                {
                  if ( (v29[4] & 1) != 0 )
                    goto LABEL_837;
                  goto LABEL_834;
                }
              }
LABEL_835:
              if ( *v29 != 27 || (v29[4] & 1) == 0 )
              {
LABEL_838:
                if ( !v326 )
                  goto LABEL_60;
LABEL_579:
                v13 = StorEtwLoggingEnabled == 0;
                *(_BYTE *)(v5 + 3) = 1;
                *(_QWORD *)(a2 + 56) = 0;
                *(_BYTE *)(a2 + 141) = -84;
                *(_DWORD *)(a2 + 48) = 0;
                if ( !v13 )
                {
                  v332 = 0;
                  IoGetActivityIdIrp(a2, &v332);
                  v285 = *(char **)(a2 + 184);
                  v286 = *v285;
                  if ( *v285 != 15 )
                  {
                    if ( v286 == 14 )
                    {
                      if ( (byte_140177432 & 8) != 0 )
                        McTemplateK0pd_EtwWriteTransfer(
                          v284,
                          EventNonReadWriteRequestComplete,
                          &v332,
                          a2,
                          *(_DWORD *)(a2 + 48));
                    }
                    else if ( v286 == 27 )
                    {
                      if ( v285[1] == 7 && !*((_DWORD *)v285 + 2) )
                      {
                        if ( (byte_140177432 & 0x40) != 0 )
                        {
                          v287 = *(_DWORD **)(a2 + 56);
                          if ( v287 )
                            LODWORD(v10) = *v287;
                          McTemplateK0pqd_EtwWriteTransfer(
                            v284,
                            (_DWORD)v285,
                            (unsigned int)&v332,
                            a2,
                            (char)v10,
                            *(_DWORD *)(a2 + 48));
                        }
                      }
                      else if ( (byte_140177432 & 0x20) != 0 )
                      {
                        McTemplateK0pd_EtwWriteTransfer(v284, EventPnpRequestComplete, &v332, a2, *(_DWORD *)(a2 + 48));
                      }
                    }
                    goto LABEL_235;
                  }
                  if ( byte_140177431 < 0 )
                  {
                    v165 = *((_QWORD *)v285 + 1);
                    if ( *(_BYTE *)(v165 + 2) != 40 )
                    {
                      LODWORD(v163) = *(unsigned __int8 *)(v165 + 72);
                      v10 = *(char **)(v165 + 32);
                      v162 = *(_BYTE *)(v165 + 11);
                      v161 = *(_BYTE *)(v165 + 4);
                      if ( !*(_BYTE *)(v165 + 2) )
                        goto LABEL_312;
                      goto LABEL_235;
                    }
                    if ( *(_DWORD *)(v165 + 20) )
                      goto LABEL_235;
                    v288 = *(_DWORD *)(v165 + 56);
                    if ( !v288 )
                      goto LABEL_235;
                    v161 = 0;
                    v160 = 0;
                    v162 = 0;
                    v289 = 0;
                    while ( 1 )
                    {
                      v290 = *(unsigned int *)(v165 + 4LL * v289 + 120);
                      if ( (unsigned int)v290 >= 0x80 )
                      {
                        v291 = *(unsigned int *)(v165 + 16);
                        if ( (unsigned int)v290 < (unsigned int)v291 )
                        {
                          v292 = (unsigned int)v290;
                          v293 = *(_DWORD *)(v165 + v290);
                          if ( v293 == 64 )
                          {
                            if ( v292 + 40 <= v291 )
                            {
                              if ( *(_BYTE *)(v165 + v292 + 10) )
LABEL_309:
                                v160 = (unsigned __int8 *)(v292 + v165 + 24);
LABEL_310:
                              v10 = *(char **)(v165 + v292 + 16);
                              v161 = *(_BYTE *)(v165 + v292 + 8);
                              v162 = *(_BYTE *)(v165 + v292 + 9);
                              goto LABEL_749;
                            }
                          }
                          else
                          {
                            v232 = v293 - 65;
                            if ( v232 )
                            {
                              if ( v232 == 1 && v292 + 40 <= v291 )
                              {
                                if ( *(_DWORD *)(v165 + v292 + 12) )
                                  v160 = (unsigned __int8 *)(v292 + v165 + 32);
                                v10 = *(char **)(v165 + v292 + 24);
                                v161 = *(_BYTE *)(v165 + v292 + 8);
                                v162 = *(_BYTE *)(v165 + v292 + 9);
LABEL_749:
                                if ( !v160 )
                                  break;
                                LODWORD(v163) = *v160;
LABEL_312:
                                LOBYTE(v163) = v163 - 8;
                                if ( (v163 & 0x5D) != 0 )
                                  break;
                                v164 = *(_BYTE *)(v165 + 3);
                                if ( v164 == 1 || !v10 || !v162 )
                                  goto LABEL_603;
                                LOBYTE(v165) = 0;
                                v166 = 0;
                                v167 = 0;
                                v163 = (unsigned __int64)&v10[v162];
                                v168 = v10 + 8;
                                if ( (unsigned __int8)((*v10 & 0x7F) - 114) <= 1u )
                                {
                                  if ( (unsigned __int64)v168 <= v163 )
                                  {
                                    LODWORD(v165) = (unsigned __int8)v10[1];
                                    v166 = v10[2];
                                    LOBYTE(v165) = v165 & 0xF;
                                    v167 = v10[3];
                                    goto LABEL_324;
                                  }
                                }
                                else if ( (unsigned __int64)v168 <= v163 )
                                {
                                  v169 = v10 + 13;
                                  LODWORD(v165) = (unsigned __int8)v10[2];
                                  LOBYTE(v165) = v165 & 0xF;
                                  v170 = v162;
                                  if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v162 )
                                    v170 = (unsigned __int8)v10[7] + 8;
                                  v163 = (unsigned __int64)&v10[v170];
                                  if ( (unsigned __int64)v169 <= v163 )
                                    v166 = v10[12];
                                  if ( (unsigned __int64)(v10 + 14) > v163 )
                                    v167 = 0;
                                  else
                                    v167 = *v169;
LABEL_324:
                                  v171 = 1;
LABEL_755:
                                  if ( !v171 )
                                  {
LABEL_603:
                                    v167 = 0;
                                    v166 = 0;
                                    LOBYTE(v165) = 0;
                                  }
                                  McTemplateK0pduuuuup_EtwWriteTransfer(
                                    v163,
                                    v165,
                                    (unsigned int)&v332,
                                    a2,
                                    *(_DWORD *)(a2 + 48),
                                    v164,
                                    v161,
                                    v165,
                                    v166,
                                    v167,
                                    a2);
                                  break;
                                }
                                v171 = 0;
                                goto LABEL_755;
                              }
                            }
                            else if ( v292 + 56 <= v291 )
                            {
                              if ( *(_BYTE *)(v165 + v292 + 10) )
                                goto LABEL_309;
                              goto LABEL_310;
                            }
                          }
                        }
                      }
                      if ( ++v289 >= v288 )
                        goto LABEL_749;
                    }
                  }
                }
LABEL_235:
                IofCompleteRequest((PIRP)a2, 0);
                v102 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
                v103 = *(_DWORD *)(v102 + *(_QWORD *)(a1 + 40));
                while ( (v103 & 1) == 0 )
                {
                  v104 = v103;
                  v103 = _InterlockedCompareExchange(
                           (volatile signed __int32 *)(v102 + *(_QWORD *)(a1 + 40)),
                           v103 - 2,
                           v103);
                  if ( v104 == v103 )
                    goto LABEL_238;
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
                  KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
LABEL_238:
                if ( *v29 == 53 )
                {
                  v74 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                  {
                    return 0;
                  }
                  v105 = 17;
                }
                else
                {
                  if ( *v29 != 27 )
                    return 0;
                  v74 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                  {
                    return 0;
                  }
                  v105 = 18;
                }
                goto LABEL_846;
              }
LABEL_837:
              if ( (*(_DWORD *)(a1 + 512) & 0x20) != 0 )
                goto LABEL_579;
              goto LABEL_838;
            }
          }
          *(_BYTE *)(v5 + 3) = 6;
          *(_QWORD *)(a2 + 56) = 0;
          v325 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          v258 = *(_DWORD *)(v325 + *(_QWORD *)(a1 + 40));
          while ( (v258 & 1) == 0 )
          {
            v259 = v258;
            v258 = _InterlockedCompareExchange((volatile signed __int32 *)(v325 + *(_QWORD *)(a1 + 40)), v258 - 2, v258);
            if ( v259 == v258 )
              goto LABEL_524;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
            KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
LABEL_524:
          v13 = StorEtwLoggingEnabled == 0;
          *(_BYTE *)(a2 + 141) = -84;
          *(_DWORD *)(a2 + 48) = -1073741811;
          if ( v13 )
            goto LABEL_12;
          v332 = 0;
          IoGetActivityIdIrp(a2, &v332);
          v260 = *(char **)(a2 + 184);
          v261 = *v260;
          if ( *v260 == 15 )
          {
            if ( byte_140177431 >= 0 )
              goto LABEL_12;
            v263 = *((_QWORD *)v260 + 1);
            if ( *(_BYTE *)(v263 + 2) != 40 )
            {
              LODWORD(v125) = *(unsigned __int8 *)(v263 + 72);
              v10 = *(char **)(v263 + 32);
              v124 = *(_BYTE *)(v263 + 11);
              v123 = *(_BYTE *)(v263 + 4);
              if ( !*(_BYTE *)(v263 + 2) )
                goto LABEL_264;
              goto LABEL_12;
            }
            if ( *(_DWORD *)(v263 + 20) )
              goto LABEL_12;
            v264 = *(_DWORD *)(v263 + 56);
            if ( !v264 )
              goto LABEL_12;
            v123 = 0;
            v122 = 0;
            v124 = 0;
            v265 = 0;
            while ( 1 )
            {
              v266 = *(unsigned int *)(v263 + 4LL * v265 + 120);
              if ( (unsigned int)v266 >= 0x80 )
              {
                v267 = *(unsigned int *)(v263 + 16);
                if ( (unsigned int)v266 < (unsigned int)v267 )
                {
                  v268 = (unsigned int)v266;
                  v269 = *(_DWORD *)(v266 + v263);
                  if ( v269 == 64 )
                  {
                    if ( v268 + 40 <= v267 )
                    {
                      if ( *(_BYTE *)(v268 + v263 + 10) )
LABEL_261:
                        v122 = (unsigned __int8 *)(v268 + v263 + 24);
LABEL_262:
                      v10 = *(char **)(v268 + v263 + 16);
                      v123 = *(_BYTE *)(v268 + v263 + 8);
                      v124 = *(_BYTE *)(v268 + v263 + 9);
                      goto LABEL_704;
                    }
                  }
                  else
                  {
                    v229 = v269 - 65;
                    if ( v229 )
                    {
                      if ( v229 == 1 && v268 + 40 <= v267 )
                      {
                        if ( *(_DWORD *)(v268 + v263 + 12) )
                          v122 = (unsigned __int8 *)(v268 + v263 + 32);
                        v10 = *(char **)(v268 + v263 + 24);
                        v123 = *(_BYTE *)(v268 + v263 + 8);
                        v124 = *(_BYTE *)(v268 + v263 + 9);
LABEL_704:
                        if ( !v122 )
                          goto LABEL_12;
                        LODWORD(v125) = *v122;
LABEL_264:
                        LOBYTE(v125) = v125 - 8;
                        if ( (v125 & 0x5D) != 0 )
                          goto LABEL_12;
                        v126 = *(_BYTE *)(v263 + 3);
                        if ( v126 == 1 || !v10 || !v124 )
                          goto LABEL_546;
                        v127 = 0;
                        v128 = 0;
                        v129 = 0;
                        v125 = (unsigned __int64)&v10[v124];
                        v130 = v10 + 8;
                        if ( (unsigned __int8)((*v10 & 0x7F) - 114) <= 1u )
                        {
                          if ( (unsigned __int64)v130 <= v125 )
                          {
                            v128 = v10[2];
                            v127 = v10[1] & 0xF;
                            v129 = v10[3];
                            goto LABEL_276;
                          }
                        }
                        else if ( (unsigned __int64)v130 <= v125 )
                        {
                          v131 = v10 + 13;
                          v127 = v10[2] & 0xF;
                          v132 = v124;
                          if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v124 )
                            v132 = (unsigned __int8)v10[7] + 8;
                          v125 = (unsigned __int64)&v10[v132];
                          if ( (unsigned __int64)v131 <= v125 )
                            v128 = v10[12];
                          if ( (unsigned __int64)(v10 + 14) > v125 )
                            v129 = 0;
                          else
                            v129 = *v131;
LABEL_276:
                          v133 = 1;
LABEL_710:
                          if ( !v133 )
                          {
LABEL_546:
                            v129 = 0;
                            v128 = 0;
                            v127 = 0;
                          }
                          McTemplateK0pduuuuup_EtwWriteTransfer(
                            v125,
                            *(_DWORD *)(a2 + 48),
                            (unsigned int)&v332,
                            a2,
                            *(_DWORD *)(a2 + 48),
                            v126,
                            v123,
                            v127,
                            v128,
                            v129,
                            a2);
LABEL_12:
                          IofCompleteRequest((PIRP)a2, 0);
                          return 3221225485LL;
                        }
                        v133 = 0;
                        goto LABEL_710;
                      }
                    }
                    else if ( v268 + 56 <= v267 )
                    {
                      if ( *(_BYTE *)(v268 + v263 + 10) )
                        goto LABEL_261;
                      goto LABEL_262;
                    }
                  }
                }
              }
              if ( ++v265 >= v264 )
                goto LABEL_704;
            }
          }
          if ( v261 != 14 )
          {
            if ( v261 != 27 )
              goto LABEL_12;
            if ( v260[1] == 7 && !*((_DWORD *)v260 + 2) )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                v262 = *(_DWORD **)(a2 + 56);
                if ( v262 )
                  LODWORD(v10) = *v262;
                McTemplateK0pqd_EtwWriteTransfer(
                  (_DWORD)v15,
                  (_DWORD)v260,
                  (unsigned int)&v332,
                  a2,
                  (char)v10,
                  *(_DWORD *)(a2 + 48));
              }
              goto LABEL_12;
            }
            goto LABEL_28;
          }
          goto LABEL_24;
        }
      }
    }
    v11 = -1073741738;
    goto LABEL_30;
  }
  v11 = -1073741738;
LABEL_7:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
  v13 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(v5 + 3) = 4;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v11;
  if ( v13 )
    goto LABEL_223;
  v333 = 0;
  IoGetActivityIdIrp(a2, &v333);
  v99 = *(unsigned __int8 **)(a2 + 184);
  v100 = *v99;
  if ( (_BYTE)v100 != 15 )
  {
    if ( (_BYTE)v100 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v100, EventNonReadWriteRequestComplete, &v333, a2, *(_DWORD *)(a2 + 48));
    }
    else if ( (_BYTE)v100 == 27 )
    {
      if ( v99[1] != 7 || *((_DWORD *)v99 + 2) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v100, EventPnpRequestComplete, &v333, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v101 = *(_DWORD **)(a2 + 56);
        if ( v101 )
          LODWORD(v10) = *v101;
        McTemplateK0pqd_EtwWriteTransfer(v100, v98, (unsigned int)&v333, a2, (char)v10, *(_DWORD *)(a2 + 48));
      }
    }
    goto LABEL_223;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_223;
  v217 = *((_QWORD *)v99 + 1);
  if ( *(_BYTE *)(v217 + 2) != 40 )
  {
    v214 = *(_BYTE *)(v217 + 72);
    v318 = *(unsigned __int8 *)(v217 + 2);
    v215 = *(_BYTE **)(v217 + 32);
    v212 = *(_BYTE *)(v217 + 11);
    v211 = *(_BYTE *)(v217 + 4);
    goto LABEL_375;
  }
  v318 = *(_DWORD *)(v217 + 20);
  if ( v318 )
    goto LABEL_223;
  v213 = *(_DWORD *)(v217 + 56);
  v214 = 0;
  v211 = 0;
  v212 = 0;
  if ( !v213 )
  {
    v215 = 0;
    goto LABEL_375;
  }
  v210 = 0;
  v330 = 0;
  while ( 1 )
  {
    v319 = *(unsigned int *)(v217 + 4LL * v330 + 120);
    if ( (unsigned int)v319 < 0x80 )
      goto LABEL_811;
    v320 = *(unsigned int *)(v217 + 16);
    if ( (unsigned int)v319 >= (unsigned int)v320 )
      goto LABEL_811;
    v321 = (unsigned int)v319;
    v322 = *(_DWORD *)(v319 + v217);
    if ( v322 == 64 )
    {
      if ( v321 + 40 <= v320 )
      {
        if ( !*(_BYTE *)(v321 + v217 + 10) )
          goto LABEL_372;
LABEL_371:
        v210 = (char *)(v321 + v217 + 24);
LABEL_372:
        v211 = *(_BYTE *)(v321 + v217 + 8);
        v212 = *(_BYTE *)(v321 + v217 + 9);
        *(_QWORD *)&v332 = *(_QWORD *)(v321 + v217 + 16);
        goto LABEL_812;
      }
      goto LABEL_811;
    }
    v237 = v322 - 65;
    if ( v237 )
      break;
    if ( v321 + 56 <= v320 )
    {
      if ( !*(_BYTE *)(v321 + v217 + 10) )
        goto LABEL_372;
      goto LABEL_371;
    }
LABEL_811:
    if ( ++v330 >= v213 )
      goto LABEL_812;
  }
  if ( v237 != 1 || v321 + 40 > v320 )
    goto LABEL_811;
  if ( *(_DWORD *)(v321 + v217 + 12) )
    v210 = (char *)(v321 + v217 + 32);
  v211 = *(_BYTE *)(v321 + v217 + 8);
  v212 = *(_BYTE *)(v321 + v217 + 9);
  *(_QWORD *)&v332 = *(_QWORD *)(v321 + v217 + 24);
LABEL_812:
  v215 = (_BYTE *)v332;
  if ( !v210 )
  {
LABEL_375:
    if ( !v318 )
      goto LABEL_376;
    goto LABEL_223;
  }
  v214 = *v210;
LABEL_376:
  if ( ((v214 - 8) & 0x5D) == 0 )
  {
    v216 = *(_BYTE *)(v217 + 3);
    if ( v216 == 1 || !v215 || !v212 )
      goto LABEL_676;
    LOBYTE(v217) = 0;
    v218 = 0;
    v219 = 0;
    v220 = &v215[v212];
    v221 = v215 + 8;
    if ( (unsigned __int8)((*v215 & 0x7F) - 114) <= 1u )
    {
      if ( v221 <= v220 )
      {
        LODWORD(v217) = (unsigned __int8)v215[1];
        v218 = v215[2];
        LOBYTE(v217) = v217 & 0xF;
        v219 = v215[3];
        goto LABEL_388;
      }
    }
    else if ( v221 <= v220 )
    {
      v222 = v215 + 13;
      LODWORD(v217) = (unsigned __int8)v215[2];
      LOBYTE(v217) = v217 & 0xF;
      v223 = v212;
      if ( (unsigned int)(unsigned __int8)v215[7] + 8 <= v212 )
        v223 = (unsigned __int8)v215[7] + 8;
      v224 = (unsigned __int64)&v215[v223];
      if ( (unsigned __int64)v222 <= v224 )
        v218 = v215[12];
      if ( (unsigned __int64)(v215 + 14) > v224 )
        v219 = 0;
      else
        v219 = *v222;
LABEL_388:
      v225 = 1;
LABEL_818:
      if ( v225 )
      {
LABEL_677:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          *(_DWORD *)(a2 + 48),
          v217,
          (unsigned int)&v333,
          a2,
          *(_DWORD *)(a2 + 48),
          v216,
          v211,
          v217,
          v218,
          v219,
          a2);
        goto LABEL_223;
      }
LABEL_676:
      v219 = 0;
      v218 = 0;
      LOBYTE(v217) = 0;
      goto LABEL_677;
    }
    v225 = 0;
    goto LABEL_818;
  }
LABEL_223:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140017e80  mov     [rsp-8+arg_10], rbx
0x140017e85  push    rbp
0x140017e86  push    rsi
0x140017e87  push    rdi
0x140017e88  push    r12
0x140017e8a  push    r13
0x140017e8c  push    r14
0x140017e8e  push    r15
0x140017e90  lea     rbp, [rsp-27h]
0x140017e95  sub     rsp, 0A0h
0x140017e9c  mov     rax, cs:__security_cookie
0x140017ea3  xor     rax, rsp
0x140017ea6  mov     [rbp+57h+var_38], rax
0x140017eaa  mov     rax, [rdx+0B8h]
0x140017eb1  xorps   xmm0, xmm0
0x140017eb4  movups  [rbp+57h+var_48], xmm0
0x140017eb8  mov     r14, rdx
0x140017ebb  mov     rdi, rcx
0x140017ebe  mov     rbx, [rax+8]
0x140017ec2  test    rbx, rbx
0x140017ec5  jz      short loc_140017F41
0x140017ec7  mov     eax, gs:1A4h
0x140017ecf  mov     r8d, eax
0x140017ed2  mov     rax, [rcx+28h]
0x140017ed6  shl     r8, 6
0x140017eda  mov     eax, [r8+rax]
0x140017ede  test    al, 1
0x140017ee0  jnz     loc_140017FE4
0x140017ee6  mov     rcx, [rdi+28h]
0x140017eea  lea     edx, [rax+2]
0x140017eed  lock cmpxchg [r8+rcx], edx
0x140017ef3  jnz     short loc_140017EDE
0x140017ef5  mov     eax, [rdi+38h]
0x140017ef8  xor     r13d, r13d
0x140017efb  mov     qword ptr [rbp+57h+var_68], r13
0x140017eff  cmp     eax, 6
0x140017f02  jnz     loc_140017FF0
0x140017f08  mov     esi, 0C0000056h
0x140017f0d  mov     eax, 0FFFFFFFFh
0x140017f12  lock xadd [rdi+408h], eax
0x140017f1a  cmp     eax, 1
0x140017f1d  jnz     loc_14014DC72
0x140017f23  lea     rcx, [rdi+208h]; Event
0x140017f2a  xor     r8d, r8d; Wait
0x140017f2d  xor     edx, edx; Increment
0x140017f2f  call    cs:__imp_KeSetEvent
0x140017f36  nop     dword ptr [rax+rax+00h]
0x140017f3b  nop
0x140017f3c  jmp     loc_14014DC72
0x140017f41  xor     r15d, r15d
0x140017f44  mov     byte ptr [rdx+8Dh], 0ACh
0x140017f4b  cmp     cs:StorEtwLoggingEnabled, r15b
0x140017f52  mov     [rdx+38h], r15
0x140017f56  mov     dword ptr [rdx+30h], 0C000000Dh
0x140017f5d  jz      short loc_140017F95
0x140017f5f  lea     rdx, [rbp+57h+var_68]
0x140017f63  mov     rcx, r14
0x140017f66  movups  [rbp+57h+var_68], xmm0
0x140017f6a  call    cs:__imp_IoGetActivityIdIrp
0x140017f71  nop     dword ptr [rax+rax+00h]
0x140017f76  mov     rcx, [r14+0B8h]
0x140017f7d  movzx   eax, byte ptr [rcx]
0x140017f80  cmp     al, 0Fh
0x140017f82  jnz     loc_140018036
0x140017f88  cmp     cs:byte_140177431, r15b
0x140017f8f  jl      loc_14001A426
0x140017f95  xor     edx, edx; PriorityBoost
0x140017f97  mov     rcx, r14; Irp
0x140017f9a  call    cs:__imp_IofCompleteRequest
0x140017fa1  nop     dword ptr [rax+rax+00h]
0x140017fa6  mov     eax, 0C000000Dh
0x140017fab  jmp     loc_14001AB09
0x140017fb0  mov     rdx, r14
0x140017fb3  mov     rcx, rdi
0x140017fb6  call    RaidStartIoPacket
0x140017fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fc2  lea     rax, WPP_GLOBAL_Control
0x140017fc9  cmp     rcx, rax
0x140017fcc  jz      short loc_140017FD9
0x140017fce  mov     eax, [rcx+2Ch]
0x140017fd1  test    al, 8
0x140017fd3  jnz     loc_14001A80D
0x140017fd9  mov     eax, 103h
0x140017fde  jmp     loc_14001AB09
0x140017fe4  lock inc dword ptr [rdi+408h]
0x140017feb  jmp     loc_140017EF5
0x140017ff0  cmp     eax, 5
0x140017ff3  jz      loc_14001A48E
0x140017ff9  cmp     eax, 7
0x140017ffc  jnz     loc_1400180AE
0x140018002  mov     rcx, [r14+0B8h]
0x140018009  movzx   eax, byte ptr [rcx]
0x14001800c  movzx   edx, byte ptr [rcx+1]
0x140018010  cmp     al, 0Fh
0x140018012  jnz     loc_14014DA8B
0x140018018  mov     rcx, r14
0x14001801b  call    RaidSrbFunctionFromIrp
0x140018020  cmp     dl, 0F0h
0x140018023  jz      loc_14014DACD
0x140018029  cmp     al, 1
0x14001802b  jnz     loc_14014DAB5
0x140018031  jmp     loc_14014DACD
0x140018036  cmp     al, 0Eh
0x140018038  jnz     short loc_140018067
0x14001803a  test    cs:byte_140177432, 8
0x140018041  jz      loc_140017F95
0x140018047  mov     eax, [r14+30h]
0x14001804b  lea     r8, [rbp+57h+var_68]
0x14001804f  mov     r9, r14
0x140018052  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140018056  lea     rdx, EventNonReadWriteRequestComplete
0x14001805d  call    McTemplateK0pd_EtwWriteTransfer
0x140018062  jmp     loc_140017F95
0x140018067  cmp     al, 1Bh
0x140018069  jnz     loc_140017F95
0x14001806f  cmp     byte ptr [rcx+1], 7
0x140018073  jz      loc_1400189B9
0x140018079  test    cs:byte_140177432, 20h
0x140018080  jz      loc_140017F95
0x140018086  mov     eax, [r14+30h]
0x14001808a  lea     r8, [rbp+57h+var_68]
0x14001808e  mov     r9, r14
0x140018091  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140018095  lea     rdx, EventPnpRequestComplete
0x14001809c  call    McTemplateK0pd_EtwWriteTransfer
0x1400180a1  jmp     loc_140017F95
0x1400180a6  test    esi, esi
0x1400180a8  js      loc_140017F0D
0x1400180ae  mov     rax, [rdi+18h]
0x1400180b2  mov     ecx, [rax]
0x1400180b4  cmp     ecx, 4E564144h
0x1400180ba  jz      loc_1400182E5
0x1400180c0  cmp     ecx, 41445452h
0x1400180c6  jnz     loc_140018A18
0x1400180cc  lea     rcx, [rax+1D2h]
0x1400180d3  movzx   eax, byte ptr [rbx+2]
0x1400180d7  cmp     al, 28h ; '('
0x1400180d9  jnz     loc_1400182CC
0x1400180df  cmp     byte ptr [rcx], 1
0x1400180e2  jnz     loc_14001864B
0x1400180e8  cmp     dword ptr [rbx+8], 53524258h
0x1400180ef  jnz     loc_14001A50F
0x1400180f5  cmp     [rbx+30h], r13d
0x1400180f9  jnz     loc_14001A50F
0x1400180ff  mov     r15, rbx
0x140018102  mov     esi, [rbx+14h]
0x140018105  mov     r12d, [rbx+18h]
0x140018109  cmp     [rbx+48h], r13
0x14001810d  jnz     loc_14001A50F
0x140018113  mov     rcx, cs:WPP_GLOBAL_Control
0x14001811a  lea     rax, WPP_GLOBAL_Control
0x140018121  cmp     rcx, rax
0x140018124  jz      short loc_140018131
0x140018126  mov     eax, [rcx+2Ch]
0x140018129  test    al, 8
0x14001812b  jnz     loc_14001A584
0x140018131  bt      r12d, 14h
0x140018136  jb      loc_1400188B7
0x14001813c  test    esi, esi
0x14001813e  jnz     loc_140018304
0x140018144  cmp     byte ptr [rbx+2], 28h ; '('
0x140018148  jnz     short loc_1400181A7
0x14001814a  cmp     byte ptr [r15+2], 28h ; '('
0x14001814f  mov     rsi, r13
0x140018152  jnz     short loc_1400181AB
0x140018154  cmp     [r15+14h], esi
0x140018158  jnz     short loc_1400181AB
0x14001815a  mov     r10d, [r15+38h]
0x14001815e  test    r10d, r10d
0x140018161  jz      short loc_1400181AB
0x140018163  mov     r8d, r13d
0x140018166  mov     eax, r8d
0x140018169  mov     ecx, [r15+rax*4+78h]
0x14001816e  cmp     ecx, 80h
0x140018174  jb      short loc_14001819D
0x140018176  mov     edx, [r15+10h]
0x14001817a  cmp     ecx, edx
0x14001817c  jnb     short loc_14001819D
0x14001817e  mov     r11d, [rcx+r15]
0x140018182  lea     r9, [rcx+r15]
0x140018186  cmp     r11d, 40h ; '@'
0x14001818a  jnz     loc_1400183FC
0x140018190  add     rcx, 28h ; '('
0x140018194  cmp     rcx, rdx
0x140018197  jbe     loc_1400182F1
0x14001819d  inc     r8d
0x1400181a0  cmp     r8d, r10d
0x1400181a3  jb      short loc_140018166
0x1400181a5  jmp     short loc_1400181AB
0x1400181a7  lea     rsi, [rbx+48h]
0x1400181ab  test    rsi, rsi
0x1400181ae  jz      short loc_1400181D9
0x1400181b0  cmp     byte ptr [rsi], 1Bh
0x1400181b3  jz      loc_140018430
0x1400181b9  mov     rcx, [rdi+18h]
0x1400181bd  mov     eax, [rcx+80h]
0x1400181c3  test    al, 4
0x1400181c5  jnz     loc_14001A6C3
0x1400181cb  mov     eax, [rcx+138h]
0x1400181d1  test    eax, eax
0x1400181d3  jnz     loc_14001A6C3
0x1400181d9  cmp     cs:DisableIEEE1667, r13b
0x1400181e0  jnz     loc_14001A751
0x1400181e6  cmp     cs:StorEtwLoggingEnabled, r13b
0x1400181ed  jz      short loc_14001821C
0x1400181ef  test    cs:byte_140177431, 1Eh
0x1400181f6  jz      short loc_14001821C
0x1400181f8  movzx   eax, byte ptr [rsi]
0x1400181fb  sub     al, 8
0x1400181fd  test    al, 5Dh
0x1400181ff  jnz     short loc_14001821C
0x140018201  lea     rdx, [rbp+57h+var_48]
0x140018205  mov     rcx, r14
0x140018208  call    cs:__imp_IoGetActivityIdIrp
0x14001820f  nop     dword ptr [rax+rax+00h]
0x140018214  mov     rcx, r14
0x140018217  call    StorEtwIORequestDispatch
0x14001821c  mov     rax, [r14+0B8h]
0x140018223  mov     rcx, [rax+8]
0x140018227  or      byte ptr [rax+3], 1
0x14001822b  mov     [rcx+3], r13b
0x14001822f  mov     rax, [r14+0B8h]
0x140018236  mov     [rax+18h], r13
0x14001823a  movzx   eax, byte ptr [rcx+2]
0x14001823e  cmp     al, 28h ; '('
0x140018240  jnz     loc_1400182DA
0x140018246  mov     esi, [rcx+14h]
0x140018249  lea     rbx, [rcx+18h]
0x14001824d  mov     rax, cs:qword_140176450
0x140018254  mov     ebx, [rbx]
0x140018256  test    al, 20h
0x140018258  jnz     loc_14001A7C5
0x14001825e  mov     edx, ebx
0x140018260  and     edx, 80000h
0x140018266  mov     eax, edx
0x140018268  neg     eax
0x14001826a  mov     eax, ebx
0x14001826c  sbb     ecx, ecx
0x14001826e  and     ecx, 4
0x140018271  mov     r8d, ecx
0x140018274  or      r8d, 2
0x140018278  and     eax, 10h
0x14001827b  cmovz   r8d, ecx
0x14001827f  cmp     cs:EnableSolitaryIO, r13b
0x140018286  jnz     short loc_1400182C3
0x140018288  and     ebx, 102h
0x14001828e  cmp     ebx, 102h
0x140018294  jz      loc_140017FB0
0x14001829a  test    eax, eax
0x14001829c  jnz     loc_140017FB0
0x1400182a2  test    edx, edx
0x1400182a4  jnz     loc_140017FB0
0x1400182aa  cmp     esi, 20h ; ' '
0x1400182ad  ja      short loc_1400182C3
0x1400182af  mov     rcx, 1000D0000h
0x1400182b9  bt      rcx, rsi
0x1400182bd  jb      loc_140017FB0
0x1400182c3  or      r8d, 1
0x1400182c7  jmp     loc_140017FB0
0x1400182cc  mov     r12d, [rbx+0Ch]
0x1400182d0  mov     r15, r13
0x1400182d3  mov     esi, eax
0x1400182d5  jmp     loc_140018113
0x1400182da  mov     esi, eax
0x1400182dc  lea     rbx, [rcx+0Ch]
0x1400182e0  jmp     loc_14001824D
0x1400182e5  lea     rcx, [rax+11Ah]
0x1400182ec  jmp     loc_1400180D3
0x1400182f1  cmp     [r9+0Ah], sil
0x1400182f5  jbe     loc_1400181AB
0x1400182fb  lea     rsi, [r9+18h]
0x1400182ff  jmp     loc_1400181AB
0x140018304  cmp     esi, 0Ah
0x140018307  jz      loc_14001882A
0x14001830d  cmp     esi, 7
0x140018310  jnz     loc_140018491
0x140018316  mov     rax, [r14+0B8h]
0x14001831d  mov     rcx, [rax+8]
0x140018321  or      byte ptr [rax+3], 1
0x140018325  mov     [rcx+3], r13b
0x140018329  mov     rax, [r14+0B8h]
0x140018330  mov     [rax+18h], r13
0x140018334  movzx   eax, byte ptr [rcx+2]
0x140018338  cmp     al, 28h ; '('
0x14001833a  jnz     loc_14001853F
0x140018340  mov     esi, [rcx+14h]
0x140018343  lea     rbx, [rcx+18h]
0x140018347  mov     rax, cs:qword_140176450
0x14001834e  mov     ebx, [rbx]
0x140018350  test    al, 20h
0x140018352  jnz     loc_14001AA00
0x140018358  mov     edx, ebx
0x14001835a  and     edx, 80000h
0x140018360  mov     eax, edx
0x140018362  neg     eax
0x140018364  mov     eax, ebx
0x140018366  sbb     ecx, ecx
0x140018368  and     ecx, 4
0x14001836b  mov     r8d, ecx
0x14001836e  or      r8d, 2
  ... truncated ...
```
