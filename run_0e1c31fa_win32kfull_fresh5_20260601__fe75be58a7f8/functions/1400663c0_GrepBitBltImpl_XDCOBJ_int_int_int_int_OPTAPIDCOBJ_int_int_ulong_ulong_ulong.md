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
  __int64 flXlate; // rdx
  __int64 j; // r8
  __int64 XlateObject; // rax
  Gre::Base *v96; // rcx
  XLATEOBJ *v97; // rdi
  struct Gre::Base::SESSION_GLOBALS *v98; // r14
  __int64 v99; // rdx
  __int64 i; // r8
  __int64 v101; // rcx
  __int64 v102; // rdx
  int v103; // eax
  __int64 v104; // rdx
  int v105; // eax
  __int64 v106; // rcx
  LONG v107; // r14d
  __int64 v108; // r11
  __int64 v109; // r10
  __int64 v110; // rbx
  unsigned int v111; // edx
  __int64 v112; // r13
  int v113; // ecx
  int v114; // eax
  __int64 v115; // rdx
  __int64 v116; // r12
  __int64 v117; // r14
  __int64 v118; // r15
  int v119; // r9d
  __int64 v120; // r9
  __int64 v121; // rbx
  __int64 v122; // rcx
  __int64 v123; // r8
  int v124; // r8d
  int v125; // ecx
  __int64 v126; // r10
  signed int v127; // r14d
  int v128; // r15d
  __int64 v129; // rbx
  __int64 v130; // r9
  __int64 v131; // r11
  __int64 v132; // r8
  DC *v133; // rcx
  int v134; // eax
  SURFACE *v135; // r15
  char v136; // bl
  DC *v137; // r11
  __int64 v138; // r14
  int v139; // r13d
  int v140; // eax
  int cEntries; // eax
  __int64 v142; // rax
  struct REGION *v143; // rax
  XCLIPOBJ *v144; // r10
  int (*v145)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  __int64 v146; // r11
  __int64 v147; // r10
  int v148; // r8d
  __int64 v149; // rcx
  __int64 v150; // r9
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rdx
  char *v154; // r13
  __int64 v155; // rdx
  int v156; // ecx
  SURFOBJ *v157; // r11
  _BYTE *v158; // rdx
  unsigned int v159; // ebx
  int v160; // r10d
  int v161; // ecx
  struct _GRETHREAD *v162; // rax
  struct _GRETHREAD *v163; // rax
  struct _GRETHREAD *v164; // rax
  struct _GRETHREAD *CurrentThread; // rax
  int v166; // ebx
  int v167; // edx
  int v168; // eax
  _DWORD *v169; // rcx
  _DWORD *v170; // rcx
  struct _GRETHREAD *v171; // rax
  __m128i v172; // xmm2
  __m128i v173; // xmm0
  float v174; // xmm5_4
  int v175; // r8d
  __m128i v176; // xmm1
  unsigned int v177; // edx
  __m128i v178; // xmm3
  __int64 v179; // rax
  __int64 v180; // rax
  int v181; // r8d
  unsigned int v182; // edx
  __int64 v183; // rax
  __int64 v184; // rax
  int v185; // r8d
  unsigned int v186; // edx
  __int64 v187; // rax
  __int64 v188; // rax
  __int64 v189; // r9
  int v190; // r8d
  unsigned int v191; // edx
  __int64 v192; // rax
  __int64 v193; // rax
  __m128i v194; // xmm0
  __m128i v195; // xmm1
  int v196; // r8d
  __m128i v197; // xmm4
  unsigned int v198; // edx
  __int64 v199; // rax
  __int64 v200; // rax
  int v201; // r8d
  unsigned int v202; // edx
  __int64 v203; // rax
  __int64 v204; // rax
  int v205; // r8d
  unsigned int v206; // edx
  __int64 v207; // rax
  __int64 v208; // rax
  int v209; // r8d
  unsigned int v210; // edx
  __int64 v211; // rax
  __int64 v212; // rax
  float v213; // xmm4_4
  float v214; // xmm6_4
  __m128i v215; // xmm0
  __m128i v216; // xmm1
  int v217; // r9d
  __m128i v218; // xmm2
  unsigned int v219; // r8d
  __m128i v220; // xmm3
  __int64 v221; // rax
  __int64 v222; // rax
  __int64 v223; // rax
  int v224; // r9d
  unsigned int v225; // r8d
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // r11
  int v229; // r9d
  unsigned int v230; // r8d
  __int64 v231; // rax
  __int64 v232; // rax
  int v233; // r10d
  unsigned int v234; // r8d
  __int64 v235; // rax
  __int64 v236; // rax
  __m128i v237; // xmm0
  __m128i v238; // xmm1
  __m128i v239; // xmm2
  int v240; // r10d
  __m128i v241; // xmm3
  unsigned int v242; // r8d
  __int64 v243; // rax
  __int64 v244; // rax
  int v245; // r11d
  unsigned int v246; // r10d
  __int64 v247; // rax
  __int64 v248; // rax
  float v249; // xmm3_4
  __m128i v250; // xmm2
  __m128i v251; // xmm4
  __m128i v252; // xmm0
  __m128i v253; // xmm1
  int v254; // r9d
  __m128i v255; // xmm2
  unsigned int v256; // r8d
  __m128i v257; // xmm4
  float v258; // xmm0_4
  __int64 v259; // rax
  __int64 v260; // rax
  int v261; // r9d
  unsigned int v262; // r8d
  __int64 v263; // rax
  __int64 v264; // rax
  int v265; // r12d
  unsigned int v266; // r8d
  __int64 v267; // rax
  __int64 v268; // rax
  int v269; // r12d
  unsigned int v270; // r8d
  __int64 v271; // rax
  __int64 v272; // rax
  __m128i v273; // xmm2
  __m128i v274; // xmm4
  float v275; // xmm3_4
  __m128i v276; // xmm0
  __m128i v277; // xmm1
  int v278; // r14d
  __m128i v279; // xmm2
  unsigned int v280; // edx
  __m128i v281; // xmm4
  float v282; // xmm0_4
  __int64 v283; // rax
  __int64 v284; // rax
  int v285; // r14d
  unsigned int v286; // edx
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // rcx
  int v290; // r14d
  unsigned int v291; // edx
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rcx
  int v295; // r12d
  unsigned int v296; // ecx
  __int64 v297; // rax
  __int64 v298; // rax
  unsigned int v299; // [rsp+70h] [rbp-90h]
  int v300; // [rsp+74h] [rbp-8Ch]
  int v301; // [rsp+78h] [rbp-88h]
  LONG v302; // [rsp+78h] [rbp-88h]
  LONG v304; // [rsp+88h] [rbp-78h]
  unsigned int v305; // [rsp+88h] [rbp-78h]
  int v306; // [rsp+8Ch] [rbp-74h]
  int v307; // [rsp+8Ch] [rbp-74h]
  int v308; // [rsp+90h] [rbp-70h]
  LONG v309; // [rsp+90h] [rbp-70h]
  LONG v310; // [rsp+94h] [rbp-6Ch]
  int v311; // [rsp+94h] [rbp-6Ch]
  XLATEOBJ *v312; // [rsp+98h] [rbp-68h] BYREF
  OPTAPIDCOBJ *v313; // [rsp+A0h] [rbp-60h]
  __int64 v314; // [rsp+A8h] [rbp-58h] BYREF
  LONG v315; // [rsp+B0h] [rbp-50h]
  __int64 v316; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v317; // [rsp+C0h] [rbp-40h]
  __int64 v318; // [rsp+C8h] [rbp-38h]
  __int64 v319; // [rsp+D0h] [rbp-30h]
  __int64 v320; // [rsp+D8h] [rbp-28h]
  int v321; // [rsp+E0h] [rbp-20h]
  unsigned int v322; // [rsp+E4h] [rbp-1Ch]
  unsigned int v323; // [rsp+E8h] [rbp-18h]
  char *v324; // [rsp+F0h] [rbp-10h]
  __int64 v325; // [rsp+F8h] [rbp-8h]
  __int64 v326; // [rsp+100h] [rbp+0h] BYREF
  SURFACE *v327; // [rsp+108h] [rbp+8h]
  SURFOBJ *v328; // [rsp+110h] [rbp+10h]
  DC *v329; // [rsp+120h] [rbp+20h] BYREF
  int v330; // [rsp+128h] [rbp+28h]
  __int64 v331; // [rsp+130h] [rbp+30h]
  __int64 v332; // [rsp+138h] [rbp+38h]
  _OWORD v333[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v334[2]; // [rsp+160h] [rbp+60h] BYREF
  char v335; // [rsp+180h] [rbp+80h]
  const struct MATRIX *v336; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v337[80]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v338; // [rsp+1F0h] [rbp+F0h]
  RECTL v339; // [rsp+330h] [rbp+230h] BYREF
  POINTL v340; // [rsp+340h] [rbp+240h] BYREF
  int v341; // [rsp+348h] [rbp+248h]
  int v342; // [rsp+34Ch] [rbp+24Ch]
  __m128i v343; // [rsp+350h] [rbp+250h] BYREF

  v11 = (struct XDCOBJ *)a1;
  x = a7;
  v14 = a5;
  y = a8;
  v17 = a6;
  v313 = a6;
  v301 = a4;
  if ( (a11 & 4) != 0
    && (CurrentThread = GreGetCurrentThread(), v17 = v313, a4 = v301, v14 = a5, v11 = (struct XDCOBJ *)a1, CurrentThread) )
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
    v159 = GrepStretchBlt(
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
      v171 = GreGetCurrentThread();
      *((_DWORD *)v171 + 84) &= ~8u;
    }
    return v159;
  }
  v19 = 0;
  v300 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)v11 + 36LL) & 0x10000) != 0 )
    goto LABEL_61;
  v20 = a9 & 0x5FFFFFFF;
  if ( ((*((_BYTE *)gajRop3 + (unsigned __int8)a9) | *((_BYTE *)gajRop3 + BYTE1(a9))) & 2) != 0
    && v20 != 16711778
    && v20 != 66 )
  {
    bSpDwmValidateSurface(v11, left, top, a4, v14);
  }
  if ( !OPTAPIDCOBJ::bValid(v313) )
  {
    v19 = 0;
    goto LABEL_61;
  }
  memset(v333, 0, sizeof(v333));
  v331 = *((_QWORD *)v313 + 2);
  v332 = 0;
  v329 = 0;
  v330 = 0;
  PushThreadGuardedObject(
    v333,
    &v329,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v334, 0, sizeof(v334));
  PushThreadGuardedObject(
    v334,
    &v329,
    UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v335 = 0;
  v329 = *(DC **)v313;
  bSpDwmValidateSurface((struct XDCOBJ *)&v329, a7, a8, v301, a5);
  v21 = *((_QWORD *)*a1 + 122);
  v22 = *(_DWORD *)(v21 + 108);
  if ( ((*(_BYTE *)(*((_QWORD *)v329 + 122) + 108LL) ^ *(_BYTE *)(v21 + 108)) & 7) != 0
    && (a9 < 0 && (v22 & 1) != 0 || (v22 & 9) == 9) )
  {
    v166 = *(_DWORD *)(v21 + 308);
    v323 = DC::dwSetLayout(*a1, -1, 0);
    left = v166 - v301 - left;
    v322 = 0x80000000;
  }
  else
  {
    v323 = 0;
    v322 = 0;
  }
  DC::QuickInitXform(*a1, &v326, 516);
  DC::QuickInitXform(v329, &v336, 516);
  if ( (*(_BYTE *)(v326 + 32) & 1) == 0 || !EXFORMOBJ::bEqualExceptTranslations((EXFORMOBJ *)&v326, v336) )
  {
    v27 = a1;
    v19 = GrepStretchBlt((struct XDCOBJ *)a1, left, top, v301, a5, v313, a7, a8, v301, a5, v20, a10, 0);
    goto LABEL_55;
  }
  v23 = a8 + a5;
  v325 = (__int64)v329;
  v24 = a7 + v301;
  v340.x = a7;
  v341 = a7 + v301;
  v340.y = a8;
  v342 = a8 + a5;
  if ( (*((_BYTE *)v336 + 32) & 0x43) == 0x43
    || (v25 = bCvtPts1(v336, &v340, 2), v23 = v342, v24 = v341, y = v340.y, x = v340.x, v25) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v325 + 976) + 108LL) & 1) != 0 )
    {
      ++x;
      ++v24;
      v340.x = x;
      v341 = v24;
    }
  }
  if ( x > v24 )
  {
    v340.x = v24;
    v341 = x;
  }
  if ( y > v23 )
  {
    v340.y = v23;
    v342 = y;
  }
  right = v301 + left;
  v27 = a1;
  v339.bottom = top + a5;
  v339.left = left;
  v339.top = top;
  v28 = *a1;
  v339.right = v301 + left;
  if ( (*(_BYTE *)(v326 + 32) & 0x43) == 0x43
    || (v29 = bCvtPts1(v326, &v339, 2), right = v339.right, top = v339.top, left = v339.left, v29) )
  {
    if ( (*(_DWORD *)(*((_QWORD *)v28 + 122) + 108LL) & 1) != 0 )
    {
      ++left;
      ++right;
      v339.left = left;
      v339.right = right;
    }
  }
  if ( left > right )
  {
    v30 = left;
    v339.left = right;
    left = right;
    v339.right = v30;
    right = v30;
  }
  bottom = v339.bottom;
  if ( top > v339.bottom )
  {
    v339.top = v339.bottom;
    v339.bottom = top;
    top = bottom;
  }
  if ( top == v339.bottom || left == right )
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
        right = v339.right;
        top = v339.top;
        left = v339.left;
      }
      if ( top < *((_DWORD *)v32 + 267) )
      {
        *((_DWORD *)v32 + 267) = top;
        right = v339.right;
        top = v339.top;
        left = v339.left;
      }
      if ( right > *((_DWORD *)v32 + 268) )
      {
        *((_DWORD *)v32 + 268) = right;
        right = v339.right;
        top = v339.top;
        left = v339.left;
      }
      if ( v339.bottom > *((_DWORD *)v32 + 269) )
      {
        *((_DWORD *)v32 + 269) = v339.bottom;
        right = v339.right;
        top = v339.top;
        left = v339.left;
      }
    }
    v34 = *a1;
    if ( (*((_DWORD *)*a1 + 9) & 0x80u) != 0 )
    {
      if ( left < *((_DWORD *)v34 + 274) )
      {
        *((_DWORD *)v34 + 274) = left;
        right = v339.right;
        top = v339.top;
      }
      if ( top < *((_DWORD *)v34 + 275) )
      {
        *((_DWORD *)v34 + 275) = top;
        right = v339.right;
      }
      if ( right > *((_DWORD *)v34 + 276) )
        *((_DWORD *)v34 + 276) = right;
      if ( v339.bottom > *((_DWORD *)v34 + 277) )
        *((_DWORD *)v34 + 277) = v339.bottom;
    }
  }
  DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(v337);
  if ( !(unsigned int)DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v337, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v329) )
  {
    v167 = XDCOBJ::bFullScreen((XDCOBJ *)a1);
    if ( !*((_QWORD *)v329 + 62) || (v168 = DC::bInFullScreen(v329)) != 0 )
      v168 = 1;
    v300 = v168 | v167;
    goto LABEL_54;
  }
  v35 = *a1;
  v36 = *((_QWORD *)*a1 + 62);
  v327 = (SURFACE *)v36;
  if ( !v36 )
  {
    v300 = 1;
    goto LABEL_54;
  }
  v37 = *((_QWORD *)v35 + 11);
  v38 = *(_QWORD *)(v36 + 176);
  v317 = v37;
  v39 = (a9 & 0x5FFFFFFFu) >> 16;
  v321 = v39 | (v39 << 8);
  if ( ((v39 ^ (unsigned __int8)(16 * v39)) & 0xF0) != 0 )
  {
    v153 = *((_QWORD *)v35 + 122);
    v154 = (char *)v35 + 1200;
    v325 = (__int64)v35 + 1200;
    if ( (*(_DWORD *)(v153 + 152) & 0x1000) != 0 )
      GreDCSelectBrush(v35, *(_QWORD *)(v153 + 160));
    v35 = *a1;
    v155 = *((_QWORD *)*a1 + 122);
    v156 = *(_DWORD *)(v155 + 152);
    if ( (v156 & 1) != 0 || (*((_DWORD *)v35 + 79) & 1) != 0 )
    {
      *(_DWORD *)(v155 + 152) = v156 & 0xFFFFFFFE;
      *((_DWORD *)*a1 + 79) &= ~1u;
      EBRUSHOBJ::vInitBrush(v154, *a1, *((_QWORD *)*a1 + 17), v37, v38, v36, 1);
      v35 = *a1;
    }
  }
  else
  {
    v325 = 0;
  }
  v40 = (Gre::Base *)(*((_DWORD *)v35 + 10) & 1);
  v339.left += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 254);
  v339.right += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 254);
  v339.top += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 255);
  v339.bottom += *((_DWORD *)v35 + 2 * (_QWORD)v40 + 255);
  if ( !*((_QWORD *)v329 + 62) )
    goto LABEL_53;
  v49 = Gre::Base::Globals(v40);
  v50 = *((_QWORD *)v329 + 62);
  if ( v50 )
  {
    if ( v332 )
      v50 = v332;
  }
  else
  {
    v50 = *((_QWORD *)v49 + 547);
  }
  v318 = v50;
  if ( !v50 )
    goto LABEL_53;
  if ( (a11 & 2) != 0 )
    goto LABEL_85;
  if ( (v338 & 0x400000) == 0
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
  v50 = v318;
LABEL_85:
  v53 = 0;
  v54 = v339.left;
  v55 = v339.top;
  v56 = *(_QWORD *)(v50 + 48);
  v57 = *(_QWORD *)(v50 + 176);
  v58 = *((_DWORD *)v329 + 10) & 1;
  v59 = 0;
  v60 = v339.top - *((_DWORD *)v329 + 2 * v58 + 255) - v340.y;
  v61 = v339.left - *((_DWORD *)v329 + 2 * v58 + 254) - v340.x;
  v308 = v60;
  v328 = (SURFOBJ *)(v50 + 24);
  if ( v56 && v50 == *(_QWORD *)(v56 + 2544) && (*(_DWORD *)(v56 + 40) & 0x20000) != 0 )
  {
    v59 = *(_DWORD *)(v56 + 2576);
    v53 = *(_DWORD *)(v56 + 2580);
  }
  if ( v59 + v61 > v339.left )
    v54 = v59 + v61;
  v339.left = v54;
  v299 = v54;
  if ( v53 + v60 > v339.top )
    v55 = v53 + v60;
  v339.top = v55;
  v62 = v59 + *(_DWORD *)(v50 + 56);
  v63 = v339.right;
  v64 = v61 + v62;
  if ( v64 < v339.right )
    v63 = v64;
  v339.right = v63;
  v65 = v53 + *(_DWORD *)(v50 + 60);
  v66 = v339.bottom;
  v67 = v60 + v65;
  if ( v67 < v339.bottom )
    v66 = v67;
  v339.bottom = v66;
  if ( v54 >= v63 || v55 >= v66 )
    goto LABEL_53;
  v68 = a1;
  v69 = *a1;
  if ( v54 < *((_DWORD *)*a1 + 250)
    || v63 > *((_DWORD *)v69 + 252)
    || v55 < *((_DWORD *)v69 + 251)
    || (v324 = 0, v66 > *((_DWORD *)v69 + 253)) )
  {
    v324 = (char *)v69 + 1768;
    v143 = XDCOBJ::prgnEffRao((XDCOBJ *)a1);
    XCLIPOBJ::vSetup(v144, v143, (const struct ERECTL *)&v339, 2);
    v70 = *(__m128i *)(v324 + 4);
    v54 = _mm_cvtsi128_si32(v70);
    v339 = (RECTL)v70;
    v299 = v54;
    v339.right = _mm_cvtsi128_si32(_mm_srli_si128(v70, 8));
    if ( v54 != v339.right && v70.m128i_i32[1] != _mm_srli_si128(v70, 8).m128i_i32[1] )
    {
      v68 = a1;
      v339.bottom = _mm_cvtsi128_si32(_mm_srli_si128(v70, 12));
      v339.top = _mm_cvtsi128_si32(_mm_srli_si128(v70, 4));
      goto LABEL_102;
    }
LABEL_53:
    v27 = a1;
    v300 = 1;
    goto LABEL_54;
  }
  v70 = (__m128i)v339;
LABEL_102:
  v71 = *v68;
  v72 = *((_DWORD *)v71 + 9);
  if ( (v72 & 0xE0) != 0 )
  {
    v343 = v70;
    v73 = *((_DWORD *)v71 + 10) & 1;
    v74 = v54 - *((_DWORD *)v71 + 2 * v73 + 254);
    v343.m128i_i32[0] = v74;
    v75 = v70.m128i_i32[2] - *((_DWORD *)v71 + 2 * v73 + 254);
    v343.m128i_i32[2] = v75;
    v76 = v70.m128i_i32[1] - *((_DWORD *)v71 + 2 * v73 + 255);
    v343.m128i_i32[1] = v76;
    v343.m128i_i32[3] = v70.m128i_i32[3] - *((_DWORD *)v71 + 2 * v73 + 255);
    if ( (v72 & 0x40) != 0 )
    {
      v77 = *((_DWORD *)v71 + 270);
      v78 = *((_DWORD *)v71 + 272);
      if ( v77 == v78 || (v79 = *((_DWORD *)v71 + 273), *((_DWORD *)v71 + 271) == v79) )
      {
        *(__m128i *)((char *)v71 + 1080) = v343;
        v54 = v339.left;
        v299 = v339.left;
      }
      else
      {
        if ( v74 < v77 )
        {
          *((_DWORD *)v71 + 270) = v74;
          v75 = v343.m128i_i32[2];
          v76 = v343.m128i_i32[1];
          v299 = v339.left;
        }
        if ( v76 < *((_DWORD *)v71 + 271) )
        {
          *((_DWORD *)v71 + 271) = v76;
          v75 = v343.m128i_i32[2];
          v299 = v339.left;
        }
        if ( v75 > v78 )
        {
          *((_DWORD *)v71 + 272) = v75;
          v299 = v339.left;
        }
        if ( v343.m128i_i32[3] <= v79 )
        {
          v54 = v299;
        }
        else
        {
          *((_DWORD *)v71 + 273) = v343.m128i_i32[3];
          v54 = v339.left;
          v299 = v339.left;
        }
      }
      v312 = (XLATEOBJ *)*((_QWORD *)*a1 + 148);
      if ( v312 )
      {
        v314 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v314, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v314);
        v316 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v316, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v316);
        if ( v314 )
        {
          if ( v316 )
          {
            RGNOBJ::vSet((RGNOBJ *)&v316, (const struct _RECTL *const)&v343);
            if ( RGNOBJ::bMerge((RGNOBJ *)&v314, (struct RGNOBJ *)&v312, (struct RGNOBJ *)&v316, 0xEu) )
            {
              RGNOBJ::vSwap((RGNOBJ *)&v312, (struct RGNOBJ *)&v314);
              *((_QWORD *)*a1 + 148) = v312;
            }
          }
        }
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v316);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v316);
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v314);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v314);
        v54 = v339.left;
        v299 = v339.left;
      }
    }
  }
  v340.x = v54 - v61;
  v304 = v54 - v61;
  v80 = *a1;
  v81 = (unsigned int)(v339.top - v60);
  v340.y = v339.top - v60;
  v310 = v339.top - v60;
  if ( v318 == *((_QWORD *)v80 + 62) )
  {
    v107 = v299;
    v97 = 0;
    v300 = 1;
    v27 = a1;
    goto LABEL_159;
  }
  v82 = a10;
  v305 = a10;
  if ( a10 == -1 )
  {
    v81 = *((_QWORD *)v329 + 122);
    v82 = *(_DWORD *)(v81 + 180);
    v305 = v82;
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
  v142 = *(_QWORD *)(v37 + 80);
  if ( !v142 )
    goto LABEL_210;
  v86 = v142 == *(_QWORD *)(v37 + 72);
LABEL_125:
  if ( v86 )
  {
LABEL_210:
    v97 = (XLATEOBJ *)((char *)Gre::Base::Globals((Gre::Base *)v81) + 4664);
    goto LABEL_154;
  }
LABEL_126:
  v87 = *((unsigned int *)v80 + 30);
  LODWORD(v314) = *((_DWORD *)v80 + 30);
  v343.m128i_i64[0] = *((_QWORD *)v329 + 11);
  v88 = *((_QWORD *)v80 + 122);
  v89 = (Gre::Base *)*(unsigned int *)(v88 + 176);
  v90 = *(_DWORD *)(v88 + 184);
  v311 = v90;
  v306 = (int)v89;
  if ( !v57 || !v38 )
  {
LABEL_135:
    XlateObject = CreateXlateObject(0, v87, v57, v38, v343.m128i_i64[0], v37, v90, (_DWORD)v89, v82, 0);
    v97 = (XLATEOBJ *)XlateObject;
    if ( !XlateObject )
    {
      v106 = 0;
      goto LABEL_155;
    }
    if ( v57 && v38 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
    {
      v98 = Gre::Base::Globals(v96);
      v312 = (XLATEOBJ *)(*(_QWORD *)v98 + 312LL);
      GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
      for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
      {
        v99 = *((unsigned int *)v98 + 1164);
        v101 = *((_QWORD *)v98 + 4 * v99 + 551);
        if ( !v101 )
          goto LABEL_144;
        if ( !*((_DWORD *)v98 + 8 * v99 + 1100) )
        {
          FreeThreadBufferWithTag(v101);
LABEL_144:
          PopThreadGuardedObject(&v97[-2].pulXlate);
          v102 = v57;
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1100) = 1;
          *((_QWORD *)v98 + 4 * *((unsigned int *)v98 + 1164) + 551) = v97;
          if ( *(_QWORD *)(v57 + 120) != v57 )
            v102 = *(_QWORD *)(v57 + 120);
          v103 = *(_DWORD *)(v102 + 32);
          v104 = v343.m128i_i64[0];
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1104) = v103;
          if ( *(_QWORD *)(v38 + 120) != v38 )
            v38 = *(_QWORD *)(v38 + 120);
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1105) = *(_DWORD *)(v38 + 32);
          if ( *(_QWORD *)(v104 + 120) != v104 )
            v104 = *(_QWORD *)(v104 + 120);
          v105 = *(_DWORD *)(v104 + 32);
          v99 = v317;
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1106) = v105;
          if ( *(_QWORD *)(v99 + 120) != v99 )
            v99 = *(_QWORD *)(v99 + 120);
          *((_DWORD *)v98 + 8 * *((unsigned int *)v98 + 1164) + 1107) = *(_DWORD *)(v99 + 32);
          v97[1].cEntries = *((_DWORD *)v98 + 1164);
          *(_DWORD *)(v57 + 56) = *((_DWORD *)v98 + 1164);
          *((_DWORD *)v98 + 1164) = ((unsigned __int8)*((_DWORD *)v98 + 1164) + 1) & 7;
          break;
        }
        *((_DWORD *)v98 + 1164) = ((_BYTE)v99 + 1) & 7;
      }
      SEMOBJ<13>::vUnlock(&v312, v99, i);
    }
