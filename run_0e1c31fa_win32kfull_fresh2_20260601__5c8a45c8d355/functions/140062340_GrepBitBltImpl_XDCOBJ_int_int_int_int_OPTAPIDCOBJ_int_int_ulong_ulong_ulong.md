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
  __int64 flXlate; // rdx
  __int64 i; // r8
  __int64 XlateObject; // rax
  Gre::Base *v98; // rcx
  XLATEOBJ *v99; // rdi
  struct Gre::Base::SESSION_GLOBALS *v100; // r14
  __int64 v101; // rdx
  __int64 j; // r8
  __int64 v103; // rcx
  __int64 v104; // rdx
  int v105; // eax
  __int64 v106; // rcx
  __int64 v107; // r11
  __int64 v108; // r10
  __int64 v109; // rbx
  unsigned int v110; // edx
  __int64 v111; // r13
  unsigned int v112; // ecx
  int v113; // eax
  __int64 v114; // rdx
  __int64 v115; // r12
  __int64 v116; // r15
  __int64 v117; // r14
  int v118; // r9d
  __int64 v119; // r9
  __int64 v120; // rbx
  __int64 v121; // rcx
  __int64 v122; // r8
  int v123; // r8d
  int v124; // ecx
  __int64 v125; // r10
  signed int v126; // r14d
  int v127; // r15d
  __int64 v128; // rbx
  __int64 v129; // r9
  __int64 v130; // r11
  __int64 v131; // r8
  DC *v132; // rcx
  int v133; // eax
  SURFACE *v134; // r15
  char v135; // bl
  DC *v136; // r11
  int v137; // r14d
  __int64 v138; // r14
  int v139; // r13d
  int v140; // eax
  int cEntries; // eax
  __int64 v142; // rax
  char *v143; // r15
  struct REGION *v144; // rax
  int (*v145)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  __int64 v146; // r11
  __int64 v147; // rdx
  __int64 v148; // rcx
  __int64 v149; // r9
  __int64 v150; // rax
  XLATEOBJ *v151; // rax
  __int64 v152; // rdx
  char *v153; // r15
  __int64 v154; // rdx
  int v155; // ecx
  SURFOBJ *v156; // r11
  _OWORD *v157; // rdx
  unsigned int v158; // ebx
  int v159; // r10d
  int v160; // ecx
  struct _GRETHREAD *v161; // rax
  struct _GRETHREAD *v162; // rax
  struct _GRETHREAD *v163; // rax
  struct _GRETHREAD *CurrentThread; // rax
  int v165; // ebx
  int v166; // edx
  BOOL v167; // eax
  _DWORD *v168; // rcx
  _DWORD *v169; // rcx
  struct _GRETHREAD *v170; // rax
  __m128i v171; // xmm2
  __m128i v172; // xmm0
  __m128i v173; // xmm4
  int v174; // r8d
  unsigned int v175; // edx
  __int64 v176; // rax
  __int64 v177; // rax
  int v178; // r8d
  unsigned int v179; // edx
  __int64 v180; // rax
  __int64 v181; // rax
  int v182; // r8d
  unsigned int v183; // edx
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // r9
  int v187; // r8d
  unsigned int v188; // edx
  __int64 v189; // rax
  __int64 v190; // rax
  __m128i v191; // xmm0
  int v192; // r8d
  unsigned int v193; // edx
  __m128i v194; // xmm0
  __int64 v195; // rax
  __int64 v196; // rax
  int v197; // r8d
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
  __m128i v209; // xmm4
  float v210; // xmm6_4
  __m128i v211; // xmm0
  __m128i v212; // xmm1
  int v213; // r9d
  unsigned int v214; // r8d
  __m128i v215; // xmm3
  __int64 v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  int v219; // r9d
  unsigned int v220; // r8d
  __int64 v221; // rax
  __int64 v222; // rax
  __int64 v223; // r11
  int v224; // r9d
  unsigned int v225; // r8d
  __int64 v226; // rax
  __int64 v227; // rax
  int v228; // r10d
  unsigned int v229; // r8d
  __int64 v230; // rax
  __int64 v231; // rax
  __m128i v232; // xmm0
  __m128i v233; // xmm1
  int v234; // r10d
  __m128i v235; // xmm2
  unsigned int v236; // r8d
  __int64 v237; // rax
  __int64 v238; // rax
  int v239; // r11d
  unsigned int v240; // r10d
  __int64 v241; // rax
  __int64 v242; // rax
  float v243; // xmm3_4
  __m128i v244; // xmm2
  __m128i v245; // xmm4
  __m128i v246; // xmm0
  __m128i v247; // xmm1
  int v248; // r9d
  __m128i v249; // xmm2
  unsigned int v250; // r8d
  __m128i v251; // xmm4
  float v252; // xmm0_4
  __int64 v253; // rax
  __int64 v254; // rax
  int v255; // r9d
  unsigned int v256; // r8d
  __int64 v257; // rax
  __int64 v258; // rax
  int v259; // r12d
  unsigned int v260; // r8d
  __int64 v261; // rax
  __int64 v262; // rax
  int v263; // r12d
  unsigned int v264; // r8d
  __int64 v265; // rax
  __int64 v266; // rax
  __m128i v267; // xmm4
  __m128i v268; // xmm5
  __m128i v269; // xmm1
  __m128i v270; // xmm0
  int v271; // r14d
  float v272; // xmm4_4
  unsigned int v273; // edx
  float v274; // xmm5_4
  __m128i v275; // xmm2
  __int64 v276; // rax
  __m128i v277; // xmm0
  __int64 v278; // rax
  int v279; // r14d
  unsigned int v280; // edx
  __int64 v281; // rax
  __int64 v282; // rax
  __int64 v283; // rcx
  int v284; // r14d
  unsigned int v285; // edx
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rcx
  int v289; // r12d
  unsigned int v290; // ecx
  __int64 v291; // rax
  __int64 v292; // rax
  int v293; // [rsp+70h] [rbp-90h]
  unsigned int v294; // [rsp+74h] [rbp-8Ch]
  int v295; // [rsp+78h] [rbp-88h]
  LONG v296; // [rsp+78h] [rbp-88h]
  LONG v298; // [rsp+88h] [rbp-78h]
  unsigned int v299; // [rsp+88h] [rbp-78h]
  int v300; // [rsp+8Ch] [rbp-74h]
  int v301; // [rsp+8Ch] [rbp-74h]
  int v302; // [rsp+90h] [rbp-70h]
  LONG v303; // [rsp+90h] [rbp-70h]
  LONG v304; // [rsp+94h] [rbp-6Ch]
  int v305; // [rsp+94h] [rbp-6Ch]
  XLATEOBJ *v306; // [rsp+98h] [rbp-68h] BYREF
  OPTAPIDCOBJ *v307; // [rsp+A0h] [rbp-60h]
  __int64 v308; // [rsp+A8h] [rbp-58h] BYREF
  LONG v309; // [rsp+B0h] [rbp-50h]
  __int64 v310; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v311; // [rsp+C0h] [rbp-40h]
  __int64 v312; // [rsp+C8h] [rbp-38h]
  __int64 v313; // [rsp+D0h] [rbp-30h]
  __int64 v314; // [rsp+D8h] [rbp-28h]
  int v315; // [rsp+E0h] [rbp-20h]
  unsigned int v316; // [rsp+E4h] [rbp-1Ch]
  unsigned int v317; // [rsp+E8h] [rbp-18h]
  __int64 v318; // [rsp+F0h] [rbp-10h]
  char *v319; // [rsp+F8h] [rbp-8h]
  __int64 v320; // [rsp+100h] [rbp+0h] BYREF
  SURFACE *v321; // [rsp+108h] [rbp+8h]
  SURFOBJ *v322; // [rsp+110h] [rbp+10h]
  DC *v323; // [rsp+120h] [rbp+20h] BYREF
  int v324; // [rsp+128h] [rbp+28h]
  __int64 v325; // [rsp+130h] [rbp+30h]
  __int64 v326; // [rsp+138h] [rbp+38h]
  _OWORD v327[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v328[2]; // [rsp+160h] [rbp+60h] BYREF
  char v329; // [rsp+180h] [rbp+80h]
  const struct MATRIX *v330; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v331[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v332; // [rsp+1C0h] [rbp+C0h]
  char v333[24]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v334; // [rsp+1E0h] [rbp+E0h]
  int v335; // [rsp+1F0h] [rbp+F0h]
  __int64 v336; // [rsp+1F8h] [rbp+F8h] BYREF
  int v337; // [rsp+200h] [rbp+100h]
  struct Gre::Base::SESSION_GLOBALS *v338; // [rsp+208h] [rbp+108h]
  __int64 v339; // [rsp+210h] [rbp+110h]
  _OWORD v340[2]; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v341[2]; // [rsp+238h] [rbp+138h] BYREF
  __int16 v342; // [rsp+258h] [rbp+158h]
  __int64 v343; // [rsp+260h] [rbp+160h] BYREF
  int v344; // [rsp+268h] [rbp+168h]
  struct Gre::Base::SESSION_GLOBALS *v345; // [rsp+270h] [rbp+170h]
  __int64 v346; // [rsp+278h] [rbp+178h]
  _OWORD v347[2]; // [rsp+280h] [rbp+180h] BYREF
  _OWORD v348[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v349; // [rsp+2C0h] [rbp+1C0h]
  __int64 v350; // [rsp+2C8h] [rbp+1C8h]
  __int128 v351; // [rsp+2D0h] [rbp+1D0h]
  __int64 v352; // [rsp+2E0h] [rbp+1E0h]
  __int64 v353; // [rsp+2E8h] [rbp+1E8h]
  __int64 v354; // [rsp+2F0h] [rbp+1F0h]
  __int64 v355; // [rsp+2F8h] [rbp+1F8h]
  __int64 v356; // [rsp+300h] [rbp+200h]
  RECTL v357; // [rsp+310h] [rbp+210h] BYREF
  POINTL v358; // [rsp+320h] [rbp+220h] BYREF
  int v359; // [rsp+328h] [rbp+228h]
  int v360; // [rsp+32Ch] [rbp+22Ch]
  __m128i v361; // [rsp+330h] [rbp+230h] BYREF

  v11 = (struct XDCOBJ *)a1;
  x = a7;
  v14 = a5;
  y = a8;
  v17 = a6;
  v307 = a6;
  v295 = a4;
  if ( (a11 & 4) != 0
    && (CurrentThread = GreGetCurrentThread(), v17 = v307, a4 = v295, v14 = a5, v11 = (struct XDCOBJ *)a1, CurrentThread) )
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
    v293 = 0;
    if ( (*(_DWORD *)(*(_QWORD *)v11 + 36LL) & 0x10000) == 0 )
    {
      v20 = a9 & 0x5FFFFFFF;
      if ( ((*((_BYTE *)gajRop3 + (unsigned __int8)a9) | *((_BYTE *)gajRop3 + BYTE1(a9))) & 2) != 0
        && v20 != 16711778
        && v20 != 66 )
      {
        bSpDwmValidateSurface(v11, left, top, a4, v14);
      }
      if ( OPTAPIDCOBJ::bValid(v307) )
      {
        memset(v327, 0, sizeof(v327));
        v325 = *((_QWORD *)v307 + 2);
        v326 = 0;
        v323 = 0;
        v324 = 0;
        PushThreadGuardedObject(
          v327,
          &v323,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v328, 0, sizeof(v328));
        PushThreadGuardedObject(
          v328,
          &v323,
          UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
        v329 = 0;
        v323 = *(DC **)v307;
        bSpDwmValidateSurface((struct XDCOBJ *)&v323, a7, a8, v295, a5);
        v21 = *((_QWORD *)*a1 + 122);
        v22 = *(_DWORD *)(v21 + 108);
        if ( ((*(_BYTE *)(*((_QWORD *)v323 + 122) + 108LL) ^ *(_BYTE *)(v21 + 108)) & 7) != 0
          && (a9 < 0 && (v22 & 1) != 0 || (v22 & 9) == 9) )
        {
          v165 = *(_DWORD *)(v21 + 308);
          v317 = DC::dwSetLayout(*a1, -1, 0);
          left = v165 - v295 - left;
          v316 = 0x80000000;
        }
        else
        {
          v317 = 0;
          v316 = 0;
        }
        DC::QuickInitXform(*a1, &v320, 516);
        DC::QuickInitXform(v323, &v330, 516);
        if ( (*(_BYTE *)(v320 + 32) & 1) == 0 || !EXFORMOBJ::bEqualExceptTranslations((EXFORMOBJ *)&v320, v330) )
        {
          v27 = a1;
          v19 = GrepStretchBlt((struct XDCOBJ *)a1, left, top, v295, a5, v307, a7, a8, v295, a5, v20, a10, 0);
          goto LABEL_55;
        }
        v23 = a8 + a5;
        v318 = (__int64)v323;
        v24 = a7 + v295;
        v358.x = a7;
        v359 = a7 + v295;
        v358.y = a8;
        v360 = a8 + a5;
        if ( (*((_BYTE *)v330 + 32) & 0x43) == 0x43
          || (v25 = bCvtPts1(v330, &v358, 2), v23 = v360, v24 = v359, y = v358.y, x = v358.x, v25) )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(v318 + 976) + 108LL) & 1) != 0 )
          {
            ++x;
            ++v24;
            v358.x = x;
            v359 = v24;
          }
        }
        if ( x > v24 )
        {
          v358.x = v24;
          v359 = x;
        }
        if ( y > v23 )
        {
          v358.y = v23;
          v360 = y;
        }
        right = v295 + left;
        v27 = a1;
        v357.bottom = top + a5;
        v357.left = left;
        v357.top = top;
        v28 = *a1;
        v357.right = v295 + left;
        if ( (*(_BYTE *)(v320 + 32) & 0x43) == 0x43
          || (v29 = bCvtPts1(v320, &v357, 2), right = v357.right, top = v357.top, left = v357.left, v29) )
        {
          if ( (*(_DWORD *)(*((_QWORD *)v28 + 122) + 108LL) & 1) != 0 )
          {
            ++left;
            ++right;
            v357.left = left;
            v357.right = right;
          }
        }
        if ( left > right )
        {
          v30 = left;
          v357.left = right;
          left = right;
          v357.right = v30;
          right = v30;
        }
        bottom = v357.bottom;
        if ( top > v357.bottom )
        {
          v357.top = v357.bottom;
          v357.bottom = top;
          top = bottom;
        }
        if ( top == v357.bottom || left == right )
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
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
            if ( top < *((_DWORD *)v32 + 267) )
            {
              *((_DWORD *)v32 + 267) = top;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
            if ( right > *((_DWORD *)v32 + 268) )
            {
              *((_DWORD *)v32 + 268) = right;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
            if ( v357.bottom > *((_DWORD *)v32 + 269) )
            {
              *((_DWORD *)v32 + 269) = v357.bottom;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
          }
          v34 = *a1;
          if ( (*((_DWORD *)*a1 + 9) & 0x80u) != 0 )
          {
            if ( left < *((_DWORD *)v34 + 274) )
            {
              *((_DWORD *)v34 + 274) = left;
              right = v357.right;
              top = v357.top;
            }
            if ( top < *((_DWORD *)v34 + 275) )
            {
              *((_DWORD *)v34 + 275) = top;
              right = v357.right;
            }
            if ( right > *((_DWORD *)v34 + 276) )
              *((_DWORD *)v34 + 276) = right;
            if ( v357.bottom > *((_DWORD *)v34 + 277) )
              *((_DWORD *)v34 + 277) = v357.bottom;
          }
        }
        SURFMEM::SURFMEM(v333, 2);
        v336 = 0;
        v337 = 0;
        v36 = Gre::Base::Globals(v35);
        v339 = 0;
        v338 = v36;
        v336 = 0;
        v337 = 0;
        memset(v340, 0, sizeof(v340));
        PushThreadGuardedObject(
          v340,
          &v336,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v341, 0, sizeof(v341));
        PushThreadGuardedObject(
          v341,
          &v336,
          UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic);
        v342 = 256;
        v343 = 0;
        v344 = 0;
        v38 = Gre::Base::Globals(v37);
        v346 = 0;
        v345 = v38;
        v343 = 0;
        v344 = 0;
        memset(v347, 0, sizeof(v347));
        PushThreadGuardedObject(
          v347,
          &v343,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v348, 0, sizeof(v348));
        PushThreadGuardedObject(
          v348,
          &v343,
          UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic);
        v349 = 256;
        memset(v331, 0, sizeof(v331));
        v334 = 0;
        v351 = 0;
        v356 = 0;
        v332 = 0;
        v335 = 0;
        v350 = 0;
        v352 = 0;
        v355 = 0;
        v353 = 0;
        v354 = 0;
        v336 = 0;
        v343 = 0;
        if ( !(unsigned int)DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v331, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v323) )
        {
          v166 = XDCOBJ::bFullScreen((XDCOBJ *)a1);
          v167 = !*((_QWORD *)v323 + 62) || (unsigned int)DC::bInFullScreen(v323);
          v293 = v166 | v167;
          goto LABEL_54;
        }
        v39 = *a1;
        v40 = *((_QWORD *)*a1 + 62);
        v321 = (SURFACE *)v40;
        if ( !v40 )
        {
          v293 = 1;
          goto LABEL_54;
        }
        v41 = *((_QWORD *)v39 + 11);
        v42 = *(_QWORD *)(v40 + 160);
        v311 = v41;
        v315 = BYTE2(v20) | (BYTE2(v20) << 8);
        if ( ((BYTE2(v20) ^ (unsigned __int8)(16 * BYTE2(v20))) & 0xF0) != 0 )
        {
          v152 = *((_QWORD *)v39 + 122);
          v153 = (char *)v39 + 1200;
          v318 = (__int64)v39 + 1200;
          if ( (*(_DWORD *)(v152 + 152) & 0x1000) != 0 )
            GreDCSelectBrush(v39, *(_QWORD *)(v152 + 160));
          v39 = *a1;
          v154 = *((_QWORD *)*a1 + 122);
          v155 = *(_DWORD *)(v154 + 152);
          if ( (v155 & 1) != 0 || (*((_DWORD *)v39 + 79) & 1) != 0 )
          {
            *(_DWORD *)(v154 + 152) = v155 & 0xFFFFFFFE;
            *((_DWORD *)*a1 + 79) &= ~1u;
            EBRUSHOBJ::vInitBrush(v153, *a1, *((_QWORD *)*a1 + 17), v41, v42, v40, 1);
            v39 = *a1;
          }
        }
        else
        {
          v318 = 0;
        }
        v43 = (Gre::Base *)(*((_DWORD *)v39 + 10) & 1);
        v357.left += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 254);
        v357.right += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 254);
        v357.top += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 255);
        v357.bottom += *((_DWORD *)v39 + 2 * (_QWORD)v43 + 255);
        if ( !*((_QWORD *)v323 + 62) )
          goto LABEL_53;
        v52 = Gre::Base::Globals(v43);
        v53 = *((_QWORD *)v323 + 62);
        if ( v53 )
        {
          if ( v326 )
            v53 = v326;
        }
        else
        {
          v53 = *((_QWORD *)v52 + 547);
        }
        v312 = v53;
        if ( !v53 )
          goto LABEL_53;
        if ( (a11 & 2) == 0 )
        {
          if ( (v335 & 0x400000) == 0
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
          v53 = v312;
        }
LABEL_85:
        v56 = 0;
        v57 = v357.left;
        v58 = v357.top;
        v59 = *(_QWORD *)(v53 + 48);
        v60 = *(_QWORD *)(v53 + 160);
        v61 = *((_DWORD *)v323 + 10) & 1;
        v62 = 0;
        v63 = v357.top - *((_DWORD *)v323 + 2 * v61 + 255) - v358.y;
        v64 = v357.left - *((_DWORD *)v323 + 2 * v61 + 254) - v358.x;
        v302 = v63;
        v322 = (SURFOBJ *)(v53 + 24);
        if ( v59 && v53 == *(_QWORD *)(v59 + 2544) && (*(_DWORD *)(v59 + 40) & 0x20000) != 0 )
        {
          v62 = *(_DWORD *)(v59 + 2576);
          v56 = *(_DWORD *)(v59 + 2580);
        }
        if ( v62 + v64 > v357.left )
          v57 = v62 + v64;
        v357.left = v57;
        v294 = v57;
        if ( v63 + v56 > v357.top )
          v58 = v63 + v56;
        v357.top = v58;
        v65 = v62 + v64 + *(_DWORD *)(v53 + 56);
        v66 = v357.right;
        if ( v65 < v357.right )
          v66 = v65;
        v357.right = v66;
        v67 = v56 + v63 + *(_DWORD *)(v53 + 60);
        v68 = v357.bottom;
        if ( v67 < v357.bottom )
          v68 = v67;
        v357.bottom = v68;
        if ( v57 < v66 && v58 < v68 )
        {
          v69 = a1;
          v70 = *a1;
          if ( v57 >= *((_DWORD *)*a1 + 250) && v66 <= *((_DWORD *)v70 + 252) && v58 >= *((_DWORD *)v70 + 251) )
          {
            v319 = 0;
            if ( v68 <= *((_DWORD *)v70 + 253) )
            {
              v71 = (__m128i)v357;
LABEL_102:
              v72 = *v69;
              v73 = *((_DWORD *)v72 + 9);
              if ( (v73 & 0xE0) == 0 )
                goto LABEL_116;
              v361 = v71;
              v74 = *((_DWORD *)v72 + 10) & 1;
              v75 = v57 - *((_DWORD *)v72 + 2 * v74 + 254);
              v361.m128i_i32[0] = v75;
              v76 = v71.m128i_i32[2] - *((_DWORD *)v72 + 2 * v74 + 254);
              v361.m128i_i32[2] = v76;
              v77 = v71.m128i_i32[1] - *((_DWORD *)v72 + 2 * v74 + 255);
              v361.m128i_i32[1] = v77;
              v361.m128i_i32[3] = v71.m128i_i32[3] - *((_DWORD *)v72 + 2 * v74 + 255);
              if ( (v73 & 0x40) == 0 )
                goto LABEL_116;
              v78 = *((_DWORD *)v72 + 270);
              v79 = *((_DWORD *)v72 + 272);
              if ( v78 == v79 || (v80 = *((_DWORD *)v72 + 273), *((_DWORD *)v72 + 271) == v80) )
              {
                *(__m128i *)((char *)v72 + 1080) = v361;
              }
              else
              {
                if ( v75 < v78 )
                {
                  *((_DWORD *)v72 + 270) = v75;
                  v57 = v357.left;
                  v76 = v361.m128i_i32[2];
                  v77 = v361.m128i_i32[1];
                  v294 = v357.left;
                }
                if ( v77 < *((_DWORD *)v72 + 271) )
                {
                  *((_DWORD *)v72 + 271) = v77;
                  v57 = v357.left;
                  v76 = v361.m128i_i32[2];
                  v294 = v357.left;
                }
                if ( v76 > v79 )
                {
                  *((_DWORD *)v72 + 272) = v76;
                  v57 = v357.left;
                  v294 = v357.left;
                }
                if ( v361.m128i_i32[3] <= v80 )
                  goto LABEL_115;
                *((_DWORD *)v72 + 273) = v361.m128i_i32[3];
              }
              v57 = v357.left;
              v294 = v357.left;
LABEL_115:
              v306 = (XLATEOBJ *)*((_QWORD *)*a1 + 148);
              if ( v306 )
              {
                v308 = 0;
                RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v308, 0x70u);
                RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v308);
                v310 = 0;
                RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v310, 0x70u);
                RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v310);
                if ( v308 )
                {
                  if ( v310 )
                  {
                    RGNOBJ::vSet((RGNOBJ *)&v310, (const struct _RECTL *const)&v361);
                    if ( RGNOBJ::bMerge((RGNOBJ *)&v308, (struct RGNOBJ *)&v306, (struct RGNOBJ *)&v310, 0xEu) )
                    {
                      RGNOBJ::vSwap((RGNOBJ *)&v306, (struct RGNOBJ *)&v308);
                      *((_QWORD *)*a1 + 148) = v306;
                    }
                  }
                }
                RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v310);
                RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v310);
                RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v308);
                RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v308);
                v57 = v357.left;
                v294 = v357.left;
              }
