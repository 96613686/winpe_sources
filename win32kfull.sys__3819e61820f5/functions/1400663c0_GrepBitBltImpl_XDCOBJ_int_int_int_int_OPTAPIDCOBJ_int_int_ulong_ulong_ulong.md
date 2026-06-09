# GrepBitBltImpl(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,ulong,ulong,ulong)

- ea: `0x1400663c0`
- end: `0x140068764`
- name: `?GrepBitBltImpl@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHKKK@Z`
- size: `9124`
- prototype: `__int64 __fastcall(struct XDCOBJ *, int, int, int, int, struct OPTAPIDCOBJ *, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400646b4`
- `0x140080850`
- `0x14019ef40`

## callees

- `0x14005db18`
- `0x14005def4`
- `0x140063ee0`
- `0x140064ba0`
- `0x1400661bc`
- `0x1400663c0`
- `0x14006876c`
- `0x140068f04`
- `0x14006a090`
- `0x14006ba5c`
- `0x14006d5e4`
- `0x1400704e0`
- `0x1400797f8`
- `0x14007aed0`
- `0x14007ba10`
- `0x14007bb1c`
- `0x14007bc10`
- `0x140135050`
- `0x140251428`
- `0x140261a04`
- `0x140302ddc`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400669c1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400669c1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140066a75`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140066e3d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140066f2d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400673dc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006768e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140066a75`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140066e3d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140066f2d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400673dc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006768e`
- `win32kbase!HmgPentryFromPobj` at `0x1400669e8`
- `win32kbase!HmgPentryFromPobj` at `0x1400669e8`
- `win32kbase!PopThreadGuardedObject` at `0x140066971`
- `win32kbase!PopThreadGuardedObject` at `0x14006698a`
- `win32kbase!PopThreadGuardedObject` at `0x140066f9c`
- `win32kbase!PopThreadGuardedObject` at `0x140066971`
- `win32kbase!PopThreadGuardedObject` at `0x14006698a`
- `win32kbase!PopThreadGuardedObject` at `0x140066f9c`
- `win32kbase!PushThreadGuardedObject` at `0x1400664e0`
- `win32kbase!PushThreadGuardedObject` at `0x140066506`
- `win32kbase!PushThreadGuardedObject` at `0x1400664e0`
- `win32kbase!PushThreadGuardedObject` at `0x140066506`
- `win32kbase!FreeThreadBufferWithTag` at `0x140066f8c`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400673b2`
- `win32kbase!FreeThreadBufferWithTag` at `0x140066f8c`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400673b2`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140067754`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140067781`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140067754`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140067781`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140067744`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140067771`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140067744`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140067771`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006780b`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006782b`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006780b`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006782b`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1400677fb`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006781b`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1400677fb`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006781b`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400677a6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400677a6`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140067454`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140067454`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400677c1`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400677c1`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400677d9`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400677d9`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140066e5a`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140066e5a`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140066f39`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140066a1e`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140066a1e`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140066a06`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140066a06`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006872b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006872b`
- `win32kbase!EngSetLastError` at `0x140067859`
- `win32kbase!EngSetLastError` at `0x140067859`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140066583`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x1400665a0`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140066583`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x1400665a0`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140067912`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140067912`
- `win32kbase!GreDCSelectBrush` at `0x1400678ab`
- `win32kbase!GreDCSelectBrush` at `0x1400678ab`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x14006694e`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140067bdc`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x14006694e`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140067bdc`
- `win32kbase!?bEqualExceptTranslations@EXFORMOBJ@@QEBA_NPEBUMATRIX@@@Z` at `0x1400665c5`
- `win32kbase!?bEqualExceptTranslations@EXFORMOBJ@@QEBA_NPEBUMATRIX@@@Z` at `0x1400665c5`
- `win32kbase!EtwWindowRendering` at `0x140067b17`
- `win32kbase!EtwWindowRendering` at `0x140067b17`
- `win32kbase!UserSurfaceAccessCheck` at `0x14006750b`
- `win32kbase!UserSurfaceAccessCheck` at `0x14006750b`
- `win32kbase!UserScreenAccessCheck` at `0x140066af4`
- `win32kbase!UserScreenAccessCheck` at `0x140066af4`

## pseudocode