LABEL_154:
    v106 = 1;
    goto LABEL_155;
  }
  v91 = *(_DWORD *)(v57 + 56);
  v92 = (XLATEOBJ **)Gre::Base::Globals(v89);
  v312 = *v92 + 13;
  GreAcquireSemaphoreInternal((HSEMAPHORE)v312);
  GrepAcquireLockValidate<13>();
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= 8 )
    {
      SEMOBJ<13>::vUnlock(&v312, flXlate, j);
      LODWORD(v89) = v306;
      v90 = v311;
      v87 = (unsigned int)v314;
      v82 = v305;
      v37 = v317;
      goto LABEL_135;
    }
    flXlate = v57;
    if ( *(_QWORD *)(v57 + 120) != v57 )
      flXlate = *(_QWORD *)(v57 + 120);
    if ( LODWORD(v92[4 * v91 + 552]) != *(_DWORD *)(flXlate + 32) )
      goto LABEL_133;
    v149 = v38;
    if ( *(_QWORD *)(v38 + 120) != v38 )
      v149 = *(_QWORD *)(v38 + 120);
    v150 = 4LL * v91;
    if ( HIDWORD(v92[v150 + 552]) != *(_DWORD *)(v149 + 32) )
      goto LABEL_133;
    flXlate = v317;
    v151 = v317;
    if ( *(_QWORD *)(v317 + 120) != v317 )
      v151 = *(_QWORD *)(v317 + 120);
    if ( HIDWORD(v92[v150 + 553]) != *(_DWORD *)(v151 + 32) )
      goto LABEL_133;
    v97 = v92[v150 + 551];
    flXlate = v97[3].flXlate;
    if ( (flXlate & 0x6000) != 0 )
      goto LABEL_133;
    flXlate &= 0x100u;
    if ( (v97->flXlate & 4) != 0 )
      break;
    if ( !(_DWORD)flXlate )
      goto LABEL_243;