LABEL_116:
              v358.x = v57 - v64;
              v298 = v57 - v64;
              v81 = *a1;
              v82 = (unsigned int)(v357.top - v63);
              v358.y = v357.top - v63;
              v304 = v357.top - v63;
              if ( v312 == *((_QWORD *)v81 + 62) )
              {
                v99 = 0;
                v293 = 1;
                v27 = a1;
LABEL_165:
                LODWORD(v107) = 0;
                LODWORD(v108) = 0;
                v303 = v357.top;
                v309 = v357.right;
                v306 = v99;
                v296 = v357.bottom;
                v314 = 0;
                v313 = 0;
                if ( *((int *)v321 + 36) < 0 )
                {
                  v168 = (_DWORD *)*((_QWORD *)v321 + 6);
                  if ( v168 )
                  {
                    if ( (v168[10] & 0x20000) != 0 )
                    {
                      LODWORD(v107) = v168[644];
                      v108 = (unsigned int)v168[645];
                      v314 = (unsigned int)v107;
                      v313 = v108;
                    }
                  }
                }
                LODWORD(v109) = 0;
                v110 = 0;
                LODWORD(v111) = v108 + *((_DWORD *)v321 + 15);
                v311 = (unsigned int)(v107 + *((_DWORD *)v321 + 14));
                v307 = 0;
                v361.m128i_i64[0] = 0;
                if ( *(int *)(v312 + 144) < 0 )
                {
                  v169 = *(_DWORD **)(v312 + 48);
                  if ( v169 )
                  {
                    if ( (v169[10] & 0x20000) != 0 )
                    {
                      v110 = v169[644];
                      v109 = (unsigned int)v169[645];
                      v307 = (OPTAPIDCOBJ *)v110;
                      v361.m128i_i64[0] = v109;
                    }
                  }
                }
                v112 = v110 + *(_DWORD *)(v312 + 56);
                LODWORD(v308) = v109 + *(_DWORD *)(v312 + 60);
                if ( v27 && (v113 = *((_DWORD *)v81 + 130), (v113 & 1) != 0) && (v113 & 2) == 0 )
                {
                  v171 = (__m128i)LODWORD(FLOAT_1_0);
                  *(float *)v171.m128i_i32 = 1.0 / *((float *)v81 + 131);
                  v172 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v107);
                  v173 = (__m128i)LODWORD(FLOAT_1_0);
                  *(float *)v173.m128i_i32 = 1.0 / *((float *)v81 + 132);
                  *(float *)v172.m128i_i32 = *(float *)v172.m128i_i32 * *(float *)v171.m128i_i32;
                  v174 = _mm_cvtsi128_si32(v172);
                  v175 = (unsigned __int8)(v174 >> 23);
                  if ( v175 > 0x9E )
                    goto LABEL_356;
                  v176 = v174 & 0x7FFFFF | 0x800000LL;
                  if ( v175 < 0x76 )
                    v177 = v176 >> (118 - (unsigned __int8)v175);
                  else
                    v177 = v176 << ((unsigned __int8)v175 - 118);
                  v107 = (v177 + 0x80000000LL) >> 32;
                  if ( v174 < 0 )
                    v107 = (unsigned int)-(int)v107;
                  v178 = _mm_cvtsi128_si32(v173);
                  v314 = v107;
                  v179 = (unsigned __int8)(v178 >> 23);
                  if ( v179 > 0x9E )
                    goto LABEL_356;
                  v180 = v178 & 0x7FFFFF | 0x800000LL;
                  if ( v179 < 0x76 )
                    v181 = v180 >> (118 - (unsigned __int8)v179);
                  else
                    v181 = v180 << ((unsigned __int8)v179 - 118);
                  v108 = (v181 + 0x80000000LL) >> 32;
                  if ( v178 < 0 )
                    v108 = (unsigned int)-(int)v108;
                  v182 = _mm_cvtsi128_si32(v171);
                  v313 = v108;
                  v183 = (unsigned __int8)(v182 >> 23);
                  if ( v183 > 0x9E )
                    goto LABEL_356;
                  v184 = v182 & 0x7FFFFF | 0x800000LL;
                  if ( v183 < 0x76 )
                    v185 = v184 >> (118 - (unsigned __int8)v183);
                  else
                    v185 = v184 << ((unsigned __int8)v183 - 118);
                  v186 = (v185 + 0x80000000LL) >> 32;
                  if ( v182 < 0 )
                    v186 = (unsigned int)-(int)v186;
                  v187 = _mm_cvtsi128_si32(v173);
                  v311 = v186;
                  v188 = (unsigned __int8)(v187 >> 23);
                  if ( v188 > 0x9E )
                  {
LABEL_356:
                    LODWORD(v111) = 0;
                    LODWORD(v108) = 0;
                    LODWORD(v107) = 0;
                    LODWORD(v311) = 0;
                    v314 = 0;
                    v313 = 0;
                  }
                  else
                  {
                    v189 = v187 & 0x7FFFFF | 0x800000LL;
                    if ( v188 < 0x76 )
                      v190 = v189 >> (118 - (unsigned __int8)v188);
                    else
                      v190 = v189 << ((unsigned __int8)v188 - 118);
                    v111 = (v190 + 0x80000000LL) >> 32;
                    if ( v187 < 0 )
                      LODWORD(v111) = -(int)v111;
                  }
                  v191 = (__m128i)COERCE_UNSIGNED_INT((float)v57);
                  *(float *)v191.m128i_i32 = *(float *)v191.m128i_i32 * *(float *)v171.m128i_i32;
                  v192 = _mm_cvtsi128_si32(v191);
                  v193 = (unsigned __int8)(v192 >> 23);
                  if ( v193 > 0x9E )
                    goto LABEL_357;
                  v194 = v173;
                  v195 = v192 & 0x7FFFFF | 0x800000LL;
                  if ( v193 < 0x76 )
                    v196 = v195 >> (118 - (unsigned __int8)v193);
                  else
                    v196 = v195 << ((unsigned __int8)v193 - 118);
                  v115 = (v196 + 0x80000000LL) >> 32;
                  if ( v192 < 0 )
                    LODWORD(v115) = -(int)v115;
                  *(float *)v194.m128i_i32 = *(float *)v173.m128i_i32 * (float)v357.top;
                  v197 = _mm_cvtsi128_si32(v194);
                  v198 = (unsigned __int8)(v197 >> 23);
                  if ( v198 > 0x9E )
                    goto LABEL_357;
                  *(float *)v171.m128i_i32 = *(float *)v171.m128i_i32 * (float)v309;
                  v199 = v197 & 0x7FFFFF | 0x800000LL;
                  if ( v198 < 0x76 )
                    v200 = v199 >> (118 - (unsigned __int8)v198);
                  else
                    v200 = v199 << ((unsigned __int8)v198 - 118);
                  v116 = (v200 + 0x80000000LL) >> 32;
                  if ( v197 < 0 )
                    LODWORD(v116) = -(int)v116;
                  v201 = _mm_cvtsi128_si32(v171);
                  v202 = (unsigned __int8)(v201 >> 23);
                  if ( v202 > 0x9E )
                    goto LABEL_357;
                  *(float *)v173.m128i_i32 = *(float *)v173.m128i_i32 * (float)v357.bottom;
                  v203 = v201 & 0x7FFFFF | 0x800000LL;
                  if ( v202 < 0x76 )
                    v204 = v203 >> (118 - (unsigned __int8)v202);
                  else
                    v204 = v203 << ((unsigned __int8)v202 - 118);
                  v117 = (v204 + 0x80000000LL) >> 32;
                  if ( v201 < 0 )
                    LODWORD(v117) = -(int)v117;
                  v205 = _mm_cvtsi128_si32(v173);
                  v206 = (unsigned __int8)(v205 >> 23);
                  if ( v206 > 0x9E )
                  {
LABEL_357:
                    LODWORD(v114) = 0;
                    LODWORD(v117) = 0;
                    LODWORD(v116) = 0;
                    LODWORD(v115) = 0;
                  }
                  else
                  {
                    v207 = v205 & 0x7FFFFF | 0x800000LL;
                    if ( v206 < 0x76 )
                      v208 = v207 >> (118 - (unsigned __int8)v206);
                    else
                      v208 = v207 << ((unsigned __int8)v206 - 118);
                    v114 = (v208 + 0x80000000LL) >> 32;
                    if ( v205 < 0 )
                      LODWORD(v114) = -(int)v114;
                  }
                }
                else
                {
                  LODWORD(v114) = v357.bottom;
                  LODWORD(v115) = v57;
                  LODWORD(v116) = v357.top;
                  LODWORD(v117) = v309;
                }
                v118 = *((_DWORD *)v323 + 130);
                LODWORD(v310) = v118;
                v301 = v118 & 1;
                if ( (v118 & 1) == 0 || (v118 & 2) != 0 )
                {
                  LODWORD(v119) = v308;
                  LODWORD(v120) = v112;
                  LODWORD(v121) = v304;
                  LODWORD(v122) = v298;
                }
                else
                {
                  v209 = (__m128i)LODWORD(FLOAT_1_0);
                  *(float *)v209.m128i_i32 = 1.0 / *((float *)v323 + 131);
                  v210 = 1.0 / *((float *)v323 + 132);
                  v211 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v307);
                  *(float *)v211.m128i_i32 = *(float *)v211.m128i_i32 * *(float *)v209.m128i_i32;
                  v212 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v109);
                  v213 = _mm_cvtsi128_si32(v211);
                  v214 = (unsigned __int8)(v213 >> 23);
                  v215 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v308);
                  if ( v214 > 0x9E )
                    goto LABEL_397;
                  *(float *)v212.m128i_i32 = *(float *)v212.m128i_i32 * v210;
                  v216 = v213 & 0x7FFFFF | 0x800000LL;
                  if ( v214 < 0x76 )
                    v217 = v216 >> (118 - (unsigned __int8)v214);
                  else
                    v217 = v216 << ((unsigned __int8)v214 - 118);
                  v218 = (v217 + 0x80000000LL) >> 32;
                  if ( v213 < 0 )
                    v218 = (unsigned int)-(int)v218;
                  v307 = (OPTAPIDCOBJ *)v218;
                  v219 = _mm_cvtsi128_si32(v212);
                  v220 = (unsigned __int8)(v219 >> 23);
                  if ( v220 > 0x9E )
                    goto LABEL_397;
                  v221 = v219 & 0x7FFFFF | 0x800000LL;
                  if ( v220 < 0x76 )
                    v222 = v221 >> (118 - (unsigned __int8)v220);
                  else
                    v222 = v221 << ((unsigned __int8)v220 - 118);
                  v223 = (v222 + 0x80000000LL) >> 32;
                  if ( v219 < 0 )
                    v223 = (unsigned int)-(int)v223;
                  v224 = _mm_cvtsi128_si32(v209);
                  v361.m128i_i64[0] = v223;
                  v225 = (unsigned __int8)(v224 >> 23);
                  if ( v225 > 0x9E )
                    goto LABEL_397;
                  *(float *)v215.m128i_i32 = *(float *)v215.m128i_i32 * v210;
                  v226 = v224 & 0x7FFFFF | 0x800000LL;
                  if ( v225 < 0x76 )
                    v227 = v226 >> (118 - (unsigned __int8)v225);
                  else
                    v227 = v226 << ((unsigned __int8)v225 - 118);
                  v120 = (v227 + 0x80000000LL) >> 32;
                  if ( v224 < 0 )
                    LODWORD(v120) = -(int)v120;
                  v228 = _mm_cvtsi128_si32(v215);
                  v229 = (unsigned __int8)(v228 >> 23);
                  if ( v229 > 0x9E )
                  {
LABEL_397:
                    LODWORD(v120) = 0;
                    LODWORD(v119) = 0;
                    v361.m128i_i32[0] = 0;
                    v307 = 0;
                  }
                  else
                  {
                    v230 = v228 & 0x7FFFFF | 0x800000LL;
                    if ( v229 < 0x76 )
                      v231 = v230 >> (118 - (unsigned __int8)v229);
                    else
                      v231 = v230 << ((unsigned __int8)v229 - 118);
                    v119 = (v231 + 0x80000000LL) >> 32;
                    if ( v228 < 0 )
                      LODWORD(v119) = -(int)v119;
                  }
                  v232 = (__m128i)COERCE_UNSIGNED_INT((float)v298);
                  v233 = (__m128i)COERCE_UNSIGNED_INT((float)v304);
                  *(float *)v232.m128i_i32 = *(float *)v232.m128i_i32 * *(float *)v209.m128i_i32;
                  v234 = _mm_cvtsi128_si32(v232);
                  v235 = (__m128i)COERCE_UNSIGNED_INT((float)v360);
                  v236 = (unsigned __int8)(v234 >> 23);
                  if ( v236 > 0x9E )
                    goto LABEL_398;
                  *(float *)v233.m128i_i32 = *(float *)v233.m128i_i32 * v210;
                  v237 = v234 & 0x7FFFFF | 0x800000LL;
                  if ( v236 < 0x76 )
                    v238 = v237 >> (118 - (unsigned __int8)v236);
                  else
                    v238 = v237 << ((unsigned __int8)v236 - 118);
                  v122 = (v238 + 0x80000000LL) >> 32;
                  if ( v234 < 0 )
                    LODWORD(v122) = -(int)v122;
                  v239 = _mm_cvtsi128_si32(v233);
                  v240 = (unsigned __int8)(v239 >> 23);
                  if ( v240 > 0x9E )
                    goto LABEL_398;
                  *(float *)v209.m128i_i32 = *(float *)v209.m128i_i32 * (float)v359;
                  v241 = v239 & 0x7FFFFF | 0x800000LL;
                  if ( v240 < 0x76 )
                    v242 = v241 >> (118 - (unsigned __int8)v240);
                  else
                    v242 = v241 << ((unsigned __int8)v240 - 118);
                  v121 = (v242 + 0x80000000LL) >> 32;
                  if ( v239 < 0 )
                    LODWORD(v121) = -(int)v121;
                  if ( (unsigned __int8)(_mm_cvtsi128_si32(v209) >> 23) > 0x9Eu
                    || (*(float *)v235.m128i_i32 = *(float *)v235.m128i_i32 * v210,
                        (unsigned __int8)(_mm_cvtsi128_si32(v235) >> 23) > 0x9Eu) )
                  {
LABEL_398:
                    LODWORD(v107) = v314;
                    LODWORD(v121) = 0;
                    LODWORD(v108) = v313;
                    LODWORD(v122) = 0;
                  }
                  else
                  {
                    LODWORD(v107) = v314;
                    LODWORD(v108) = v313;
                  }
                }
                v123 = v122 - v115;
                v124 = v121 - v116;
                if ( (int)v107 > (int)v115 )
                  LODWORD(v115) = v107;
                if ( (int)v108 > (int)v116 )
                  LODWORD(v116) = v108;
                if ( (int)v311 < (int)v117 )
                  LODWORD(v117) = v311;
                if ( (int)v111 < (int)v114 )
                  LODWORD(v114) = v111;
                if ( (int)v117 < (int)v115 )
                {
                  LODWORD(v115) = v117;
                }
                else if ( (int)v114 < (int)v116 )
                {
                  LODWORD(v116) = v114;
                }
                LODWORD(v125) = v123 + v115;
                v126 = v123 + v117;
                v127 = v124 + v116;
                LODWORD(v114) = v124 + v114;
                if ( (int)v307 > v123 + (int)v115 )
                  LODWORD(v125) = (_DWORD)v307;
                if ( v361.m128i_i32[0] > v127 )
                  v127 = v361.m128i_i32[0];
                if ( (int)v120 < v126 )
                  v126 = v120;
                if ( (int)v119 < (int)v114 )
                  LODWORD(v114) = v119;
                if ( v126 < (int)v125 )
                {
                  LODWORD(v125) = v126;
                }
                else if ( (int)v114 < v127 )
                {
                  v127 = v114;
                }
                LODWORD(v128) = v125 - v123;
                LODWORD(v129) = v126 - v123;
                if ( (int)v125 - v123 >= v126 - v123
                  || (LODWORD(v130) = v127 - v124, LODWORD(v131) = v114 - v124, v127 - v124 >= (int)v114 - v124) )
                {
                  v134 = v321;
                  v135 = 0;
                }
                else
                {
                  if ( a1 )
                  {
                    v132 = *a1;
                    v133 = *((_DWORD *)*a1 + 130);
                    if ( (v133 & 1) != 0 && (v133 & 2) == 0 )
                    {
                      v243 = *((float *)v132 + 131);
                      v244 = _mm_cvtsi32_si128(v129);
                      v245 = _mm_cvtsi32_si128(v131);
                      v246 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v128);
                      *(float *)v246.m128i_i32 = *(float *)v246.m128i_i32 * v243;
                      v247 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v130);
                      v248 = _mm_cvtsi128_si32(v246);
                      v249 = (__m128i)_mm_cvtepi32_ps(v244);
                      v250 = (unsigned __int8)(v248 >> 23);
                      v251 = (__m128i)_mm_cvtepi32_ps(v245);
                      if ( v250 > 0x9E )
                        goto LABEL_423;
                      v252 = *((float *)v132 + 132);
                      *(float *)v247.m128i_i32 = *(float *)v247.m128i_i32 * v252;
                      v253 = v248 & 0x7FFFFF | 0x800000LL;
                      if ( v250 < 0x76 )
                        v254 = v253 >> (118 - (unsigned __int8)v250);
                      else
                        v254 = v253 << ((unsigned __int8)v250 - 118);
                      v128 = (v254 + 0x80000000LL) >> 32;
                      if ( v248 < 0 )
                        LODWORD(v128) = -(int)v128;
                      v255 = _mm_cvtsi128_si32(v247);
                      v256 = (unsigned __int8)(v255 >> 23);
                      if ( v256 > 0x9E )
                        goto LABEL_423;
                      *(float *)v249.m128i_i32 = *(float *)v249.m128i_i32 * v243;
                      v257 = v255 & 0x7FFFFF | 0x800000LL;
                      if ( v256 < 0x76 )
                        v258 = v257 >> (118 - (unsigned __int8)v256);
                      else
                        v258 = v257 << ((unsigned __int8)v256 - 118);
                      v130 = (v258 + 0x80000000LL) >> 32;
                      if ( v255 < 0 )
                        LODWORD(v130) = -(int)v130;
                      v259 = _mm_cvtsi128_si32(v249);
                      v260 = (unsigned __int8)(v259 >> 23);
                      if ( v260 > 0x9E )
                        goto LABEL_423;
                      *(float *)v251.m128i_i32 = *(float *)v251.m128i_i32 * v252;
                      v261 = v259 & 0x7FFFFF | 0x800000LL;
                      if ( v260 < 0x76 )
                        v262 = v261 >> (118 - (unsigned __int8)v260);
                      else
                        v262 = v261 << ((unsigned __int8)v260 - 118);
                      v129 = (v262 + 0x80000000LL) >> 32;
                      if ( v259 < 0 )
                        LODWORD(v129) = -(int)v129;
                      v263 = _mm_cvtsi128_si32(v251);
                      v264 = (unsigned __int8)(v263 >> 23);
                      if ( v264 > 0x9E )
                      {
LABEL_423:
                        LODWORD(v131) = 0;
                        LODWORD(v129) = 0;
                        LODWORD(v130) = 0;
                        LODWORD(v128) = 0;
                      }
                      else
                      {
                        v265 = v263 & 0x7FFFFF | 0x800000LL;
                        if ( v264 < 0x76 )
                          v266 = v265 >> (118 - (unsigned __int8)v264);
                        else
                          v266 = v265 << ((unsigned __int8)v264 - 118);
                        v131 = (v266 + 0x80000000LL) >> 32;
                        if ( v263 < 0 )
                          LODWORD(v131) = -(int)v131;
                      }
                    }
                  }
                  if ( v301 && (v310 & 2) == 0 )
                  {
                    v267 = _mm_cvtsi32_si128(v126);
                    v268 = _mm_cvtsi32_si128(v114);
                    v269 = (__m128i)*((unsigned int *)v323 + 131);
                    v270 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v125);
                    *(float *)v270.m128i_i32 = *(float *)v270.m128i_i32 * *(float *)v269.m128i_i32;
                    v271 = _mm_cvtsi128_si32(v270);
                    LODWORD(v272) = _mm_cvtepi32_ps(v267).m128_u32[0];
                    v273 = (unsigned __int8)(v271 >> 23);
                    LODWORD(v274) = _mm_cvtepi32_ps(v268).m128_u32[0];
                    if ( v273 > 0x9E )
                      goto LABEL_448;
                    v275 = (__m128i)*((unsigned int *)v323 + 132);
                    v276 = v271 & 0x7FFFFF | 0x800000LL;
                    v277 = v275;
                    if ( v273 < 0x76 )
                      v278 = v276 >> (118 - (unsigned __int8)v273);
                    else
                      v278 = v276 << ((unsigned __int8)v273 - 118);
                    v125 = (v278 + 0x80000000LL) >> 32;
                    if ( v271 < 0 )
                      LODWORD(v125) = -(int)v125;
                    *(float *)v277.m128i_i32 = *(float *)v275.m128i_i32 * (float)v127;
                    v279 = _mm_cvtsi128_si32(v277);
                    v280 = (unsigned __int8)(v279 >> 23);
                    if ( v280 > 0x9E )
                      goto LABEL_448;
                    *(float *)v269.m128i_i32 = *(float *)v269.m128i_i32 * v272;
                    v281 = v279 & 0x7FFFFF | 0x800000LL;
                    if ( v280 < 0x76 )
                      v282 = v281 >> (118 - (unsigned __int8)v280);
                    else
                      v282 = v281 << ((unsigned __int8)v280 - 118);
                    v283 = (v282 + 0x80000000LL) >> 32;
                    if ( v279 < 0 )
                      LODWORD(v283) = -(int)v283;
                    v284 = _mm_cvtsi128_si32(v269);
                    v127 = v283;
                    v285 = (unsigned __int8)(v284 >> 23);
                    if ( v285 > 0x9E )
                      goto LABEL_448;
                    *(float *)v275.m128i_i32 = *(float *)v275.m128i_i32 * v274;
                    v286 = v284 & 0x7FFFFF | 0x800000LL;
                    if ( v285 < 0x76 )
                      v287 = v286 >> (118 - (unsigned __int8)v285);
                    else
                      v287 = v286 << ((unsigned __int8)v285 - 118);
                    v288 = (v287 + 0x80000000LL) >> 32;
                    if ( v284 < 0 )
                      LODWORD(v288) = -(int)v288;
                    v289 = _mm_cvtsi128_si32(v275);
                    v126 = v288;
                    v290 = (unsigned __int8)(v289 >> 23);
                    if ( v290 > 0x9E )
                    {
LABEL_448:
                      LODWORD(v114) = 0;
                      v126 = 0;
                      v127 = 0;
                      LODWORD(v125) = 0;
                    }
                    else
                    {
                      v291 = v289 & 0x7FFFFF | 0x800000LL;
                      if ( v290 < 0x76 )
                        v292 = v291 >> (118 - (unsigned __int8)v290);
                      else
                        v292 = v291 << ((unsigned __int8)v290 - 118);
                      v114 = (v292 + 0x80000000LL) >> 32;
                      if ( v289 < 0 )
                        LODWORD(v114) = -(int)v114;
                    }
                  }
                  v358.y = v127;
                  v134 = v321;
                  v357.left = v128;
                  v135 = 1;
                  v358.x = v125;
                  v359 = v126;
                  v360 = v114;
                  v357.top = v130;
                  v357.right = v129;
                  v357.bottom = v131;
                  ++*((_DWORD *)v321 + 23);
                }
                v27 = a1;
                v136 = *a1;
                v106 = *((_QWORD *)v323 + 6);
                if ( *((_QWORD *)*a1 + 6) != v106 )
                {
                  if ( !(unsigned int)XDCOBJ::bRedirHooked((XDCOBJ *)a1)
                    || (v136 = *a1, v106 = *((_QWORD *)v323 + 6), *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) != v106) )
                  {
                    if ( *(_WORD *)(v312 + 100) )
                      goto LABEL_270;
                    v156 = (SURFOBJ *)(v312 + 24);
                    if ( *(_QWORD *)(v312 + 24) )
                      goto LABEL_271;
                    v136 = *a1;
                    v106 = *(unsigned int *)(*((_QWORD *)*a1 + 6) + 40LL);
                    if ( (v106 & 0x80u) != 0LL )
                    {
LABEL_270:
                      v156 = v322;
LABEL_271:
                      if ( v135 )
                      {
                        v157 = v331;
                        if ( (*(_DWORD *)(*((_QWORD *)v134 + 6) + 40LL) & 0x80u) == 0 )
                          v157 = 0;
                        v293 = SimBitBlt(
                                 (SURFOBJ *)((char *)v134 + 24),
                                 v156,
                                 v306,
                                 &v357,
                                 &v358,
                                 0,
                                 v318,
                                 (POINTL *)*a1 + 149,
                                 v315,
                                 (__int64)v157);
                      }
                      goto LABEL_208;
                    }
                  }
                }
                v137 = v315;
                if ( v315 == 52428 )
                {
                  v138 = *((_QWORD *)v134 + 6);
                  v139 = a11 & 1;
                  if ( v139 )
                  {
                    v159 = v303 - v296;
                    if ( v303 - v296 < 0 )
                      v159 = v296 - v303;
                    v160 = v296 - v309;
                    if ( v296 - v309 < 0 )
                      v160 = v309 - v296;
                    EtwWindowRendering(
                      *((_QWORD *)v136 + 58),
                      *((_QWORD *)v136 + 59),
                      **((_QWORD **)v136 + 62),
                      v294,
                      v303,
                      v309,
                      v296,
                      *((_QWORD *)v323 + 58),
                      *((_QWORD *)v323 + 59),
                      **((_QWORD **)v323 + 62),
                      v298,
                      v304,
                      v298 + v160,
                      v304 + v159);
                    *((_WORD *)v134 + 51) |= 0x40u;
                    v161 = GreGetCurrentThread();
                    if ( v161 )
                      *((_DWORD *)v161 + 84) &= ~1u;
                    GreClientRgnUpdated(0);
                    GreClientRgnUpdatedStable();
                  }
                  if ( v135 )
                  {
                    if ( (*((_DWORD *)v134 + 36) & 0x400) != 0 )
                      v140 = (*(__int64 (__fastcall **)(__int64, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *))(v138 + 2832))(
                               (__int64)v134 + 24,
                               v322,
                               v319,
                               v306,
                               &v357,
                               &v358);
                    else
                      v140 = ((__int64 (__fastcall *)(char *, SURFOBJ *, char *, XLATEOBJ *, RECTL *, POINTL *))EngCopyBits)(
                               (char *)v134 + 24,
                               v322,
                               v319,
                               v306,
                               &v357,
                               &v358);
                    v293 = v140;
                  }
                  if ( v139 )
                  {
                    *((_WORD *)v134 + 51) &= ~0x40u;
                    v162 = GreGetCurrentThread();
                    if ( v162 )
                      *((_DWORD *)v162 + 84) |= 1u;
                  }
                }
                else if ( v135 )
                {
                  v145 = SURFACE::pfnBitBlt(v134);
                  v293 = ((__int64 (__fastcall *)(char *, __int64, _QWORD, char *, XLATEOBJ *, RECTL *, POINTL *, _QWORD, __int64, __int64, int))v145)(
                           (char *)v134 + 24,
                           v147 + 24,
                           0,
                           v319,
                           v306,
                           &v357,
                           &v358,
                           0,
                           v318,
                           v146 + 1192,
                           v137);
                }
                goto LABEL_208;
              }
              v83 = a10;
              v299 = a10;
              if ( a10 == -1 )
              {
                v82 = *((_QWORD *)v323 + 122);
                v83 = *(_DWORD *)(v82 + 180);
                v299 = v83;
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
                  v142 = *(_QWORD *)(v41 + 80);
                  if ( !v142 )
                    goto LABEL_159;
                  v87 = v142 == *(_QWORD *)(v41 + 72);
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
              LODWORD(v308) = *((_DWORD *)v81 + 30);
              v89 = (XLATEOBJ *)*((_QWORD *)v323 + 11);
              v90 = *((_QWORD *)v81 + 122);
              v306 = v89;
              v91 = (Gre::Base *)*(unsigned int *)(v90 + 176);
              v92 = *(_DWORD *)(v90 + 184);
              v305 = v92;
              v300 = (int)v91;
              if ( v60 && v42 )
              {
                v93 = *(_DWORD *)(v60 + 56);
                v94 = Gre::Base::Globals(v91);
                v361.m128i_i64[0] = *(_QWORD *)v94 + 312LL;
                GreAcquireSemaphoreInternal((HSEMAPHORE)v361.m128i_i64[0]);
                GrepAcquireLockValidate<13>();
                for ( i = 0; ; i = (unsigned int)(i + 1) )
                {
                  if ( (unsigned int)i >= 8 )
                  {
                    SEMOBJ<13>::vUnlock(&v361, flXlate, i);
                    LODWORD(v91) = v300;
                    v92 = v305;
                    v88 = (unsigned int)v308;
                    v83 = v299;
                    v89 = v306;
                    v41 = v311;
                    goto LABEL_136;
                  }
                  flXlate = v60;
                  if ( *(_QWORD *)(v60 + 120) != v60 )
                    flXlate = *(_QWORD *)(v60 + 120);
                  if ( *((_DWORD *)v94 + 8 * v93 + 1104) != *(_DWORD *)(flXlate + 32) )
                    goto LABEL_134;
                  v148 = v42;
                  if ( *(_QWORD *)(v42 + 120) != v42 )
                    v148 = *(_QWORD *)(v42 + 120);
                  v149 = 32LL * v93;
                  if ( *(_DWORD *)((char *)v94 + v149 + 4420) != *(_DWORD *)(v148 + 32) )
                    goto LABEL_134;
                  flXlate = v311;
                  v150 = v311;
                  if ( *(_QWORD *)(v311 + 120) != v311 )
                    v150 = *(_QWORD *)(v311 + 120);
                  if ( *(_DWORD *)((char *)v94 + v149 + 4428) != *(_DWORD *)(v150 + 32) )
                    goto LABEL_134;
                  v99 = *(XLATEOBJ **)((char *)v94 + v149 + 4408);
                  flXlate = v99[3].flXlate;
                  if ( (flXlate & 0x6000) != 0 )
                    goto LABEL_134;
                  flXlate &= 0x100u;
                  if ( (v99->flXlate & 4) == 0 )
                    break;
                  if ( v299 == v99[1].iUniq )
                  {
                    v151 = v306;
                    if ( *(XLATEOBJ **)&v306[5].iUniq != v306 )
                      v151 = *(XLATEOBJ **)&v306[5].iUniq;
                    if ( *(_DWORD *)((char *)v94 + v149 + 4424) == *(_DWORD *)&v151[1].iSrcType )
                    {
LABEL_244:
                      _InterlockedIncrement((volatile signed __int32 *)((char *)v94 + v149 + 4400));
                      *(_DWORD *)(v60 + 56) = v93;
                      SEMOBJ<13>::vUnlock(&v361, flXlate, i);
                      goto LABEL_160;
                    }
                  }
                  if ( (_DWORD)flXlate )
                    goto LABEL_242;
LABEL_134:
                  v93 = ((_BYTE)v93 + 1) & 7;
                }
                if ( !(_DWORD)flXlate )
                  goto LABEL_244;
LABEL_242:
                if ( v305 == v99[1].flXlate && v300 == *(_DWORD *)&v99[1].iSrcType )
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
                  v306 = (XLATEOBJ *)(*(_QWORD *)v100 + 312LL);
                  GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
                  for ( j = 0; (unsigned int)j < 8; j = (unsigned int)(j + 1) )
                  {
                    v101 = *((unsigned int *)v100 + 1164);
                    v103 = *((_QWORD *)v100 + 4 * v101 + 551);
                    if ( !v103 )
                      goto LABEL_145;
                    if ( !*((_DWORD *)v100 + 8 * v101 + 1100) )
                    {
                      FreeThreadBufferWithTag(v103);
LABEL_145:
                      PopThreadGuardedObject(&v99[-2].pulXlate);
                      v104 = v60;
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1100) = 1;
                      *((_QWORD *)v100 + 4 * *((unsigned int *)v100 + 1164) + 551) = v99;
                      if ( *(_QWORD *)(v60 + 120) != v60 )
                        v104 = *(_QWORD *)(v60 + 120);
                      v105 = *(_DWORD *)(v104 + 32);
                      v101 = v311;
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1104) = v105;
                      if ( *(_QWORD *)(v42 + 120) != v42 )
                        v42 = *(_QWORD *)(v42 + 120);
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1105) = *(_DWORD *)(v42 + 32);
                      if ( *(XLATEOBJ **)&v89[5].iUniq != v89 )
                        v89 = *(XLATEOBJ **)&v89[5].iUniq;
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1106) = *(_DWORD *)&v89[1].iSrcType;
                      if ( *(_QWORD *)(v101 + 120) != v101 )
                        v101 = *(_QWORD *)(v101 + 120);
                      *((_DWORD *)v100 + 8 * *((unsigned int *)v100 + 1164) + 1107) = *(_DWORD *)(v101 + 32);
                      v99[1].cEntries = *((_DWORD *)v100 + 1164);
                      *(_DWORD *)(v60 + 56) = *((_DWORD *)v100 + 1164);
                      *((_DWORD *)v100 + 1164) = ((unsigned __int8)*((_DWORD *)v100 + 1164) + 1) & 7;
                      break;
                    }
                    *((_DWORD *)v100 + 1164) = ((_BYTE)v101 + 1) & 7;
                  }
                  SEMOBJ<13>::vUnlock(&v306, v101, j);
                }