```c
__int64 __fastcall GrepBitBltImpl(
        DC **a1,
        LONG left,
        LONG top,
        int a4,
        int a5,
        struct OPTAPIDCOBJ *a6,
        int a7,
        LONG a8,
        signed int a9,
        unsigned int a10,
        char a11)
{
  struct XDCOBJ *v11; // r10
  int x; // r15d
  int v14; // r8d
  LONG y; // r12d
  struct OPTAPIDCOBJ *v17; // rcx
  char v18; // si
  unsigned int v19; // r13d
  unsigned int v20; // r13d
  __int64 v21; // r8
  int v22; // edx
  LONG v23; // r8d
  LONG v24; // edx
  int v25; // eax
  LONG right; // edx
  DC **v27; // r12
  DC *v28; // rbx
  int v29; // eax
  LONG v30; // eax
  LONG bottom; // r8d
  DC *v32; // rax
  int v33; // ecx
  DC *v34; // rcx
  DC *v35; // r8
  __int64 v36; // rbx
  __int64 v37; // r14
  __int64 v38; // r12
  unsigned __int8 v39; // cl
  Gre::Base *v40; // rcx
  DC *v41; // rcx
  DC *v42; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v45; // rdi
  unsigned int v46; // ebx
  char *v47; // r14
  struct _DC_ATTR *UserAttr; // rax
  struct Gre::Base::SESSION_GLOBALS *v49; // rax
  __int64 v50; // r10
  int v51; // eax
  int v52; // eax
  int v53; // r9d
  int v54; // r11d
  LONG v55; // r8d
  __int64 v56; // rcx
  __int64 v57; // rbx
  __int64 v58; // rax
  int v59; // edx
  int v60; // edi
  int v61; // r13d
  int v62; // ecx
  LONG v63; // edx
  LONG v64; // ecx
  int v65; // ecx
  LONG v66; // r9d
  LONG v67; // ecx
  DC **v68; // rcx
  DC *v69; // rax
  __m128i v70; // xmm2
  DC *v71; // rcx
  int v72; // r10d
  __int64 v73; // rax
  LONG v74; // r9d
  int v75; // edx
  int v76; // r8d
  LONG v77; // r11d
  int v78; // eax
  LONG v79; // r10d
  DC *v80; // r8
  unsigned __int64 v81; // rcx
  unsigned int v82; // edi
  __int64 v83; // rax
  int v84; // edx
  __int64 v85; // rax
  bool v86; // zf
  __int64 v87; // rdx
  __int64 v88; // rax
  Gre::Base *v89; // rcx
  int v90; // eax
  unsigned int v91; // r14d
  XLATEOBJ **v92; // r15
  unsigned int j; // r8d
  __int64 v94; // rdx
  __int64 XlateObject; // rax
  Gre::Base *v96; // rcx
  XLATEOBJ *v97; // rdi
  struct Gre::Base::SESSION_GLOBALS *v98; // r14
  unsigned int i; // r8d
  unsigned int v100; // edx
  __int64 v101; // rax
  __int64 v102; // rcx
  __int64 v103; // rdx
  int v104; // eax
  __int64 v105; // rdx
  int v106; // eax
  __int64 v107; // rdx
  __int64 v108; // rcx
  LONG v109; // r14d
  __int64 v110; // r11
  __int64 v111; // r10
  __int64 v112; // rbx
  unsigned int v113; // edx
  __int64 v114; // r13
  int v115; // ecx
  int v116; // eax
  __int64 v117; // rdx
  __int64 v118; // r12
  __int64 v119; // r14
  __int64 v120; // r15
  int v121; // r9d
  __int64 v122; // r9
  __int64 v123; // rbx
  __int64 v124; // rcx
  __int64 v125; // r8
  int v126; // r8d
  int v127; // ecx
  __int64 v128; // r10
  signed int v129; // r14d
  int v130; // r15d
  __int64 v131; // rbx
  __int64 v132; // r9
  __int64 v133; // r11
  __int64 v134; // r8
  DC *v135; // rcx
  int v136; // eax
  SURFACE *v137; // r15
  char v138; // bl
  DC *v139; // r11
  __int64 v140; // r14
  int v141; // r13d
  int v142; // eax
  int cEntries; // eax
  __int64 v144; // rax
  struct REGION *v145; // rax
  XCLIPOBJ *v146; // r10
  int (*v147)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  __int64 v148; // r11
  __int64 v149; // r10
  int v150; // r8d
  __int64 v151; // rcx
  __int64 v152; // r9
  __int64 v153; // rax
  int v154; // edx
  __int64 v155; // rax
  __int64 v156; // rdx
  char *v157; // r13
  __int64 v158; // rdx
  int v159; // ecx
  SURFOBJ *v160; // r11
  _BYTE *v161; // rdx
  unsigned int v162; // ebx
  int v163; // r10d
  int v164; // ecx
  struct _GRETHREAD *v165; // rax
  struct _GRETHREAD *v166; // rax
  struct _GRETHREAD *v167; // rax
  struct _GRETHREAD *CurrentThread; // rax
  int v169; // ebx
  int v170; // edx
  int v171; // eax
  _DWORD *v172; // rcx
  _DWORD *v173; // rcx
  struct _GRETHREAD *v174; // rax
  __m128i v175; // xmm2
  __m128i v176; // xmm0
  float v177; // xmm5_4
  int v178; // r8d
  __m128i v179; // xmm1
  unsigned int v180; // edx
  __m128i v181; // xmm3
  __int64 v182; // rax
  __int64 v183; // rax
  int v184; // r8d
  unsigned int v185; // edx
  __int64 v186; // rax
  __int64 v187; // rax
  int v188; // r8d
  unsigned int v189; // edx
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // r9
  int v193; // r8d
  unsigned int v194; // edx
  __int64 v195; // rax
  __int64 v196; // rax
  __m128i v197; // xmm0
  __m128i v198; // xmm1
  int v199; // r8d
  __m128i v200; // xmm4
  unsigned int v201; // edx
  __int64 v202; // rax
  __int64 v203; // rax
  int v204; // r8d
  unsigned int v205; // edx
  __int64 v206; // rax
  __int64 v207; // rax
  int v208; // r8d
  unsigned int v209; // edx
  __int64 v210; // rax
  __int64 v211; // rax
  int v212; // r8d
  unsigned int v213; // edx
  __int64 v214; // rax
  __int64 v215; // rax
  float v216; // xmm4_4
  float v217; // xmm6_4
  __m128i v218; // xmm0
  __m128i v219; // xmm1
  int v220; // r9d
  __m128i v221; // xmm2
  unsigned int v222; // r8d
  __m128i v223; // xmm3
  __int64 v224; // rax
  __int64 v225; // rax
  __int64 v226; // rax
  int v227; // r9d
  unsigned int v228; // r8d
  __int64 v229; // rax
  __int64 v230; // rax
  __int64 v231; // r11
  int v232; // r9d
  unsigned int v233; // r8d
  __int64 v234; // rax
  __int64 v235; // rax
  int v236; // r10d
  unsigned int v237; // r8d
  __int64 v238; // rax
  __int64 v239; // rax
  __m128i v240; // xmm0
  __m128i v241; // xmm1
  __m128i v242; // xmm2
  int v243; // r10d
  __m128i v244; // xmm3
  unsigned int v245; // r8d
  __int64 v246; // rax
  __int64 v247; // rax
  int v248; // r11d
  unsigned int v249; // r10d
  __int64 v250; // rax
  __int64 v251; // rax
  float v252; // xmm3_4
  __m128i v253; // xmm2
  __m128i v254; // xmm4
  __m128i v255; // xmm0
  __m128i v256; // xmm1
  int v257; // r9d
  __m128i v258; // xmm2
  unsigned int v259; // r8d
  __m128i v260; // xmm4
  float v261; // xmm0_4
  __int64 v262; // rax
  __int64 v263; // rax
  int v264; // r9d
  unsigned int v265; // r8d
  __int64 v266; // rax
  __int64 v267; // rax
  int v268; // r12d
  unsigned int v269; // r8d
  __int64 v270; // rax
  __int64 v271; // rax
  int v272; // r12d
  unsigned int v273; // r8d
  __int64 v274; // rax
  __int64 v275; // rax
  __m128i v276; // xmm2
  __m128i v277; // xmm4
  float v278; // xmm3_4
  __m128i v279; // xmm0
  __m128i v280; // xmm1
  int v281; // r14d
  __m128i v282; // xmm2
  unsigned int v283; // edx
  __m128i v284; // xmm4
  float v285; // xmm0_4
  __int64 v286; // rax
  __int64 v287; // rax
  int v288; // r14d
  unsigned int v289; // edx
  __int64 v290; // rax
  __int64 v291; // rax
  __int64 v292; // rcx
  int v293; // r14d
  unsigned int v294; // edx
  __int64 v295; // rax
  __int64 v296; // rax
  __int64 v297; // rcx
  int v298; // r12d
  unsigned int v299; // ecx
  __int64 v300; // rax
  __int64 v301; // rax
  RECTL *v302; // [rsp+28h] [rbp-D8h]
  int v303; // [rsp+30h] [rbp-D0h]
  unsigned int v304; // [rsp+70h] [rbp-90h]
  int v305; // [rsp+74h] [rbp-8Ch]
  int v306; // [rsp+78h] [rbp-88h]
  LONG v307; // [rsp+78h] [rbp-88h]
  LONG v309; // [rsp+88h] [rbp-78h]
  unsigned int v310; // [rsp+88h] [rbp-78h]
  int v311; // [rsp+8Ch] [rbp-74h]
  int v312; // [rsp+8Ch] [rbp-74h]
  int v313; // [rsp+90h] [rbp-70h]
  LONG v314; // [rsp+90h] [rbp-70h]
  LONG v315; // [rsp+94h] [rbp-6Ch]
  int v316; // [rsp+94h] [rbp-6Ch]
  XLATEOBJ *v317; // [rsp+98h] [rbp-68h] BYREF
  OPTAPIDCOBJ *v318; // [rsp+A0h] [rbp-60h]
  __int64 v319; // [rsp+A8h] [rbp-58h] BYREF
  LONG v320; // [rsp+B0h] [rbp-50h]
  __int64 v321; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v322; // [rsp+C0h] [rbp-40h]
  __int64 v323; // [rsp+C8h] [rbp-38h]
  __int64 v324; // [rsp+D0h] [rbp-30h]
  __int64 v325; // [rsp+D8h] [rbp-28h]
  int v326; // [rsp+E0h] [rbp-20h]
  unsigned int v327; // [rsp+E4h] [rbp-1Ch]
  unsigned int v328; // [rsp+E8h] [rbp-18h]
  char *v329; // [rsp+F0h] [rbp-10h]
  __int64 v330; // [rsp+F8h] [rbp-8h]
  __int64 v331; // [rsp+100h] [rbp+0h] BYREF
  SURFACE *v332; // [rsp+108h] [rbp+8h]
  SURFOBJ *v333; // [rsp+110h] [rbp+10h]
  DC *v334; // [rsp+120h] [rbp+20h] BYREF
  int v335; // [rsp+128h] [rbp+28h]
  __int64 v336; // [rsp+130h] [rbp+30h]
  __int64 v337; // [rsp+138h] [rbp+38h]
  _OWORD v338[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v339[2]; // [rsp+160h] [rbp+60h] BYREF
  char v340; // [rsp+180h] [rbp+80h]
  const struct MATRIX *v341; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v342[80]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v343; // [rsp+1F0h] [rbp+F0h]
  RECTL v344; // [rsp+330h] [rbp+230h] BYREF
  POINTL v345; // [rsp+340h] [rbp+240h] BYREF
  int v346; // [rsp+348h] [rbp+248h]
  int v347; // [rsp+34Ch] [rbp+24Ch]
  __m128i v348; // [rsp+350h] [rbp+250h] BYREF

  v11 = (struct XDCOBJ *)a1;
  x = a7;
  v14 = a5;
  y = a8;
  v17 = a6;
  v318 = a6;
  v306 = a4;
  if ( (a11 & 4) != 0
    && (CurrentThread = GreGetCurrentThread(), v17 = v318, a4 = v306, v14 = a5, v11 = (struct XDCOBJ *)a1, CurrentThread) )
  {
    *((_DWORD *)CurrentThread + 84) |= 8u;
    v18 = 1;
  }
  else
  {
    v18 = 0;
  }
  if ( (a9 & 0x40000000) != 0 )
  {
    v162 = GrepStretchBlt(
             v11,
             left,
             top,
             a4,
             v14,
             v17,
             a7,
             a8,
             a4,
             v14,
             a9 & 0xDFFFFFFF,
             a10,
             ((unsigned int)a9 >> 28) & 2);
    if ( v18 )
    {
      v174 = GreGetCurrentThread();
      *((_DWORD *)v174 + 84) &= ~8u;
    }
    return v162;
  }
  v19 = 0;
  v305 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)v11 + 36LL) & 0x10000) != 0 )
    goto LABEL_61;
  v20 = a9 & 0x5FFFFFFF;
  if ( ((*((_BYTE *)gajRop3 + (unsigned __int8)a9) | *((_BYTE *)gajRop3 + BYTE1(a9))) & 2) != 0
    && v20 != 16711778
    && v20 != 66 )
  {
    bSpDwmValidateSurface(v11, left, top, a4, v14);
  }
  if ( !OPTAPIDCOBJ::bValid(v318) )
  {
    v19 = 0;
    goto LABEL_61;
  }
  memset(v338, 0, sizeof(v338));
  v336 = *((_QWORD *)v318 + 2);
  v337 = 0;
  v334 = 0;
  v335 = 0;
  PushThreadGuardedObject(
    v338,
    &v334,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v339, 0, sizeof(v339));
  PushThreadGuardedObject(
    v339,
    &v334,
    UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v340 = 0;
  v334 = *(DC **)v318;
  bSpDwmValidateSurface((struct XDCOBJ *)&v334, a7, a8, v306, a5);
  v21 = *((_QWORD *)*a1 + 122);
  v22 = *(_DWORD *)(v21 + 108);
  if ( ((*(_BYTE *)(*((_QWORD *)v334 + 122) + 108LL) ^ *(_BYTE *)(v21 + 108)) & 7) != 0
    && (a9 < 0 && (v22 & 1) != 0 || (v22 & 9) == 9) )
  {
    v169 = *(_DWORD *)(v21 + 308);
    v328 = DC::dwSetLayout(*a1, -1, 0);
    left = v169 - v306 - left;
    v327 = 0x80000000;
  }
  else
  {
    v328 = 0;
    v327 = 0;
  }
  DC::QuickInitXform(*a1, &v331, 516);
  DC::QuickInitXform(v334, &v341, 516);
  if ( (*(_BYTE *)(v331 + 32) & 1) == 0 || !EXFORMOBJ::bEqualExceptTranslations((EXFORMOBJ *)&v331, v341) )
  {
    v27 = a1;
    v19 = GrepStretchBlt((struct XDCOBJ *)a1, left, top, v306, a5, v318, a7, a8, v306, a5, v20, a10, 0);
    goto LABEL_55;
  }
  v23 = a8 + a5;
  v330 = (__int64)v334;
  v24 = a7 + v306;
  v345.x = a7;
  v346 = a7 + v306;
  v345.y = a8;
  v347 = a8 + a5;
  if ( (*((_BYTE *)v341 + 32) & 0x43) == 0x43
    || (v25 = bCvtPts1(v341, &v345, 2), v23 = v347, v24 = v346, y = v345.y, x = v345.x, v25) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v330 + 976) + 108LL) & 1) != 0 )
    {
      ++x;
      ++v24;
      v345.x = x;
      v346 = v24;
    }
  }
  if ( x > v24 )
  {
    v345.x = v24;
    v346 = x;
  }
  if ( y > v23 )
  {
    v345.y = v23;
    v347 = y;
  }
  right = v306 + left;
  v27 = a1;
  v344.bottom = top + a5;
  v344.left = left;
  v344.top = top;
  v28 = *a1;
  v344.right = v306 + left;
  if ( (*(_BYTE *)(v331 + 32) & 0x43) == 0x43
    || (v29 = bCvtPts1(v331, &v344, 2), right = v344.right, top = v344.top, left = v344.left, v29) )
  {
    if ( (*(_DWORD *)(*((_QWORD *)v28 + 122) + 108LL) & 1) != 0 )
    {
      ++left;
      ++right;
      v344.left = left;
      v344.right = right;
    }
  }
  if ( left > right )
  {
    v30 = left;
    v344.left = right;
    left = right;
    v344.right = v30;
    right = v30;
  }
  bottom = v344.bottom;
  if ( top > v344.bottom )
  {
    v344.top = v344.bottom;
    v344.bottom = top;
    top = bottom;
  }
  if ( top == v344.bottom || left == right )
  {
    v19 = 1;
    goto LABEL_55;
  }
  v32 = *a1;
  v33 = *((_DWORD *)*a1 + 9);
  if ( (v33 & 0xE0) != 0 )
  {
    if ( (v33 & 0x20) != 0 )
    {
      if ( left < *((_DWORD *)v32 + 266) )
      {
        *((_DWORD *)v32 + 266) = left;
        right = v344.right;
        top = v344.top;
        left = v344.left;
      }
      if ( top < *((_DWORD *)v32 + 267) )
      {
        *((_DWORD *)v32 + 267) = top;
        right = v344.right;
        top = v344.top;
        left = v344.left;
      }
      if ( right > *((_DWORD *)v32 + 268) )
      {
        *((_DWORD *)v32 + 268) = right;
        right = v344.right;
        top = v344.top;
        left = v344.left;
      }
      if ( v344.bottom > *((_DWORD *)v32 + 269) )
      {
        *((_DWORD *)v32 + 269) = v344.bottom;
        right = v344.right;
        top = v344.top;
        left = v344.left;
      }
    }
    v34 = *a1;
    if ( (*((_DWORD *)*a1 + 9) & 0x80u) != 0 )
    {
      if ( left < *((_DWORD *)v34 + 274) )
      {
        *((_DWORD *)v34 + 274) = left;
        right = v344.right;
        top = v344.top;
      }
      if ( top < *((_DWORD *)v34 + 275) )
      {
        *((_DWORD *)v34 + 275) = top;
        right = v344.right;
      }
      if ( right > *((_DWORD *)v34 + 276) )
        *((_DWORD *)v34 + 276) = right;
      if ( v344.bottom > *((_DWORD *)v34 + 277) )
        *((_DWORD *)v34 + 277) = v344.bottom;
    }
  }
  DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(v342);
  if ( !(unsigned int)DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v342, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v334) )
  {
    v170 = XDCOBJ::bFullScreen((XDCOBJ *)a1);
    if ( !*((_QWORD *)v334 + 62) || (v171 = DC::bInFullScreen(v334)) != 0 )
      v171 = 1;
    v305 = v171 | v170;
    goto LABEL_54;
  }
  v35 = *a1;
  v36 = *((_QWORD *)*a1 + 62);
  v332 = (SURFACE *)v36;
  if ( !v36 )
  {
    v305 = 1;
    goto LABEL_54;
  }
  v37 = *((_QWORD *)v35 + 11);
  v38 = *(_QWORD *)(v36 + 176);
  v322 = v37;
  v39 = (a9 & 0x5FFFFFFFu) >> 16;
  v326 = v39 | (v39 << 8);
  if ( ((v39 ^ (unsigned __int8)(16 * v39)) & 0xF0) != 0 )
  {
    v156 = *((_QWORD *)v35 + 122);
    v157 = (char *)v35 + 1200;
    v330 = (__int64)v35 + 1200;
    if ( (*(_DWORD *)(v156 + 152) & 0x1000) != 0 )
      GreDCSelectBrush(v35, *(_QWORD *)(v156 + 160));
    v35 = *a1;
    v158 = *((_QWORD *)*a1 + 122);
    v159 = *(_DWORD *)(v158 + 152);
    if ( (v159 & 1) != 0 || (*((_DWORD *)v35 + 79) & 1) != 0 )
    {
      v303 = 1;
      *(_DWORD *)(v158 + 152) = v159 & 0xFFFFFFFE;
      HIDWORD(v302) = HIDWORD(v36);
      *((_DWORD *)*a1 + 79) &= ~1u;
      EBRUSHOBJ::vInitBrush(v157, *a1, *((_QWORD *)*a1 + 17), v37, v38);
      v35 = *a1;
    }
  }
  else
  {
    v330 = 0;
  }
  v40 = (Gre::Base *)(*((_DWORD *)v35 + 10) & 1);
  v344.left += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 254);
  v344.right += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 254);
  v344.top += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 255);
  v344.bottom += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 255);
  if ( !*((_QWORD *)v334 + 62) )
    goto LABEL_53;
  v49 = Gre::Base::Globals(v40);
  v50 = *((_QWORD *)v334 + 62);
  if ( v50 )
  {
    if ( v337 )
      v50 = v337;
  }
  else
  {
    v50 = *((_QWORD *)v49 + 547);
  }
  v323 = v50;
  if ( !v50 )
    goto LABEL_53;
  if ( (a11 & 2) != 0 )
    goto LABEL_85;
  if ( (v343 & 0x400000) == 0
    || ((*(_DWORD *)(v36 + 164) & 8) != 0 || *(_QWORD *)(v36 + 272))
    && _bittest16((const signed __int16 *)(v36 + 102), 9u) )
  {
    goto LABEL_255;
  }
  v51 = *(_DWORD *)(v36 + 160);
  if ( (v51 & 0x800) != 0 )
  {
    v52 = UserSurfaceAccessCheck(*(_QWORD *)(v36 + 696));
  }
  else
  {
    if ( (v51 & 0x10000000) == 0 )
      goto LABEL_85;
    v52 = UserScreenAccessCheck();
  }
  if ( !v52 )
  {
LABEL_255:
    EngSetLastError(6u);
    v27 = a1;
    goto LABEL_54;
  }
  v50 = v323;
LABEL_85:
  v53 = 0;
  v54 = v344.left;
  v55 = v344.top;
  v56 = *(_QWORD *)(v50 + 48);
  v57 = *(_QWORD *)(v50 + 176);
  v58 = *((_DWORD *)v334 + 10) & 1;
  v59 = 0;
  v60 = v344.top - *((_DWORD *)v334 + 2 * v58 + 255) - v345.y;
  v61 = v344.left - *((_DWORD *)v334 + 2 * v58 + 254) - v345.x;
  v313 = v60;
  v333 = (SURFOBJ *)(v50 + 24);
  if ( v56 && v50 == *(_QWORD *)(v56 + 2544) && (*(_DWORD *)(v56 + 40) & 0x20000) != 0 )
  {
    v59 = *(_DWORD *)(v56 + 2576);
    v53 = *(_DWORD *)(v56 + 2580);
  }
  if ( v59 + v61 > v344.left )
    v54 = v59 + v61;
  v344.left = v54;
  v304 = v54;
  if ( v53 + v60 > v344.top )
    v55 = v53 + v60;
  v344.top = v55;
  v62 = v59 + *(_DWORD *)(v50 + 56);
  v63 = v344.right;
  v64 = v61 + v62;
  if ( v64 < v344.right )
    v63 = v64;
  v344.right = v63;
  v65 = v53 + *(_DWORD *)(v50 + 60);
  v66 = v344.bottom;
  v67 = v60 + v65;
  if ( v67 < v344.bottom )
    v66 = v67;
  v344.bottom = v66;
  if ( v54 >= v63 || v55 >= v66 )
    goto LABEL_53;
  v68 = a1;
  v69 = *a1;
  if ( v54 < *((_DWORD *)*a1 + 250)
    || v63 > *((_DWORD *)v69 + 252)
    || v55 < *((_DWORD *)v69 + 251)
    || (v329 = 0, v66 > *((_DWORD *)v69 + 253)) )
  {
    v329 = (char *)v69 + 1768;
    v145 = XDCOBJ::prgnEffRao((XDCOBJ *)a1);
    XCLIPOBJ::vSetup(v146, v145, (const struct ERECTL *)&v344, 2);
    v70 = *(__m128i *)(v329 + 4);
    v54 = _mm_cvtsi128_si32(v70);
    v344 = (RECTL)v70;
    v304 = v54;
    v344.right = _mm_cvtsi128_si32(_mm_srli_si128(v70, 8));
    if ( v54 != v344.right && v70.m128i_i32[1] != _mm_srli_si128(v70, 8).m128i_i32[1] )
    {
      v68 = a1;
      v344.bottom = _mm_cvtsi128_si32(_mm_srli_si128(v70, 12));
      v344.top = _mm_cvtsi128_si32(_mm_srli_si128(v70, 4));
      goto LABEL_102;
    }
LABEL_53:
    v27 = a1;
    v305 = 1;
    goto LABEL_54;
  }
  v70 = (__m128i)v344;
LABEL_102:
  v71 = *v68;
  v72 = *((_DWORD *)v71 + 9);
  if ( (v72 & 0xE0) != 0 )
  {
    v348 = v70;
    v73 = *((_DWORD *)v71 + 10) & 1;
    v74 = v54 - *((_DWORD *)v71 + 2 * v73 + 254);
    v348.m128i_i32[0] = v74;
    v75 = v70.m128i_i32[2] - *((_DWORD *)v71 + 2 * v73 + 254);
    v348.m128i_i32[2] = v75;
    v76 = v70.m128i_i32[1] - *((_DWORD *)v71 + 2 * v73 + 255);
    v348.m128i_i32[1] = v76;
    v348.m128i_i32[3] = v70.m128i_i32[3] - *((_DWORD *)v71 + 2 * v73 + 255);
    if ( (v72 & 0x40) != 0 )
    {
      v77 = *((_DWORD *)v71 + 270);
      v78 = *((_DWORD *)v71 + 272);
      if ( v77 == v78 || (v79 = *((_DWORD *)v71 + 273), *((_DWORD *)v71 + 271) == v79) )
      {
        *(__m128i *)((char *)v71 + 1080) = v348;
        v54 = v344.left;
        v304 = v344.left;
      }
      else
      {
        if ( v74 < v77 )
        {
          *((_DWORD *)v71 + 270) = v74;
          v75 = v348.m128i_i32[2];
          v76 = v348.m128i_i32[1];
          v304 = v344.left;
        }
        if ( v76 < *((_DWORD *)v71 + 271) )
        {
          *((_DWORD *)v71 + 271) = v76;
          v75 = v348.m128i_i32[2];
          v304 = v344.left;
        }
        if ( v75 > v78 )
        {
          *((_DWORD *)v71 + 272) = v75;
          v304 = v344.left;
        }
        if ( v348.m128i_i32[3] <= v79 )
        {
          v54 = v304;
        }
        else
        {
          *((_DWORD *)v71 + 273) = v348.m128i_i32[3];
          v54 = v344.left;
          v304 = v344.left;
        }
      }
      v317 = (XLATEOBJ *)*((_QWORD *)*a1 + 148);
      if ( v317 )
      {
        v319 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v319, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v319);
        v321 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v321, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v321);
        if ( v319 )
        {
          if ( v321 )
          {
            RGNOBJ::vSet((RGNOBJ *)&v321, (const struct _RECTL *const)&v348);
            if ( RGNOBJ::bMerge((RGNOBJ *)&v319, (struct RGNOBJ *)&v317, (struct RGNOBJ *)&v321, 0xEu) )
            {
              RGNOBJ::vSwap((RGNOBJ *)&v317, (struct RGNOBJ *)&v319);
              *((_QWORD *)*a1 + 148) = v317;
            }
          }
        }
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v321);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v321);
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v319);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v319);
        v54 = v344.left;
        v304 = v344.left;
      }
    }
  }
  v345.x = v54 - v61;
  v309 = v54 - v61;
  v80 = *a1;
  v81 = (unsigned int)(v344.top - v60);
  v345.y = v344.top - v60;
  v315 = v344.top - v60;
  if ( v323 == *((_QWORD *)v80 + 62) )
  {
    v109 = v304;
    v97 = 0;
    v305 = 1;
    v27 = a1;
    goto LABEL_159;
  }
  v82 = a10;
  v310 = a10;
  if ( a10 == -1 )
  {
    v81 = *((_QWORD *)v334 + 122);
    v82 = *(_DWORD *)(v81 + 180);
    v310 = v82;
  }
  if ( v57 )
  {
    if ( v38 )
    {
      v83 = v57;
      if ( *(_QWORD *)(v57 + 120) != v57 )
        v83 = *(_QWORD *)(v57 + 120);
      v81 = *(_QWORD *)(v38 + 120);
      v84 = *(_DWORD *)(v83 + 32);
      v85 = v38;
      if ( v81 != v38 )
        v85 = *(_QWORD *)(v38 + 120);
      v86 = v84 == *(_DWORD *)(v85 + 32);
      goto LABEL_125;
    }
    if ( (*(_DWORD *)(v57 + 24) & 0x800) == 0 )
      goto LABEL_126;
  }
  else
  {
    if ( !v38 )
      goto LABEL_210;
    if ( (*(_DWORD *)(v38 + 24) & 0x800) == 0 )
      goto LABEL_126;
  }
  v144 = *(_QWORD *)(v37 + 80);
  if ( !v144 )
    goto LABEL_210;
  v86 = v144 == *(_QWORD *)(v37 + 72);
LABEL_125:
  if ( v86 )
  {
LABEL_210:
    v97 = (XLATEOBJ *)((char *)Gre::Base::Globals((Gre::Base *)v81) + 4664);
    goto LABEL_154;
  }
LABEL_126:
  v87 = *((unsigned int *)v80 + 30);
  LODWORD(v319) = *((_DWORD *)v80 + 30);
  v348.m128i_i64[0] = *((_QWORD *)v334 + 11);
  v88 = *((_QWORD *)v80 + 122);
  v89 = (Gre::Base *)*(unsigned int *)(v88 + 176);
  v90 = *(_DWORD *)(v88 + 184);
  v316 = v90;
  v311 = (int)v89;
  if ( !v57 || !v38 )
  {
LABEL_135:
    XlateObject = CreateXlateObject(0, v87, v57, v38, v348.m128i_i64[0], v37, v90, (_DWORD)v89, v82, 0);
    v97 = (XLATEOBJ *)XlateObject;
    if ( !XlateObject )
    {
      v108 = 0;
      goto LABEL_155;
    }
    if ( v57 && v38 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
    {
      v98 = Gre::Base::Globals(v96);
      v317 = (XLATEOBJ *)(*(_QWORD *)v98 + 312LL);
      GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
      for ( i = 0; i < 8; ++i )
      {
        v100 = *((_DWORD *)v98 + 1164);
        v101 = 32LL * v100;
        v102 = *(_QWORD *)((char *)v98 + v101 + 4408);
        if ( !v102 )
          goto LABEL_144;
        if ( !*(_DWORD *)((char *)v98 + v101 + 4400) )
        {
          FreeThreadBufferWithTag(v102);
LABEL_144:
          PopThreadGuardedObject(&v97[-2].pulXlate);
          v103 = v57;
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1100) = 1;
          *((_QWORD *)v98 + 4 * *((unsigned int *)v98 + 1164) + 551) = v97;
          if ( *(_QWORD *)(v57 + 120) != v57 )
            v103 = *(_QWORD *)(v57 + 120);
          v104 = *(_DWORD *)(v103 + 32);
          v105 = v348.m128i_i64[0];
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1104) = v104;
          if ( *(_QWORD *)(v38 + 120) != v38 )
            v38 = *(_QWORD *)(v38 + 120);
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1105) = *(_DWORD *)(v38 + 32);
          if ( *(_QWORD *)(v105 + 120) != v105 )
            v105 = *(_QWORD *)(v105 + 120);
          v106 = *(_DWORD *)(v105 + 32);
          v107 = v322;
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1106) = v106;
          if ( *(_QWORD *)(v107 + 120) != v107 )
            v107 = *(_QWORD *)(v107 + 120);
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1107) = *(_DWORD *)(v107 + 32);
          v97[1].cEntries = *((_DWORD *)v98 + 1164);
          *(_DWORD *)(v57 + 56) = *((_DWORD *)v98 + 1164);
          *((_DWORD *)v98 + 1164) = ((unsigned __int8)*((_DWORD *)v98 + 1164) + 1) & 7;
          break;
        }
        *((_DWORD *)v98 + 1164) = ((_BYTE)v100 + 1) & 7;
      }
      SEMOBJ<13>::vUnlock(&v317);
    }
LABEL_154:
    v108 = 1;
    goto LABEL_155;
  }
  v91 = *(_DWORD *)(v57 + 56);
  v92 = (XLATEOBJ **)Gre::Base::Globals(v89);
  v317 = *v92 + 13;
  GreAcquireSemaphoreInternal((HSEMAPHORE)v317);
  GrepAcquireLockValidate<13>();
  for ( j = 0; ; ++j )
  {
    if ( j >= 8 )
    {
      SEMOBJ<13>::vUnlock(&v317);
      LODWORD(v89) = v311;
      v90 = v316;
      v87 = (unsigned int)v319;
      v82 = v310;
      v37 = v322;
      goto LABEL_135;
    }
    v94 = v57;
    if ( *(_QWORD *)(v57 + 120) != v57 )
      v94 = *(_QWORD *)(v57 + 120);
    if ( LODWORD(v92[4 * v91 + 552]) != *(_DWORD *)(v94 + 32) )
      goto LABEL_133;
    v151 = v38;
    if ( *(_QWORD *)(v38 + 120) != v38 )
      v151 = *(_QWORD *)(v38 + 120);
    v152 = 4LL * v91;
    if ( HIDWORD(v92[v152 + 552]) != *(_DWORD *)(v151 + 32) )
      goto LABEL_133;
    v153 = v322;
    if ( *(_QWORD *)(v322 + 120) != v322 )
      v153 = *(_QWORD *)(v322 + 120);
    if ( HIDWORD(v92[v152 + 553]) != *(_DWORD *)(v153 + 32) )
      goto LABEL_133;
    v97 = v92[v152 + 551];
    if ( (v97[3].flXlate & 0x6000) != 0 )
      goto LABEL_133;
    v154 = v97[3].flXlate & 0x100;
    if ( (v97->flXlate & 4) != 0 )
      break;
    if ( !v154 )
      goto LABEL_243;
LABEL_241:
    if ( v316 == v97[1].flXlate && v311 == *(_DWORD *)&v97[1].iSrcType )
      goto LABEL_243;
LABEL_133:
    v91 = ((_BYTE)v91 + 1) & 7;
  }
  if ( v310 != v97[1].iUniq )
    goto LABEL_240;
  v155 = v348.m128i_i64[0];
  if ( *(_QWORD *)(v348.m128i_i64[0] + 120) != v348.m128i_i64[0] )
    v155 = *(_QWORD *)(v348.m128i_i64[0] + 120);
  if ( LODWORD(v92[v152 + 553]) != *(_DWORD *)(v155 + 32) )
  {
LABEL_240:
    if ( !v154 )
      goto LABEL_133;
    goto LABEL_241;
  }
LABEL_243:
  _InterlockedIncrement((volatile signed __int32 *)&v92[v152 + 550]);
  *(_DWORD *)(v57 + 56) = v91;
  SEMOBJ<13>::vUnlock(&v317);
  v108 = 1;
LABEL_155:
  v27 = a1;
  v305 = v108;
  v80 = *a1;
  if ( (*((_DWORD *)*a1 + 9) & 1) == 0 )
  {
    v346 = v344.right - v61;
    v347 = v344.bottom - v313;
  }
  if ( (_DWORD)v108 )
  {
    v109 = v344.left;
    v315 = v345.y;
    v309 = v345.x;
    v304 = v344.left;
LABEL_159:
    LODWORD(v110) = 0;
    LODWORD(v111) = 0;
    v314 = v344.top;
    v320 = v344.right;
    v317 = v97;
    v307 = v344.bottom;
    v325 = 0;
    v324 = 0;
    if ( *((int *)v332 + 40) < 0 )
    {
      v172 = (_DWORD *)*((_QWORD *)v332 + 6);
      if ( v172 )
      {
        if ( (v172[10] & 0x20000) != 0 )
        {
          LODWORD(v110) = v172[644];
          v111 = (unsigned int)v172[645];
          v325 = (unsigned int)v110;
          v324 = v111;
        }
      }
    }
    LODWORD(v112) = 0;
    v113 = 0;
    LODWORD(v114) = v111 + *((_DWORD *)v332 + 15);
    v322 = (unsigned int)(v110 + *((_DWORD *)v332 + 14));
    v318 = 0;
    v348.m128i_i64[0] = 0;
    if ( *(int *)(v323 + 160) < 0 )
    {
      v173 = *(_DWORD **)(v323 + 48);
      if ( v173 )
      {
        if ( (v173[10] & 0x20000) != 0 )
        {
          v113 = v173[644];
          v112 = (unsigned int)v173[645];
          v318 = (OPTAPIDCOBJ *)v113;
          v348.m128i_i64[0] = v112;
        }
      }
    }
    v115 = v113 + *(_DWORD *)(v323 + 56);
    LODWORD(v319) = v112 + *(_DWORD *)(v323 + 60);
    if ( v27 && (v116 = *((_DWORD *)v80 + 130), (v116 & 1) != 0) && (v116 & 2) == 0 )
    {
      v175 = (__m128i)LODWORD(FLOAT_1_0);
      *(float *)v175.m128i_i32 = 1.0 / *((float *)v80 + 131);
      v176 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v110);
      v177 = 1.0 / *((float *)v80 + 132);
      *(float *)v176.m128i_i32 = *(float *)v176.m128i_i32 * *(float *)v175.m128i_i32;
      v178 = _mm_cvtsi128_si32(v176);
      v179 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v111);
      v180 = (unsigned __int8)(v178 >> 23);
      v181 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v114);
      if ( v180 > 0x9E )
        goto LABEL_355;
      *(float *)v179.m128i_i32 = *(float *)v179.m128i_i32 * v177;
      v182 = v178 & 0x7FFFFF | 0x800000LL;
      if ( v180 < 0x76 )
        v183 = v182 >> (118 - (unsigned __int8)v180);
      else
        v183 = v182 << ((unsigned __int8)v180 - 118);
      v110 = (v183 + 0x80000000LL) >> 32;
      if ( v178 < 0 )
        v110 = (unsigned int)-(int)v110;
      v184 = _mm_cvtsi128_si32(v179);
      v325 = v110;
      v185 = (unsigned __int8)(v184 >> 23);
      if ( v185 > 0x9E )
        goto LABEL_355;
      v186 = v184 & 0x7FFFFF | 0x800000LL;
      if ( v185 < 0x76 )
        v187 = v186 >> (118 - (unsigned __int8)v185);
      else
        v187 = v186 << ((unsigned __int8)v185 - 118);
      v111 = (v187 + 0x80000000LL) >> 32;
      if ( v184 < 0 )
        v111 = (unsigned int)-(int)v111;
      v188 = _mm_cvtsi128_si32(v175);
      v324 = v111;
      v189 = (unsigned __int8)(v188 >> 23);
      if ( v189 > 0x9E )
        goto LABEL_355;
      *(float *)v181.m128i_i32 = *(float *)v181.m128i_i32 * v177;
      v190 = v188 & 0x7FFFFF | 0x800000LL;
      if ( v189 < 0x76 )
        v191 = v190 >> (118 - (unsigned __int8)v189);
      else
        v191 = v190 << ((unsigned __int8)v189 - 118);
      v192 = (v191 + 0x80000000LL) >> 32;
      if ( v188 < 0 )
        v192 = (unsigned int)-(int)v192;
      v193 = _mm_cvtsi128_si32(v181);
      v322 = v192;
      v194 = (unsigned __int8)(v193 >> 23);
      if ( v194 > 0x9E )
      {
LABEL_355:
        LODWORD(v114) = 0;
        LODWORD(v111) = 0;
        LODWORD(v110) = 0;
        LODWORD(v322) = 0;
        v325 = 0;
        v324 = 0;
      }
      else
      {
        v195 = v193 & 0x7FFFFF | 0x800000LL;
        if ( v194 < 0x76 )
          v196 = v195 >> (118 - (unsigned __int8)v194);
        else
          v196 = v195 << ((unsigned __int8)v194 - 118);
        v114 = (v196 + 0x80000000LL) >> 32;
        if ( v193 < 0 )
          LODWORD(v114) = -(int)v114;
      }
      v197 = (__m128i)COERCE_UNSIGNED_INT((float)v109);
      v198 = (__m128i)COERCE_UNSIGNED_INT((float)v344.top);
      *(float *)v197.m128i_i32 = *(float *)v197.m128i_i32 * *(float *)v175.m128i_i32;
      v199 = _mm_cvtsi128_si32(v197);
      v200 = (__m128i)COERCE_UNSIGNED_INT((float)v344.bottom);
      v201 = (unsigned __int8)(v199 >> 23);
      if ( v201 > 0x9E )
        goto LABEL_356;
      *(float *)v198.m128i_i32 = *(float *)v198.m128i_i32 * v177;
      v202 = v199 & 0x7FFFFF | 0x800000LL;
      if ( v201 < 0x76 )
        v203 = v202 >> (118 - (unsigned __int8)v201);
      else
        v203 = v202 << ((unsigned __int8)v201 - 118);
      v118 = (v203 + 0x80000000LL) >> 32;
      if ( v199 < 0 )
        LODWORD(v118) = -(int)v118;
      v204 = _mm_cvtsi128_si32(v198);
      v205 = (unsigned __int8)(v204 >> 23);
      if ( v205 > 0x9E )
        goto LABEL_356;
      *(float *)v175.m128i_i32 = *(float *)v175.m128i_i32 * (float)v320;
      v206 = v204 & 0x7FFFFF | 0x800000LL;
      if ( v205 < 0x76 )
        v207 = v206 >> (118 - (unsigned __int8)v205);
      else
        v207 = v206 << ((unsigned __int8)v205 - 118);
      v120 = (v207 + 0x80000000LL) >> 32;
      if ( v204 < 0 )
        LODWORD(v120) = -(int)v120;
      v208 = _mm_cvtsi128_si32(v175);
      v209 = (unsigned __int8)(v208 >> 23);
      if ( v209 > 0x9E )
        goto LABEL_356;
      *(float *)v200.m128i_i32 = *(float *)v200.m128i_i32 * v177;
      v210 = v208 & 0x7FFFFF | 0x800000LL;
      if ( v209 < 0x76 )
        v211 = v210 >> (118 - (unsigned __int8)v209);
      else
        v211 = v210 << ((unsigned __int8)v209 - 118);
      v119 = (v211 + 0x80000000LL) >> 32;
      if ( v208 < 0 )
        LODWORD(v119) = -(int)v119;
      v212 = _mm_cvtsi128_si32(v200);
      v213 = (unsigned __int8)(v212 >> 23);
      if ( v213 > 0x9E )
      {
LABEL_356:
        LODWORD(v117) = 0;
        LODWORD(v119) = 0;
        LODWORD(v120) = 0;
        LODWORD(v118) = 0;
      }
      else
      {
        v214 = v212 & 0x7FFFFF | 0x800000LL;
        if ( v213 < 0x76 )
          v215 = v214 >> (118 - (unsigned __int8)v213);
        else
          v215 = v214 << ((unsigned __int8)v213 - 118);
        v117 = (v215 + 0x80000000LL) >> 32;
        if ( v212 < 0 )
          LODWORD(v117) = -(int)v117;
      }
    }
    else
    {
      LODWORD(v117) = v344.bottom;
      LODWORD(v118) = v109;
      LODWORD(v119) = v320;
      LODWORD(v120) = v344.top;
    }
    v121 = *((_DWORD *)v334 + 130);
    LODWORD(v321) = v121;
    v312 = v121 & 1;
    if ( (v121 & 1) == 0 || (v121 & 2) != 0 )
    {
      LODWORD(v122) = v319;
      LODWORD(v123) = v115;
      LODWORD(v124) = v315;
      LODWORD(v125) = v309;
    }
    else
    {
      v216 = 1.0 / *((float *)v334 + 131);
      v217 = 1.0 / *((float *)v334 + 132);
      v218 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v318);
      *(float *)v218.m128i_i32 = *(float *)v218.m128i_i32 * v216;
      v219 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v112);
      v220 = _mm_cvtsi128_si32(v218);
      v221 = (__m128i)COERCE_UNSIGNED_INT((float)v115);
      v222 = (unsigned __int8)(v220 >> 23);
      v223 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v319);
      if ( v222 > 0x9E )
        goto LABEL_396;
      *(float *)v219.m128i_i32 = *(float *)v219.m128i_i32 * v217;
      v224 = v220 & 0x7FFFFF | 0x800000LL;
      if ( v222 < 0x76 )
        v225 = v224 >> (118 - (unsigned __int8)v222);
      else
        v225 = v224 << ((unsigned __int8)v222 - 118);
      v226 = (v225 + 0x80000000LL) >> 32;
      if ( v220 < 0 )
        v226 = (unsigned int)-(int)v226;
      v318 = (OPTAPIDCOBJ *)v226;
      v227 = _mm_cvtsi128_si32(v219);
      v228 = (unsigned __int8)(v227 >> 23);
      if ( v228 > 0x9E )
        goto LABEL_396;
      *(float *)v221.m128i_i32 = *(float *)v221.m128i_i32 * v216;
      v229 = v227 & 0x7FFFFF | 0x800000LL;
      if ( v228 < 0x76 )
        v230 = v229 >> (118 - (unsigned __int8)v228);
      else
        v230 = v229 << ((unsigned __int8)v228 - 118);
      v231 = (v230 + 0x80000000LL) >> 32;
      if ( v227 < 0 )
        v231 = (unsigned int)-(int)v231;
      v232 = _mm_cvtsi128_si32(v221);
      v348.m128i_i64[0] = v231;
      v233 = (unsigned __int8)(v232 >> 23);
      if ( v233 > 0x9E )
        goto LABEL_396;
      *(float *)v223.m128i_i32 = *(float *)v223.m128i_i32 * v217;
      v234 = v232 & 0x7FFFFF | 0x800000LL;
      if ( v233 < 0x76 )
        v235 = v234 >> (118 - (unsigned __int8)v233);
      else
        v235 = v234 << ((unsigned __int8)v233 - 118);
      v123 = (v235 + 0x80000000LL) >> 32;
      if ( v232 < 0 )
        LODWORD(v123) = -(int)v123;
      v236 = _mm_cvtsi128_si32(v223);
      v237 = (unsigned __int8)(v236 >> 23);
      if ( v237 > 0x9E )
      {
LABEL_396:
        LODWORD(v123) = 0;
        LODWORD(v122) = 0;
        v348.m128i_i32[0] = 0;
        v318 = 0;
      }
      else
      {
        v238 = v236 & 0x7FFFFF | 0x800000LL;
        if ( v237 < 0x76 )
          v239 = v238 >> (118 - (unsigned __int8)v237);
        else
          v239 = v238 << ((unsigned __int8)v237 - 118);
        v122 = (v239 + 0x80000000LL) >> 32;
        if ( v236 < 0 )
          LODWORD(v122) = -(int)v122;
      }
      v240 = (__m128i)COERCE_UNSIGNED_INT((float)v309);
      v241 = (__m128i)COERCE_UNSIGNED_INT((float)v315);
      *(float *)v240.m128i_i32 = *(float *)v240.m128i_i32 * v216;
      v242 = (__m128i)COERCE_UNSIGNED_INT((float)v346);
      v243 = _mm_cvtsi128_si32(v240);
      v244 = (__m128i)COERCE_UNSIGNED_INT((float)v347);
      v245 = (unsigned __int8)(v243 >> 23);
      if ( v245 > 0x9E )
        goto LABEL_397;
      *(float *)v241.m128i_i32 = *(float *)v241.m128i_i32 * v217;
      v246 = v243 & 0x7FFFFF | 0x800000LL;
      if ( v245 < 0x76 )
        v247 = v246 >> (118 - (unsigned __int8)v245);
      else
        v247 = v246 << ((unsigned __int8)v245 - 118);
      v125 = (v247 + 0x80000000LL) >> 32;
      if ( v243 < 0 )
        LODWORD(v125) = -(int)v125;
      v248 = _mm_cvtsi128_si32(v241);
      v249 = (unsigned __int8)(v248 >> 23);
      if ( v249 > 0x9E )
        goto LABEL_397;
      *(float *)v242.m128i_i32 = *(float *)v242.m128i_i32 * v216;
      v250 = v248 & 0x7FFFFF | 0x800000LL;
      if ( v249 < 0x76 )
        v251 = v250 >> (118 - (unsigned __int8)v249);
      else
        v251 = v250 << ((unsigned __int8)v249 - 118);
      v124 = (v251 + 0x80000000LL) >> 32;
      if ( v248 < 0 )
        LODWORD(v124) = -(int)v124;
      if ( (unsigned __int8)(_mm_cvtsi128_si32(v242) >> 23) > 0x9Eu
        || (*(float *)v244.m128i_i32 = *(float *)v244.m128i_i32 * v217,
            (unsigned __int8)(_mm_cvtsi128_si32(v244) >> 23) > 0x9Eu) )
      {
LABEL_397:
        LODWORD(v110) = v325;
        LODWORD(v124) = 0;
        LODWORD(v111) = v324;
        LODWORD(v125) = 0;
      }
      else
      {
        LODWORD(v110) = v325;
        LODWORD(v111) = v324;
      }
    }
    v126 = v125 - v118;
    v127 = v124 - v120;
    if ( (int)v110 > (int)v118 )
      LODWORD(v118) = v110;
    if ( (int)v111 > (int)v120 )
      LODWORD(v120) = v111;
    if ( (int)v322 < (int)v119 )
      LODWORD(v119) = v322;
    if ( (int)v114 < (int)v117 )
      LODWORD(v117) = v114;
    if ( (int)v119 < (int)v118 )
    {
      LODWORD(v118) = v119;
    }
    else if ( (int)v117 < (int)v120 )
    {
      LODWORD(v120) = v117;
    }
    LODWORD(v128) = v126 + v118;
    v129 = v126 + v119;
    v130 = v127 + v120;
    LODWORD(v117) = v127 + v117;
    if ( (int)v318 > v126 + (int)v118 )
      LODWORD(v128) = (_DWORD)v318;
    if ( v348.m128i_i32[0] > v130 )
      v130 = v348.m128i_i32[0];
    if ( (int)v123 < v129 )
      v129 = v123;
    if ( (int)v122 < (int)v117 )
      LODWORD(v117) = v122;
    if ( v129 < (int)v128 )
    {
      LODWORD(v128) = v129;
    }
    else if ( (int)v117 < v130 )
    {
      v130 = v117;
    }
    LODWORD(v131) = v128 - v126;
    LODWORD(v132) = v129 - v126;
    if ( (int)v128 - v126 >= v129 - v126
      || (LODWORD(v133) = v130 - v127, LODWORD(v134) = v117 - v127, v130 - v127 >= (int)v117 - v127) )
    {
      v137 = v332;
      v138 = 0;
    }
    else
    {
      if ( a1 )
      {
        v135 = *a1;
        v136 = *((_DWORD *)*a1 + 130);
        if ( (v136 & 1) != 0 && (v136 & 2) == 0 )
        {
          v252 = *((float *)v135 + 131);
          v253 = _mm_cvtsi32_si128(v132);
          v254 = _mm_cvtsi32_si128(v134);
          v255 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v131);
          *(float *)v255.m128i_i32 = *(float *)v255.m128i_i32 * v252;
          v256 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v133);
          v257 = _mm_cvtsi128_si32(v255);
          v258 = (__m128i)_mm_cvtepi32_ps(v253);
          v259 = (unsigned __int8)(v257 >> 23);
          v260 = (__m128i)_mm_cvtepi32_ps(v254);
          if ( v259 > 0x9E )
            goto LABEL_422;
          v261 = *((float *)v135 + 132);
          *(float *)v256.m128i_i32 = *(float *)v256.m128i_i32 * v261;
          v262 = v257 & 0x7FFFFF | 0x800000LL;
          if ( v259 < 0x76 )
            v263 = v262 >> (118 - (unsigned __int8)v259);
          else
            v263 = v262 << ((unsigned __int8)v259 - 118);
          v131 = (v263 + 0x80000000LL) >> 32;
          if ( v257 < 0 )
            LODWORD(v131) = -(int)v131;
          v264 = _mm_cvtsi128_si32(v256);
          v265 = (unsigned __int8)(v264 >> 23);
          if ( v265 > 0x9E )
            goto LABEL_422;
          *(float *)v258.m128i_i32 = *(float *)v258.m128i_i32 * v252;
          v266 = v264 & 0x7FFFFF | 0x800000LL;
          if ( v265 < 0x76 )
            v267 = v266 >> (118 - (unsigned __int8)v265);
          else
            v267 = v266 << ((unsigned __int8)v265 - 118);
          v133 = (v267 + 0x80000000LL) >> 32;
          if ( v264 < 0 )
            LODWORD(v133) = -(int)v133;
          v268 = _mm_cvtsi128_si32(v258);
          v269 = (unsigned __int8)(v268 >> 23);
          if ( v269 > 0x9E )
            goto LABEL_422;
          *(float *)v260.m128i_i32 = *(float *)v260.m128i_i32 * v261;
          v270 = v268 & 0x7FFFFF | 0x800000LL;
          if ( v269 < 0x76 )
            v271 = v270 >> (118 - (unsigned __int8)v269);
          else
            v271 = v270 << ((unsigned __int8)v269 - 118);
          v132 = (v271 + 0x80000000LL) >> 32;
          if ( v268 < 0 )
            LODWORD(v132) = -(int)v132;
          v272 = _mm_cvtsi128_si32(v260);
          v273 = (unsigned __int8)(v272 >> 23);
          if ( v273 > 0x9E )
          {
LABEL_422:
            LODWORD(v134) = 0;
            LODWORD(v132) = 0;
            LODWORD(v133) = 0;
            LODWORD(v131) = 0;
          }
          else
          {
            v274 = v272 & 0x7FFFFF | 0x800000LL;
            if ( v273 < 0x76 )
              v275 = v274 >> (118 - (unsigned __int8)v273);
            else
              v275 = v274 << ((unsigned __int8)v273 - 118);
            v134 = (v275 + 0x80000000LL) >> 32;
            if ( v272 < 0 )
              LODWORD(v134) = -(int)v134;
          }
        }
      }
      if ( v312 && (v321 & 2) == 0 )
      {
        v276 = _mm_cvtsi32_si128(v129);
        v277 = _mm_cvtsi32_si128(v117);
        v278 = *((float *)v334 + 131);
        v279 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v128);
        *(float *)v279.m128i_i32 = *(float *)v279.m128i_i32 * v278;
        v280 = (__m128i)COERCE_UNSIGNED_INT((float)v130);
        v281 = _mm_cvtsi128_si32(v279);
        v282 = (__m128i)_mm_cvtepi32_ps(v276);
        v283 = (unsigned __int8)(v281 >> 23);
        v284 = (__m128i)_mm_cvtepi32_ps(v277);
        if ( v283 > 0x9E )
          goto LABEL_447;
        v285 = *((float *)v334 + 132);
        *(float *)v280.m128i_i32 = *(float *)v280.m128i_i32 * v285;
        v286 = v281 & 0x7FFFFF | 0x800000LL;
        if ( v283 < 0x76 )
          v287 = v286 >> (118 - (unsigned __int8)v283);
        else
          v287 = v286 << ((unsigned __int8)v283 - 118);
        v128 = (v287 + 0x80000000LL) >> 32;
        if ( v281 < 0 )
          LODWORD(v128) = -(int)v128;
        v288 = _mm_cvtsi128_si32(v280);
        v289 = (unsigned __int8)(v288 >> 23);
        if ( v289 > 0x9E )
          goto LABEL_447;
        *(float *)v282.m128i_i32 = *(float *)v282.m128i_i32 * v278;
        v290 = v288 & 0x7FFFFF | 0x800000LL;
        if ( v289 < 0x76 )
          v291 = v290 >> (118 - (unsigned __int8)v289);
        else
          v291 = v290 << ((unsigned __int8)v289 - 118);
        v292 = (v291 + 0x80000000LL) >> 32;
        if ( v288 < 0 )
          LODWORD(v292) = -(int)v292;
        v293 = _mm_cvtsi128_si32(v282);
        v130 = v292;
        v294 = (unsigned __int8)(v293 >> 23);
        if ( v294 > 0x9E )
          goto LABEL_447;
        *(float *)v284.m128i_i32 = *(float *)v284.m128i_i32 * v285;
        v295 = v293 & 0x7FFFFF | 0x800000LL;
        if ( v294 < 0x76 )
          v296 = v295 >> (118 - (unsigned __int8)v294);
        else
          v296 = v295 << ((unsigned __int8)v294 - 118);
        v297 = (v296 + 0x80000000LL) >> 32;
        if ( v293 < 0 )
          LODWORD(v297) = -(int)v297;
        v298 = _mm_cvtsi128_si32(v284);
        v129 = v297;
        v299 = (unsigned __int8)(v298 >> 23);
        if ( v299 > 0x9E )
        {
LABEL_447:
          LODWORD(v117) = 0;
          v129 = 0;
          v130 = 0;
          LODWORD(v128) = 0;
        }
        else
        {
          v300 = v298 & 0x7FFFFF | 0x800000LL;
          if ( v299 < 0x76 )
            v301 = v300 >> (118 - (unsigned __int8)v299);
          else
            v301 = v300 << ((unsigned __int8)v299 - 118);
          v117 = (v301 + 0x80000000LL) >> 32;
          if ( v298 < 0 )
            LODWORD(v117) = -(int)v117;
        }
      }
      v345.y = v130;
      v137 = v332;
      v344.left = v131;
      v138 = 1;
      v345.x = v128;
      v346 = v129;
      v347 = v117;
      v344.top = v133;
      v344.right = v132;
      v344.bottom = v134;
      ++*((_DWORD *)v332 + 23);
    }
    v27 = a1;
    v139 = *a1;
    v108 = *((_QWORD *)v334 + 6);
    if ( *((_QWORD *)*a1 + 6) == v108 )
      goto LABEL_195;
    if ( (unsigned int)XDCOBJ::bRedirHooked((XDCOBJ *)a1) )
    {
      v139 = *a1;
      v108 = *((_QWORD *)v334 + 6);
      if ( *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) == v108 )
        goto LABEL_195;
    }
    if ( *(_WORD *)(v323 + 100) )
      goto LABEL_269;
    v160 = (SURFOBJ *)(v323 + 24);
    if ( *(_QWORD *)(v323 + 24) )
    {
LABEL_270:
      if ( v138 )
      {
        v161 = v342;
        if ( (*(_DWORD *)(*((_QWORD *)v137 + 6) + 40LL) & 0x80u) == 0 )
          v161 = 0;
        v305 = SimBitBlt(
                 (SURFOBJ *)((char *)v137 + 24),
                 v160,
                 v317,
                 &v344,
                 &v345,
                 0,
                 v330,
                 (POINTL *)*a1 + 149,
                 v326,
                 (__int64)v161);
      }
    }
    else
    {
      v139 = *a1;
      v108 = *(unsigned int *)(*((_QWORD *)*a1 + 6) + 40LL);
      if ( (v108 & 0x80u) != 0LL )
      {
LABEL_269:
        v160 = v333;
        goto LABEL_270;
      }
LABEL_195:
      if ( v326 == 52428 )
      {
        v140 = *((_QWORD *)v137 + 6);
        v141 = a11 & 1;
        if ( v141 )
        {
          v163 = v314 - v307;
          if ( v314 - v307 < 0 )
            v163 = v307 - v314;
          v164 = v307 - v320;
          if ( v307 - v320 < 0 )
            v164 = v320 - v307;
          LODWORD(v302) = v320;
          EtwWindowRendering(
            *((_QWORD *)v139 + 58),
            *((_QWORD *)v139 + 59),
            **((_QWORD **)v139 + 62),
            v304,
            v314,
            v302,
            v307,
            *((_QWORD *)v334 + 58),
            *((_QWORD *)v334 + 59),
            **((_QWORD **)v334 + 62),
            v309,
            v315,
            v309 + v164,
            v315 + v163);
          *((_WORD *)v137 + 51) |= 0x40u;
          v165 = GreGetCurrentThread();
          if ( v165 )
            *((_DWORD *)v165 + 84) &= ~1u;
          GreClientRgnUpdated(0);
          GreClientRgnUpdatedStable();
        }
        if ( v138 )
        {
          if ( (*((_DWORD *)v137 + 40) & 0x400) != 0 )
            v142 = (*(__int64 (__fastcall **)(__int64, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *, int))(v140 + 2832))(
                     (__int64)v137 + 24,
                     v333,
                     v329,
                     v317,
                     &v344,
                     &v345,
                     v303);
          else
            v142 = ((__int64 (__fastcall *)(char *, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *, int))EngCopyBits)(
                     (char *)v137 + 24,
                     v333,
                     v329,
                     v317,
                     &v344,
                     &v345,
                     v303);
          v305 = v142;
        }
        if ( v141 )
        {
          *((_WORD *)v137 + 51) &= ~0x40u;
          v166 = GreGetCurrentThread();
          if ( v166 )
            *((_DWORD *)v166 + 84) |= 1u;
        }
      }
      else if ( v138 )
      {
        v147 = SURFACE::pfnBitBlt(v137);
        v305 = ((__int64 (__fastcall *)(char *, __int64, _QWORD, char *, XLATEOBJ *, RECTL *, POINTL *, _QWORD, __int64, __int64, int))v147)(
                 (char *)v137 + 24,
                 v149 + 24,
                 0,
                 v329,
                 v317,
                 &v344,
                 &v345,
                 0,
                 v330,
                 v148 + 1192,
                 v150);
      }
    }
  }
  if ( v97 )
  {
    cEntries = v97[1].cEntries;
    if ( cEntries >= 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)Gre::Base::Globals((Gre::Base *)v108) + 8 * (int)v97[1].cEntries
                                                                                             + 1100);
    }
    else if ( cEntries == -1 )
    {
      FreeThreadBufferWithTag(v97);
    }
  }
LABEL_54:
  DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v342);
  v19 = v305;
LABEL_55:
  if ( v327 )
    DC::dwSetLayout(*v27, -1, v328);
  v41 = v334;
  if ( !v340 )
    v41 = 0;
  v334 = v41;
  PopThreadGuardedObject(v339);
  v42 = v334;
  if ( v334 )
  {
    if ( v335 && (*((_DWORD *)v334 + 11) & 2) != 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v45 = v334;
      v46 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v334 )
      {
        v47 = (char *)HmgPentryFromPobj(v336, v334);
      }
      else
      {
        v47 = (char *)v334 + 2152;
        *(_OWORD *)((char *)v334 + 2152) = 0;
        *((_QWORD *)v45 + 271) = 0;
        *((_DWORD *)v45 + 540) = -2147483630;
        *((_QWORD *)v45 + 271) = GreEncodeUserModePointer(0);
      }
      if ( v46 == (*((_DWORD *)v47 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v334);
        if ( UserAttr )
          DC::RestoreAttributes(v334, UserAttr);
      }
      *((_DWORD *)v334 + 11) &= ~2u;
      v42 = v334;
      v335 = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)v42 + 6);
    v334 = 0;
  }
  PopThreadGuardedObject(v338);
LABEL_61:
  if ( v18 )
  {
    v167 = GreGetCurrentThread();
    *((_DWORD *)v167 + 84) &= ~8u;
  }
  return v19;
}

```