LABEL_241:
    if ( v311 == v97[1].flXlate && v306 == *(_DWORD *)&v97[1].iSrcType )
      goto LABEL_243;
LABEL_133:
    v91 = ((_BYTE)v91 + 1) & 7;
  }
  if ( v305 != v97[1].iUniq )
    goto LABEL_240;
  v152 = v343.m128i_i64[0];
  if ( *(_QWORD *)(v343.m128i_i64[0] + 120) != v343.m128i_i64[0] )
    v152 = *(_QWORD *)(v343.m128i_i64[0] + 120);
  if ( LODWORD(v92[v150 + 553]) != *(_DWORD *)(v152 + 32) )
  {
LABEL_240:
    if ( !(_DWORD)flXlate )
      goto LABEL_133;
    goto LABEL_241;
  }
LABEL_243:
  _InterlockedIncrement((volatile signed __int32 *)&v92[v150 + 550]);
  *(_DWORD *)(v57 + 56) = v91;
  SEMOBJ<13>::vUnlock(&v312, flXlate, j);
  v106 = 1;
LABEL_155:
  v27 = a1;
  v300 = v106;
  v80 = *a1;
  if ( (*((_DWORD *)*a1 + 9) & 1) == 0 )
  {
    v341 = v339.right - v61;
    v342 = v339.bottom - v308;
  }
  if ( (_DWORD)v106 )
  {
    v107 = v339.left;
    v310 = v340.y;
    v304 = v340.x;
    v299 = v339.left;
LABEL_159:
    LODWORD(v108) = 0;
    LODWORD(v109) = 0;
    v309 = v339.top;
    v315 = v339.right;
    v312 = v97;
    v302 = v339.bottom;
    v320 = 0;
    v319 = 0;
    if ( *((int *)v327 + 40) < 0 )
    {
      v169 = (_DWORD *)*((_QWORD *)v327 + 6);
      if ( v169 )
      {
        if ( (v169[10] & 0x20000) != 0 )
        {
          LODWORD(v108) = v169[644];
          v109 = (unsigned int)v169[645];
          v320 = (unsigned int)v108;
          v319 = v109;
        }
      }
    }
    LODWORD(v110) = 0;
    v111 = 0;
    LODWORD(v112) = v109 + *((_DWORD *)v327 + 15);
    v317 = (unsigned int)(v108 + *((_DWORD *)v327 + 14));
    v313 = 0;
    v343.m128i_i64[0] = 0;
    if ( *(int *)(v318 + 160) < 0 )
    {
      v170 = *(_DWORD **)(v318 + 48);
      if ( v170 )
      {
        if ( (v170[10] & 0x20000) != 0 )
        {
          v111 = v170[644];
          v110 = (unsigned int)v170[645];
          v313 = (OPTAPIDCOBJ *)v111;
          v343.m128i_i64[0] = v110;
        }
      }
    }
    v113 = v111 + *(_DWORD *)(v318 + 56);
    LODWORD(v314) = v110 + *(_DWORD *)(v318 + 60);
    if ( v27 && (v114 = *((_DWORD *)v80 + 130), (v114 & 1) != 0) && (v114 & 2) == 0 )
    {
      v172 = (__m128i)LODWORD(FLOAT_1_0);
      *(float *)v172.m128i_i32 = 1.0 / *((float *)v80 + 131);
      v173 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v108);
      v174 = 1.0 / *((float *)v80 + 132);
      *(float *)v173.m128i_i32 = *(float *)v173.m128i_i32 * *(float *)v172.m128i_i32;
      v175 = _mm_cvtsi128_si32(v173);
      v176 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v109);
      v177 = (unsigned __int8)(v175 >> 23);
      v178 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v112);
      if ( v177 > 0x9E )
        goto LABEL_355;
      *(float *)v176.m128i_i32 = *(float *)v176.m128i_i32 * v174;
      v179 = v175 & 0x7FFFFF | 0x800000LL;
      if ( v177 < 0x76 )
        v180 = v179 >> (118 - (unsigned __int8)v177);
      else
        v180 = v179 << ((unsigned __int8)v177 - 118);
      v108 = (v180 + 0x80000000LL) >> 32;
      if ( v175 < 0 )
        v108 = (unsigned int)-(int)v108;
      v181 = _mm_cvtsi128_si32(v176);
      v320 = v108;
      v182 = (unsigned __int8)(v181 >> 23);
      if ( v182 > 0x9E )
        goto LABEL_355;
      v183 = v181 & 0x7FFFFF | 0x800000LL;
      if ( v182 < 0x76 )
        v184 = v183 >> (118 - (unsigned __int8)v182);
      else
        v184 = v183 << ((unsigned __int8)v182 - 118);
      v109 = (v184 + 0x80000000LL) >> 32;
      if ( v181 < 0 )
        v109 = (unsigned int)-(int)v109;
      v185 = _mm_cvtsi128_si32(v172);
      v319 = v109;
      v186 = (unsigned __int8)(v185 >> 23);
      if ( v186 > 0x9E )
        goto LABEL_355;
      *(float *)v178.m128i_i32 = *(float *)v178.m128i_i32 * v174;
      v187 = v185 & 0x7FFFFF | 0x800000LL;
      if ( v186 < 0x76 )
        v188 = v187 >> (118 - (unsigned __int8)v186);
      else
        v188 = v187 << ((unsigned __int8)v186 - 118);
      v189 = (v188 + 0x80000000LL) >> 32;
      if ( v185 < 0 )
        v189 = (unsigned int)-(int)v189;
      v190 = _mm_cvtsi128_si32(v178);
      v317 = v189;
      v191 = (unsigned __int8)(v190 >> 23);
      if ( v191 > 0x9E )
      {
LABEL_355:
        LODWORD(v112) = 0;
        LODWORD(v109) = 0;
        LODWORD(v108) = 0;
        LODWORD(v317) = 0;
        v320 = 0;
        v319 = 0;
      }
      else
      {
        v192 = v190 & 0x7FFFFF | 0x800000LL;
        if ( v191 < 0x76 )
          v193 = v192 >> (118 - (unsigned __int8)v191);
        else
          v193 = v192 << ((unsigned __int8)v191 - 118);
        v112 = (v193 + 0x80000000LL) >> 32;
        if ( v190 < 0 )
          LODWORD(v112) = -(int)v112;
      }
      v194 = (__m128i)COERCE_UNSIGNED_INT((float)v107);
      v195 = (__m128i)COERCE_UNSIGNED_INT((float)v339.top);
      *(float *)v194.m128i_i32 = *(float *)v194.m128i_i32 * *(float *)v172.m128i_i32;
      v196 = _mm_cvtsi128_si32(v194);
      v197 = (__m128i)COERCE_UNSIGNED_INT((float)v339.bottom);
      v198 = (unsigned __int8)(v196 >> 23);
      if ( v198 > 0x9E )
        goto LABEL_356;
      *(float *)v195.m128i_i32 = *(float *)v195.m128i_i32 * v174;
      v199 = v196 & 0x7FFFFF | 0x800000LL;
      if ( v198 < 0x76 )
        v200 = v199 >> (118 - (unsigned __int8)v198);
      else
        v200 = v199 << ((unsigned __int8)v198 - 118);
      v116 = (v200 + 0x80000000LL) >> 32;
      if ( v196 < 0 )
        LODWORD(v116) = -(int)v116;
      v201 = _mm_cvtsi128_si32(v195);
      v202 = (unsigned __int8)(v201 >> 23);
      if ( v202 > 0x9E )
        goto LABEL_356;
      *(float *)v172.m128i_i32 = *(float *)v172.m128i_i32 * (float)v315;
      v203 = v201 & 0x7FFFFF | 0x800000LL;
      if ( v202 < 0x76 )
        v204 = v203 >> (118 - (unsigned __int8)v202);
      else
        v204 = v203 << ((unsigned __int8)v202 - 118);
      v118 = (v204 + 0x80000000LL) >> 32;
      if ( v201 < 0 )
        LODWORD(v118) = -(int)v118;
      v205 = _mm_cvtsi128_si32(v172);
      v206 = (unsigned __int8)(v205 >> 23);
      if ( v206 > 0x9E )
        goto LABEL_356;
      *(float *)v197.m128i_i32 = *(float *)v197.m128i_i32 * v174;
      v207 = v205 & 0x7FFFFF | 0x800000LL;
      if ( v206 < 0x76 )
        v208 = v207 >> (118 - (unsigned __int8)v206);
      else
        v208 = v207 << ((unsigned __int8)v206 - 118);
      v117 = (v208 + 0x80000000LL) >> 32;
      if ( v205 < 0 )
        LODWORD(v117) = -(int)v117;
      v209 = _mm_cvtsi128_si32(v197);
      v210 = (unsigned __int8)(v209 >> 23);
      if ( v210 > 0x9E )
      {
LABEL_356:
        LODWORD(v115) = 0;
        LODWORD(v117) = 0;
        LODWORD(v118) = 0;
        LODWORD(v116) = 0;
      }
      else
      {
        v211 = v209 & 0x7FFFFF | 0x800000LL;
        if ( v210 < 0x76 )
          v212 = v211 >> (118 - (unsigned __int8)v210);
        else
          v212 = v211 << ((unsigned __int8)v210 - 118);
        v115 = (v212 + 0x80000000LL) >> 32;
        if ( v209 < 0 )
          LODWORD(v115) = -(int)v115;
      }
    }
    else
    {
      LODWORD(v115) = v339.bottom;
      LODWORD(v116) = v107;
      LODWORD(v117) = v315;
      LODWORD(v118) = v339.top;
    }
    v119 = *((_DWORD *)v329 + 130);
    LODWORD(v316) = v119;
    v307 = v119 & 1;
    if ( (v119 & 1) == 0 || (v119 & 2) != 0 )
    {
      LODWORD(v120) = v314;
      LODWORD(v121) = v113;
      LODWORD(v122) = v310;
      LODWORD(v123) = v304;
    }
    else
    {
      v213 = 1.0 / *((float *)v329 + 131);
      v214 = 1.0 / *((float *)v329 + 132);
      v215 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v313);
      *(float *)v215.m128i_i32 = *(float *)v215.m128i_i32 * v213;
      v216 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v110);
      v217 = _mm_cvtsi128_si32(v215);
      v218 = (__m128i)COERCE_UNSIGNED_INT((float)v113);
      v219 = (unsigned __int8)(v217 >> 23);
      v220 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v314);
      if ( v219 > 0x9E )
        goto LABEL_396;
      *(float *)v216.m128i_i32 = *(float *)v216.m128i_i32 * v214;
      v221 = v217 & 0x7FFFFF | 0x800000LL;
      if ( v219 < 0x76 )
        v222 = v221 >> (118 - (unsigned __int8)v219);
      else
        v222 = v221 << ((unsigned __int8)v219 - 118);
      v223 = (v222 + 0x80000000LL) >> 32;
      if ( v217 < 0 )
        v223 = (unsigned int)-(int)v223;
      v313 = (OPTAPIDCOBJ *)v223;
      v224 = _mm_cvtsi128_si32(v216);
      v225 = (unsigned __int8)(v224 >> 23);
      if ( v225 > 0x9E )
        goto LABEL_396;
      *(float *)v218.m128i_i32 = *(float *)v218.m128i_i32 * v213;
      v226 = v224 & 0x7FFFFF | 0x800000LL;
      if ( v225 < 0x76 )
        v227 = v226 >> (118 - (unsigned __int8)v225);
      else
        v227 = v226 << ((unsigned __int8)v225 - 118);
      v228 = (v227 + 0x80000000LL) >> 32;
      if ( v224 < 0 )
        v228 = (unsigned int)-(int)v228;
      v229 = _mm_cvtsi128_si32(v218);
      v343.m128i_i64[0] = v228;
      v230 = (unsigned __int8)(v229 >> 23);
      if ( v230 > 0x9E )
        goto LABEL_396;
      *(float *)v220.m128i_i32 = *(float *)v220.m128i_i32 * v214;
      v231 = v229 & 0x7FFFFF | 0x800000LL;
      if ( v230 < 0x76 )
        v232 = v231 >> (118 - (unsigned __int8)v230);
      else
        v232 = v231 << ((unsigned __int8)v230 - 118);
      v121 = (v232 + 0x80000000LL) >> 32;
      if ( v229 < 0 )
        LODWORD(v121) = -(int)v121;
      v233 = _mm_cvtsi128_si32(v220);
      v234 = (unsigned __int8)(v233 >> 23);
      if ( v234 > 0x9E )
      {
LABEL_396:
        LODWORD(v121) = 0;
        LODWORD(v120) = 0;
        v343.m128i_i32[0] = 0;
        v313 = 0;
      }
      else
      {
        v235 = v233 & 0x7FFFFF | 0x800000LL;
        if ( v234 < 0x76 )
          v236 = v235 >> (118 - (unsigned __int8)v234);
        else
          v236 = v235 << ((unsigned __int8)v234 - 118);
        v120 = (v236 + 0x80000000LL) >> 32;
        if ( v233 < 0 )
          LODWORD(v120) = -(int)v120;
      }
      v237 = (__m128i)COERCE_UNSIGNED_INT((float)v304);
      v238 = (__m128i)COERCE_UNSIGNED_INT((float)v310);
      *(float *)v237.m128i_i32 = *(float *)v237.m128i_i32 * v213;
      v239 = (__m128i)COERCE_UNSIGNED_INT((float)v341);
      v240 = _mm_cvtsi128_si32(v237);
      v241 = (__m128i)COERCE_UNSIGNED_INT((float)v342);
      v242 = (unsigned __int8)(v240 >> 23);
      if ( v242 > 0x9E )
        goto LABEL_397;
      *(float *)v238.m128i_i32 = *(float *)v238.m128i_i32 * v214;
      v243 = v240 & 0x7FFFFF | 0x800000LL;
      if ( v242 < 0x76 )
        v244 = v243 >> (118 - (unsigned __int8)v242);
      else
        v244 = v243 << ((unsigned __int8)v242 - 118);
      v123 = (v244 + 0x80000000LL) >> 32;
      if ( v240 < 0 )
        LODWORD(v123) = -(int)v123;
      v245 = _mm_cvtsi128_si32(v238);
      v246 = (unsigned __int8)(v245 >> 23);
      if ( v246 > 0x9E )
        goto LABEL_397;
      *(float *)v239.m128i_i32 = *(float *)v239.m128i_i32 * v213;
      v247 = v245 & 0x7FFFFF | 0x800000LL;
      if ( v246 < 0x76 )
        v248 = v247 >> (118 - (unsigned __int8)v246);
      else
        v248 = v247 << ((unsigned __int8)v246 - 118);
      v122 = (v248 + 0x80000000LL) >> 32;
      if ( v245 < 0 )
        LODWORD(v122) = -(int)v122;
      if ( (unsigned __int8)(_mm_cvtsi128_si32(v239) >> 23) > 0x9Eu
        || (*(float *)v241.m128i_i32 = *(float *)v241.m128i_i32 * v214,
            (unsigned __int8)(_mm_cvtsi128_si32(v241) >> 23) > 0x9Eu) )
      {
LABEL_397:
        LODWORD(v108) = v320;
        LODWORD(v122) = 0;
        LODWORD(v109) = v319;
        LODWORD(v123) = 0;
      }
      else
      {
        LODWORD(v108) = v320;
        LODWORD(v109) = v319;
      }
    }
    v124 = v123 - v116;
    v125 = v122 - v118;
    if ( (int)v108 > (int)v116 )
      LODWORD(v116) = v108;
    if ( (int)v109 > (int)v118 )
      LODWORD(v118) = v109;
    if ( (int)v317 < (int)v117 )
      LODWORD(v117) = v317;
    if ( (int)v112 < (int)v115 )
      LODWORD(v115) = v112;
    if ( (int)v117 < (int)v116 )
    {
      LODWORD(v116) = v117;
    }
    else if ( (int)v115 < (int)v118 )
    {
      LODWORD(v118) = v115;
    }
    LODWORD(v126) = v124 + v116;
    v127 = v124 + v117;
    v128 = v125 + v118;
    LODWORD(v115) = v125 + v115;
    if ( (int)v313 > v124 + (int)v116 )
      LODWORD(v126) = (_DWORD)v313;
    if ( v343.m128i_i32[0] > v128 )
      v128 = v343.m128i_i32[0];
    if ( (int)v121 < v127 )
      v127 = v121;
    if ( (int)v120 < (int)v115 )
      LODWORD(v115) = v120;
    if ( v127 < (int)v126 )
    {
      LODWORD(v126) = v127;
    }
    else if ( (int)v115 < v128 )
    {
      v128 = v115;
    }
    LODWORD(v129) = v126 - v124;
    LODWORD(v130) = v127 - v124;
    if ( (int)v126 - v124 >= v127 - v124
      || (LODWORD(v131) = v128 - v125, LODWORD(v132) = v115 - v125, v128 - v125 >= (int)v115 - v125) )
    {
      v135 = v327;
      v136 = 0;
    }
    else
    {
      if ( a1 )
      {
        v133 = *a1;
        v134 = *((_DWORD *)*a1 + 130);
        if ( (v134 & 1) != 0 && (v134 & 2) == 0 )
        {
          v249 = *((float *)v133 + 131);
          v250 = _mm_cvtsi32_si128(v130);
          v251 = _mm_cvtsi32_si128(v132);
          v252 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v129);
          *(float *)v252.m128i_i32 = *(float *)v252.m128i_i32 * v249;
          v253 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v131);
          v254 = _mm_cvtsi128_si32(v252);
          v255 = (__m128i)_mm_cvtepi32_ps(v250);
          v256 = (unsigned __int8)(v254 >> 23);
          v257 = (__m128i)_mm_cvtepi32_ps(v251);
          if ( v256 > 0x9E )
            goto LABEL_422;
          v258 = *((float *)v133 + 132);
          *(float *)v253.m128i_i32 = *(float *)v253.m128i_i32 * v258;
          v259 = v254 & 0x7FFFFF | 0x800000LL;
          if ( v256 < 0x76 )
            v260 = v259 >> (118 - (unsigned __int8)v256);
          else
            v260 = v259 << ((unsigned __int8)v256 - 118);
          v129 = (v260 + 0x80000000LL) >> 32;
          if ( v254 < 0 )
            LODWORD(v129) = -(int)v129;
          v261 = _mm_cvtsi128_si32(v253);
          v262 = (unsigned __int8)(v261 >> 23);
          if ( v262 > 0x9E )
            goto LABEL_422;
          *(float *)v255.m128i_i32 = *(float *)v255.m128i_i32 * v249;
          v263 = v261 & 0x7FFFFF | 0x800000LL;
          if ( v262 < 0x76 )
            v264 = v263 >> (118 - (unsigned __int8)v262);
          else
            v264 = v263 << ((unsigned __int8)v262 - 118);
          v131 = (v264 + 0x80000000LL) >> 32;
          if ( v261 < 0 )
            LODWORD(v131) = -(int)v131;
          v265 = _mm_cvtsi128_si32(v255);
          v266 = (unsigned __int8)(v265 >> 23);
          if ( v266 > 0x9E )
            goto LABEL_422;
          *(float *)v257.m128i_i32 = *(float *)v257.m128i_i32 * v258;
          v267 = v265 & 0x7FFFFF | 0x800000LL;
          if ( v266 < 0x76 )
            v268 = v267 >> (118 - (unsigned __int8)v266);
          else
            v268 = v267 << ((unsigned __int8)v266 - 118);
          v130 = (v268 + 0x80000000LL) >> 32;
          if ( v265 < 0 )
            LODWORD(v130) = -(int)v130;
          v269 = _mm_cvtsi128_si32(v257);
          v270 = (unsigned __int8)(v269 >> 23);
          if ( v270 > 0x9E )
          {
LABEL_422:
            LODWORD(v132) = 0;
            LODWORD(v130) = 0;
            LODWORD(v131) = 0;
            LODWORD(v129) = 0;
          }
          else
          {
            v271 = v269 & 0x7FFFFF | 0x800000LL;
            if ( v270 < 0x76 )
              v272 = v271 >> (118 - (unsigned __int8)v270);
            else
              v272 = v271 << ((unsigned __int8)v270 - 118);
            v132 = (v272 + 0x80000000LL) >> 32;
            if ( v269 < 0 )
              LODWORD(v132) = -(int)v132;
          }
        }
      }
      if ( v307 && (v316 & 2) == 0 )
      {
        v273 = _mm_cvtsi32_si128(v127);
        v274 = _mm_cvtsi32_si128(v115);
        v275 = *((float *)v329 + 131);
        v276 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v126);
        *(float *)v276.m128i_i32 = *(float *)v276.m128i_i32 * v275;
        v277 = (__m128i)COERCE_UNSIGNED_INT((float)v128);
        v278 = _mm_cvtsi128_si32(v276);
        v279 = (__m128i)_mm_cvtepi32_ps(v273);
        v280 = (unsigned __int8)(v278 >> 23);
        v281 = (__m128i)_mm_cvtepi32_ps(v274);
        if ( v280 > 0x9E )
          goto LABEL_447;
        v282 = *((float *)v329 + 132);
        *(float *)v277.m128i_i32 = *(float *)v277.m128i_i32 * v282;
        v283 = v278 & 0x7FFFFF | 0x800000LL;
        if ( v280 < 0x76 )
          v284 = v283 >> (118 - (unsigned __int8)v280);
        else
          v284 = v283 << ((unsigned __int8)v280 - 118);
        v126 = (v284 + 0x80000000LL) >> 32;
        if ( v278 < 0 )
          LODWORD(v126) = -(int)v126;
        v285 = _mm_cvtsi128_si32(v277);
        v286 = (unsigned __int8)(v285 >> 23);
        if ( v286 > 0x9E )
          goto LABEL_447;
        *(float *)v279.m128i_i32 = *(float *)v279.m128i_i32 * v275;
        v287 = v285 & 0x7FFFFF | 0x800000LL;
        if ( v286 < 0x76 )
          v288 = v287 >> (118 - (unsigned __int8)v286);
        else
          v288 = v287 << ((unsigned __int8)v286 - 118);
        v289 = (v288 + 0x80000000LL) >> 32;
        if ( v285 < 0 )
          LODWORD(v289) = -(int)v289;
        v290 = _mm_cvtsi128_si32(v279);
        v128 = v289;
        v291 = (unsigned __int8)(v290 >> 23);
        if ( v291 > 0x9E )
          goto LABEL_447;
        *(float *)v281.m128i_i32 = *(float *)v281.m128i_i32 * v282;
        v292 = v290 & 0x7FFFFF | 0x800000LL;
        if ( v291 < 0x76 )
          v293 = v292 >> (118 - (unsigned __int8)v291);
        else
          v293 = v292 << ((unsigned __int8)v291 - 118);
        v294 = (v293 + 0x80000000LL) >> 32;
        if ( v290 < 0 )
          LODWORD(v294) = -(int)v294;
        v295 = _mm_cvtsi128_si32(v281);
        v127 = v294;
        v296 = (unsigned __int8)(v295 >> 23);
        if ( v296 > 0x9E )
        {
LABEL_447:
          LODWORD(v115) = 0;
          v127 = 0;
          v128 = 0;
          LODWORD(v126) = 0;
        }
        else
        {
          v297 = v295 & 0x7FFFFF | 0x800000LL;
          if ( v296 < 0x76 )
            v298 = v297 >> (118 - (unsigned __int8)v296);
          else
            v298 = v297 << ((unsigned __int8)v296 - 118);
          v115 = (v298 + 0x80000000LL) >> 32;
          if ( v295 < 0 )
            LODWORD(v115) = -(int)v115;
        }
      }
      v340.y = v128;
      v135 = v327;
      v339.left = v129;
      v136 = 1;
      v340.x = v126;
      v341 = v127;
      v342 = v115;
      v339.top = v131;
      v339.right = v130;
      v339.bottom = v132;
      ++*((_DWORD *)v327 + 23);
    }
    v27 = a1;
    v137 = *a1;
    v106 = *((_QWORD *)v329 + 6);
    if ( *((_QWORD *)*a1 + 6) == v106 )
      goto LABEL_195;
    if ( (unsigned int)XDCOBJ::bRedirHooked((XDCOBJ *)a1) )
    {
      v137 = *a1;
      v106 = *((_QWORD *)v329 + 6);
      if ( *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) == v106 )
        goto LABEL_195;
    }
    if ( *(_WORD *)(v318 + 100) )
      goto LABEL_269;
    v157 = (SURFOBJ *)(v318 + 24);
    if ( *(_QWORD *)(v318 + 24) )
    {
LABEL_270:
      if ( v136 )
      {
        v158 = v337;
        if ( (*(_DWORD *)(*((_QWORD *)v135 + 6) + 40LL) & 0x80u) == 0 )
          v158 = 0;
        v300 = SimBitBlt(
                 (SURFOBJ *)((char *)v135 + 24),
                 v157,
                 v312,
                 &v339,
                 &v340,
                 0,
                 v325,
                 (POINTL *)*a1 + 149,
                 v321,
                 (__int64)v158);
      }
    }
    else
    {
      v137 = *a1;
      v106 = *(unsigned int *)(*((_QWORD *)*a1 + 6) + 40LL);
      if ( (v106 & 0x80u) != 0LL )
      {
LABEL_269:
        v157 = v328;
        goto LABEL_270;
      }
LABEL_195:
      if ( v321 == 52428 )
      {
        v138 = *((_QWORD *)v135 + 6);
        v139 = a11 & 1;
        if ( v139 )
        {
          v160 = v309 - v302;
          if ( v309 - v302 < 0 )
            v160 = v302 - v309;
          v161 = v302 - v315;
          if ( v302 - v315 < 0 )
            v161 = v315 - v302;
          EtwWindowRendering(
            *((_QWORD *)v137 + 58),
            *((_QWORD *)v137 + 59),
            **((_QWORD **)v137 + 62),
            v299,
            v309,
            v315,
            v302,
            *((_QWORD *)v329 + 58),
            *((_QWORD *)v329 + 59),
            **((_QWORD **)v329 + 62),
            v304,
            v310,
            v304 + v161,
            v310 + v160);
          *((_WORD *)v135 + 51) |= 0x40u;
          v162 = GreGetCurrentThread();
          if ( v162 )
            *((_DWORD *)v162 + 84) &= ~1u;
          GreClientRgnUpdated(0);
          GreClientRgnUpdatedStable();
        }
        if ( v136 )
        {
          if ( (*((_DWORD *)v135 + 40) & 0x400) != 0 )
            v140 = (*(__int64 (__fastcall **)(__int64, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *))(v138 + 2832))(
                     (__int64)v135 + 24,
                     v328,
                     v324,
                     v312,
                     &v339,
                     &v340);
          else
            v140 = ((__int64 (__fastcall *)(char *, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *))EngCopyBits)(
                     (char *)v135 + 24,
                     v328,
                     v324,
                     v312,
                     &v339,
                     &v340);
          v300 = v140;
        }
        if ( v139 )
        {
          *((_WORD *)v135 + 51) &= ~0x40u;
          v163 = GreGetCurrentThread();
          if ( v163 )
            *((_DWORD *)v163 + 84) |= 1u;
        }
      }
      else if ( v136 )
      {
        v145 = SURFACE::pfnBitBlt(v135);
        v300 = ((__int64 (__fastcall *)(char *, __int64, _QWORD, char *, XLATEOBJ *, RECTL *, POINTL *, _QWORD, __int64, __int64, int))v145)(
                 (char *)v135 + 24,
                 v147 + 24,
                 0,
                 v324,
                 v312,
                 &v339,
                 &v340,
                 0,
                 v325,
                 v146 + 1192,
                 v148);
      }
    }
  }
  if ( v97 )
  {
    cEntries = v97[1].cEntries;
    if ( cEntries >= 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)Gre::Base::Globals((Gre::Base *)v106) + 8 * (int)v97[1].cEntries
                                                                                             + 1100);
    }
    else if ( cEntries == -1 )
    {
      FreeThreadBufferWithTag(v97);
    }
  }
