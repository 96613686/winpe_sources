# GrepBitBltImpl(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,ulong,ulong,ulong)

- ea: `0x140062340`
- end: `0x140064875`
- name: `?GrepBitBltImpl@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHKKK@Z`
- size: `9525`
- prototype: `__int64 __fastcall(struct XDCOBJ *, int, int, int, int, struct OPTAPIDCOBJ *, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140060360`
- `0x140060630`
- `0x1401a0c80`

## callees

- `0x1400512b0`
- `0x140051df0`
- `0x140051efc`
- `0x140052618`
- `0x140057fe0`
- `0x140060b1c`
- `0x140062138`
- `0x140062340`
- `0x14006487c`
- `0x140065000`
- `0x140067498`
- `0x1400697e4`
- `0x14006b59c`
- `0x140098cc8`
- `0x1400990a4`
- `0x14009b5c8`
- `0x14009be70`
- `0x14009d1d0`
- `0x140252b28`
- `0x140264c24`
- `0x140298e04`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140062af2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140062af2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400627f2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140062893`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140062ba6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140062f67`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140063055`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400631d7`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400637a1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400627f2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140062893`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140062ba6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140062f67`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140063055`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400631d7`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400637a1`
- `win32kbase!HmgPentryFromPobj` at `0x140062b19`
- `win32kbase!HmgPentryFromPobj` at `0x140062b19`
- `win32kbase!PopThreadGuardedObject` at `0x140062aa2`
- `win32kbase!PopThreadGuardedObject` at `0x140062abb`
- `win32kbase!PopThreadGuardedObject` at `0x1400630c4`
- `win32kbase!PopThreadGuardedObject` at `0x140062aa2`
- `win32kbase!PopThreadGuardedObject` at `0x140062abb`
- `win32kbase!PopThreadGuardedObject` at `0x1400630c4`
- `win32kbase!PushThreadGuardedObject` at `0x140062460`
- `win32kbase!PushThreadGuardedObject` at `0x140062486`
- `win32kbase!PushThreadGuardedObject` at `0x14006283f`
- `win32kbase!PushThreadGuardedObject` at `0x140062871`
- `win32kbase!PushThreadGuardedObject` at `0x1400628e0`
- `win32kbase!PushThreadGuardedObject` at `0x140062912`
- `win32kbase!PushThreadGuardedObject` at `0x140062460`
- `win32kbase!PushThreadGuardedObject` at `0x140062486`
- `win32kbase!PushThreadGuardedObject` at `0x14006283f`
- `win32kbase!PushThreadGuardedObject` at `0x140062871`
- `win32kbase!PushThreadGuardedObject` at `0x1400628e0`
- `win32kbase!PushThreadGuardedObject` at `0x140062912`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400630b4`
- `win32kbase!FreeThreadBufferWithTag` at `0x14006350a`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400630b4`
- `win32kbase!FreeThreadBufferWithTag` at `0x14006350a`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140063866`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006388f`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140063866`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006388f`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140063856`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14006387f`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140063856`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14006387f`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140063917`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140063937`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140063917`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140063937`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140063907`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140063927`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140063907`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140063927`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400638b2`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400638b2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006357f`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006357f`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400638cd`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400638cd`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400638e5`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1400638e5`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140062f87`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140062f87`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140063061`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140062b4f`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140062b4f`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140062b37`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140062b37`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006483c`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006483c`
- `win32kbase!EngSetLastError` at `0x140063965`
- `win32kbase!EngSetLastError` at `0x140063965`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140062503`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140062520`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140062503`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140062520`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140063a22`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140063a22`
- `win32kbase!GreDCSelectBrush` at `0x1400639b9`
- `win32kbase!GreDCSelectBrush` at `0x1400639b9`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140062a7f`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140063ce7`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140062a7f`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140063ce7`
- `win32kbase!?bEqualExceptTranslations@EXFORMOBJ@@QEBA_NPEBUMATRIX@@@Z` at `0x140062545`
- `win32kbase!?bEqualExceptTranslations@EXFORMOBJ@@QEBA_NPEBUMATRIX@@@Z` at `0x140062545`
- `win32kbase!EtwWindowRendering` at `0x140063c22`
- `win32kbase!EtwWindowRendering` at `0x140063c22`
- `win32kbase!UserSurfaceAccessCheck` at `0x140063631`
- `win32kbase!UserSurfaceAccessCheck` at `0x140063631`
- `win32kbase!UserScreenAccessCheck` at `0x140062c25`
- `win32kbase!UserScreenAccessCheck` at `0x140062c25`

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
  Gre::Base *v35; // rcx
  struct Gre::Base::SESSION_GLOBALS *v36; // rax
  Gre::Base *v37; // rcx
  struct Gre::Base::SESSION_GLOBALS *v38; // rax
  DC *v39; // r8
  __int64 v40; // rbx
  __int64 v41; // r14
  __int64 v42; // r12
  Gre::Base *v43; // rcx
  DC *v44; // rcx
  DC *v45; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v48; // rdi
  unsigned int v49; // ebx
  char *v50; // r14
  struct _DC_ATTR *UserAttr; // rax
  struct Gre::Base::SESSION_GLOBALS *v52; // rax
  __int64 v53; // r10
  int v54; // eax
  int v55; // eax
  int v56; // r9d
  int v57; // r15d
  LONG v58; // r8d
  __int64 v59; // rcx
  __int64 v60; // rbx
  __int64 v61; // rax
  int v62; // edx
  int v63; // edi
  int v64; // r13d
  LONG v65; // ecx
  LONG v66; // edx
  LONG v67; // ecx
  LONG v68; // r9d
  DC **v69; // rcx
  DC *v70; // rax
  __m128i v71; // xmm2
  DC *v72; // rcx
  int v73; // r10d
  __int64 v74; // rax
  LONG v75; // r9d
  int v76; // edx
  int v77; // r8d
  LONG v78; // r11d
  int v79; // eax
  LONG v80; // r10d
  DC *v81; // r8
  unsigned __int64 v82; // rcx
  unsigned int v83; // edi
  __int64 v84; // rax
  int v85; // edx
  __int64 v86; // rax
  bool v87; // zf
  __int64 v88; // rdx
  XLATEOBJ *v89; // r15
  __int64 v90; // rax
  Gre::Base *v91; // rcx
  int v92; // eax
  unsigned int v93; // r14d
  struct Gre::Base::SESSION_GLOBALS *v94; // r15
  unsigned int i; // r8d
  __int64 v96; // rdx
  __int64 XlateObject; // rax
  Gre::Base *v98; // rcx
  XLATEOBJ *v99; // rdi
  struct Gre::Base::SESSION_GLOBALS *v100; // r14
  unsigned int j; // r8d
  unsigned int v102; // edx
  __int64 v103; // rax
  __int64 v104; // rcx
  __int64 v105; // rdx
  int v106; // eax
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r11
  __int64 v110; // r10
  __int64 v111; // rbx
  unsigned int v112; // edx
  __int64 v113; // r13
  unsigned int v114; // ecx
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // r12
  __int64 v118; // r15
  __int64 v119; // r14
  int v120; // r9d
  __int64 v121; // r9
  __int64 v122; // rbx
  __int64 v123; // rcx
  __int64 v124; // r8
  int v125; // r8d
  int v126; // ecx
  __int64 v127; // r10
  signed int v128; // r14d
  int v129; // r15d
  __int64 v130; // rbx
  __int64 v131; // r9
  __int64 v132; // r11
  __int64 v133; // r8
  DC *v134; // rcx
  int v135; // eax
  SURFACE *v136; // r15
  char v137; // bl
  DC *v138; // r11
  int v139; // r14d
  __int64 v140; // r14
  int v141; // r13d
  int v142; // eax
  int cEntries; // eax
  __int64 v144; // rax
  char *v145; // r15
  struct REGION *v146; // rax
  int (*v147)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  __int64 v148; // r11
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // r9
  __int64 v152; // rax
  int v153; // edx
  XLATEOBJ *v154; // rax
  __int64 v155; // rdx
  char *v156; // r15
  __int64 v157; // rdx
  int v158; // ecx
  SURFOBJ *v159; // r11
  _OWORD *v160; // rdx
  unsigned int v161; // ebx
  int v162; // r10d
  int v163; // ecx
  struct _GRETHREAD *v164; // rax
  struct _GRETHREAD *v165; // rax
  struct _GRETHREAD *v166; // rax
  struct _GRETHREAD *CurrentThread; // rax
  int v168; // ebx
  int v169; // edx
  BOOL v170; // eax
  _DWORD *v171; // rcx
  _DWORD *v172; // rcx
  struct _GRETHREAD *v173; // rax
  __m128i v174; // xmm2
  __m128i v175; // xmm0
  __m128i v176; // xmm4
  int v177; // r8d
  unsigned int v178; // edx
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
  int v195; // r8d
  unsigned int v196; // edx
  __m128i v197; // xmm0
  __int64 v198; // rax
  __int64 v199; // rax
  int v200; // r8d
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
  __m128i v212; // xmm4
  float v213; // xmm6_4
  __m128i v214; // xmm0
  __m128i v215; // xmm1
  int v216; // r9d
  unsigned int v217; // r8d
  __m128i v218; // xmm3
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rax
  int v222; // r9d
  unsigned int v223; // r8d
  __int64 v224; // rax
  __int64 v225; // rax
  __int64 v226; // r11
  int v227; // r9d
  unsigned int v228; // r8d
  __int64 v229; // rax
  __int64 v230; // rax
  int v231; // r10d
  unsigned int v232; // r8d
  __int64 v233; // rax
  __int64 v234; // rax
  __m128i v235; // xmm0
  __m128i v236; // xmm1
  int v237; // r10d
  __m128i v238; // xmm2
  unsigned int v239; // r8d
  __int64 v240; // rax
  __int64 v241; // rax
  int v242; // r11d
  unsigned int v243; // r10d
  __int64 v244; // rax
  __int64 v245; // rax
  float v246; // xmm3_4
  __m128i v247; // xmm2
  __m128i v248; // xmm4
  __m128i v249; // xmm0
  __m128i v250; // xmm1
  int v251; // r9d
  __m128i v252; // xmm2
  unsigned int v253; // r8d
  __m128i v254; // xmm4
  float v255; // xmm0_4
  __int64 v256; // rax
  __int64 v257; // rax
  int v258; // r9d
  unsigned int v259; // r8d
  __int64 v260; // rax
  __int64 v261; // rax
  int v262; // r12d
  unsigned int v263; // r8d
  __int64 v264; // rax
  __int64 v265; // rax
  int v266; // r12d
  unsigned int v267; // r8d
  __int64 v268; // rax
  __int64 v269; // rax
  __m128i v270; // xmm4
  __m128i v271; // xmm5
  __m128i v272; // xmm1
  __m128i v273; // xmm0
  int v274; // r14d
  float v275; // xmm4_4
  unsigned int v276; // edx
  float v277; // xmm5_4
  __m128i v278; // xmm2
  __int64 v279; // rax
  __m128i v280; // xmm0
  __int64 v281; // rax
  int v282; // r14d
  unsigned int v283; // edx
  __int64 v284; // rax
  __int64 v285; // rax
  __int64 v286; // rcx
  int v287; // r14d
  unsigned int v288; // edx
  __int64 v289; // rax
  __int64 v290; // rax
  __int64 v291; // rcx
  int v292; // r12d
  unsigned int v293; // ecx
  __int64 v294; // rax
  __int64 v295; // rax
  int v296; // [rsp+70h] [rbp-90h]
  unsigned int v297; // [rsp+74h] [rbp-8Ch]
  int v298; // [rsp+78h] [rbp-88h]
  LONG v299; // [rsp+78h] [rbp-88h]
  LONG v301; // [rsp+88h] [rbp-78h]
  unsigned int v302; // [rsp+88h] [rbp-78h]
  int v303; // [rsp+8Ch] [rbp-74h]
  int v304; // [rsp+8Ch] [rbp-74h]
  int v305; // [rsp+90h] [rbp-70h]
  LONG v306; // [rsp+90h] [rbp-70h]
  LONG v307; // [rsp+94h] [rbp-6Ch]
  int v308; // [rsp+94h] [rbp-6Ch]
  XLATEOBJ *v309; // [rsp+98h] [rbp-68h] BYREF
  OPTAPIDCOBJ *v310; // [rsp+A0h] [rbp-60h]
  __int64 v311; // [rsp+A8h] [rbp-58h] BYREF
  LONG v312; // [rsp+B0h] [rbp-50h]
  __int64 v313; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v314; // [rsp+C0h] [rbp-40h]
  __int64 v315; // [rsp+C8h] [rbp-38h]
  __int64 v316; // [rsp+D0h] [rbp-30h]
  __int64 v317; // [rsp+D8h] [rbp-28h]
  int v318; // [rsp+E0h] [rbp-20h]
  unsigned int v319; // [rsp+E4h] [rbp-1Ch]
  unsigned int v320; // [rsp+E8h] [rbp-18h]
  __int64 v321; // [rsp+F0h] [rbp-10h]
  char *v322; // [rsp+F8h] [rbp-8h]
  __int64 v323; // [rsp+100h] [rbp+0h] BYREF
  SURFACE *v324; // [rsp+108h] [rbp+8h]
  SURFOBJ *v325; // [rsp+110h] [rbp+10h]
  DC *v326; // [rsp+120h] [rbp+20h] BYREF
  int v327; // [rsp+128h] [rbp+28h]
  __int64 v328; // [rsp+130h] [rbp+30h]
  __int64 v329; // [rsp+138h] [rbp+38h]
  _OWORD v330[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v331[2]; // [rsp+160h] [rbp+60h] BYREF
  char v332; // [rsp+180h] [rbp+80h]
  const struct MATRIX *v333; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v334[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v335; // [rsp+1C0h] [rbp+C0h]
  char v336[24]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v337; // [rsp+1E0h] [rbp+E0h]
  int v338; // [rsp+1F0h] [rbp+F0h]
  __int64 v339; // [rsp+1F8h] [rbp+F8h] BYREF
  int v340; // [rsp+200h] [rbp+100h]
  struct Gre::Base::SESSION_GLOBALS *v341; // [rsp+208h] [rbp+108h]
  __int64 v342; // [rsp+210h] [rbp+110h]
  _OWORD v343[2]; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v344[2]; // [rsp+238h] [rbp+138h] BYREF
  __int16 v345; // [rsp+258h] [rbp+158h]
  __int64 v346; // [rsp+260h] [rbp+160h] BYREF
  int v347; // [rsp+268h] [rbp+168h]
  struct Gre::Base::SESSION_GLOBALS *v348; // [rsp+270h] [rbp+170h]
  __int64 v349; // [rsp+278h] [rbp+178h]
  _OWORD v350[2]; // [rsp+280h] [rbp+180h] BYREF
  _OWORD v351[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v352; // [rsp+2C0h] [rbp+1C0h]
  __int64 v353; // [rsp+2C8h] [rbp+1C8h]
  __int128 v354; // [rsp+2D0h] [rbp+1D0h]
  __int64 v355; // [rsp+2E0h] [rbp+1E0h]
  __int64 v356; // [rsp+2E8h] [rbp+1E8h]
  __int64 v357; // [rsp+2F0h] [rbp+1F0h]
  __int64 v358; // [rsp+2F8h] [rbp+1F8h]
  __int64 v359; // [rsp+300h] [rbp+200h]
  RECTL v360; // [rsp+310h] [rbp+210h] BYREF
  POINTL v361; // [rsp+320h] [rbp+220h] BYREF
  int v362; // [rsp+328h] [rbp+228h]
  int v363; // [rsp+32Ch] [rbp+22Ch]
  __m128i v364; // [rsp+330h] [rbp+230h] BYREF

  v11 = (struct XDCOBJ *)a1;
  x = a7;
  v14 = a5;
  y = a8;
  v17 = a6;
  v310 = a6;
  v298 = a4;
  if ( (a11 & 4) != 0
    && (CurrentThread = GreGetCurrentThread(), v17 = v310, a4 = v298, v14 = a5, v11 = (struct XDCOBJ *)a1, CurrentThread) )
  {
    *((_DWORD *)CurrentThread + 84) |= 8u;
    v18 = 1;
  }
  else
  {
    v18 = 0;
  }
  if ( (a9 & 0x40000000) == 0 )
  {
    v19 = 0;
    v296 = 0;
    if ( (*(_DWORD *)(*(_QWORD *)v11 + 36LL) & 0x10000) == 0 )
    {
      v20 = a9 & 0x5FFFFFFF;
      if ( ((*((_BYTE *)gajRop3 + (unsigned __int8)a9) | *((_BYTE *)gajRop3 + BYTE1(a9))) & 2) != 0
        && v20 != 16711778
        && v20 != 66 )
      {
        bSpDwmValidateSurface(v11, left, top, a4, v14);
      }
      if ( OPTAPIDCOBJ::bValid(v310) )
      {
        memset(v330, 0, sizeof(v330));
        v328 = *((_QWORD *)v310 + 2);
        v329 = 0;
        v326 = 0;
        v327 = 0;
        PushThreadGuardedObject(
          v330,
          &v326,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v331, 0, sizeof(v331));
        PushThreadGuardedObject(
          v331,
          &v326,
          UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
        v332 = 0;
        v326 = *(DC **)v310;
        bSpDwmValidateSurface((struct XDCOBJ *)&v326, a7, a8, v298, a5);
        v21 = *((_QWORD *)*a1 + 122);
        v22 = *(_DWORD *)(v21 + 108);
        if ( ((*(_BYTE *)(*((_QWORD *)v326 + 122) + 108LL) ^ *(_BYTE *)(v21 + 108)) & 7) != 0
          && (a9 < 0 && (v22 & 1) != 0 || (v22 & 9) == 9) )
        {
          v168 = *(_DWORD *)(v21 + 308);
          v320 = DC::dwSetLayout(*a1, -1, 0);
          left = v168 - v298 - left;
          v319 = 0x80000000;
        }
        else
        {
          v320 = 0;
          v319 = 0;
        }
        DC::QuickInitXform(*a1, &v323, 516);
        DC::QuickInitXform(v326, &v333, 516);
        if ( (*(_BYTE *)(v323 + 32) & 1) == 0 || !EXFORMOBJ::bEqualExceptTranslations((EXFORMOBJ *)&v323, v333) )
        {
          v27 = a1;
          v19 = GrepStretchBlt((struct XDCOBJ *)a1, left, top, v298, a5, v310, a7, a8, v298, a5, v20, a10, 0);
          goto LABEL_55;
        }
        v23 = a8 + a5;
        v321 = (__int64)v326;
        v24 = a7 + v298;
        v361.x = a7;
        v362 = a7 + v298;
        v361.y = a8;
        v363 = a8 + a5;
        if ( (*((_BYTE *)v333 + 32) & 0x43) == 0x43
          || (v25 = bCvtPts1(v333, &v361, 2), v23 = v363, v24 = v362, y = v361.y, x = v361.x, v25) )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(v321 + 976) + 108LL) & 1) != 0 )
          {
            ++x;
            ++v24;
            v361.x = x;
            v362 = v24;
          }
        }
        if ( x > v24 )
        {
          v361.x = v24;
          v362 = x;
        }
        if ( y > v23 )
        {
          v361.y = v23;
          v363 = y;
        }
        right = v298 + left;
        v27 = a1;
        v360.bottom = top + a5;
        v360.left = left;
        v360.top = top;
        v28 = *a1;
        v360.right = v298 + left;
        if ( (*(_BYTE *)(v323 + 32) & 0x43) == 0x43
          || (v29 = bCvtPts1(v323, &v360, 2), right = v360.right, top = v360.top, left = v360.left, v29) )
        {
          if ( (*(_DWORD *)(*((_QWORD *)v28 + 122) + 108LL) & 1) != 0 )
          {
            ++left;
            ++right;
            v360.left = left;
            v360.right = right;
          }
        }
        if ( left > right )
        {
          v30 = left;
          v360.left = right;
          left = right;
          v360.right = v30;
          right = v30;
        }
        bottom = v360.bottom;
        if ( top > v360.bottom )
        {
          v360.top = v360.bottom;
          v360.bottom = top;
          top = bottom;
        }
        if ( top == v360.bottom || left == right )
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
              right = v360.right;
              top = v360.top;
              left = v360.left;
            }
            if ( top < *((_DWORD *)v32 + 267) )
            {
              *((_DWORD *)v32 + 267) = top;
              right = v360.right;
              top = v360.top;
              left = v360.left;
            }
            if ( right > *((_DWORD *)v32 + 268) )
            {
              *((_DWORD *)v32 + 268) = right;
              right = v360.right;
              top = v360.top;
              left = v360.left;
            }
            if ( v360.bottom > *((_DWORD *)v32 + 269) )
            {
              *((_DWORD *)v32 + 269) = v360.bottom;
              right = v360.right;
              top = v360.top;
              left = v360.left;
            }
          }
          v34 = *a1;
          if ( (*((_DWORD *)*a1 + 9) & 0x80u) != 0 )
          {
            if ( left < *((_DWORD *)v34 + 274) )
            {
              *((_DWORD *)v34 + 274) = left;
              right = v360.right;
              top = v360.top;
            }
            if ( top < *((_DWORD *)v34 + 275) )
            {
              *((_DWORD *)v34 + 275) = top;
              right = v360.right;
            }
            if ( right > *((_DWORD *)v34 + 276) )
              *((_DWORD *)v34 + 276) = right;
            if ( v360.bottom > *((_DWORD *)v34 + 277) )
              *((_DWORD *)v34 + 277) = v360.bottom;
          }
        }
        SURFMEM::SURFMEM(v336, 2);
        v339 = 0;
        v340 = 0;
        v36 = Gre::Base::Globals(v35);
        v342 = 0;
        v341 = v36;
        v339 = 0;
        v340 = 0;
        memset(v343, 0, sizeof(v343));
        PushThreadGuardedObject(
          v343,
          &v339,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v344, 0, sizeof(v344));
        PushThreadGuardedObject(
          v344,
          &v339,
          UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic);
        v345 = 256;
        v346 = 0;
        v347 = 0;
        v38 = Gre::Base::Globals(v37);
        v349 = 0;
        v348 = v38;
        v346 = 0;
        v347 = 0;
        memset(v350, 0, sizeof(v350));
        PushThreadGuardedObject(
          v350,
          &v346,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v351, 0, sizeof(v351));
        PushThreadGuardedObject(
          v351,
          &v346,
          UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic);
        v352 = 256;
        memset(v334, 0, sizeof(v334));
        v337 = 0;
        v354 = 0;
        v359 = 0;
        v335 = 0;
        v338 = 0;
        v353 = 0;
        v355 = 0;
        v358 = 0;
        v356 = 0;
        v357 = 0;
        v339 = 0;
        v346 = 0;
        if ( !(unsigned int)DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v334, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v326) )
        {
          v169 = XDCOBJ::bFullScreen((XDCOBJ *)a1);
          v170 = !*((_QWORD *)v326 + 62) || (unsigned int)DC::bInFullScreen(v326);
          v296 = v169 | v170;
          goto LABEL_54;
        }
        v39 = *a1;
        v40 = *((_QWORD *)*a1 + 62);
        v324 = (SURFACE *)v40;
        if ( !v40 )
        {
          v296 = 1;
          goto LABEL_54;
        }
        v41 = *((_QWORD *)v39 + 11);
        v42 = *(_QWORD *)(v40 + 160);
        v314 = v41;
        v318 = BYTE2(v20) | (BYTE2(v20) << 8);
        if ( ((BYTE2(v20) ^ (unsigned __int8)(16 * BYTE2(v20))) & 0xF0) != 0 )
        {
          v155 = *((_QWORD *)v39 + 122);
          v156 = (char *)v39 + 1200;
          v321 = (__int64)v39 + 1200;
          if ( (*(_DWORD *)(v155 + 152) & 0x1000) != 0 )
            GreDCSelectBrush(v39, *(_QWORD *)(v155 + 160));
          v39 = *a1;
          v157 = *((_QWORD *)*a1 + 122);
          v158 = *(_DWORD *)(v157 + 152);
          if ( (v158 & 1) != 0 || (*((_DWORD *)v39 + 79) & 1) != 0 )
          {
            *(_DWORD *)(v157 + 152) = v158 & 0xFFFFFFFE;
            *((_DWORD *)*a1 + 79) &= ~1u;
            EBRUSHOBJ::vInitBrush(v156, *a1, *((_QWORD *)*a1 + 17), v41, v42, v40, 1);
            v39 = *a1;
          }
        }
        else
        {
          v321 = 0;
        }
        v43 = (Gre::Base *)(*((_DWORD *)v39 + 10) & 1);
        v360.left += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 254);
        v360.right += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 254);
        v360.top += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 255);
        v360.bottom += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 255);
        if ( !*((_QWORD *)v326 + 62) )
          goto LABEL_53;
        v52 = Gre::Base::Globals(v43);
        v53 = *((_QWORD *)v326 + 62);
        if ( v53 )
        {
          if ( v329 )
            v53 = v329;
        }
        else
        {
          v53 = *((_QWORD *)v52 + 547);
        }
        v315 = v53;
        if ( !v53 )
          goto LABEL_53;
        if ( (a11 & 2) == 0 )
        {
          if ( (v338 & 0x400000) == 0
            || ((*(_DWORD *)(v40 + 148) & 8) != 0 || *(_QWORD *)(v40 + 256))
            && _bittest16((const signed __int16 *)(v40 + 102), 9u) )
          {
            goto LABEL_256;
          }
          v54 = *(_DWORD *)(v40 + 144);
          if ( (v54 & 0x800) != 0 )
          {
            v55 = UserSurfaceAccessCheck(*(_QWORD *)(v40 + 680));
          }
          else
          {
            if ( (v54 & 0x10000000) == 0 )
              goto LABEL_85;
            v55 = UserScreenAccessCheck();
          }
          if ( !v55 )
          {
LABEL_256:
            EngSetLastError(6u);
            v27 = a1;
            goto LABEL_54;
          }
          v53 = v315;
        }
LABEL_85:
        v56 = 0;
        v57 = v360.left;
        v58 = v360.top;
        v59 = *(_QWORD *)(v53 + 48);
        v60 = *(_QWORD *)(v53 + 160);
        v61 = *((_DWORD *)v326 + 10) & 1;
        v62 = 0;
        v63 = v360.top - *((_DWORD *)v326 + 2 * v61 + 255) - v361.y;
        v64 = v360.left - *((_DWORD *)v326 + 2 * v61 + 254) - v361.x;
        v305 = v63;
        v325 = (SURFOBJ *)(v53 + 24);
        if ( v59 && v53 == *(_QWORD *)(v59 + 2544) && (*(_DWORD *)(v59 + 40) & 0x20000) != 0 )
        {
          v62 = *(_DWORD *)(v59 + 2576);
          v56 = *(_DWORD *)(v59 + 2580);
        }
        if ( v62 + v64 > v360.left )
          v57 = v62 + v64;
        v360.left = v57;
        v297 = v57;
        if ( v63 + v56 > v360.top )
          v58 = v63 + v56;
        v360.top = v58;
        v65 = v62 + v64 + *(_DWORD *)(v53 + 56);
        v66 = v360.right;
        if ( v65 < v360.right )
          v66 = v65;
        v360.right = v66;
        v67 = v56 + v63 + *(_DWORD *)(v53 + 60);
        v68 = v360.bottom;
        if ( v67 < v360.bottom )
          v68 = v67;
        v360.bottom = v68;
        if ( v57 < v66 && v58 < v68 )
        {
          v69 = a1;
          v70 = *a1;
          if ( v57 >= *((_DWORD *)*a1 + 250) && v66 <= *((_DWORD *)v70 + 252) && v58 >= *((_DWORD *)v70 + 251) )
          {
            v322 = 0;
            if ( v68 <= *((_DWORD *)v70 + 253) )
            {
              v71 = (__m128i)v360;
LABEL_102:
              v72 = *v69;
              v73 = *((_DWORD *)v72 + 9);
              if ( (v73 & 0xE0) == 0 )
                goto LABEL_116;
              v364 = v71;
              v74 = *((_DWORD *)v72 + 10) & 1;
              v75 = v57 - *((_DWORD *)v72 + 2 * v74 + 254);
              v364.m128i_i32[0] = v75;
              v76 = v71.m128i_i32[2] - *((_DWORD *)v72 + 2 * v74 + 254);
              v364.m128i_i32[2] = v76;
              v77 = v71.m128i_i32[1] - *((_DWORD *)v72 + 2 * v74 + 255);
              v364.m128i_i32[1] = v77;
              v364.m128i_i32[3] = v71.m128i_i32[3] - *((_DWORD *)v72 + 2 * v74 + 255);
              if ( (v73 & 0x40) == 0 )
                goto LABEL_116;
              v78 = *((_DWORD *)v72 + 270);
              v79 = *((_DWORD *)v72 + 272);
              if ( v78 == v79 || (v80 = *((_DWORD *)v72 + 273), *((_DWORD *)v72 + 271) == v80) )
              {
                *(__m128i *)((char *)v72 + 1080) = v364;
              }
              else
              {
                if ( v75 < v78 )
                {
                  *((_DWORD *)v72 + 270) = v75;
                  v57 = v360.left;
                  v76 = v364.m128i_i32[2];
                  v77 = v364.m128i_i32[1];
                  v297 = v360.left;
                }
                if ( v77 < *((_DWORD *)v72 + 271) )
                {
                  *((_DWORD *)v72 + 271) = v77;
                  v57 = v360.left;
                  v76 = v364.m128i_i32[2];
                  v297 = v360.left;
                }
                if ( v76 > v79 )
                {
                  *((_DWORD *)v72 + 272) = v76;
                  v57 = v360.left;
                  v297 = v360.left;
                }
                if ( v364.m128i_i32[3] <= v80 )
                  goto LABEL_115;
                *((_DWORD *)v72 + 273) = v364.m128i_i32[3];
              }
              v57 = v360.left;
              v297 = v360.left;
LABEL_115:
              v309 = (XLATEOBJ *)*((_QWORD *)*a1 + 148);
              if ( v309 )
              {
                v311 = 0;
                RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v311, 0x70u);
                RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v311);
                v313 = 0;
                RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v313, 0x70u);
                RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v313);
                if ( v311 )
                {
                  if ( v313 )
                  {
                    RGNOBJ::vSet((RGNOBJ *)&v313, (const struct _RECTL *const)&v364);
                    if ( RGNOBJ::bMerge((RGNOBJ *)&v311, (struct RGNOBJ *)&v309, (struct RGNOBJ *)&v313, 0xEu) )
                    {
                      RGNOBJ::vSwap((RGNOBJ *)&v309, (struct RGNOBJ *)&v311);
                      *((_QWORD *)*a1 + 148) = v309;
                    }
                  }
                }
                RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v313);
                RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v313);
                RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v311);
                RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v311);
                v57 = v360.left;
                v297 = v360.left;
              }
LABEL_116:
              v361.x = v57 - v64;
              v301 = v57 - v64;
              v81 = *a1;
              v82 = (unsigned int)(v360.top - v63);
              v361.y = v360.top - v63;
              v307 = v360.top - v63;
              if ( v315 == *((_QWORD *)v81 + 62) )
              {
                v99 = 0;
                v296 = 1;
                v27 = a1;
LABEL_165:
                LODWORD(v109) = 0;
                LODWORD(v110) = 0;
                v306 = v360.top;
                v312 = v360.right;
                v309 = v99;
                v299 = v360.bottom;
                v317 = 0;
                v316 = 0;
                if ( *((int *)v324 + 36) < 0 )
                {
                  v171 = (_DWORD *)*((_QWORD *)v324 + 6);
                  if ( v171 )
                  {
                    if ( (v171[10] & 0x20000) != 0 )
                    {
                      LODWORD(v109) = v171[644];
                      v110 = (unsigned int)v171[645];
                      v317 = (unsigned int)v109;
                      v316 = v110;
                    }
                  }
                }
                LODWORD(v111) = 0;
                v112 = 0;
                LODWORD(v113) = v110 + *((_DWORD *)v324 + 15);
                v314 = (unsigned int)(v109 + *((_DWORD *)v324 + 14));
                v310 = 0;
                v364.m128i_i64[0] = 0;
                if ( *(int *)(v315 + 144) < 0 )
                {
                  v172 = *(_DWORD **)(v315 + 48);
                  if ( v172 )
                  {
                    if ( (v172[10] & 0x20000) != 0 )
                    {
                      v112 = v172[644];
                      v111 = (unsigned int)v172[645];
                      v310 = (OPTAPIDCOBJ *)v112;
                      v364.m128i_i64[0] = v111;
                    }
                  }
                }
                v114 = v112 + *(_DWORD *)(v315 + 56);
                LODWORD(v311) = v111 + *(_DWORD *)(v315 + 60);
                if ( v27 && (v115 = *((_DWORD *)v81 + 130), (v115 & 1) != 0) && (v115 & 2) == 0 )
                {
                  v174 = (__m128i)LODWORD(FLOAT_1_0);
                  *(float *)v174.m128i_i32 = 1.0 / *((float *)v81 + 131);
                  v175 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v109);
                  v176 = (__m128i)LODWORD(FLOAT_1_0);
                  *(float *)v176.m128i_i32 = 1.0 / *((float *)v81 + 132);
                  *(float *)v175.m128i_i32 = *(float *)v175.m128i_i32 * *(float *)v174.m128i_i32;
                  v177 = _mm_cvtsi128_si32(v175);
                  v178 = (unsigned __int8)(v177 >> 23);
                  if ( v178 > 0x9E )
                    goto LABEL_356;
                  v179 = v177 & 0x7FFFFF | 0x800000LL;
                  if ( v178 < 0x76 )
                    v180 = v179 >> (118 - (unsigned __int8)v178);
                  else
                    v180 = v179 << ((unsigned __int8)v178 - 118);
                  v109 = (v180 + 0x80000000LL) >> 32;
                  if ( v177 < 0 )
                    v109 = (unsigned int)-(int)v109;
                  v181 = _mm_cvtsi128_si32(v176);
                  v317 = v109;
                  v182 = (unsigned __int8)(v181 >> 23);
                  if ( v182 > 0x9E )
                    goto LABEL_356;
                  v183 = v181 & 0x7FFFFF | 0x800000LL;
                  if ( v182 < 0x76 )
                    v184 = v183 >> (118 - (unsigned __int8)v182);
                  else
                    v184 = v183 << ((unsigned __int8)v182 - 118);
                  v110 = (v184 + 0x80000000LL) >> 32;
                  if ( v181 < 0 )
                    v110 = (unsigned int)-(int)v110;
                  v185 = _mm_cvtsi128_si32(v174);
                  v316 = v110;
                  v186 = (unsigned __int8)(v185 >> 23);
                  if ( v186 > 0x9E )
                    goto LABEL_356;
                  v187 = v185 & 0x7FFFFF | 0x800000LL;
                  if ( v186 < 0x76 )
                    v188 = v187 >> (118 - (unsigned __int8)v186);
                  else
                    v188 = v187 << ((unsigned __int8)v186 - 118);
                  v189 = (v188 + 0x80000000LL) >> 32;
                  if ( v185 < 0 )
                    v189 = (unsigned int)-(int)v189;
                  v190 = _mm_cvtsi128_si32(v176);
                  v314 = v189;
                  v191 = (unsigned __int8)(v190 >> 23);
                  if ( v191 > 0x9E )
                  {
LABEL_356:
                    LODWORD(v113) = 0;
                    LODWORD(v110) = 0;
                    LODWORD(v109) = 0;
                    LODWORD(v314) = 0;
                    v317 = 0;
                    v316 = 0;
                  }
                  else
                  {
                    v192 = v190 & 0x7FFFFF | 0x800000LL;
                    if ( v191 < 0x76 )
                      v193 = v192 >> (118 - (unsigned __int8)v191);
                    else
                      v193 = v192 << ((unsigned __int8)v191 - 118);
                    v113 = (v193 + 0x80000000LL) >> 32;
                    if ( v190 < 0 )
                      LODWORD(v113) = -(int)v113;
                  }
                  v194 = (__m128i)COERCE_UNSIGNED_INT((float)v57);
                  *(float *)v194.m128i_i32 = *(float *)v194.m128i_i32 * *(float *)v174.m128i_i32;
                  v195 = _mm_cvtsi128_si32(v194);
                  v196 = (unsigned __int8)(v195 >> 23);
                  if ( v196 > 0x9E )
                    goto LABEL_357;
                  v197 = v176;
                  v198 = v195 & 0x7FFFFF | 0x800000LL;
                  if ( v196 < 0x76 )
                    v199 = v198 >> (118 - (unsigned __int8)v196);
                  else
                    v199 = v198 << ((unsigned __int8)v196 - 118);
                  v117 = (v199 + 0x80000000LL) >> 32;
                  if ( v195 < 0 )
                    LODWORD(v117) = -(int)v117;
                  *(float *)v197.m128i_i32 = *(float *)v176.m128i_i32 * (float)v360.top;
                  v200 = _mm_cvtsi128_si32(v197);
                  v201 = (unsigned __int8)(v200 >> 23);
                  if ( v201 > 0x9E )
                    goto LABEL_357;
                  *(float *)v174.m128i_i32 = *(float *)v174.m128i_i32 * (float)v312;
                  v202 = v200 & 0x7FFFFF | 0x800000LL;
                  if ( v201 < 0x76 )
                    v203 = v202 >> (118 - (unsigned __int8)v201);
                  else
                    v203 = v202 << ((unsigned __int8)v201 - 118);
                  v118 = (v203 + 0x80000000LL) >> 32;
                  if ( v200 < 0 )
                    LODWORD(v118) = -(int)v118;
                  v204 = _mm_cvtsi128_si32(v174);
                  v205 = (unsigned __int8)(v204 >> 23);
                  if ( v205 > 0x9E )
                    goto LABEL_357;
                  *(float *)v176.m128i_i32 = *(float *)v176.m128i_i32 * (float)v360.bottom;
                  v206 = v204 & 0x7FFFFF | 0x800000LL;
                  if ( v205 < 0x76 )
                    v207 = v206 >> (118 - (unsigned __int8)v205);
                  else
                    v207 = v206 << ((unsigned __int8)v205 - 118);
                  v119 = (v207 + 0x80000000LL) >> 32;
                  if ( v204 < 0 )
                    LODWORD(v119) = -(int)v119;
                  v208 = _mm_cvtsi128_si32(v176);
                  v209 = (unsigned __int8)(v208 >> 23);
                  if ( v209 > 0x9E )
                  {
LABEL_357:
                    LODWORD(v116) = 0;
                    LODWORD(v119) = 0;
                    LODWORD(v118) = 0;
                    LODWORD(v117) = 0;
                  }
                  else
                  {
                    v210 = v208 & 0x7FFFFF | 0x800000LL;
                    if ( v209 < 0x76 )
                      v211 = v210 >> (118 - (unsigned __int8)v209);
                    else
                      v211 = v210 << ((unsigned __int8)v209 - 118);
                    v116 = (v211 + 0x80000000LL) >> 32;
                    if ( v208 < 0 )
                      LODWORD(v116) = -(int)v116;
                  }
                }
                else
                {
                  LODWORD(v116) = v360.bottom;
                  LODWORD(v117) = v57;
                  LODWORD(v118) = v360.top;
                  LODWORD(v119) = v312;
                }
                v120 = *((_DWORD *)v326 + 130);
                LODWORD(v313) = v120;
                v304 = v120 & 1;
                if ( (v120 & 1) == 0 || (v120 & 2) != 0 )
                {
                  LODWORD(v121) = v311;
                  LODWORD(v122) = v114;
                  LODWORD(v123) = v307;
                  LODWORD(v124) = v301;
                }
                else
                {
                  v212 = (__m128i)LODWORD(FLOAT_1_0);
                  *(float *)v212.m128i_i32 = 1.0 / *((float *)v326 + 131);
                  v213 = 1.0 / *((float *)v326 + 132);
                  v214 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v310);
                  *(float *)v214.m128i_i32 = *(float *)v214.m128i_i32 * *(float *)v212.m128i_i32;
                  v215 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v111);
                  v216 = _mm_cvtsi128_si32(v214);
                  v217 = (unsigned __int8)(v216 >> 23);
                  v218 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v311);
                  if ( v217 > 0x9E )
                    goto LABEL_397;
                  *(float *)v215.m128i_i32 = *(float *)v215.m128i_i32 * v213;
                  v219 = v216 & 0x7FFFFF | 0x800000LL;
                  if ( v217 < 0x76 )
                    v220 = v219 >> (118 - (unsigned __int8)v217);
                  else
                    v220 = v219 << ((unsigned __int8)v217 - 118);
                  v221 = (v220 + 0x80000000LL) >> 32;
                  if ( v216 < 0 )
                    v221 = (unsigned int)-(int)v221;
                  v310 = (OPTAPIDCOBJ *)v221;
                  v222 = _mm_cvtsi128_si32(v215);
                  v223 = (unsigned __int8)(v222 >> 23);
                  if ( v223 > 0x9E )
                    goto LABEL_397;
                  v224 = v222 & 0x7FFFFF | 0x800000LL;
                  if ( v223 < 0x76 )
                    v225 = v224 >> (118 - (unsigned __int8)v223);
                  else
                    v225 = v224 << ((unsigned __int8)v223 - 118);
                  v226 = (v225 + 0x80000000LL) >> 32;
                  if ( v222 < 0 )
                    v226 = (unsigned int)-(int)v226;
                  v227 = _mm_cvtsi128_si32(v212);
                  v364.m128i_i64[0] = v226;
                  v228 = (unsigned __int8)(v227 >> 23);
                  if ( v228 > 0x9E )
                    goto LABEL_397;
                  *(float *)v218.m128i_i32 = *(float *)v218.m128i_i32 * v213;
                  v229 = v227 & 0x7FFFFF | 0x800000LL;
                  if ( v228 < 0x76 )
                    v230 = v229 >> (118 - (unsigned __int8)v228);
                  else
                    v230 = v229 << ((unsigned __int8)v228 - 118);
                  v122 = (v230 + 0x80000000LL) >> 32;
                  if ( v227 < 0 )
                    LODWORD(v122) = -(int)v122;
                  v231 = _mm_cvtsi128_si32(v218);
                  v232 = (unsigned __int8)(v231 >> 23);
                  if ( v232 > 0x9E )
                  {
LABEL_397:
                    LODWORD(v122) = 0;
                    LODWORD(v121) = 0;
                    v364.m128i_i32[0] = 0;
                    v310 = 0;
                  }
                  else
                  {
                    v233 = v231 & 0x7FFFFF | 0x800000LL;
                    if ( v232 < 0x76 )
                      v234 = v233 >> (118 - (unsigned __int8)v232);
                    else
                      v234 = v233 << ((unsigned __int8)v232 - 118);
                    v121 = (v234 + 0x80000000LL) >> 32;
                    if ( v231 < 0 )
                      LODWORD(v121) = -(int)v121;
                  }
                  v235 = (__m128i)COERCE_UNSIGNED_INT((float)v301);
                  v236 = (__m128i)COERCE_UNSIGNED_INT((float)v307);
                  *(float *)v235.m128i_i32 = *(float *)v235.m128i_i32 * *(float *)v212.m128i_i32;
                  v237 = _mm_cvtsi128_si32(v235);
                  v238 = (__m128i)COERCE_UNSIGNED_INT((float)v363);
                  v239 = (unsigned __int8)(v237 >> 23);
                  if ( v239 > 0x9E )
                    goto LABEL_398;
                  *(float *)v236.m128i_i32 = *(float *)v236.m128i_i32 * v213;
                  v240 = v237 & 0x7FFFFF | 0x800000LL;
                  if ( v239 < 0x76 )
                    v241 = v240 >> (118 - (unsigned __int8)v239);
                  else
                    v241 = v240 << ((unsigned __int8)v239 - 118);
                  v124 = (v241 + 0x80000000LL) >> 32;
                  if ( v237 < 0 )
                    LODWORD(v124) = -(int)v124;
                  v242 = _mm_cvtsi128_si32(v236);
                  v243 = (unsigned __int8)(v242 >> 23);
                  if ( v243 > 0x9E )
                    goto LABEL_398;
                  *(float *)v212.m128i_i32 = *(float *)v212.m128i_i32 * (float)v362;
                  v244 = v242 & 0x7FFFFF | 0x800000LL;
                  if ( v243 < 0x76 )
                    v245 = v244 >> (118 - (unsigned __int8)v243);
                  else
                    v245 = v244 << ((unsigned __int8)v243 - 118);
                  v123 = (v245 + 0x80000000LL) >> 32;
                  if ( v242 < 0 )
                    LODWORD(v123) = -(int)v123;
                  if ( (unsigned __int8)(_mm_cvtsi128_si32(v212) >> 23) > 0x9Eu
                    || (*(float *)v238.m128i_i32 = *(float *)v238.m128i_i32 * v213,
                        (unsigned __int8)(_mm_cvtsi128_si32(v238) >> 23) > 0x9Eu) )
                  {
LABEL_398:
                    LODWORD(v109) = v317;
                    LODWORD(v123) = 0;
                    LODWORD(v110) = v316;
                    LODWORD(v124) = 0;
                  }
                  else
                  {
                    LODWORD(v109) = v317;
                    LODWORD(v110) = v316;
                  }
                }
                v125 = v124 - v117;
                v126 = v123 - v118;
                if ( (int)v109 > (int)v117 )
                  LODWORD(v117) = v109;
                if ( (int)v110 > (int)v118 )
                  LODWORD(v118) = v110;
                if ( (int)v314 < (int)v119 )
                  LODWORD(v119) = v314;
                if ( (int)v113 < (int)v116 )
                  LODWORD(v116) = v113;
                if ( (int)v119 < (int)v117 )
                {
                  LODWORD(v117) = v119;
                }
                else if ( (int)v116 < (int)v118 )
                {
                  LODWORD(v118) = v116;
                }
                LODWORD(v127) = v125 + v117;
                v128 = v125 + v119;
                v129 = v126 + v118;
                LODWORD(v116) = v126 + v116;
                if ( (int)v310 > v125 + (int)v117 )
                  LODWORD(v127) = (_DWORD)v310;
                if ( v364.m128i_i32[0] > v129 )
                  v129 = v364.m128i_i32[0];
                if ( (int)v122 < v128 )
                  v128 = v122;
                if ( (int)v121 < (int)v116 )
                  LODWORD(v116) = v121;
                if ( v128 < (int)v127 )
                {
                  LODWORD(v127) = v128;
                }
                else if ( (int)v116 < v129 )
                {
                  v129 = v116;
                }
                LODWORD(v130) = v127 - v125;
                LODWORD(v131) = v128 - v125;
                if ( (int)v127 - v125 >= v128 - v125
                  || (LODWORD(v132) = v129 - v126, LODWORD(v133) = v116 - v126, v129 - v126 >= (int)v116 - v126) )
                {
                  v136 = v324;
                  v137 = 0;
                }
                else
                {
                  if ( a1 )
                  {
                    v134 = *a1;
                    v135 = *((_DWORD *)*a1 + 130);
                    if ( (v135 & 1) != 0 && (v135 & 2) == 0 )
                    {
                      v246 = *((float *)v134 + 131);
                      v247 = _mm_cvtsi32_si128(v131);
                      v248 = _mm_cvtsi32_si128(v133);
                      v249 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v130);
                      *(float *)v249.m128i_i32 = *(float *)v249.m128i_i32 * v246;
                      v250 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v132);
                      v251 = _mm_cvtsi128_si32(v249);
                      v252 = (__m128i)_mm_cvtepi32_ps(v247);
                      v253 = (unsigned __int8)(v251 >> 23);
                      v254 = (__m128i)_mm_cvtepi32_ps(v248);
                      if ( v253 > 0x9E )
                        goto LABEL_423;
                      v255 = *((float *)v134 + 132);
                      *(float *)v250.m128i_i32 = *(float *)v250.m128i_i32 * v255;
                      v256 = v251 & 0x7FFFFF | 0x800000LL;
                      if ( v253 < 0x76 )
                        v257 = v256 >> (118 - (unsigned __int8)v253);
                      else
                        v257 = v256 << ((unsigned __int8)v253 - 118);
                      v130 = (v257 + 0x80000000LL) >> 32;
                      if ( v251 < 0 )
                        LODWORD(v130) = -(int)v130;
                      v258 = _mm_cvtsi128_si32(v250);
                      v259 = (unsigned __int8)(v258 >> 23);
                      if ( v259 > 0x9E )
                        goto LABEL_423;
                      *(float *)v252.m128i_i32 = *(float *)v252.m128i_i32 * v246;
                      v260 = v258 & 0x7FFFFF | 0x800000LL;
                      if ( v259 < 0x76 )
                        v261 = v260 >> (118 - (unsigned __int8)v259);
                      else
                        v261 = v260 << ((unsigned __int8)v259 - 118);
                      v132 = (v261 + 0x80000000LL) >> 32;
                      if ( v258 < 0 )
                        LODWORD(v132) = -(int)v132;
                      v262 = _mm_cvtsi128_si32(v252);
                      v263 = (unsigned __int8)(v262 >> 23);
                      if ( v263 > 0x9E )
                        goto LABEL_423;
                      *(float *)v254.m128i_i32 = *(float *)v254.m128i_i32 * v255;
                      v264 = v262 & 0x7FFFFF | 0x800000LL;
                      if ( v263 < 0x76 )
                        v265 = v264 >> (118 - (unsigned __int8)v263);
                      else
                        v265 = v264 << ((unsigned __int8)v263 - 118);
                      v131 = (v265 + 0x80000000LL) >> 32;
                      if ( v262 < 0 )
                        LODWORD(v131) = -(int)v131;
                      v266 = _mm_cvtsi128_si32(v254);
                      v267 = (unsigned __int8)(v266 >> 23);
                      if ( v267 > 0x9E )
                      {
LABEL_423:
                        LODWORD(v133) = 0;
                        LODWORD(v131) = 0;
                        LODWORD(v132) = 0;
                        LODWORD(v130) = 0;
                      }
                      else
                      {
                        v268 = v266 & 0x7FFFFF | 0x800000LL;
                        if ( v267 < 0x76 )
                          v269 = v268 >> (118 - (unsigned __int8)v267);
                        else
                          v269 = v268 << ((unsigned __int8)v267 - 118);
                        v133 = (v269 + 0x80000000LL) >> 32;
                        if ( v266 < 0 )
                          LODWORD(v133) = -(int)v133;
                      }
                    }
                  }
                  if ( v304 && (v313 & 2) == 0 )
                  {
                    v270 = _mm_cvtsi32_si128(v128);
                    v271 = _mm_cvtsi32_si128(v116);
                    v272 = (__m128i)*((unsigned int *)v326 + 131);
                    v273 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v127);
                    *(float *)v273.m128i_i32 = *(float *)v273.m128i_i32 * *(float *)v272.m128i_i32;
                    v274 = _mm_cvtsi128_si32(v273);
                    LODWORD(v275) = _mm_cvtepi32_ps(v270).m128_u32[0];
                    v276 = (unsigned __int8)(v274 >> 23);
                    LODWORD(v277) = _mm_cvtepi32_ps(v271).m128_u32[0];
                    if ( v276 > 0x9E )
                      goto LABEL_448;
                    v278 = (__m128i)*((unsigned int *)v326 + 132);
                    v279 = v274 & 0x7FFFFF | 0x800000LL;
                    v280 = v278;
                    if ( v276 < 0x76 )
                      v281 = v279 >> (118 - (unsigned __int8)v276);
                    else
                      v281 = v279 << ((unsigned __int8)v276 - 118);
                    v127 = (v281 + 0x80000000LL) >> 32;
                    if ( v274 < 0 )
                      LODWORD(v127) = -(int)v127;
                    *(float *)v280.m128i_i32 = *(float *)v278.m128i_i32 * (float)v129;
                    v282 = _mm_cvtsi128_si32(v280);
                    v283 = (unsigned __int8)(v282 >> 23);
                    if ( v283 > 0x9E )
                      goto LABEL_448;
                    *(float *)v272.m128i_i32 = *(float *)v272.m128i_i32 * v275;
                    v284 = v282 & 0x7FFFFF | 0x800000LL;
                    if ( v283 < 0x76 )
                      v285 = v284 >> (118 - (unsigned __int8)v283);
                    else
                      v285 = v284 << ((unsigned __int8)v283 - 118);
                    v286 = (v285 + 0x80000000LL) >> 32;
                    if ( v282 < 0 )
                      LODWORD(v286) = -(int)v286;
                    v287 = _mm_cvtsi128_si32(v272);
                    v129 = v286;
                    v288 = (unsigned __int8)(v287 >> 23);
                    if ( v288 > 0x9E )
                      goto LABEL_448;
                    *(float *)v278.m128i_i32 = *(float *)v278.m128i_i32 * v277;
                    v289 = v287 & 0x7FFFFF | 0x800000LL;
                    if ( v288 < 0x76 )
                      v290 = v289 >> (118 - (unsigned __int8)v288);
                    else
                      v290 = v289 << ((unsigned __int8)v288 - 118);
                    v291 = (v290 + 0x80000000LL) >> 32;
                    if ( v287 < 0 )
                      LODWORD(v291) = -(int)v291;
                    v292 = _mm_cvtsi128_si32(v278);
                    v128 = v291;
                    v293 = (unsigned __int8)(v292 >> 23);
                    if ( v293 > 0x9E )
                    {
LABEL_448:
                      LODWORD(v116) = 0;
                      v128 = 0;
                      v129 = 0;
                      LODWORD(v127) = 0;
                    }
                    else
                    {
                      v294 = v292 & 0x7FFFFF | 0x800000LL;
                      if ( v293 < 0x76 )
                        v295 = v294 >> (118 - (unsigned __int8)v293);
                      else
                        v295 = v294 << ((unsigned __int8)v293 - 118);
                      v116 = (v295 + 0x80000000LL) >> 32;
                      if ( v292 < 0 )
                        LODWORD(v116) = -(int)v116;
                    }
                  }
                  v361.y = v129;
                  v136 = v324;
                  v360.left = v130;
                  v137 = 1;
                  v361.x = v127;
                  v362 = v128;
                  v363 = v116;
                  v360.top = v132;
                  v360.right = v131;
                  v360.bottom = v133;
                  ++*((_DWORD *)v324 + 23);
                }
                v27 = a1;
                v138 = *a1;
                v108 = *((_QWORD *)v326 + 6);
                if ( *((_QWORD *)*a1 + 6) != v108 )
                {
                  if ( !(unsigned int)XDCOBJ::bRedirHooked((XDCOBJ *)a1)
                    || (v138 = *a1, v108 = *((_QWORD *)v326 + 6), *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) != v108) )
                  {
                    if ( *(_WORD *)(v315 + 100) )
                      goto LABEL_270;
                    v159 = (SURFOBJ *)(v315 + 24);
                    if ( *(_QWORD *)(v315 + 24) )
                      goto LABEL_271;
                    v138 = *a1;
                    v108 = *(unsigned int *)(*((_QWORD *)*a1 + 6) + 40LL);
                    if ( (v108 & 0x80u) != 0LL )
                    {
LABEL_270:
                      v159 = v325;
LABEL_271:
                      if ( v137 )
                      {
                        v160 = v334;
                        if ( (*(_DWORD *)(*((_QWORD *)v136 + 6) + 40LL) & 0x80u) == 0 )
                          v160 = 0;
                        v296 = SimBitBlt(
                                 (SURFOBJ *)((char *)v136 + 24),
                                 v159,
                                 v309,
                                 &v360,
                                 &v361,
                                 0,
                                 v321,
                                 (POINTL *)*a1 + 149,
                                 v318,
                                 (__int64)v160);
                      }
                      goto LABEL_208;
                    }
                  }
                }
                v139 = v318;
                if ( v318 == 52428 )
                {
                  v140 = *((_QWORD *)v136 + 6);
                  v141 = a11 & 1;
                  if ( v141 )
                  {
                    v162 = v306 - v299;
                    if ( v306 - v299 < 0 )
                      v162 = v299 - v306;
                    v163 = v299 - v312;
                    if ( v299 - v312 < 0 )
                      v163 = v312 - v299;
                    EtwWindowRendering(
                      *((_QWORD *)v138 + 58),
                      *((_QWORD *)v138 + 59),
                      **((_QWORD **)v138 + 62),
                      v297,
                      v306,
                      v312,
                      v299,
                      *((_QWORD *)v326 + 58),
                      *((_QWORD *)v326 + 59),
                      **((_QWORD **)v326 + 62),
                      v301,
                      v307,
                      v301 + v163,
                      v307 + v162);
                    *((_WORD *)v136 + 51) |= 0x40u;
                    v164 = GreGetCurrentThread();
                    if ( v164 )
                      *((_DWORD *)v164 + 84) &= ~1u;
                    GreClientRgnUpdated(0);
                    GreClientRgnUpdatedStable();
                  }
                  if ( v137 )
                  {
                    if ( (*((_DWORD *)v136 + 36) & 0x400) != 0 )
                      v142 = (*(__int64 (__fastcall **)(__int64, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *))(v140 + 2832))(
                               (__int64)v136 + 24,
                               v325,
                               v322,
                               v309,
                               &v360,
                               &v361);
                    else
                      v142 = ((__int64 (__fastcall *)(char *, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *))EngCopyBits)(
                               (char *)v136 + 24,
                               v325,
                               v322,
                               v309,
                               &v360,
                               &v361);
                    v296 = v142;
                  }
                  if ( v141 )
                  {
                    *((_WORD *)v136 + 51) &= ~0x40u;
                    v165 = GreGetCurrentThread();
                    if ( v165 )
                      *((_DWORD *)v165 + 84) |= 1u;
                  }
                }
                else if ( v137 )
                {
                  v147 = SURFACE::pfnBitBlt(v136);
                  v296 = ((__int64 (__fastcall *)(char *, __int64, _QWORD, char *, XLATEOBJ *, RECTL *, POINTL *, _QWORD, __int64, __int64, int))v147)(
                           (char *)v136 + 24,
                           v149 + 24,
                           0,
                           v322,
                           v309,
                           &v360,
                           &v361,
                           0,
                           v321,
                           v148 + 1192,
                           v139);
                }
                goto LABEL_208;
              }
              v83 = a10;
              v302 = a10;
              if ( a10 == -1 )
              {
                v82 = *((_QWORD *)v326 + 122);
                v83 = *(_DWORD *)(v82 + 180);
                v302 = v83;
              }
              if ( v60 )
              {
                if ( v42 )
                {
                  v84 = v60;
                  if ( *(_QWORD *)(v60 + 120) != v60 )
                    v84 = *(_QWORD *)(v60 + 120);
                  v82 = *(_QWORD *)(v42 + 120);
                  v85 = *(_DWORD *)(v84 + 32);
                  v86 = v42;
                  if ( v82 != v42 )
                    v86 = *(_QWORD *)(v42 + 120);
                  v87 = v85 == *(_DWORD *)(v86 + 32);
LABEL_126:
                  if ( !v87 )
                    goto LABEL_127;
LABEL_159:
                  v99 = (XLATEOBJ *)((char *)Gre::Base::Globals((Gre::Base *)v82) + 4664);
                  goto LABEL_160;
                }
                if ( (*(_DWORD *)(v60 + 24) & 0x800) != 0 )
                {
LABEL_213:
                  v144 = *(_QWORD *)(v41 + 80);
                  if ( !v144 )
                    goto LABEL_159;
                  v87 = v144 == *(_QWORD *)(v41 + 72);
                  goto LABEL_126;
                }
              }
              else
              {
                if ( !v42 )
                  goto LABEL_159;
                if ( (*(_DWORD *)(v42 + 24) & 0x800) != 0 )
                  goto LABEL_213;
              }
LABEL_127:
              v88 = *((unsigned int *)v81 + 30);
              LODWORD(v311) = *((_DWORD *)v81 + 30);
              v89 = (XLATEOBJ *)*((_QWORD *)v326 + 11);
              v90 = *((_QWORD *)v81 + 122);
              v309 = v89;
              v91 = (Gre::Base *)*(unsigned int *)(v90 + 176);
              v92 = *(_DWORD *)(v90 + 184);
              v308 = v92;
              v303 = (int)v91;
              if ( v60 && v42 )
              {
                v93 = *(_DWORD *)(v60 + 56);
                v94 = Gre::Base::Globals(v91);
                v364.m128i_i64[0] = *(_QWORD *)v94 + 312LL;
                GreAcquireSemaphoreInternal((HSEMAPHORE)v364.m128i_i64[0]);
                GrepAcquireLockValidate<13>();
                for ( i = 0; ; ++i )
                {
                  if ( i >= 8 )
                  {
                    SEMOBJ<13>::vUnlock(&v364);
                    LODWORD(v91) = v303;
                    v92 = v308;
                    v88 = (unsigned int)v311;
                    v83 = v302;
                    v89 = v309;
                    v41 = v314;
                    goto LABEL_136;
                  }
                  v96 = v60;
                  if ( *(_QWORD *)(v60 + 120) != v60 )
                    v96 = *(_QWORD *)(v60 + 120);
                  if ( *((_DWORD *)v94 + 8 * v93 + 1104) != *(_DWORD *)(v96 + 32) )
                    goto LABEL_134;
                  v150 = v42;
                  if ( *(_QWORD *)(v42 + 120) != v42 )
                    v150 = *(_QWORD *)(v42 + 120);
                  v151 = 32LL * v93;
                  if ( *(_DWORD *)((char *)v94 + v151 + 4420) != *(_DWORD *)(v150 + 32) )
                    goto LABEL_134;
                  v152 = v314;
                  if ( *(_QWORD *)(v314 + 120) != v314 )
                    v152 = *(_QWORD *)(v314 + 120);
                  if ( *(_DWORD *)((char *)v94 + v151 + 4428) != *(_DWORD *)(v152 + 32) )
                    goto LABEL_134;
                  v99 = *(XLATEOBJ **)((char *)v94 + v151 + 4408);
                  if ( (v99[3].flXlate & 0x6000) != 0 )
                    goto LABEL_134;
                  v153 = v99[3].flXlate & 0x100;
                  if ( (v99->flXlate & 4) == 0 )
                    break;
                  if ( v302 == v99[1].iUniq )
                  {
                    v154 = v309;
                    if ( *(XLATEOBJ **)&v309[5].iUniq != v309 )
                      v154 = *(XLATEOBJ **)&v309[5].iUniq;
                    if ( *(_DWORD *)((char *)v94 + v151 + 4424) == *(_DWORD *)&v154[1].iSrcType )
                    {
LABEL_244:
                      _InterlockedIncrement((volatile signed __int32 *)((char *)v94 + v151 + 4400));
                      *(_DWORD *)(v60 + 56) = v93;
                      SEMOBJ<13>::vUnlock(&v364);
                      goto LABEL_160;
                    }
                  }
                  if ( v153 )
                    goto LABEL_242;
LABEL_134:
                  v93 = ((_BYTE)v93 + 1) & 7;
                }
                if ( !v153 )
                  goto LABEL_244;
LABEL_242:
                if ( v308 == v99[1].flXlate && v303 == *(_DWORD *)&v99[1].iSrcType )
                  goto LABEL_244;
                goto LABEL_134;
              }
LABEL_136:
              XlateObject = CreateXlateObject(0, v88, v60, v42, v89, v41, v92, (_DWORD)v91, v83, 0);
              v99 = (XLATEOBJ *)XlateObject;
              if ( XlateObject )
              {
                if ( v60 && v42 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
                {
                  v100 = Gre::Base::Globals(v98);
                  v309 = (XLATEOBJ *)(*(_QWORD *)v100 + 312LL);
                  GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
                  for ( j = 0; j < 8; ++j )
                  {
                    v102 = *((_DWORD *)v100 + 1164);
                    v103 = 32LL * v102;
                    v104 = *(_QWORD *)((char *)v100 + v103 + 4408);
                    if ( !v104 )
                      goto LABEL_145;
                    if ( !*(_DWORD *)((char *)v100 + v103 + 4400) )
                    {
                      FreeThreadBufferWithTag(v104);
LABEL_145:
                      PopThreadGuardedObject(&v99[-2].pulXlate);
                      v105 = v60;
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1100) = 1;
                      *((_QWORD *)v100 + 4 * *((unsigned int *)v100 + 1164) + 551) = v99;
                      if ( *(_QWORD *)(v60 + 120) != v60 )
                        v105 = *(_QWORD *)(v60 + 120);
                      v106 = *(_DWORD *)(v105 + 32);
                      v107 = v314;
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1104) = v106;
                      if ( *(_QWORD *)(v42 + 120) != v42 )
                        v42 = *(_QWORD *)(v42 + 120);
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1105) = *(_DWORD *)(v42 + 32);
                      if ( *(XLATEOBJ **)&v89[5].iUniq != v89 )
                        v89 = *(XLATEOBJ **)&v89[5].iUniq;
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1106) = *(_DWORD *)&v89[1].iSrcType;
                      if ( *(_QWORD *)(v107 + 120) != v107 )
                        v107 = *(_QWORD *)(v107 + 120);
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1107) = *(_DWORD *)(v107 + 32);
                      v99[1].cEntries = *((_DWORD *)v100 + 1164);
                      *(_DWORD *)(v60 + 56) = *((_DWORD *)v100 + 1164);
                      *((_DWORD *)v100 + 1164) = ((unsigned __int8)*((_DWORD *)v100 + 1164) + 1) & 7;
                      break;
                    }
                    *((_DWORD *)v100 + 1164) = ((_BYTE)v102 + 1) & 7;
                  }
                  SEMOBJ<13>::vUnlock(&v309);
                }
LABEL_160:
                v108 = 1;
              }
              else
              {
                v108 = 0;
              }
              v27 = a1;
              v296 = v108;
              v81 = *a1;
              if ( (*((_DWORD *)*a1 + 9) & 1) == 0 )
              {
                v362 = v360.right - v64;
                v363 = v360.bottom - v305;
              }
              if ( !(_DWORD)v108 )
              {
LABEL_208:
                if ( v99 )
                {
                  cEntries = v99[1].cEntries;
                  if ( cEntries >= 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)Gre::Base::Globals((Gre::Base *)v108) + 8 * (int)v99[1].cEntries + 1100);
                  }
                  else if ( cEntries == -1 )
                  {
                    FreeThreadBufferWithTag(v99);
                  }
                }
                goto LABEL_54;
              }
              v57 = v360.left;
              v307 = v361.y;
              v301 = v361.x;
              v297 = v360.left;
              goto LABEL_165;
            }
          }
          v145 = (char *)v70 + 1768;
          v322 = (char *)v70 + 1768;
          v146 = XDCOBJ::prgnEffRao((XDCOBJ *)a1);
          XCLIPOBJ::vSetup((XCLIPOBJ *)v145, v146, (const struct ERECTL *)&v360, 2);
          v71 = *(__m128i *)(v145 + 4);
          v57 = _mm_cvtsi128_si32(v71);
          v360 = (RECTL)v71;
          v297 = v57;
          v360.right = _mm_cvtsi128_si32(_mm_srli_si128(v71, 8));
          if ( v57 != v360.right && v71.m128i_i32[1] != _mm_srli_si128(v71, 8).m128i_i32[1] )
          {
            v69 = a1;
            v360.bottom = _mm_cvtsi128_si32(_mm_srli_si128(v71, 12));
            v360.top = _mm_cvtsi128_si32(_mm_srli_si128(v71, 4));
            goto LABEL_102;
          }
        }
LABEL_53:
        v27 = a1;
        v296 = 1;
LABEL_54:
        DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v334);
        v19 = v296;
LABEL_55:
        if ( v319 )
          DC::dwSetLayout(*v27, -1, v320);
        v44 = v326;
        if ( !v332 )
          v44 = 0;
        v326 = v44;
        PopThreadGuardedObject(v331);
        v45 = v326;
        if ( v326 )
        {
          if ( v327 && (*((_DWORD *)v326 + 11) & 2) != 0 )
          {
            CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
            v48 = v326;
            v49 = CurrentProcessId & 0xFFFFFFFC;
            if ( *(_QWORD *)v326 )
            {
              v50 = (char *)HmgPentryFromPobj(v328, v326);
            }
            else
            {
              v50 = (char *)v326 + 2152;
              *(_OWORD *)((char *)v326 + 2152) = 0;
              *((_QWORD *)v48 + 271) = 0;
              *((_DWORD *)v48 + 540) = -2147483630;
              *((_QWORD *)v48 + 271) = GreEncodeUserModePointer(0);
            }
            if ( v49 == (*((_DWORD *)v50 + 2) & 0xFFFFFFFE) )
            {
              UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v326);
              if ( UserAttr )
                DC::RestoreAttributes(v326, UserAttr);
            }
            *((_DWORD *)v326 + 11) &= ~2u;
            v45 = v326;
            v327 = 0;
          }
          _InterlockedDecrement16((volatile signed __int16 *)v45 + 6);
          v326 = 0;
        }
        PopThreadGuardedObject(v330);
        goto LABEL_61;
      }
      v19 = 0;
    }
LABEL_61:
    if ( v18 )
    {
      v166 = GreGetCurrentThread();
      *((_DWORD *)v166 + 84) &= ~8u;
    }
    return v19;
  }
  v161 = GrepStretchBlt(
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
    v173 = GreGetCurrentThread();
    *((_DWORD *)v173 + 84) &= ~8u;
  }
  return v161;
}

```