## disassembly

```asm
0x1400663c0  push    rbp
0x1400663c2  push    rbx
0x1400663c3  push    rsi
0x1400663c4  push    rdi
0x1400663c5  push    r12
0x1400663c7  push    r14
0x1400663c9  push    r15
0x1400663cb  lea     rbp, [rsp-290h]
0x1400663d3  sub     rsp, 390h
0x1400663da  mov     rax, cs:__security_cookie
0x1400663e1  xor     rax, rsp
0x1400663e4  mov     [rbp+2C0h+var_60], rax
0x1400663eb  test    byte ptr [rbp+2C0h+arg_50], 4
0x1400663f2  mov     r10, rcx
0x1400663f5  mov     r15d, [rbp+2C0h+arg_30]
0x1400663fc  mov     r14d, r8d
0x1400663ff  mov     r8d, [rbp+2C0h+arg_20]
0x140066406  mov     edi, edx
0x140066408  mov     r12d, [rbp+2C0h+arg_38]
0x14006640f  mov     ebx, [rbp+2C0h+arg_40]
0x140066415  mov     [rbp+2C0h+var_340], rcx
0x140066419  mov     rcx, [rbp+2C0h+arg_28]
0x140066420  mov     [rbp+2C0h+var_320], rcx
0x140066424  mov     [rsp+3C0h+var_348], r9d
0x140066429  mov     [rsp+3C0h+var_350], r8d
0x14006642e  jnz     loc_140067B87
0x140066434  xor     sil, sil
0x140066437  mov     eax, ebx
0x140066439  btr     ebx, 1Dh
0x14006643d  shr     eax, 1Ch
0x140066440  and     eax, 2
0x140066443  bt      ebx, 1Eh
0x140066447  jb      loc_140067A2A
0x14006644d  mov     rax, [r10]
0x140066450  mov     [rsp+3C0h+var_38], r13
0x140066458  xor     r13d, r13d
0x14006645b  mov     [rsp+3C0h+var_34C], r13d
0x140066460  test    dword ptr [rax+24h], 10000h
0x140066467  jnz     loc_140066996
0x14006646d  mov     eax, ebx
0x14006646f  lea     r11, gajRop3
0x140066476  btr     eax, 1Fh
0x14006647a  mov     r13d, eax
0x14006647d  shr     rax, 8
0x140066481  movzx   edx, al
0x140066484  movzx   eax, r13b
0x140066488  movzx   ecx, byte ptr [rax+r11]
0x14006648d  movzx   eax, byte ptr [rdx+r11]
0x140066492  or      al, cl
0x140066494  test    al, 2
0x140066496  jnz     loc_140067705
0x14006649c  mov     rcx, [rbp+2C0h+var_320]; this
0x1400664a0  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x1400664a5  test    al, al
0x1400664a7  jz      loc_140067C53
0x1400664ad  mov     rax, [rbp+2C0h+var_320]
0x1400664b1  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400664b8  xorps   xmm0, xmm0
0x1400664bb  lea     rdx, [rbp+2C0h+var_2A0]
0x1400664bf  lea     rcx, [rbp+2C0h+var_280]
0x1400664c3  movups  [rbp+2C0h+var_280], xmm0
0x1400664c7  mov     rax, [rax+10h]
0x1400664cb  mov     [rbp+2C0h+var_290], rax
0x1400664cf  xor     eax, eax
0x1400664d1  mov     [rbp+2C0h+var_288], rax
0x1400664d5  mov     [rbp+2C0h+var_2A0], rax
0x1400664d9  mov     [rbp+2C0h+var_298], eax
0x1400664dc  movups  [rbp+2C0h+var_270], xmm0
0x1400664e0  call    cs:__imp_PushThreadGuardedObject
0x1400664e7  nop     dword ptr [rax+rax+00h]
0x1400664ec  xorps   xmm0, xmm0
0x1400664ef  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400664f6  lea     rdx, [rbp+2C0h+var_2A0]
0x1400664fa  lea     rcx, [rbp+2C0h+var_260]
0x1400664fe  movups  [rbp+2C0h+var_260], xmm0
0x140066502  movups  [rbp+2C0h+var_250], xmm0
0x140066506  call    cs:__imp_PushThreadGuardedObject
0x14006650d  nop     dword ptr [rax+rax+00h]
0x140066512  mov     rax, [rbp+2C0h+var_320]
0x140066516  lea     rcx, [rbp+2C0h+var_2A0]; struct XDCOBJ *
0x14006651a  mov     r9d, [rsp+3C0h+var_348]; int
0x14006651f  mov     r8d, r12d; int
0x140066522  mov     edx, r15d; int
0x140066525  mov     [rbp+2C0h+var_240], 0
0x14006652c  mov     rax, [rax]
0x14006652f  mov     [rbp+2C0h+var_2A0], rax
0x140066533  mov     eax, [rsp+3C0h+var_350]
0x140066537  mov     dword ptr [rsp+3C0h+var_3A0], eax; int
0x14006653b  call    ?bSpDwmValidateSurface@@YAHAEAVXDCOBJ@@HHHH@Z; bSpDwmValidateSurface(XDCOBJ &,int,int,int,int)
0x140066540  mov     rax, [rbp+2C0h+var_340]
0x140066544  mov     r9, [rax]
0x140066547  mov     rax, [rbp+2C0h+var_2A0]
0x14006654b  mov     r8, [r9+3D0h]
0x140066552  mov     rcx, [rax+3D0h]
0x140066559  mov     edx, [r8+6Ch]
0x14006655d  mov     eax, edx
0x14006655f  xor     eax, [rcx+6Ch]
0x140066562  test    al, 7
0x140066564  jnz     loc_140067BB6
0x14006656a  xor     ebx, ebx
0x14006656c  mov     [rbp+2C0h+var_2D8], ebx
0x14006656f  mov     [rbp+2C0h+var_2DC], ebx
0x140066572  mov     rax, [rbp+2C0h+var_340]
0x140066576  lea     rdx, [rbp+2C0h+var_2C0]
0x14006657a  mov     r8d, 204h
0x140066580  mov     rcx, [rax]
0x140066583  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14006658a  nop     dword ptr [rax+rax+00h]
0x14006658f  mov     rcx, [rbp+2C0h+var_2A0]
0x140066593  lea     rdx, [rbp+2C0h+var_230]
0x14006659a  mov     r8d, 204h
0x1400665a0  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x1400665a7  nop     dword ptr [rax+rax+00h]
0x1400665ac  mov     rax, [rbp+2C0h+var_2C0]
0x1400665b0  test    byte ptr [rax+20h], 1
0x1400665b4  jz      loc_1400676AF
0x1400665ba  mov     rdx, [rbp+2C0h+var_230]
0x1400665c1  lea     rcx, [rbp+2C0h+var_2C0]
0x1400665c5  call    cs:__imp_?bEqualExceptTranslations@EXFORMOBJ@@QEBA_NPEBUMATRIX@@@Z; EXFORMOBJ::bEqualExceptTranslations(MATRIX const *)
0x1400665cc  nop     dword ptr [rax+rax+00h]
0x1400665d1  test    al, al
0x1400665d3  jz      loc_1400676AF
0x1400665d9  mov     rax, [rbp+2C0h+var_2A0]
0x1400665dd  mov     ebx, [rsp+3C0h+var_348]
0x1400665e1  mov     r8d, [rsp+3C0h+var_350]
0x1400665e6  mov     rcx, [rbp+2C0h+var_230]
0x1400665ed  add     r8d, r12d
0x1400665f0  mov     [rbp+2C0h+var_2C8], rax
0x1400665f4  lea     edx, [r15+rbx]
0x1400665f8  mov     [rbp+2C0h+var_80.x], r15d
0x1400665ff  mov     [rbp+2C0h+var_78], edx
0x140066605  mov     [rbp+2C0h+var_80.y], r12d
0x14006660c  mov     [rbp+2C0h+var_74], r8d
0x140066613  mov     eax, [rcx+20h]
0x140066616  and     eax, 43h
0x140066619  cmp     al, 43h ; 'C'
0x14006661b  jz      short loc_14006664E
0x14006661d  mov     r8d, 2
0x140066623  lea     rdx, [rbp+2C0h+var_80]
0x14006662a  call    bCvtPts1
0x14006662f  mov     r8d, [rbp+2C0h+var_74]
0x140066636  mov     edx, [rbp+2C0h+var_78]
0x14006663c  mov     r12d, [rbp+2C0h+var_80.y]
0x140066643  mov     r15d, [rbp+2C0h+var_80.x]
0x14006664a  test    eax, eax
0x14006664c  jz      short loc_140066665
0x14006664e  mov     rax, [rbp+2C0h+var_2C8]
0x140066652  mov     rax, [rax+3D0h]
0x140066659  mov     ecx, [rax+6Ch]
0x14006665c  test    cl, 1
0x14006665f  jnz     loc_140066A49
0x140066665  cmp     r15d, edx
0x140066668  jle     short loc_140066677
0x14006666a  mov     [rbp+2C0h+var_80.x], edx
0x140066670  mov     [rbp+2C0h+var_78], r15d
0x140066677  cmp     r12d, r8d
0x14006667a  jle     short loc_14006668A
0x14006667c  mov     [rbp+2C0h+var_80.y], r8d
0x140066683  mov     [rbp+2C0h+var_74], r12d
0x14006668a  mov     eax, [rsp+3C0h+var_350]
0x14006668e  lea     edx, [rbx+rdi]
0x140066691  mov     rcx, [rbp+2C0h+var_2C0]
0x140066695  add     eax, r14d
0x140066698  mov     r12, [rbp+2C0h+var_340]
0x14006669c  mov     [rbp+2C0h+var_90.bottom], eax
0x1400666a2  mov     [rbp+2C0h+var_90.left], edi
0x1400666a8  mov     [rbp+2C0h+var_90.top], r14d
0x1400666af  mov     rbx, [r12]
0x1400666b3  mov     [rbp+2C0h+var_90.right], edx
0x1400666b9  mov     eax, [rcx+20h]
0x1400666bc  and     eax, 43h
0x1400666bf  cmp     al, 43h ; 'C'
0x1400666c1  jz      short loc_1400666EC
0x1400666c3  mov     r8d, 2
0x1400666c9  lea     rdx, [rbp+2C0h+var_90]
0x1400666d0  call    bCvtPts1
0x1400666d5  mov     edx, [rbp+2C0h+var_90.right]
0x1400666db  mov     r14d, [rbp+2C0h+var_90.top]
0x1400666e2  mov     edi, [rbp+2C0h+var_90.left]
0x1400666e8  test    eax, eax
0x1400666ea  jz      short loc_1400666FF
0x1400666ec  mov     rax, [rbx+3D0h]
0x1400666f3  mov     ecx, [rax+6Ch]
0x1400666f6  test    cl, 1
0x1400666f9  jnz     loc_140066A60
0x1400666ff  cmp     edi, edx
0x140066701  jle     short loc_140066715
0x140066703  mov     eax, edi
0x140066705  mov     [rbp+2C0h+var_90.left], edx
0x14006670b  mov     edi, edx
0x14006670d  mov     [rbp+2C0h+var_90.right], eax
0x140066713  mov     edx, eax
0x140066715  mov     r8d, [rbp+2C0h+var_90.bottom]
0x14006671c  cmp     r14d, r8d
0x14006671f  jle     short loc_140066734
0x140066721  mov     eax, r14d
0x140066724  mov     [rbp+2C0h+var_90.top], r8d
0x14006672b  mov     [rbp+2C0h+var_90.bottom], eax
0x140066731  mov     r14d, r8d
0x140066734  cmp     r14d, [rbp+2C0h+var_90.bottom]
0x14006673b  jz      loc_1400674F7
0x140066741  cmp     edi, edx
0x140066743  jz      loc_1400674F7
0x140066749  mov     rax, [r12]
0x14006674d  mov     ecx, [rax+24h]
0x140066750  test    cl, 0E0h
0x140066753  jz      loc_140066852
0x140066759  test    cl, 20h
0x14006675c  jz      loc_1400667F1
0x140066762  cmp     edi, [rax+428h]
0x140066768  jge     short loc_140066783
0x14006676a  mov     [rax+428h], edi
0x140066770  mov     edx, [rbp+2C0h+var_90.right]
0x140066776  mov     r14d, [rbp+2C0h+var_90.top]
0x14006677d  mov     edi, [rbp+2C0h+var_90.left]
0x140066783  cmp     r14d, [rax+42Ch]
0x14006678a  jge     short loc_1400667A6
0x14006678c  mov     [rax+42Ch], r14d
0x140066793  mov     edx, [rbp+2C0h+var_90.right]
0x140066799  mov     r14d, [rbp+2C0h+var_90.top]
0x1400667a0  mov     edi, [rbp+2C0h+var_90.left]
0x1400667a6  cmp     edx, [rax+430h]
0x1400667ac  jle     short loc_1400667C7
0x1400667ae  mov     [rax+430h], edx
0x1400667b4  mov     edx, [rbp+2C0h+var_90.right]
0x1400667ba  mov     r14d, [rbp+2C0h+var_90.top]
0x1400667c1  mov     edi, [rbp+2C0h+var_90.left]
0x1400667c7  mov     r8d, [rbp+2C0h+var_90.bottom]
0x1400667ce  cmp     r8d, [rax+434h]
0x1400667d5  jle     short loc_1400667F1
0x1400667d7  mov     [rax+434h], r8d
0x1400667de  mov     edx, [rbp+2C0h+var_90.right]
0x1400667e4  mov     r14d, [rbp+2C0h+var_90.top]
0x1400667eb  mov     edi, [rbp+2C0h+var_90.left]
0x1400667f1  mov     rcx, [r12]
0x1400667f5  mov     eax, [rcx+24h]
0x1400667f8  test    al, al
0x1400667fa  jns     short loc_140066852
0x1400667fc  cmp     edi, [rcx+448h]
0x140066802  jge     short loc_140066817
0x140066804  mov     [rcx+448h], edi
0x14006680a  mov     edx, [rbp+2C0h+var_90.right]
0x140066810  mov     r14d, [rbp+2C0h+var_90.top]
0x140066817  cmp     r14d, [rcx+44Ch]
0x14006681e  jge     short loc_14006682D
0x140066820  mov     [rcx+44Ch], r14d
0x140066827  mov     edx, [rbp+2C0h+var_90.right]
0x14006682d  cmp     edx, [rcx+450h]
0x140066833  jle     short loc_14006683B
0x140066835  mov     [rcx+450h], edx
0x14006683b  mov     r8d, [rbp+2C0h+var_90.bottom]
0x140066842  cmp     r8d, [rcx+454h]
0x140066849  jle     short loc_140066852
0x14006684b  mov     [rcx+454h], r8d
0x140066852  lea     rcx, [rbp+2C0h+var_220]
0x140066859  call    ??0DEVLOCKBLTOBJ@@QEAA@W4U2KMMAPStatus@@0@Z; DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(U2KMMAPStatus,U2KMMAPStatus)
0x14006685e  lea     r8, [rbp+2C0h+var_2A0]; struct XDCOBJ *
0x140066862  mov     rdx, r12; struct XDCOBJ *
0x140066865  lea     rcx, [rbp+2C0h+var_220]; this
0x14006686c  call    ?bLock@DEVLOCKBLTOBJ@@QEAAHAEAVXDCOBJ@@0@Z; DEVLOCKBLTOBJ::bLock(XDCOBJ &,XDCOBJ &)
0x140066871  test    eax, eax
0x140066873  jz      loc_140067C02
0x140066879  mov     r8, [r12]
0x14006687d  mov     rbx, [r8+1F0h]
0x140066884  mov     [rbp+2C0h+var_2B8], rbx
0x140066888  test    rbx, rbx
0x14006688b  jz      loc_1400686FE
0x140066891  mov     r14, [r8+58h]
0x140066895  mov     r15d, 1
0x14006689b  mov     r12, [rbx+0B0h]
0x1400668a2  shr     r13d, 10h
0x1400668a6  movzx   eax, r13b
0x1400668aa  mov     ecx, eax
0x1400668ac  mov     [rbp+2C0h+var_300], r14
0x1400668b0  shl     ecx, 8
0x1400668b3  or      ecx, eax
0x1400668b5  mov     eax, ecx
0x1400668b7  mov     [rbp+2C0h+var_2E0], ecx
0x1400668ba  shl     eax, 4
0x1400668bd  xor     eax, ecx
0x1400668bf  test    al, 0F0h
0x1400668c1  jnz     loc_140067883
0x1400668c7  xor     r13d, r13d
0x1400668ca  mov     [rbp+2C0h+var_2C8], r13
0x1400668ce  mov     ecx, [r8+28h]
0x1400668d2  and     ecx, r15d
0x1400668d5  mov     eax, [r8+rcx*8+3F8h]
0x1400668dd  add     [rbp+2C0h+var_90.left], eax
0x1400668e3  mov     eax, [r8+rcx*8+3F8h]
0x1400668eb  add     [rbp+2C0h+var_90.right], eax
0x1400668f1  mov     eax, [r8+rcx*8+3FCh]
0x1400668f9  add     [rbp+2C0h+var_90.top], eax
0x1400668ff  mov     eax, [r8+rcx*8+3FCh]
0x140066907  add     [rbp+2C0h+var_90.bottom], eax
0x14006690d  mov     rax, [rbp+2C0h+var_2A0]
0x140066911  cmp     qword ptr [rax+1F0h], 0
0x140066919  jnz     loc_140066A75
0x14006691f  mov     r12, [rbp+2C0h+var_340]
0x140066923  mov     [rsp+3C0h+var_34C], r15d
0x140066928  lea     rcx, [rbp+2C0h+var_220]; this
  ... truncated ...
```