LABEL_160:
                v106 = 1;
              }
              else
              {
                v106 = 0;
              }
              v27 = a1;
              v293 = v106;
              v81 = *a1;
              if ( (*((_DWORD *)*a1 + 9) & 1) == 0 )
              {
                v359 = v357.right - v64;
                v360 = v357.bottom - v302;
              }
              if ( !(_DWORD)v106 )
              {
LABEL_208:
                if ( v99 )
                {
                  cEntries = v99[1].cEntries;
                  if ( cEntries >= 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)Gre::Base::Globals((Gre::Base *)v106) + 8 * (int)v99[1].cEntries + 1100);
                  }
                  else if ( cEntries == -1 )
                  {
                    FreeThreadBufferWithTag(v99);
                  }
                }
                goto LABEL_54;
              }
              v57 = v357.left;
              v304 = v358.y;
              v298 = v358.x;
              v294 = v357.left;
              goto LABEL_165;
            }
          }
          v143 = (char *)v70 + 1768;
          v319 = (char *)v70 + 1768;
          v144 = XDCOBJ::prgnEffRao((XDCOBJ *)a1);
          XCLIPOBJ::vSetup((XCLIPOBJ *)v143, v144, (const struct ERECTL *)&v357, 2);
          v71 = *(__m128i *)(v143 + 4);
          v57 = _mm_cvtsi128_si32(v71);
          v357 = (RECTL)v71;
          v294 = v57;
          v357.right = _mm_cvtsi128_si32(_mm_srli_si128(v71, 8));
          if ( v57 != v357.right && v71.m128i_i32[1] != _mm_srli_si128(v71, 8).m128i_i32[1] )
          {
            v69 = a1;
            v357.bottom = _mm_cvtsi128_si32(_mm_srli_si128(v71, 12));
            v357.top = _mm_cvtsi128_si32(_mm_srli_si128(v71, 4));
            goto LABEL_102;
          }
        }