LABEL_54:
  DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v337);
  v19 = v300;
LABEL_55:
  if ( v322 )
    DC::dwSetLayout(*v27, -1, v323);
  v41 = v329;
  if ( !v335 )
    v41 = 0;
  v329 = v41;
  PopThreadGuardedObject(v334);
  v42 = v329;
  if ( v329 )
  {
    if ( v330 && (*((_DWORD *)v329 + 11) & 2) != 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v45 = v329;
      v46 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v329 )
      {
        v47 = (char *)HmgPentryFromPobj(v331, v329);
      }
      else
      {
        v47 = (char *)v329 + 2152;
        *(_OWORD *)((char *)v329 + 2152) = 0;
        *((_QWORD *)v45 + 271) = 0;
        *((_DWORD *)v45 + 540) = -2147483630;
        *((_QWORD *)v45 + 271) = GreEncodeUserModePointer(0);
      }
      if ( v46 == (*((_DWORD *)v47 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v329);
        if ( UserAttr )
          DC::RestoreAttributes(v329, UserAttr);
      }
      *((_DWORD *)v329 + 11) &= ~2u;
      v42 = v329;
      v330 = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)v42 + 6);
    v329 = 0;
  }
  PopThreadGuardedObject(v333);
LABEL_61:
  if ( v18 )
  {
    v164 = GreGetCurrentThread();
    *((_DWORD *)v164 + 84) &= ~8u;
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
