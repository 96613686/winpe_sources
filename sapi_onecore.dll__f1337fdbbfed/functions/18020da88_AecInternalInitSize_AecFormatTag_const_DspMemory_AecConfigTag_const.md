# AecInternalInitSize(AecFormatTag const *,_DspMemory *,AecConfigTag const *)

- ea: `0x18020da88`
- end: `0x18020f564`
- name: `?AecInternalInitSize@@YAHPEBUAecFormatTag@@PEAU_DspMemory@@PEBUAecConfigTag@@@Z`
- size: `6876`
- prototype: `__int64 __fastcall(const struct AecFormatTag *, struct _DspMemory *, const struct AecConfigTag *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180203808`

## callees

- `0x18007aae4`
- `0x1801e6000`
- `0x1801eb764`
- `0x1801ffdc0`
- `0x18020da88`
- `0x18021f100`
- `0x180220044`
- `0x180221748`
- `0x18022516c`
- `0x180228d54`
- `0x18022b5d0`
- `0x18022d254`
- `0x18022ddf8`
- `0x18022f084`
- `0x180230d5c`
- `0x180232484`
- `0x180234104`

## string_xrefs

- `0x18020e3a6`: `VadCreateSize`
- `0x18020e4d7`: `VadCreateSize`
- `0x18020e7bf`: `VadCreateSize`
- `0x18020e92f`: `VadCreateSize`
- `0x18020ed3c`: `VadCreateSize`
- `0x18020ee5a`: `VadCreateSize`
- `0x18020f014`: `VadCreateSize`
- `0x18020f483`: `VadCreateSize`
- `0x18020f105`: `NsCreateSize`
- `0x18020e04e`: `FbCreateSize`
- `0x18020f30e`: `GcCreateSize`
- `0x18020e6cf`: `EcCreateSize`
- `0x18020ead8`: `BfCreateSize`
- `0x18020ef66`: `EsCreateSize`
- `0x18020f213`: `VsCreateSize`
- `0x18020e5ae`: `CtrCreateSize`
- `0x18020ebfc`: `SfCreateSize`
- `0x18020e87f`: `DtCreateSize`
- `0x18020e9ef`: `DtCreateSize`
- `0x18020e1a7`: `SpCreateSize`
- `0x18020e244`: `SslCreateSize`
- `0x18020e29f`: `EqCreateSize`
- `0x18020e0ec`: `EeCreateSize`
- `0x18020dfb7`: `ClCreateSize`
- `0x18020eb66`: `DereverbCreateSize`
- `0x18020e2fe`: `LcCreateSize`
- `0x18020f2a6`: `PostEqCreateSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall AecInternalInitSize(
        const struct AecFormatTag *a1,
        struct _DspMemory *a2,
        const struct AecConfigTag *a3)
{
  char *v6; // r15
  int v7; // r9d
  float v8; // xmm9_4
  int v9; // edx
  int v10; // r12d
  int Size; // eax
  int v12; // ebx
  const char *v13; // r8
  int v14; // r9d
  signed int i; // r12d
  int j; // r12d
  int v17; // ebx
  signed int k; // r12d
  int m; // r12d
  int v20; // r12d
  int v21; // r9d
  int v22; // r11d
  int v23; // eax
  int v24; // edx
  int v25; // ecx
  unsigned int v26; // edx
  int v27; // ecx
  int v28; // ebx
  const struct AecConfigTag *v29; // r15
  int v30; // r14d
  int v31; // eax
  unsigned int n; // r10d
  int v33; // ecx
  int v34; // eax
  int v35; // r8d
  int v36; // r9d
  int v37; // r10d
  int v38; // ebx
  float v39; // xmm0_4
  double v40; // xmm1_8
  double v41; // xmm1_8
  int v42; // eax
  int v43; // r8d
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // r12
  float v47; // xmm0_4
  double v48; // xmm1_8
  double v49; // xmm1_8
  int v50; // eax
  int v51; // r8d
  int v52; // r8d
  int v53; // r9d
  int v54; // r8d
  int v55; // edx
  int v56; // edx
  int v57; // edx
  int v58; // ecx
  int v59; // ecx
  int v60; // r9d
  const char *v61; // r8
  int v62; // r9d
  int v63; // eax
  int v64; // ecx
  int v65; // ecx
  int v66; // eax
  const char *v67; // r8
  int v68; // r9d
  int v69; // ecx
  int v70; // ecx
  int v71; // eax
  const char *v72; // r8
  const struct AecFormatTag *v73; // rdx
  int v74; // r9d
  int v75; // ecx
  int v76; // ecx
  int v77; // eax
  const char *v78; // r8
  int v79; // edx
  int v80; // r9d
  int v81; // ecx
  int v82; // ecx
  int v83; // ecx
  int v84; // ecx
  int v85; // eax
  const char *v86; // r8
  int v87; // r8d
  int v88; // edx
  int v89; // eax
  int v90; // r8d
  __int64 v91; // r9
  int v92; // eax
  __int64 v93; // r12
  int v94; // ecx
  int v95; // ecx
  int v96; // eax
  const char *v97; // r8
  int v98; // r8d
  int v99; // r9d
  int v100; // eax
  int v101; // edx
  __int64 v102; // r8
  int v103; // ecx
  int v104; // ecx
  int v105; // edx
  int v106; // eax
  int v107; // edx
  int v108; // eax
  int v109; // eax
  const char *v110; // r8
  unsigned __int16 v111; // dx
  int v112; // r12d
  int v113; // ecx
  int v114; // ecx
  int v115; // eax
  const char *v116; // r8
  int v117; // r8d
  int v118; // r9d
  int v119; // eax
  int v120; // edx
  __int64 v121; // r8
  int v122; // ecx
  int v123; // ecx
  int v124; // eax
  const char *v125; // r8
  int v126; // r8d
  int v127; // r9d
  int v128; // eax
  int v129; // edx
  __int64 v130; // r8
  int v131; // ecx
  int v132; // ecx
  int v133; // r9d
  const char *v134; // r8
  int v135; // r9d
  int v136; // eax
  int v137; // edx
  int v138; // r9d
  int v139; // ecx
  int v140; // ecx
  int v141; // r9d
  const char *v142; // r8
  const struct AecFormatTag *v143; // rdx
  int v144; // r9d
  int v145; // eax
  int v146; // eax
  __int64 v147; // r12
  int v148; // ecx
  int v149; // ecx
  int v150; // edx
  Scratch *v151; // rcx
  int v152; // edx
  int v153; // edx
  int v154; // ecx
  int v155; // ecx
  int v156; // eax
  const char *v157; // r8
  int v158; // r8d
  int v159; // r9d
  int v160; // eax
  int v161; // edx
  __int64 v162; // r8
  int v163; // ecx
  int v164; // ecx
  int v165; // eax
  const char *v166; // r8
  int v167; // r8d
  int v168; // r9d
  int v169; // eax
  int v170; // edx
  __int64 v171; // r8
  int v172; // ecx
  int v173; // ecx
  int v174; // eax
  const char *v175; // r8
  int v176; // r9d
  int v177; // ecx
  int v178; // ecx
  int v179; // eax
  const char *v180; // r8
  int v181; // r8d
  int v182; // r9d
  int v183; // eax
  int v184; // edx
  __int64 v185; // r8
  int v186; // ecx
  int v187; // ecx
  int v188; // edx
  int v189; // eax
  Scratch *v190; // rcx
  int v191; // edx
  int v192; // eax
  int v193; // ecx
  int v194; // ecx
  int v195; // edx
  int v196; // ecx
  int v197; // ecx
  int v198; // ecx
  int v199; // edx
  float v200; // xmm0_4
  double v201; // xmm1_8
  double v202; // xmm1_8
  int v203; // eax
  int v204; // ecx
  int v205; // ecx
  int v206; // r9d
  const char *v207; // r8
  int v208; // r8d
  int v209; // eax
  int v210; // edx
  int v211; // eax
  int v212; // r8d
  __int64 v213; // r9
  int v215; // [rsp+28h] [rbp-E0h]
  int v216; // [rsp+30h] [rbp-D8h]
  int v217; // [rsp+38h] [rbp-D0h]
  char *v218; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v219; // [rsp+48h] [rbp-C0h]
  __int64 v220; // [rsp+50h] [rbp-B8h]
  char *v221; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v222; // [rsp+60h] [rbp-A8h]
  int v223; // [rsp+68h] [rbp-A0h]
  int v224; // [rsp+70h] [rbp-98h]
  signed int v225; // [rsp+74h] [rbp-94h]
  int v226; // [rsp+78h] [rbp-90h]
  int v227; // [rsp+7Ch] [rbp-8Ch]
  char *v228; // [rsp+80h] [rbp-88h] BYREF
  __int64 v229; // [rsp+88h] [rbp-80h]
  int v230; // [rsp+90h] [rbp-78h]
  unsigned int v231; // [rsp+98h] [rbp-70h]
  int v232; // [rsp+9Ch] [rbp-6Ch]
  int v233; // [rsp+A0h] [rbp-68h]
  int v234; // [rsp+A4h] [rbp-64h]
  const struct AecConfigTag *v235; // [rsp+A8h] [rbp-60h]
  char *v236; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v237; // [rsp+B8h] [rbp-50h]
  int v238; // [rsp+C0h] [rbp-48h]
  _DWORD v239[7]; // [rsp+C8h] [rbp-40h] BYREF
  float v240; // [rsp+E4h] [rbp-24h]
  int v241; // [rsp+E8h] [rbp-20h]
  int v242; // [rsp+ECh] [rbp-1Ch]
  int v243; // [rsp+F0h] [rbp-18h]
  unsigned int v244; // [rsp+F8h] [rbp-10h]
  float v245; // [rsp+FCh] [rbp-Ch]
  int v246; // [rsp+100h] [rbp-8h]
  int v247; // [rsp+104h] [rbp-4h]
  signed int v248; // [rsp+108h] [rbp+0h]
  int v249; // [rsp+10Ch] [rbp+4h]
  int v250; // [rsp+110h] [rbp+8h]
  char *v251; // [rsp+118h] [rbp+10h] BYREF
  __int64 v252; // [rsp+120h] [rbp+18h]
  int v253; // [rsp+128h] [rbp+20h]
  char *v254; // [rsp+130h] [rbp+28h] BYREF
  __int64 v255; // [rsp+138h] [rbp+30h]
  int v256; // [rsp+140h] [rbp+38h]
  char *v257; // [rsp+148h] [rbp+40h] BYREF
  __int64 v258; // [rsp+150h] [rbp+48h]
  int v259; // [rsp+158h] [rbp+50h]
  _QWORD v260[2]; // [rsp+160h] [rbp+58h] BYREF
  int v261; // [rsp+170h] [rbp+68h]
  _QWORD v262[2]; // [rsp+178h] [rbp+70h] BYREF
  int v263; // [rsp+188h] [rbp+80h]
  _QWORD v264[2]; // [rsp+190h] [rbp+88h] BYREF
  int v265; // [rsp+1A0h] [rbp+98h]
  _QWORD v266[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  int v267; // [rsp+1B8h] [rbp+B0h]
  _QWORD v268[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v269; // [rsp+1D0h] [rbp+C8h]
  _QWORD v270[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  int v271; // [rsp+1E8h] [rbp+E0h]
  _QWORD v272[2]; // [rsp+1F0h] [rbp+E8h] BYREF
  int v273; // [rsp+200h] [rbp+F8h]
  _QWORD v274[2]; // [rsp+208h] [rbp+100h] BYREF
  int v275; // [rsp+218h] [rbp+110h]
  _QWORD v276[2]; // [rsp+220h] [rbp+118h] BYREF
  int v277; // [rsp+230h] [rbp+128h]
  _QWORD v278[2]; // [rsp+238h] [rbp+130h] BYREF
  int v279; // [rsp+248h] [rbp+140h]
  _QWORD v280[2]; // [rsp+250h] [rbp+148h] BYREF
  int v281; // [rsp+260h] [rbp+158h]

  v235 = a3;
  v6 = (char *)a2 + 72;
  v280[0] = (char *)a2 + 72;
  v280[1] = *((_QWORD *)a2 + 10);
  v281 = 1;
  v225 = *((_DWORD *)a3 + 1);
  memset_0(v239, 0, 0x4Cu);
  v7 = *(_DWORD *)a3;
  v224 = v7;
  v249 = v7;
  v248 = v225;
  v232 = *((_DWORD *)a3 + 2);
  v250 = v232;
  v234 = *((_DWORD *)a3 + 3);
  v239[4] = v234;
  v246 = *((_DWORD *)a3 + 7);
  v247 = *((_DWORD *)a3 + 8);
  v233 = *((_DWORD *)a3 + 5);
  v239[0] = 1000 * v233 / v234;
  v239[1] = v233;
  v226 = *((_DWORD *)a3 + 4);
  v239[2] = v226;
  v239[3] = (int)(float)((float)((float)v226 * 1000.0) / (float)v234);
  v239[5] = v233;
  v8 = (float)v233 / (float)v234;
  *(float *)&v239[6] = v8;
  v240 = *((float *)a3 + 6);
  v241 = (int)(float)((float)(v240 * (float)v234) / 1000.0);
  v242 = v226 / 2;
  v245 = (float)v234 / (float)(2 * (v226 / 2));
  v9 = (int)(float)((float)v246 / v245);
  v244 = v9 & 0xFFFFFFFC;
  v217 = 4 * ((int)(v9 + 3 + (int)(float)((float)((float)v247 / v245) + 0.5) - (v9 & 0xFFFFFFFC)) / 4);
  v243 = v217;
  v10 = 0;
  if ( (*((_DWORD *)a1 + 3) & 0xFF0000) != 0 )
  {
    while ( v10 < v7 )
    {
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 767);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "93";
        goto LABEL_7;
      }
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 767);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "94";
LABEL_7:
        v14 = Size;
        goto LABEL_320;
      }
      ++v10;
      v7 = v224;
    }
    for ( i = 0; i < v225; ++i )
    {
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 1);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "98";
        goto LABEL_7;
      }
    }
    v227 = 1;
    v231 = 1;
    for ( j = 0; ; ++j )
    {
      v17 = v232;
      if ( j >= v232 )
        break;
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 767);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "102";
        goto LABEL_7;
      }
    }
    v20 = v225;
  }
  else
  {
    while ( v10 < v7 )
    {
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 767);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "107";
        goto LABEL_7;
      }
      ++v10;
      v7 = v224;
    }
    for ( k = 0; k < v225; ++k )
    {
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 767);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "111";
        goto LABEL_7;
      }
    }
    for ( m = 0; ; ++m )
    {
      v17 = v232;
      if ( m >= v232 )
        break;
      Size = DspStreamCreateSize((const struct DspStreamParamStruct *)v239, a2, 767);
      v12 = Size;
      if ( Size < 0 )
      {
        v13 = "115";
        goto LABEL_7;
      }
    }
    v227 = 0;
    v20 = v225;
    v231 = v225;
  }
  v21 = 0;
  v22 = v233;
  if ( v17 > 0 )
  {
    v23 = DspMallocAlignedSize(4 * v233 + 16);
    v25 = *((_DWORD *)a2 + 11);
    do
    {
      v25 += v23;
      ++v24;
    }
    while ( v24 < v17 );
    *((_DWORD *)a2 + 11) = v25;
  }
  v26 = 0;
  if ( *((int *)v235 + 2) > 0 )
  {
    do
    {
      v27 = *((_DWORD *)a1 + v26 + 245) + 1;
      if ( v21 > v27 )
        v27 = v21;
      v21 = v27;
      ++v26;
    }
    while ( (signed int)v26 < *((_DWORD *)v235 + 2) );
    v6 = (char *)a2 + 72;
  }
  v28 = 0;
  if ( v21 > 0 )
  {
    v29 = v235;
    do
    {
      v30 = 0;
      v31 = 0;
      for ( n = 0; (signed int)n < *((_DWORD *)v29 + 2); ++n )
      {
        if ( *((_DWORD *)a1 + n + 245) == v28 )
        {
          ++v30;
          v33 = *((_DWORD *)a1 + n + 250);
          if ( v33 == -1 )
            v31 = v22;
          else
            v31 = v22 / (*((_DWORD *)v29 + 3) / v33);
        }
      }
      v34 = DspMallocAlignedSize(4 * v30 * v31);
      *((_DWORD *)a2 + 11) = v34 + v35;
      ++v28;
    }
    while ( v28 < v36 );
    v6 = (char *)a2 + 72;
  }
  v37 = v234;
  v38 = v226;
  if ( v20 > 0 )
  {
    do
    {
      v39 = (float)(v37 / v22) * 1.25;
      v40 = v39;
      if ( v39 < 0.0 )
        v41 = v40 - 0.5;
      else
        v41 = v40 + 0.5;
      v42 = DspMallocAlignedSize(4 * (v226 + v22 * (int)v41) + 16);
      v44 = v42 + v43;
    }
    while ( v45 + 1 < v20 );
    *((_DWORD *)a2 + 11) = v44;
  }
  v46 = v224;
  if ( v224 > 0 )
  {
    do
    {
      v47 = (float)(v37 / v22) * 0.5;
      v48 = v47;
      if ( v47 < 0.0 )
        v49 = v48 - 0.5;
      else
        v49 = v48 + 0.5;
      v50 = DspMallocAlignedSize(4 * (v38 + v22 * (int)v49) + 16);
      v52 = v50 + v51;
    }
    while ( v53 + 1 < v224 );
    *((_DWORD *)a2 + 11) = v52;
  }
  DspMallocAlignedSize(24 * v46);
  v233 = DspMallocAlignedSize(4 * v217 + 16);
  *((_DWORD *)a2 + 11) = v55 + v54 + 2 * v233;
  v56 = *((_DWORD *)a1 + 9);
  v218 = v6;
  v219 = *((_QWORD *)v6 + 1);
  LODWORD(v220) = 0;
  v12 = 0;
  v57 = v56 & 0xFF0000;
  if ( v57 )
  {
    if ( v57 == 327680 )
    {
      v12 = 0;
    }
    else
    {
      v12 = -2147209216;
      DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "ClCreateSize", "106", -2147209216);
    }
  }
  Scratch::~Scratch((Scratch *)&v218);
  if ( v12 < 0 )
  {
    v13 = "172";
    goto LABEL_319;
  }
  v58 = *((_DWORD *)a1 + 1);
  v218 = v6;
  v219 = *((_QWORD *)v6 + 1);
  LODWORD(v220) = 1;
  v12 = 0;
  v59 = v58 & 0xFF0000;
  if ( v59 )
  {
    if ( v59 == 196608 )
    {
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0xC0u);
      v63 = FbABUCreateSize((const struct AecBasicData_st *)v239, a1, a2, v62);
      v12 = v63;
      if ( v63 >= 0 )
        goto LABEL_78;
      v60 = v63;
      v61 = "106";
    }
    else
    {
      v60 = -2147209216;
      v12 = -2147209216;
      v61 = "113";
    }
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "FbCreateSize", v61, v60);
  }
LABEL_78:
  Scratch::~Scratch((Scratch *)&v218);
  if ( v12 < 0 )
  {
    v13 = "178";
    goto LABEL_319;
  }
  v64 = *((_DWORD *)a1 + 3);
  v221 = v6;
  v222 = *((_QWORD *)v6 + 1);
  v223 = 1;
  v12 = 0;
  v65 = v64 & 0xFF0000;
  if ( v65 )
  {
    if ( v65 == 196608 )
    {
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x48u);
      v218 = v6;
      v219 = *((_QWORD *)v6 + 1);
      LODWORD(v220) = 0;
      Scratch::~Scratch((Scratch *)&v218);
      v12 = 0;
    }
    else
    {
      if ( v65 == 0x40000 )
      {
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x68u);
        v66 = EeXBOXCreateSize((const struct AecBasicData_st *)v239, a1, a2, v68);
        v12 = v66;
        if ( v66 >= 0 )
          goto LABEL_88;
        v67 = "125";
      }
      else
      {
        v66 = -2147209216;
        v12 = -2147209216;
        v67 = "132";
      }
      DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "EeCreateSize", v67, v66);
    }
  }
LABEL_88:
  Scratch::~Scratch((Scratch *)&v221);
  if ( v12 < 0 )
  {
    v13 = "181";
    goto LABEL_319;
  }
  v69 = *((_DWORD *)a1 + 5);
  v221 = v6;
  v222 = *((_QWORD *)v6 + 1);
  v223 = 1;
  v12 = 0;
  v70 = v69 & 0xFF0000;
  if ( v70 )
  {
    if ( v70 == 0x20000 )
    {
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0xE8u);
      v71 = SpMSRCreateSize((const struct AecBasicData_st *)v239, v73, a2, v74);
      v12 = v71;
      if ( v71 >= 0 )
        goto LABEL_96;
      v72 = "101";
    }
    else
    {
      v71 = -2147209216;
      v12 = -2147209216;
      v72 = "107";
    }
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "SpCreateSize", v72, v71);
  }
LABEL_96:
  Scratch::~Scratch((Scratch *)&v221);
  if ( v12 < 0 )
  {
    v13 = "184";
    goto LABEL_319;
  }
  v75 = *((_DWORD *)a1 + 6);
  v221 = v6;
  v222 = *((_QWORD *)v6 + 1);
  v223 = 1;
  v12 = 0;
  v76 = v75 & 0xFF0000;
  if ( v76 )
  {
    if ( v76 == 0x40000 )
    {
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x190u);
      v77 = SslXBOXCreateSize((const struct AecBasicData_st *)v239, a1, a2, v80, v79);
      v12 = v77;
      if ( v77 >= 0 )
        goto LABEL_104;
      v78 = "125";
    }
    else
    {
      v77 = -2147209216;
      v12 = -2147209216;
      v78 = "132";
    }
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "SslCreateSize", v78, v77);
  }
LABEL_104:
  Scratch::~Scratch((Scratch *)&v221);
  if ( v12 < 0 )
  {
    v13 = "187";
    goto LABEL_319;
  }
  v81 = *((_DWORD *)a1 + 2);
  v221 = v6;
  v222 = *((_QWORD *)v6 + 1);
  v223 = 0;
  v12 = 0;
  if ( (v81 & 0xFF0000) != 0 )
  {
    v12 = -2147209216;
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "EqCreateSize", "92", -2147209216);
  }
  Scratch::~Scratch((Scratch *)&v221);
  if ( v12 < 0 )
  {
    v13 = "190";
    goto LABEL_319;
  }
  v82 = *((_DWORD *)a1 + 7);
  v221 = v6;
  v222 = *((_QWORD *)v6 + 1);
  v223 = 1;
  v12 = 0;
  if ( (v82 & 0xFF0000) != 0 )
  {
    v12 = -2147209216;
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "LcCreateSize", "95", -2147209216);
  }
  Scratch::~Scratch((Scratch *)&v221);
  if ( v12 < 0 )
  {
    v13 = "193";
    goto LABEL_319;
  }
  v83 = *((_DWORD *)a1 + 4);
  v218 = v6;
  v219 = *((_QWORD *)v6 + 1);
  LODWORD(v220) = 1;
  v12 = 0;
  v84 = v83 & 0xFF0000;
  switch ( v84 )
  {
    case 0:
      goto LABEL_125;
    case 131072:
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
      v221 = v6;
      v222 = *((_QWORD *)a2 + 10);
      v223 = v88;
      v89 = DspMallocAlignedSize(4 * v217);
      *((_DWORD *)a2 + 11) = v89 + v89 + v90 + 4 * v89;
      *((_QWORD *)a2 + 10) = v91 + v89;
      goto LABEL_124;
    case 196608:
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
      v221 = v6;
      v222 = *((_QWORD *)a2 + 10);
      v223 = 0;
LABEL_124:
      Scratch::~Scratch((Scratch *)&v221);
      v12 = 0;
      goto LABEL_125;
  }
  if ( v84 != 0x80000 )
  {
    v85 = -2147209216;
    v12 = -2147209216;
    v86 = "172";
LABEL_121:
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v86, v85);
    goto LABEL_125;
  }
  *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
  v85 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v87);
  v12 = v85;
  if ( v85 < 0 )
  {
    v86 = "165";
    goto LABEL_121;
  }
LABEL_125:
  Scratch::~Scratch((Scratch *)&v218);
  if ( v12 < 0 )
  {
    v13 = "196";
    goto LABEL_319;
  }
  v92 = 0;
  while ( 1 )
  {
    v226 = v92;
    if ( v92 >= (int)v46 )
      break;
    v93 = v92;
    v94 = *((_DWORD *)a1 + v92 + 10);
    v218 = v6;
    v219 = *((_QWORD *)v6 + 1);
    LODWORD(v220) = 1;
    v12 = 0;
    v95 = v94 & 0xFF0000;
    switch ( v95 )
    {
      case 0:
        goto LABEL_140;
      case 0x20000:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
        v221 = v6;
        v222 = *((_QWORD *)a2 + 10);
        v223 = v99;
        v100 = DspMallocAlignedSize(4 * v217);
        *((_DWORD *)a2 + 11) = v100 + v100 + v100 + v100 + v100 + v101 + v100;
        *((_QWORD *)a2 + 10) = v102 + v100;
        goto LABEL_139;
      case 0x30000:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
        v221 = v6;
        v222 = *((_QWORD *)a2 + 10);
        v223 = 0;
LABEL_139:
        Scratch::~Scratch((Scratch *)&v221);
        v12 = 0;
        goto LABEL_140;
      case 0x80000:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
        v96 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v98);
        v12 = v96;
        if ( v96 >= 0 )
          goto LABEL_140;
        v97 = "165";
        break;
      default:
        v96 = -2147209216;
        v12 = -2147209216;
        v97 = "172";
        break;
    }
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v97, v96);
LABEL_140:
    Scratch::~Scratch((Scratch *)&v218);
    if ( v12 < 0 )
    {
      v13 = "202";
      goto LABEL_319;
    }
    v103 = *((_DWORD *)a1 + v93 + 26);
    v236 = v6;
    v237 = *((_QWORD *)v6 + 1);
    v238 = 1;
    v12 = 0;
    v104 = v103 & 0xFF0000;
    if ( v104 )
    {
      if ( v104 == 0x40000 )
      {
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x98u);
        v254 = v6;
        v255 = *((_QWORD *)v6 + 1);
        v256 = v105;
        v106 = DspMallocAlignedSize(8 * v217 + 16);
        *((_DWORD *)a2 + 11) += v106;
        *((_DWORD *)a2 + 11) += v233 + v233 + v233 + v106 + v106;
        Scratch::~Scratch((Scratch *)&v254);
        v12 = 0;
      }
      else
      {
        v12 = -2147209216;
        DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "CtrCreateSize", "109", -2147209216);
      }
    }
    Scratch::~Scratch((Scratch *)&v236);
    if ( v12 < 0 )
    {
      v13 = "205";
      goto LABEL_319;
    }
    v107 = *((_DWORD *)a1 + v93 + 74);
    v228 = v6;
    v229 = *((_QWORD *)v6 + 1);
    v230 = 1;
    v12 = 0;
    v108 = v107 & 0xFF0000;
    if ( (v107 & 0xFF0000) != 0 )
    {
      if ( v108 == 0x40000 )
      {
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x228u);
        v109 = EcXBOXCreateSize((const struct AecBasicData_st *)v239, a1, a2, v231, v215, v216);
        v12 = v109;
        if ( v109 >= 0 )
          goto LABEL_155;
        v110 = "116";
      }
      else if ( v108 == 458752 )
      {
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x230u);
        v109 = EcSydneyCreateSize((const struct AecBasicData_st *)v239, a1, a2, v231, v215, v111);
        v12 = v109;
        if ( v109 >= 0 )
          goto LABEL_155;
        v110 = "121";
      }
      else
      {
        v109 = -2147209216;
        v12 = -2147209216;
        v110 = "127";
      }
      DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "EcCreateSize", v110, v109);
    }
LABEL_155:
    Scratch::~Scratch((Scratch *)&v228);
    if ( v12 < 0 )
    {
      v13 = "208";
      goto LABEL_319;
    }
    v92 = v226 + 1;
    LODWORD(v46) = v224;
  }
  v112 = 0;
  if ( v227 == 1 )
  {
    while ( 1 )
    {
      if ( v112 >= v224 )
        goto LABEL_195;
      v113 = *((_DWORD *)a1 + v112 + 58);
      v236 = v6;
      v237 = *((_QWORD *)v6 + 1);
      v238 = 1;
      v12 = 0;
      v114 = v113 & 0xFF0000;
      if ( v114 )
      {
        switch ( v114 )
        {
          case 0x20000:
            *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
            v228 = v6;
            v229 = *((_QWORD *)a2 + 10);
            v230 = v118;
            v119 = DspMallocAlignedSize(4 * v217);
            *((_DWORD *)a2 + 11) = v119 + v119 + v119 + v119 + v119 + v120 + v119;
            *((_QWORD *)a2 + 10) = v121 + v119;
            goto LABEL_172;
          case 0x30000:
            *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
            v228 = v6;
            v229 = *((_QWORD *)a2 + 10);
            v230 = 0;
LABEL_172:
            Scratch::~Scratch((Scratch *)&v228);
            v12 = 0;
            goto LABEL_173;
          case 0x80000:
            *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
            v115 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v117);
            v12 = v115;
            if ( v115 >= 0 )
              goto LABEL_173;
            v116 = "165";
            break;
          default:
            v115 = -2147209216;
            v12 = -2147209216;
            v116 = "172";
            break;
        }
        DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v116, v115);
      }
LABEL_173:
      Scratch::~Scratch((Scratch *)&v236);
      if ( v12 < 0 )
      {
        v13 = "216";
        goto LABEL_319;
      }
      if ( (*((_DWORD *)a1 + v112 + 42) & 0xFF0000) != 0 )
      {
        v12 = -2147209216;
        DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "DtCreateSize", "91", -2147209216);
        v13 = "219";
        goto LABEL_319;
      }
      ++v112;
    }
  }
  while ( v112 < v225 )
  {
    v122 = *((_DWORD *)a1 + v112 + 58);
    v236 = v6;
    v237 = *((_QWORD *)v6 + 1);
    v238 = 1;
    v12 = 0;
    v123 = v122 & 0xFF0000;
    switch ( v123 )
    {
      case 0:
        goto LABEL_190;
      case 0x20000:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
        v228 = v6;
        v229 = *((_QWORD *)a2 + 10);
        v230 = v127;
        v128 = DspMallocAlignedSize(4 * v217);
        *((_DWORD *)a2 + 11) = v128 + v128 + v128 + v128 + v128 + v129 + v128;
        *((_QWORD *)a2 + 10) = v130 + v128;
        goto LABEL_189;
      case 0x30000:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
        v228 = v6;
        v229 = *((_QWORD *)a2 + 10);
        v230 = 0;
LABEL_189:
        Scratch::~Scratch((Scratch *)&v228);
        v12 = 0;
        goto LABEL_190;
      case 0x80000:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
        v124 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v126);
        v12 = v124;
        if ( v124 >= 0 )
          goto LABEL_190;
        v125 = "165";
        break;
      default:
        v124 = -2147209216;
        v12 = -2147209216;
        v125 = "172";
        break;
    }
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v125, v124);
LABEL_190:
    Scratch::~Scratch((Scratch *)&v236);
    if ( v12 < 0 )
    {
      v13 = "225";
      goto LABEL_319;
    }
    if ( (*((_DWORD *)a1 + v112 + 42) & 0xFF0000) != 0 )
    {
      v12 = -2147209216;
      DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "DtCreateSize", "91", -2147209216);
      v13 = "228";
      goto LABEL_319;
    }
    ++v112;
  }
LABEL_195:
  v131 = *((_DWORD *)a1 + 8);
  v228 = v6;
  v229 = *((_QWORD *)v6 + 1);
  v230 = 1;
  v12 = 0;
  v132 = v131 & 0xFF0000;
  if ( v132 )
  {
    switch ( v132 )
    {
      case 131072:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0xD0u);
        v136 = BfMSRCreateSize((const struct AecBasicData_st *)v239, a1, a2, v138, v137);
        v12 = v136;
        if ( v136 < 0 )
        {
          v134 = "144";
          goto LABEL_205;
        }
        break;
      case 196608:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x70u);
        v12 = 0;
        break;
      case 458752:
        *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x118u);
        v136 = BfSydneyCreateSize((const struct AecBasicData_st *)v239, a1, a2, v135, v215);
        v12 = v136;
        if ( v136 < 0 )
        {
          v134 = "150";
LABEL_205:
          v133 = v136;
LABEL_206:
          DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "BfCreateSize", v134, v133);
        }
        break;
      default:
        v12 = -2147209216;
        v133 = -2147209216;
        v134 = "157";
        goto LABEL_206;
    }
  }
  Scratch::~Scratch((Scratch *)&v228);
  if ( v12 < 0 )
  {
    v13 = "235";
    goto LABEL_319;
  }
  v139 = *((_DWORD *)a1 + 135);
  v228 = v6;
  v229 = *((_QWORD *)v6 + 1);
  v230 = 1;
  v12 = 0;
  v140 = v139 & 0xFF0000;
  if ( v140 )
  {
    if ( v140 != 589824 )
    {
      v12 = -2147209216;
      v141 = -2147209216;
      v142 = "110";
      goto LABEL_214;
    }
    *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
    v145 = DereverbMASCreateSize((const struct AecBasicData_st *)v239, v143, a2, v144);
    v12 = v145;
    if ( v145 < 0 )
    {
      v141 = v145;
      v142 = "103";
LABEL_214:
      DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "DereverbCreateSize", v142, v141);
    }
  }
  Scratch::~Scratch((Scratch *)&v228);
  if ( v12 < 0 )
  {
    v13 = "240";
    goto LABEL_319;
  }
  v146 = 0;
  while ( 2 )
  {
    v227 = v146;
    if ( v146 < v232 )
    {
      v147 = v146;
      v148 = *((_DWORD *)a1 + v146 + 90);
      v221 = v6;
      v222 = *((_QWORD *)v6 + 1);
      v223 = 1;
      v12 = 0;
      v149 = v148 & 0xFF0000;
      switch ( v149 )
      {
        case 0:
          goto LABEL_228;
        case 131072:
          *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0xA0u);
          v254 = v6;
          v255 = *((_QWORD *)v6 + 1);
          v256 = v153;
          *((_QWORD *)a2 + 10) += (int)DspMallocAlignedSize(4 * v217);
          v151 = (Scratch *)&v254;
          break;
        case 393216:
          *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x70u);
          v236 = v6;
          v237 = *((_QWORD *)v6 + 1);
          v238 = v152;
          v151 = (Scratch *)&v236;
          break;
        case 458752:
          *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0xF0u);
          v228 = v6;
          v229 = *((_QWORD *)v6 + 1);
          v230 = v150;
          *((_QWORD *)a2 + 10) += (int)DspMallocAlignedSize(4 * v217);
          v151 = (Scratch *)&v228;
          break;
        default:
          v12 = -2147209216;
          DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "SfCreateSize", "140", -2147209216);
          goto LABEL_228;
      }
      Scratch::~Scratch(v151);
      v12 = 0;
LABEL_228:
      Scratch::~Scratch((Scratch *)&v221);
      if ( v12 < 0 )
      {
        v13 = "245";
        goto LABEL_319;
      }
      v154 = *((_DWORD *)a1 + v147 + 95);
      v260[0] = v6;
      v260[1] = *((_QWORD *)v6 + 1);
      v261 = 1;
      v12 = 0;
      v155 = v154 & 0xFF0000;
      switch ( v155 )
      {
        case 0:
          goto LABEL_240;
        case 0x20000:
          *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
          v218 = v6;
          v219 = *((_QWORD *)a2 + 10);
          LODWORD(v220) = v159;
          v160 = DspMallocAlignedSize(4 * v217);
          *((_DWORD *)a2 + 11) = v160 + v160 + v160 + v160 + v160 + v161 + v160;
          *((_QWORD *)a2 + 10) = v162 + v160;
          break;
        case 0x30000:
          *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
          v218 = v6;
          v219 = *((_QWORD *)a2 + 10);
          LODWORD(v220) = 0;
          break;
        case 0x80000:
          *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
          v156 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v158);
          v12 = v156;
          if ( v156 < 0 )
          {
            v157 = "165";
LABEL_236:
            DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v157, v156);
          }
LABEL_240:
          Scratch::~Scratch((Scratch *)v260);
          if ( v12 < 0 )
          {
            v13 = "248";
            goto LABEL_319;
          }
          v163 = *((_DWORD *)a1 + v147 + 105);
          v262[0] = v6;
          v262[1] = *((_QWORD *)v6 + 1);
          v263 = 1;
          v12 = 0;
          v164 = v163 & 0xFF0000;
          switch ( v164 )
          {
            case 0:
              goto LABEL_252;
            case 0x20000:
              *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
              v218 = v6;
              v219 = *((_QWORD *)a2 + 10);
              LODWORD(v220) = v168;
              v169 = DspMallocAlignedSize(4 * v217);
              *((_DWORD *)a2 + 11) = v169 + v169 + v169 + v169 + v169 + v170 + v169;
              *((_QWORD *)a2 + 10) = v171 + v169;
              break;
            case 0x30000:
              *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
              v218 = v6;
              v219 = *((_QWORD *)a2 + 10);
              LODWORD(v220) = 0;
              break;
            case 0x80000:
              *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
              v165 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v167);
              v12 = v165;
              if ( v165 < 0 )
              {
                v166 = "165";
LABEL_248:
                DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v166, v165);
              }
LABEL_252:
              Scratch::~Scratch((Scratch *)v262);
              if ( v12 < 0 )
              {
                v13 = "251";
                goto LABEL_319;
              }
              v172 = *((_DWORD *)a1 + v147 + 100);
              v264[0] = v6;
              v264[1] = *((_QWORD *)v6 + 1);
              v265 = 1;
              v12 = 0;
              v173 = v172 & 0xFF0000;
              if ( v173 )
              {
                if ( v173 != 0x40000 )
                {
                  v174 = -2147209216;
                  v12 = -2147209216;
                  v175 = "112";
                  goto LABEL_258;
                }
                *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x108u);
                v174 = EsXBOXCreateSize((const struct AecBasicData_st *)v239, a1, a2, v176, v215);
                v12 = v174;
                if ( v174 < 0 )
                {
                  v175 = "105";
LABEL_258:
                  DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "EsCreateSize", v175, v174);
                }
              }
              Scratch::~Scratch((Scratch *)v264);
              if ( v12 < 0 )
              {
                v13 = "254";
                goto LABEL_319;
              }
              v177 = *((_DWORD *)a1 + v147 + 125);
              v266[0] = v6;
              v266[1] = *((_QWORD *)v6 + 1);
              v267 = 1;
              v12 = 0;
              v178 = v177 & 0xFF0000;
              switch ( v178 )
              {
                case 0:
                  goto LABEL_271;
                case 0x20000:
                  *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
                  v218 = v6;
                  v219 = *((_QWORD *)a2 + 10);
                  LODWORD(v220) = v182;
                  v183 = DspMallocAlignedSize(4 * v217);
                  *((_DWORD *)a2 + 11) = v183 + v183 + v183 + v183 + v183 + v184 + v183;
                  *((_QWORD *)a2 + 10) = v185 + v183;
                  break;
                case 0x30000:
                  *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
                  v218 = v6;
                  v219 = *((_QWORD *)a2 + 10);
                  LODWORD(v220) = 0;
                  break;
                case 0x80000:
                  *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
                  v179 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v181);
                  v12 = v179;
                  if ( v179 < 0 )
                  {
                    v180 = "165";
LABEL_267:
                    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v180, v179);
                  }
LABEL_271:
                  Scratch::~Scratch((Scratch *)v266);
                  if ( v12 < 0 )
                  {
                    v13 = "257";
                    goto LABEL_319;
                  }
                  v186 = *((_DWORD *)a1 + v147 + 110);
                  v272[0] = v6;
                  v272[1] = *((_QWORD *)v6 + 1);
                  v273 = 1;
                  v12 = 0;
                  v187 = v186 & 0xFF0000;
                  if ( v187 )
                  {
                    if ( v187 == 0x20000 )
                    {
                      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x98u);
                      v270[0] = v6;
                      v270[1] = *((_QWORD *)v6 + 1);
                      v271 = v191;
                      v192 = DspMallocAlignedSize(4 * v217);
                      *((_DWORD *)a2 + 11) += v192;
                      *((_DWORD *)a2 + 11) += v192;
                      *((_QWORD *)a2 + 10) += v192;
                      v190 = (Scratch *)v270;
                    }
                    else
                    {
                      if ( v187 != 0x80000 )
                      {
                        v12 = -2147209216;
                        DumpTraceWin32(
                          "Function %s(%s) : *** TRACE *** code = 0x%x!\n",
                          "NsCreateSize",
                          "133",
                          -2147209216);
                        goto LABEL_279;
                      }
                      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
                      v268[0] = v6;
                      v268[1] = *((_QWORD *)v6 + 1);
                      v269 = v188;
                      v189 = DspMallocAlignedSize(4 * v217);
                      *((_DWORD *)a2 + 11) += v189;
                      *((_DWORD *)a2 + 11) += v189 + v189;
                      *((_QWORD *)a2 + 10) += v189;
                      v190 = (Scratch *)v268;
                    }
                    Scratch::~Scratch(v190);
                    v12 = 0;
                  }
LABEL_279:
                  Scratch::~Scratch((Scratch *)v272);
                  if ( v12 < 0 )
                  {
                    v13 = "260";
                    goto LABEL_319;
                  }
                  v193 = *((_DWORD *)a1 + v147 + 115);
                  v276[0] = v6;
                  v276[1] = *((_QWORD *)v6 + 1);
                  v277 = 1;
                  v12 = 0;
                  v194 = v193 & 0xFF0000;
                  if ( v194 )
                  {
                    if ( v194 == 196608 )
                    {
                      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x88u);
                      v274[0] = v6;
                      v274[1] = *((_QWORD *)v6 + 1);
                      v275 = v195;
                      Scratch::~Scratch((Scratch *)v274);
                      v12 = 0;
                    }
                    else
                    {
                      v12 = -2147209216;
                      DumpTraceWin32(
                        "Function %s(%s) : *** TRACE *** code = 0x%x!\n",
                        "VsCreateSize",
                        "113",
                        -2147209216);
                    }
                  }
                  Scratch::~Scratch((Scratch *)v276);
                  if ( v12 < 0 )
                  {
                    v13 = "263";
                    goto LABEL_319;
                  }
                  v196 = *((_DWORD *)a1 + v147 + 120);
                  v278[0] = v6;
                  v278[1] = *((_QWORD *)v6 + 1);
                  v279 = 0;
                  v12 = 0;
                  if ( (v196 & 0xFF0000) != 0 )
                  {
                    v12 = -2147209216;
                    DumpTraceWin32(
                      "Function %s(%s) : *** TRACE *** code = 0x%x!\n",
                      "PostEqCreateSize",
                      "93",
                      -2147209216);
                  }
                  Scratch::~Scratch((Scratch *)v278);
                  if ( v12 < 0 )
                  {
                    v13 = "266";
                    goto LABEL_319;
                  }
                  v197 = *((_DWORD *)a1 + v147 + 130);
                  v251 = v6;
                  v252 = *((_QWORD *)v6 + 1);
                  v253 = 1;
                  v12 = 0;
                  v198 = v197 & 0xFF0000;
                  if ( v198 )
                  {
                    if ( v198 == 0x20000 )
                    {
                      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x160u);
                      v257 = v6;
                      v258 = *((_QWORD *)v6 + 1);
                      v259 = v199;
                      v200 = *((float *)a1 + 409) / v8;
                      v201 = v200;
                      if ( v200 < 0.0 )
                        v202 = v201 - 0.5;
                      else
                        v202 = v201 + 0.5;
                      v203 = DspMallocAlignedSize(4 * (int)v202);
                      *((_DWORD *)a2 + 11) += v203;
                      *((_DWORD *)a2 + 11) += v203 + v203;
                      Scratch::~Scratch((Scratch *)&v257);
                      v12 = 0;
                    }
                    else
                    {
                      v12 = -2147209216;
                      DumpTraceWin32(
                        "Function %s(%s) : *** TRACE *** code = 0x%x!\n",
                        "GcCreateSize",
                        "109",
                        -2147209216);
                    }
                  }
                  Scratch::~Scratch((Scratch *)&v251);
                  if ( v12 < 0 )
                  {
                    v13 = "269";
                    goto LABEL_319;
                  }
                  v146 = v227 + 1;
                  continue;
                default:
                  v179 = -2147209216;
                  v12 = -2147209216;
                  v180 = "172";
                  goto LABEL_267;
              }
              Scratch::~Scratch((Scratch *)&v218);
              v12 = 0;
              goto LABEL_271;
            default:
              v165 = -2147209216;
              v12 = -2147209216;
              v166 = "172";
              goto LABEL_248;
          }
          Scratch::~Scratch((Scratch *)&v218);
          v12 = 0;
          goto LABEL_252;
        default:
          v156 = -2147209216;
          v12 = -2147209216;
          v157 = "172";
          goto LABEL_236;
      }
      Scratch::~Scratch((Scratch *)&v218);
      v12 = 0;
      goto LABEL_240;
    }
    break;
  }
  v204 = *((_DWORD *)a1 + 136);
  v257 = v6;
  v258 = *((_QWORD *)v6 + 1);
  v259 = 1;
  v12 = 0;
  v205 = v204 & 0xFF0000;
  switch ( v205 )
  {
    case 0:
      goto LABEL_317;
    case 131072:
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x110u);
      v251 = v6;
      v252 = *((_QWORD *)a2 + 10);
      v253 = v210;
      v211 = DspMallocAlignedSize(4 * v217);
      *((_DWORD *)a2 + 11) = v211 + v211 + v212 + 4 * v211;
      *((_QWORD *)a2 + 10) = v213 + v211;
      goto LABEL_316;
    case 196608:
      *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x78u);
      v251 = v6;
      v252 = *((_QWORD *)a2 + 10);
      v253 = 0;
LABEL_316:
      Scratch::~Scratch((Scratch *)&v251);
      v12 = 0;
      goto LABEL_317;
  }
  if ( v205 != 0x80000 )
  {
    v12 = -2147209216;
    v206 = -2147209216;
    v207 = "172";
    goto LABEL_313;
  }
  *((_DWORD *)a2 + 11) += DspMallocAlignedSize(0x148u);
  v209 = VadIMCRACreateSize((const struct DspStreamParamStruct *)v239, a2, v208);
  v12 = v209;
  if ( v209 < 0 )
  {
    v206 = v209;
    v207 = "165";
LABEL_313:
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "VadCreateSize", v207, v206);
  }
LABEL_317:
  Scratch::~Scratch((Scratch *)&v257);
  if ( v12 < 0 )
  {
    v13 = "272";
LABEL_319:
    v14 = v12;
LABEL_320:
    DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "AecInternalInitSize", v13, v14);
  }
  Scratch::~Scratch((Scratch *)v280);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18020da88  mov     rax, rsp
0x18020da8b  mov     [rax+20h], rbx
0x18020da8f  push    rbp
0x18020da90  push    rsi
0x18020da91  push    rdi
0x18020da92  push    r12
0x18020da94  push    r13
0x18020da96  push    r14
0x18020da98  push    r15
0x18020da9a  lea     rbp, [rax-1D8h]
0x18020daa1  sub     rsp, 2A0h
0x18020daa8  movaps  xmmword ptr [rax-48h], xmm6
0x18020daac  movaps  xmmword ptr [rax-58h], xmm7
0x18020dab0  movaps  xmmword ptr [rax-68h], xmm8
0x18020dab5  movaps  xmmword ptr [rax-78h], xmm9
0x18020daba  mov     rsi, r8
0x18020dabd  mov     [rbp+1D0h+var_230], r8
0x18020dac1  mov     rdi, rdx
0x18020dac4  mov     r13, rcx
0x18020dac7  lea     r15, [rdx+48h]
0x18020dacb  mov     [rbp+1D0h+var_88], r15
0x18020dad2  mov     rax, [r15+8]
0x18020dad6  mov     [rbp+1D0h+var_80], rax
0x18020dadd  mov     [rbp+1D0h+var_78], 1
0x18020dae7  mov     ebx, [r8+4]
0x18020daeb  mov     [rsp+2D0h+var_264], ebx
0x18020daef  xor     edx, edx; Val
0x18020daf1  lea     r8d, [rdx+4Ch]; Size
0x18020daf5  lea     rcx, [rbp+1D0h+var_210]; void *
0x18020daf9  call    memset_0
0x18020dafe  mov     r9d, [rsi]
0x18020db01  mov     [rsp+2D0h+var_268], r9d
0x18020db06  mov     [rbp+1D0h+var_1CC], r9d
0x18020db0a  mov     [rbp+1D0h+var_1D0], ebx
0x18020db0d  mov     ebx, [rsi+8]
0x18020db10  mov     [rbp+1D0h+var_23C], ebx
0x18020db13  mov     [rbp+1D0h+var_1C8], ebx
0x18020db16  mov     r10d, [rsi+0Ch]
0x18020db1a  mov     [rbp+1D0h+var_234], r10d
0x18020db1e  mov     [rbp+1D0h+var_200], r10d
0x18020db22  mov     ecx, [rsi+1Ch]
0x18020db25  mov     [rbp+1D0h+var_1D8], ecx
0x18020db28  mov     r8d, [rsi+20h]
0x18020db2c  mov     [rbp+1D0h+var_1D4], r8d
0x18020db30  mov     r11d, [rsi+14h]
0x18020db34  mov     [rbp+1D0h+var_238], r11d
0x18020db38  imul    eax, r11d, 3E8h
0x18020db3f  cdq
0x18020db40  idiv    r10d
0x18020db43  mov     [rbp+1D0h+var_210], eax
0x18020db46  mov     [rbp+1D0h+var_20C], r11d
0x18020db4a  mov     edx, [rsi+10h]
0x18020db4d  mov     dword ptr [rsp+2D0h+var_260], edx
0x18020db51  mov     [rbp+1D0h+var_208], edx
0x18020db54  movd    xmm2, r10d
0x18020db59  cvtdq2ps xmm2, xmm2
0x18020db5c  movd    xmm0, edx
0x18020db60  cvtdq2ps xmm0, xmm0
0x18020db63  mulss   xmm0, cs:__real@447a0000
0x18020db6b  divss   xmm0, xmm2
0x18020db6f  cvttss2si eax, xmm0
0x18020db73  mov     [rbp+1D0h+var_204], eax
0x18020db76  mov     [rbp+1D0h+var_1FC], r11d
0x18020db7a  movd    xmm9, r11d
0x18020db7f  cvtdq2ps xmm9, xmm9
0x18020db83  divss   xmm9, xmm2
0x18020db88  movss   [rbp+1D0h+var_1F8], xmm9
0x18020db8e  movss   xmm0, dword ptr [rsi+18h]
0x18020db93  movss   [rbp+1D0h+var_1F4], xmm0
0x18020db98  mulss   xmm0, xmm2
0x18020db9c  divss   xmm0, cs:__real@447a0000
0x18020dba4  cvttss2si eax, xmm0
0x18020dba8  mov     [rbp+1D0h+var_1F0], eax
0x18020dbab  mov     eax, edx
0x18020dbad  cdq
0x18020dbae  mov     r10d, 2
0x18020dbb4  idiv    r10d
0x18020dbb7  mov     [rbp+1D0h+var_1EC], eax
0x18020dbba  add     eax, eax
0x18020dbbc  movd    xmm0, eax
0x18020dbc0  cvtdq2ps xmm0, xmm0
0x18020dbc3  divss   xmm2, xmm0
0x18020dbc7  movss   [rbp+1D0h+var_1DC], xmm2
0x18020dbcc  movd    xmm0, ecx
0x18020dbd0  cvtdq2ps xmm0, xmm0
0x18020dbd3  divss   xmm0, xmm2
0x18020dbd7  cvttss2si rdx, xmm0
0x18020dbdc  mov     ecx, edx
0x18020dbde  and     ecx, 0FFFFFFFCh
0x18020dbe1  mov     [rbp+1D0h+var_1E0], ecx
0x18020dbe4  movd    xmm0, r8d
0x18020dbe9  cvtdq2ps xmm0, xmm0
0x18020dbec  divss   xmm0, xmm2
0x18020dbf0  movss   xmm6, cs:__real@3f000000
0x18020dbf8  addss   xmm0, xmm6
0x18020dbfc  cvttss2si rax, xmm0
0x18020dc01  sub     eax, ecx
0x18020dc03  add     edx, 3
0x18020dc06  add     eax, edx
0x18020dc08  cdq
0x18020dc09  lea     ecx, [r10+2]
0x18020dc0d  idiv    ecx
0x18020dc0f  shl     eax, 2
0x18020dc12  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x18020dc16  mov     [rbp+1D0h+var_1E8], eax
0x18020dc19  xor     esi, esi
0x18020dc1b  mov     r14d, 2FFh
0x18020dc21  mov     r12d, esi
0x18020dc24  test    dword ptr [r13+0Ch], 0FF0000h
0x18020dc2c  jz      loc_18020DCFE
0x18020dc32  cmp     r12d, r9d
0x18020dc35  jge     short loc_18020DC8A
0x18020dc37  mov     r8d, r14d; int
0x18020dc3a  mov     rdx, rdi; struct _DspMemory *
0x18020dc3d  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dc41  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dc46  mov     ebx, eax
0x18020dc48  test    eax, eax
0x18020dc4a  js      short loc_18020DC81
0x18020dc4c  mov     r8d, r14d; int
0x18020dc4f  mov     rdx, rdi; struct _DspMemory *
0x18020dc52  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dc56  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dc5b  mov     ebx, eax
0x18020dc5d  test    eax, eax
0x18020dc5f  js      short loc_18020DC6B
0x18020dc61  inc     r12d
0x18020dc64  mov     r9d, [rsp+2D0h+var_268]
0x18020dc69  jmp     short loc_18020DC32
0x18020dc6b  lea     r8, a94; "94"
0x18020dc72  mov     r9d, eax
0x18020dc75  lea     rcx, aFunctionSSTrac_0; "Function %s(%s) : *** TRACE *** code = "...
0x18020dc7c  jmp     loc_18020F51A
0x18020dc81  lea     r8, a93; "93"
0x18020dc88  jmp     short loc_18020DC72
0x18020dc8a  mov     r12d, esi
0x18020dc8d  cmp     r12d, [rsp+2D0h+var_264]
0x18020dc92  jge     short loc_18020DCBA
0x18020dc94  mov     r8d, 1; int
0x18020dc9a  mov     rdx, rdi; struct _DspMemory *
0x18020dc9d  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dca1  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dca6  mov     ebx, eax
0x18020dca8  test    eax, eax
0x18020dcaa  js      short loc_18020DCB1
0x18020dcac  inc     r12d
0x18020dcaf  jmp     short loc_18020DC8D
0x18020dcb1  lea     r8, a98; "98"
0x18020dcb8  jmp     short loc_18020DC72
0x18020dcba  mov     dword ptr [rsp+2D0h+var_260+4], 1
0x18020dcc2  mov     [rbp+1D0h+var_240], 1
0x18020dcc9  mov     r12d, esi
0x18020dccc  mov     ebx, [rbp+1D0h+var_23C]
0x18020dccf  cmp     r12d, ebx
0x18020dcd2  jge     loc_18020DD9E
0x18020dcd8  mov     r8d, r14d; int
0x18020dcdb  mov     rdx, rdi; struct _DspMemory *
0x18020dcde  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dce2  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dce7  mov     ebx, eax
0x18020dce9  test    eax, eax
0x18020dceb  js      short loc_18020DCF2
0x18020dced  inc     r12d
0x18020dcf0  jmp     short loc_18020DCCC
0x18020dcf2  lea     r8, a102; "102"
0x18020dcf9  jmp     loc_18020DC72
0x18020dcfe  cmp     r12d, r9d
0x18020dd01  jge     short loc_18020DD2E
0x18020dd03  mov     r8d, r14d; int
0x18020dd06  mov     rdx, rdi; struct _DspMemory *
0x18020dd09  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dd0d  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dd12  mov     ebx, eax
0x18020dd14  test    eax, eax
0x18020dd16  js      short loc_18020DD22
0x18020dd18  inc     r12d
0x18020dd1b  mov     r9d, [rsp+2D0h+var_268]
0x18020dd20  jmp     short loc_18020DCFE
0x18020dd22  lea     r8, a107; "107"
0x18020dd29  jmp     loc_18020DC72
0x18020dd2e  mov     r12d, esi
0x18020dd31  cmp     r12d, [rsp+2D0h+var_264]
0x18020dd36  jge     short loc_18020DD5E
0x18020dd38  mov     r8d, r14d; int
0x18020dd3b  mov     rdx, rdi; struct _DspMemory *
0x18020dd3e  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dd42  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dd47  mov     ebx, eax
0x18020dd49  test    eax, eax
0x18020dd4b  js      short loc_18020DD52
0x18020dd4d  inc     r12d
0x18020dd50  jmp     short loc_18020DD31
0x18020dd52  lea     r8, a111; "111"
0x18020dd59  jmp     loc_18020DC72
0x18020dd5e  mov     r12d, esi
0x18020dd61  mov     ebx, [rbp+1D0h+var_23C]
0x18020dd64  cmp     r12d, ebx
0x18020dd67  jge     short loc_18020DD8F
0x18020dd69  mov     r8d, r14d; int
0x18020dd6c  mov     rdx, rdi; struct _DspMemory *
0x18020dd6f  lea     rcx, [rbp+1D0h+var_210]; struct DspStreamParamStruct *
0x18020dd73  call    ?DspStreamCreateSize@@YAHPEBUDspStreamParamStruct@@PEAU_DspMemory@@H@Z; DspStreamCreateSize(DspStreamParamStruct const *,_DspMemory *,int)
0x18020dd78  mov     ebx, eax
0x18020dd7a  test    eax, eax
0x18020dd7c  js      short loc_18020DD83
0x18020dd7e  inc     r12d
0x18020dd81  jmp     short loc_18020DD61
0x18020dd83  lea     r8, a115; "115"
0x18020dd8a  jmp     loc_18020DC72
0x18020dd8f  mov     dword ptr [rsp+2D0h+var_260+4], esi
0x18020dd93  mov     r12d, [rsp+2D0h+var_264]
0x18020dd98  mov     [rbp+1D0h+var_240], r12d
0x18020dd9c  jmp     short loc_18020DDA3
0x18020dd9e  mov     r12d, [rsp+2D0h+var_264]
0x18020dda3  mov     r9d, esi
0x18020dda6  mov     r11d, [rbp+1D0h+var_238]
0x18020ddaa  lea     eax, ds:10h[r11*4]
0x18020ddb2  mov     edx, esi
0x18020ddb4  test    ebx, ebx
0x18020ddb6  jle     short loc_18020DDCE
0x18020ddb8  movsxd  rcx, eax; unsigned __int64
0x18020ddbb  call    ?DspMallocAlignedSize@@YAH_K@Z; DspMallocAlignedSize(unsigned __int64)
0x18020ddc0  mov     ecx, [rdi+2Ch]
0x18020ddc3  add     ecx, eax
0x18020ddc5  inc     edx
0x18020ddc7  cmp     edx, ebx
0x18020ddc9  jl      short loc_18020DDC3
0x18020ddcb  mov     [rdi+2Ch], ecx
0x18020ddce  mov     edx, esi
0x18020ddd0  mov     rax, [rbp+1D0h+var_230]
0x18020ddd4  cmp     [rax+8], esi
0x18020ddd7  jle     short loc_18020DDFE
0x18020ddd9  mov     r15, rax
0x18020dddc  mov     eax, edx
0x18020ddde  mov     ecx, [r13+rax*4+3D4h]
0x18020dde6  inc     ecx
0x18020dde8  cmp     r9d, ecx
0x18020ddeb  cmovg   ecx, r9d
0x18020ddef  mov     r9d, ecx
0x18020ddf2  inc     edx
0x18020ddf4  cmp     edx, [r15+8]
0x18020ddf8  jl      short loc_18020DDDC
0x18020ddfa  lea     r15, [rdi+48h]
0x18020ddfe  mov     ebx, esi
0x18020de00  test    r9d, r9d
0x18020de03  jle     short loc_18020DE76
0x18020de05  mov     r8d, [rdi+2Ch]
0x18020de09  mov     r15, [rbp+1D0h+var_230]
0x18020de0d  mov     r14d, esi
0x18020de10  mov     eax, esi
0x18020de12  mov     r10d, esi
0x18020de15  cmp     [r15+8], esi
0x18020de19  jle     short loc_18020DE55
0x18020de1b  mov     ecx, r10d
0x18020de1e  cmp     [r13+rcx*4+3D4h], ebx
0x18020de26  jnz     short loc_18020DE4C
0x18020de28  inc     r14d
0x18020de2b  mov     ecx, [r13+rcx*4+3E8h]
0x18020de33  cmp     ecx, 0FFFFFFFFh
0x18020de36  jz      short loc_18020DE49
0x18020de38  mov     eax, [r15+0Ch]
0x18020de3c  cdq
0x18020de3d  idiv    ecx
0x18020de3f  mov     ecx, eax
0x18020de41  mov     eax, r11d
0x18020de44  cdq
0x18020de45  idiv    ecx
0x18020de47  jmp     short loc_18020DE4C
0x18020de49  mov     eax, r11d
0x18020de4c  inc     r10d
0x18020de4f  cmp     r10d, [r15+8]
0x18020de53  jl      short loc_18020DE1B
0x18020de55  imul    eax, r14d
0x18020de59  shl     eax, 2
0x18020de5c  movsxd  rcx, eax; unsigned __int64
0x18020de5f  call    ?DspMallocAlignedSize@@YAH_K@Z; DspMallocAlignedSize(unsigned __int64)
0x18020de64  add     r8d, eax
0x18020de67  mov     [rdi+2Ch], r8d
0x18020de6b  inc     ebx
0x18020de6d  cmp     ebx, r9d
0x18020de70  jl      short loc_18020DE0D
0x18020de72  lea     r15, [rdi+48h]
0x18020de76  mov     r9d, esi
0x18020de79  mov     r8d, [rdi+2Ch]
0x18020de7d  xorps   xmm8, xmm8
0x18020de81  movsd   xmm7, cs:__real@3fe0000000000000
0x18020de89  mov     r10d, [rbp+1D0h+var_234]
0x18020de8d  mov     ebx, dword ptr [rsp+2D0h+var_260]
0x18020de91  test    r12d, r12d
0x18020de94  jle     short loc_18020DEE9
0x18020de96  mov     eax, r10d
0x18020de99  cdq
0x18020de9a  idiv    r11d
0x18020de9d  movd    xmm0, eax
0x18020dea1  cvtdq2ps xmm0, xmm0
0x18020dea4  mulss   xmm0, cs:__real@3fa00000
0x18020deac  cvtps2pd xmm1, xmm0
0x18020deaf  mov     ecx, r11d
0x18020deb2  comiss  xmm0, xmm8
0x18020deb6  jb      short loc_18020DEBE
  ... truncated ...
```