LABEL_53:
        v27 = a1;
        v293 = 1;
LABEL_54:
        DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v331);
        v19 = v293;
LABEL_55:
        if ( v316 )
          DC::dwSetLayout(*v27, -1, v317);
        v44 = v323;
        if ( !v329 )
          v44 = 0;
        v323 = v44;
        PopThreadGuardedObject(v328);
        v45 = v323;
        if ( v323 )
        {
          if ( v324 && (*((_DWORD *)v323 + 11) & 2) != 0 )
          {
            CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
            v48 = v323;
            v49 = CurrentProcessId & 0xFFFFFFFC;
            if ( *(_QWORD *)v323 )
            {
              v50 = (char *)HmgPentryFromPobj(v325, v323);
            }
            else
            {
              v50 = (char *)v323 + 2152;
              *(_OWORD *)((char *)v323 + 2152) = 0;
              *((_QWORD *)v48 + 271) = 0;
              *((_DWORD *)v48 + 540) = -2147483630;
              *((_QWORD *)v48 + 271) = GreEncodeUserModePointer(0);
            }
            if ( v49 == (*((_DWORD *)v50 + 2) & 0xFFFFFFFE) )
            {
              UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v323);
              if ( UserAttr )
                DC::RestoreAttributes(v323, UserAttr);
            }
            *((_DWORD *)v323 + 11) &= ~2u;
            v45 = v323;
            v324 = 0;
          }
          _InterlockedDecrement16((volatile signed __int16 *)v45 + 6);
          v323 = 0;
        }
        PopThreadGuardedObject(v327);
        goto LABEL_61;
      }
      v19 = 0;
    }
LABEL_61:
    if ( v18 )
    {
      v163 = GreGetCurrentThread();
      *((_DWORD *)v163 + 84) &= ~8u;
    }
    return v19;
  }
  v158 = GrepStretchBlt(
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
    v170 = GreGetCurrentThread();
    *((_DWORD *)v170 + 84) &= ~8u;
  }
  return v158;
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