## disassembly

```asm
0x140062340  push    rbp
0x140062342  push    rbx
0x140062343  push    rsi
0x140062344  push    rdi
0x140062345  push    r12
0x140062347  push    r14
0x140062349  push    r15
0x14006234b  lea     rbp, [rsp-270h]
0x140062353  sub     rsp, 370h
0x14006235a  mov     rax, cs:__security_cookie
0x140062361  xor     rax, rsp
0x140062364  mov     [rbp+2A0h+var_60], rax
0x14006236b  test    byte ptr [rbp+2A0h+arg_50], 4
0x140062372  mov     r10, rcx
0x140062375  mov     r15d, [rbp+2A0h+arg_30]
0x14006237c  mov     r14d, r8d
0x14006237f  mov     r8d, [rbp+2A0h+arg_20]
0x140062386  mov     edi, edx
0x140062388  mov     r12d, [rbp+2A0h+arg_38]
0x14006238f  mov     ebx, [rbp+2A0h+arg_40]
0x140062395  mov     [rbp+2A0h+var_320], rcx
0x140062399  mov     rcx, [rbp+2A0h+arg_28]
0x1400623a0  mov     [rbp+2A0h+var_300], rcx
0x1400623a4  mov     [rsp+3A0h+var_328], r9d
0x1400623a9  mov     [rsp+3A0h+var_32C], r8d
0x1400623ae  jnz     loc_140063C92
0x1400623b4  xor     sil, sil
0x1400623b7  mov     eax, ebx
0x1400623b9  btr     ebx, 1Dh
0x1400623bd  shr     eax, 1Ch
0x1400623c0  and     eax, 2
0x1400623c3  bt      ebx, 1Eh
0x1400623c7  jb      loc_140063B35
0x1400623cd  mov     rax, [r10]
0x1400623d0  mov     [rsp+3A0h+var_38], r13
0x1400623d8  xor     r13d, r13d
0x1400623db  mov     [rsp+3A0h+var_330], r13d
0x1400623e0  test    dword ptr [rax+24h], 10000h
0x1400623e7  jnz     loc_140062AC7
0x1400623ed  mov     eax, ebx
0x1400623ef  lea     r11, gajRop3
0x1400623f6  btr     eax, 1Fh
0x1400623fa  mov     r13d, eax
0x1400623fd  shr     rax, 8
0x140062401  movzx   edx, al
0x140062404  movzx   eax, r13b
0x140062408  movzx   ecx, byte ptr [rax+r11]
0x14006240d  movzx   eax, byte ptr [rdx+r11]
0x140062412  or      al, cl
0x140062414  test    al, 2
0x140062416  jnz     loc_140063818
0x14006241c  mov     rcx, [rbp+2A0h+var_300]; this
0x140062420  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140062425  test    al, al
0x140062427  jz      loc_140063D55
0x14006242d  mov     rax, [rbp+2A0h+var_300]
0x140062431  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140062438  xorps   xmm0, xmm0
0x14006243b  lea     rdx, [rbp+2A0h+var_280]
0x14006243f  lea     rcx, [rbp+2A0h+var_260]
0x140062443  movups  [rbp+2A0h+var_260], xmm0
0x140062447  mov     rax, [rax+10h]
0x14006244b  mov     [rbp+2A0h+var_270], rax
0x14006244f  xor     eax, eax
0x140062451  mov     [rbp+2A0h+var_268], rax
0x140062455  mov     [rbp+2A0h+var_280], rax
0x140062459  mov     [rbp+2A0h+var_278], eax
0x14006245c  movups  [rbp+2A0h+var_250], xmm0
0x140062460  call    cs:__imp_PushThreadGuardedObject
0x140062467  nop     dword ptr [rax+rax+00h]
0x14006246c  xorps   xmm0, xmm0
0x14006246f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140062476  lea     rdx, [rbp+2A0h+var_280]
0x14006247a  lea     rcx, [rbp+2A0h+var_240]
0x14006247e  movups  [rbp+2A0h+var_240], xmm0
0x140062482  movups  [rbp+2A0h+var_230], xmm0
0x140062486  call    cs:__imp_PushThreadGuardedObject
0x14006248d  nop     dword ptr [rax+rax+00h]
0x140062492  mov     rax, [rbp+2A0h+var_300]
0x140062496  lea     rcx, [rbp+2A0h+var_280]; struct XDCOBJ *
0x14006249a  mov     r9d, [rsp+3A0h+var_328]; int
0x14006249f  mov     r8d, r12d; int
0x1400624a2  mov     edx, r15d; int
0x1400624a5  mov     [rbp+2A0h+var_220], 0
0x1400624ac  mov     rax, [rax]
0x1400624af  mov     [rbp+2A0h+var_280], rax
0x1400624b3  mov     eax, [rsp+3A0h+var_32C]
0x1400624b7  mov     dword ptr [rsp+3A0h+var_380], eax; int
0x1400624bb  call    ?bSpDwmValidateSurface@@YAHAEAVXDCOBJ@@HHHH@Z; bSpDwmValidateSurface(XDCOBJ &,int,int,int,int)
0x1400624c0  mov     rax, [rbp+2A0h+var_320]
0x1400624c4  mov     r9, [rax]
0x1400624c7  mov     rax, [rbp+2A0h+var_280]
0x1400624cb  mov     r8, [r9+3D0h]
0x1400624d2  mov     rcx, [rax+3D0h]
0x1400624d9  mov     edx, [r8+6Ch]
0x1400624dd  mov     eax, edx
0x1400624df  xor     eax, [rcx+6Ch]
0x1400624e2  test    al, 7
0x1400624e4  jnz     loc_140063CC1
0x1400624ea  xor     ebx, ebx
0x1400624ec  mov     [rbp+2A0h+var_2B8], ebx
0x1400624ef  mov     [rbp+2A0h+var_2BC], ebx
0x1400624f2  mov     rax, [rbp+2A0h+var_320]
0x1400624f6  lea     rdx, [rbp+2A0h+var_2A0]
0x1400624fa  mov     r8d, 204h
0x140062500  mov     rcx, [rax]
0x140062503  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14006250a  nop     dword ptr [rax+rax+00h]
0x14006250f  mov     rcx, [rbp+2A0h+var_280]
0x140062513  lea     rdx, [rbp+2A0h+var_210]
0x14006251a  mov     r8d, 204h
0x140062520  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140062527  nop     dword ptr [rax+rax+00h]
0x14006252c  mov     rax, [rbp+2A0h+var_2A0]
0x140062530  test    byte ptr [rax+20h], 1
0x140062534  jz      loc_1400637C2
0x14006253a  mov     rdx, [rbp+2A0h+var_210]
0x140062541  lea     rcx, [rbp+2A0h+var_2A0]
0x140062545  call    cs:__imp_?bEqualExceptTranslations@EXFORMOBJ@@QEBA_NPEBUMATRIX@@@Z; EXFORMOBJ::bEqualExceptTranslations(MATRIX const *)
0x14006254c  nop     dword ptr [rax+rax+00h]
0x140062551  test    al, al
0x140062553  jz      loc_1400637C2
0x140062559  mov     rax, [rbp+2A0h+var_280]
0x14006255d  mov     ebx, [rsp+3A0h+var_328]
0x140062561  mov     r8d, [rsp+3A0h+var_32C]
0x140062566  mov     rcx, [rbp+2A0h+var_210]
0x14006256d  add     r8d, r12d
0x140062570  mov     [rbp+2A0h+var_2B0], rax
0x140062574  lea     edx, [r15+rbx]
0x140062578  mov     [rbp+2A0h+var_80.x], r15d
0x14006257f  mov     [rbp+2A0h+var_78], edx
0x140062585  mov     [rbp+2A0h+var_80.y], r12d
0x14006258c  mov     [rbp+2A0h+var_74], r8d
0x140062593  mov     eax, [rcx+20h]
0x140062596  and     eax, 43h
0x140062599  cmp     al, 43h ; 'C'
0x14006259b  jz      short loc_1400625CE
0x14006259d  mov     r8d, 2
0x1400625a3  lea     rdx, [rbp+2A0h+var_80]
0x1400625aa  call    bCvtPts1
0x1400625af  mov     r8d, [rbp+2A0h+var_74]
0x1400625b6  mov     edx, [rbp+2A0h+var_78]
0x1400625bc  mov     r12d, [rbp+2A0h+var_80.y]
0x1400625c3  mov     r15d, [rbp+2A0h+var_80.x]
0x1400625ca  test    eax, eax
0x1400625cc  jz      short loc_1400625E5
0x1400625ce  mov     rax, [rbp+2A0h+var_2B0]
0x1400625d2  mov     rax, [rax+3D0h]
0x1400625d9  mov     ecx, [rax+6Ch]
0x1400625dc  test    cl, 1
0x1400625df  jnz     loc_140062B7A
0x1400625e5  cmp     r15d, edx
0x1400625e8  jle     short loc_1400625F7
0x1400625ea  mov     [rbp+2A0h+var_80.x], edx
0x1400625f0  mov     [rbp+2A0h+var_78], r15d
0x1400625f7  cmp     r12d, r8d
0x1400625fa  jle     short loc_14006260A
0x1400625fc  mov     [rbp+2A0h+var_80.y], r8d
0x140062603  mov     [rbp+2A0h+var_74], r12d
0x14006260a  mov     eax, [rsp+3A0h+var_32C]
0x14006260e  lea     edx, [rbx+rdi]
0x140062611  mov     rcx, [rbp+2A0h+var_2A0]
0x140062615  add     eax, r14d
0x140062618  mov     r12, [rbp+2A0h+var_320]
0x14006261c  mov     [rbp+2A0h+var_90.bottom], eax
0x140062622  mov     [rbp+2A0h+var_90.left], edi
0x140062628  mov     [rbp+2A0h+var_90.top], r14d
0x14006262f  mov     rbx, [r12]
0x140062633  mov     [rbp+2A0h+var_90.right], edx
0x140062639  mov     eax, [rcx+20h]
0x14006263c  and     eax, 43h
0x14006263f  cmp     al, 43h ; 'C'
0x140062641  jz      short loc_14006266C
0x140062643  mov     r8d, 2
0x140062649  lea     rdx, [rbp+2A0h+var_90]
0x140062650  call    bCvtPts1
0x140062655  mov     edx, [rbp+2A0h+var_90.right]
0x14006265b  mov     r14d, [rbp+2A0h+var_90.top]
0x140062662  mov     edi, [rbp+2A0h+var_90.left]
0x140062668  test    eax, eax
0x14006266a  jz      short loc_14006267F
0x14006266c  mov     rax, [rbx+3D0h]
0x140062673  mov     ecx, [rax+6Ch]
0x140062676  test    cl, 1
0x140062679  jnz     loc_140062B91
0x14006267f  cmp     edi, edx
0x140062681  jle     short loc_140062695
0x140062683  mov     eax, edi
0x140062685  mov     [rbp+2A0h+var_90.left], edx
0x14006268b  mov     edi, edx
0x14006268d  mov     [rbp+2A0h+var_90.right], eax
0x140062693  mov     edx, eax
0x140062695  mov     r8d, [rbp+2A0h+var_90.bottom]
0x14006269c  cmp     r14d, r8d
0x14006269f  jle     short loc_1400626B4
0x1400626a1  mov     eax, r14d
0x1400626a4  mov     [rbp+2A0h+var_90.top], r8d
0x1400626ab  mov     [rbp+2A0h+var_90.bottom], eax
0x1400626b1  mov     r14d, r8d
0x1400626b4  cmp     r14d, [rbp+2A0h+var_90.bottom]
0x1400626bb  jz      loc_14006361D
0x1400626c1  cmp     edi, edx
0x1400626c3  jz      loc_14006361D
0x1400626c9  mov     rax, [r12]
0x1400626cd  mov     ecx, [rax+24h]
0x1400626d0  test    cl, 0E0h
0x1400626d3  jz      loc_1400627D2
0x1400626d9  test    cl, 20h
0x1400626dc  jz      loc_140062771
0x1400626e2  cmp     edi, [rax+428h]
0x1400626e8  jge     short loc_140062703
0x1400626ea  mov     [rax+428h], edi
0x1400626f0  mov     edx, [rbp+2A0h+var_90.right]
0x1400626f6  mov     r14d, [rbp+2A0h+var_90.top]
0x1400626fd  mov     edi, [rbp+2A0h+var_90.left]
0x140062703  cmp     r14d, [rax+42Ch]
0x14006270a  jge     short loc_140062726
0x14006270c  mov     [rax+42Ch], r14d
0x140062713  mov     edx, [rbp+2A0h+var_90.right]
0x140062719  mov     r14d, [rbp+2A0h+var_90.top]
0x140062720  mov     edi, [rbp+2A0h+var_90.left]
0x140062726  cmp     edx, [rax+430h]
0x14006272c  jle     short loc_140062747
0x14006272e  mov     [rax+430h], edx
0x140062734  mov     edx, [rbp+2A0h+var_90.right]
0x14006273a  mov     r14d, [rbp+2A0h+var_90.top]
0x140062741  mov     edi, [rbp+2A0h+var_90.left]
0x140062747  mov     r8d, [rbp+2A0h+var_90.bottom]
0x14006274e  cmp     r8d, [rax+434h]
0x140062755  jle     short loc_140062771
0x140062757  mov     [rax+434h], r8d
0x14006275e  mov     edx, [rbp+2A0h+var_90.right]
0x140062764  mov     r14d, [rbp+2A0h+var_90.top]
0x14006276b  mov     edi, [rbp+2A0h+var_90.left]
0x140062771  mov     rcx, [r12]
0x140062775  mov     eax, [rcx+24h]
0x140062778  test    al, al
0x14006277a  jns     short loc_1400627D2
0x14006277c  cmp     edi, [rcx+448h]
0x140062782  jge     short loc_140062797
0x140062784  mov     [rcx+448h], edi
0x14006278a  mov     edx, [rbp+2A0h+var_90.right]
0x140062790  mov     r14d, [rbp+2A0h+var_90.top]
0x140062797  cmp     r14d, [rcx+44Ch]
0x14006279e  jge     short loc_1400627AD
0x1400627a0  mov     [rcx+44Ch], r14d
0x1400627a7  mov     edx, [rbp+2A0h+var_90.right]
0x1400627ad  cmp     edx, [rcx+450h]
0x1400627b3  jle     short loc_1400627BB
0x1400627b5  mov     [rcx+450h], edx
0x1400627bb  mov     r8d, [rbp+2A0h+var_90.bottom]
0x1400627c2  cmp     r8d, [rcx+454h]
0x1400627c9  jle     short loc_1400627D2
0x1400627cb  mov     [rcx+454h], r8d
0x1400627d2  mov     edx, 2
0x1400627d7  lea     rcx, [rbp+2A0h+var_1D8]
0x1400627de  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x1400627e3  xor     ebx, ebx
0x1400627e5  mov     [rbp+2A0h+var_1A8], rbx
0x1400627ec  mov     [rbp+2A0h+var_1A0], ebx
0x1400627f2  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400627f9  nop     dword ptr [rax+rax+00h]
0x1400627fe  xorps   xmm0, xmm0
0x140062801  mov     [rbp+2A0h+var_190], rbx
0x140062808  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14006280f  mov     [rbp+2A0h+var_198], rax
0x140062816  lea     rdx, [rbp+2A0h+var_1A8]
0x14006281d  mov     [rbp+2A0h+var_1A8], rbx
0x140062824  lea     rcx, [rbp+2A0h+var_188]
0x14006282b  mov     [rbp+2A0h+var_1A0], ebx
0x140062831  movups  [rbp+2A0h+var_188], xmm0
0x140062838  movups  [rbp+2A0h+var_178], xmm0
0x14006283f  call    cs:__imp_PushThreadGuardedObject
0x140062846  nop     dword ptr [rax+rax+00h]
0x14006284b  xorps   xmm0, xmm0
0x14006284e  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDLODCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140062855  lea     rdx, [rbp+2A0h+var_1A8]
0x14006285c  lea     rcx, [rbp+2A0h+var_168]
0x140062863  movups  [rbp+2A0h+var_168], xmm0
0x14006286a  movups  [rbp+2A0h+var_158], xmm0
0x140062871  call    cs:__imp_PushThreadGuardedObject
0x140062878  nop     dword ptr [rax+rax+00h]
0x14006287d  mov     [rbp+2A0h+var_148], 100h
0x140062886  mov     [rbp+2A0h+var_140], rbx
0x14006288d  mov     [rbp+2A0h+var_138], ebx
0x140062893  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14006289a  nop     dword ptr [rax+rax+00h]
0x14006289f  xorps   xmm0, xmm0
0x1400628a2  mov     [rbp+2A0h+var_128], rbx
0x1400628a9  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400628b0  mov     [rbp+2A0h+var_130], rax
0x1400628b7  lea     rdx, [rbp+2A0h+var_140]
0x1400628be  mov     [rbp+2A0h+var_140], rbx
0x1400628c5  lea     rcx, [rbp+2A0h+var_120]
0x1400628cc  mov     [rbp+2A0h+var_138], ebx
0x1400628d2  movups  [rbp+2A0h+var_120], xmm0
0x1400628d9  movups  [rbp+2A0h+var_110], xmm0
0x1400628e0  call    cs:__imp_PushThreadGuardedObject
0x1400628e7  nop     dword ptr [rax+rax+00h]
0x1400628ec  xorps   xmm0, xmm0
  ... truncated ...
```
