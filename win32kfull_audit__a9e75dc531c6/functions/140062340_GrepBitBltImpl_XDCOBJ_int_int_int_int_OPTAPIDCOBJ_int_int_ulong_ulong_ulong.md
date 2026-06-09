# GrepBitBltImpl(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,ulong,ulong,ulong)

- ea: `0x140062340`
- end: `0x140064875`
- name: `?GrepBitBltImpl@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHKKK@Z`
- size: `9525`
- prototype: `__int64 __fastcall(DC **, LONG left, LONG top, int, unsigned int, struct OPTAPIDCOBJ *, int, LONG, signed int, unsigned int, char)`
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
        unsigned int a5,
        struct OPTAPIDCOBJ *a6,
        int a7,
        LONG a8,
        signed int a9,
        unsigned int a10,
        char a11)
{
  struct XDCOBJ *v11; // r10
  int x; // r15d
  __int64 v14; // r8
  LONG y; // r12d
  OPTAPIDCOBJ *v17; // rcx
  char v18; // si
  unsigned int v19; // ebx
  unsigned int v20; // r13d
  unsigned int v21; // r13d
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // edx
  LONG v25; // r8d
  LONG v26; // edx
  int v27; // eax
  LONG right; // edx
  DC **v29; // r12
  DC *v30; // rbx
  int v31; // eax
  LONG v32; // eax
  LONG bottom; // r8d
  DC *v34; // rax
  int v35; // ecx
  DC *v36; // rcx
  Gre::Base *v37; // rcx
  struct Gre::Base::SESSION_GLOBALS *v38; // rax
  Gre::Base *v39; // rcx
  struct Gre::Base::SESSION_GLOBALS *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r9
  __int64 v43; // r8
  __int64 v44; // rbx
  __int64 v45; // r14
  __int64 v46; // r12
  unsigned __int8 v47; // cl
  Gre::Base *v48; // rcx
  DC *v49; // rcx
  DC *v50; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v53; // rdi
  unsigned int v54; // ebx
  char *v55; // r14
  struct _DC_ATTR *UserAttr; // rax
  struct Gre::Base::SESSION_GLOBALS *v57; // rax
  __int64 v58; // r10
  int v59; // eax
  int v60; // eax
  int v61; // r9d
  int v62; // r15d
  __int64 v63; // rcx
  __int64 v64; // rbx
  __int64 v65; // rax
  int v66; // edx
  int v67; // edi
  int v68; // r13d
  LONG v69; // ecx
  LONG v70; // ecx
  DC **v71; // rcx
  DC *v72; // rax
  __m128i v73; // xmm2
  DC *v74; // rcx
  int v75; // r10d
  __int64 v76; // rax
  LONG v77; // r9d
  int v78; // edx
  int v79; // r8d
  LONG v80; // r11d
  int v81; // eax
  LONG v82; // r10d
  unsigned __int64 v83; // rcx
  unsigned int v84; // edi
  __int64 v85; // rax
  int v86; // edx
  __int64 v87; // rax
  bool v88; // zf
  int v89; // edx
  XLATEOBJ *v90; // r15
  __int64 v91; // rax
  Gre::Base *v92; // rcx
  int v93; // eax
  unsigned int v94; // r14d
  struct Gre::Base::SESSION_GLOBALS *v95; // r15
  unsigned int i; // r8d
  __int64 v97; // rdx
  XLATEOBJ *XlateObject; // rax
  Gre::Base *v99; // rcx
  XLATEOBJ *v100; // rdi
  struct Gre::Base::SESSION_GLOBALS *v101; // r14
  unsigned int j; // r8d
  unsigned int v103; // edx
  __int64 v104; // rax
  __int64 v105; // rcx
  __int64 v106; // rdx
  int v107; // eax
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r11
  __int64 v111; // r10
  __int64 v112; // rbx
  unsigned int v113; // edx
  __int64 v114; // r13
  unsigned int v115; // ecx
  int v116; // eax
  __int64 v117; // rdx
  __int64 v118; // r12
  __int64 v119; // r15
  __int64 v120; // r14
  int v121; // r9d
  __int64 v122; // r9
  __int64 v123; // rbx
  __int64 v124; // rcx
  __int64 v125; // r8
  int v126; // ecx
  __int64 v127; // r10
  signed int v128; // r14d
  int v129; // r15d
  __int64 v130; // rbx
  __int64 v131; // r11
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
  int v151; // edx
  XLATEOBJ *v152; // rax
  __int64 v153; // rdx
  __int64 v154; // r15
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
  BOOL v166; // eax
  _DWORD *v167; // rcx
  _DWORD *v168; // rcx
  struct _GRETHREAD *v169; // rax
  __m128i v170; // xmm2
  __m128i v171; // xmm0
  __m128i v172; // xmm4
  int v173; // r8d
  unsigned int v174; // edx
  __int64 v175; // rax
  __int64 v176; // rax
  int v177; // r8d
  unsigned int v178; // edx
  __int64 v179; // rax
  __int64 v180; // rax
  int v181; // r8d
  unsigned int v182; // edx
  __int64 v183; // rax
  __int64 v184; // rax
  __int64 v185; // r9
  int v186; // r8d
  unsigned int v187; // edx
  __int64 v188; // rax
  __int64 v189; // rax
  __m128i v190; // xmm0
  int v191; // r8d
  unsigned int v192; // edx
  __m128i v193; // xmm0
  __int64 v194; // rax
  __int64 v195; // rax
  int v196; // r8d
  unsigned int v197; // edx
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
  __m128i v208; // xmm4
  float v209; // xmm6_4
  __m128i v210; // xmm0
  __m128i v211; // xmm1
  int v212; // r9d
  unsigned int v213; // r8d
  __m128i v214; // xmm3
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  int v218; // r9d
  unsigned int v219; // r8d
  __int64 v220; // rax
  __int64 v221; // rax
  __int64 v222; // r11
  int v223; // r9d
  unsigned int v224; // r8d
  __int64 v225; // rax
  __int64 v226; // rax
  int v227; // r10d
  unsigned int v228; // r8d
  __int64 v229; // rax
  __int64 v230; // rax
  __m128i v231; // xmm0
  __m128i v232; // xmm1
  int v233; // r10d
  __m128i v234; // xmm2
  unsigned int v235; // r8d
  __int64 v236; // rax
  __int64 v237; // rax
  int v238; // r11d
  unsigned int v239; // r10d
  __int64 v240; // rax
  __int64 v241; // rax
  float v242; // xmm3_4
  __m128i v243; // xmm2
  __m128i v244; // xmm4
  __m128i v245; // xmm0
  __m128i v246; // xmm1
  int v247; // r9d
  __m128i v248; // xmm2
  unsigned int v249; // r8d
  __m128i v250; // xmm4
  float v251; // xmm0_4
  __int64 v252; // rax
  __int64 v253; // rax
  int v254; // r9d
  unsigned int v255; // r8d
  __int64 v256; // rax
  __int64 v257; // rax
  int v258; // r12d
  unsigned int v259; // r8d
  __int64 v260; // rax
  __int64 v261; // rax
  int v262; // r12d
  unsigned int v263; // r8d
  __int64 v264; // rax
  __int64 v265; // rax
  __m128i v266; // xmm4
  __m128i v267; // xmm5
  __m128i v268; // xmm1
  __m128i v269; // xmm0
  int v270; // r14d
  float v271; // xmm4_4
  unsigned int v272; // edx
  float v273; // xmm5_4
  __m128i v274; // xmm2
  __int64 v275; // rax
  __m128i v276; // xmm0
  __int64 v277; // rax
  int v278; // r14d
  unsigned int v279; // edx
  __int64 v280; // rax
  __int64 v281; // rax
  __int64 v282; // rcx
  int v283; // r14d
  unsigned int v284; // edx
  __int64 v285; // rax
  __int64 v286; // rax
  __int64 v287; // rcx
  int v288; // r12d
  unsigned int v289; // ecx
  __int64 v290; // rax
  __int64 v291; // rax
  POINTL *v292; // [rsp+30h] [rbp-D0h]
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
  v19 = a9 & 0xDFFFFFFF;
  if ( (a9 & 0x40000000) == 0 )
  {
    v20 = 0;
    v293 = 0;
    if ( (*(_DWORD *)(*(_QWORD *)v11 + 36LL) & 0x10000) == 0 )
    {
      v21 = a9 & 0x5FFFFFFF;
      v22 = BYTE1(v19);
      if ( ((*((_BYTE *)gajRop3 + (unsigned __int8)a9) | *((_BYTE *)gajRop3 + BYTE1(a9))) & 2) != 0
        && v21 != 16711778
        && v21 != 66 )
      {
        bSpDwmValidateSurface(v11, left, top, a4, v14);
      }
      if ( OPTAPIDCOBJ::bValid(v307, v22, v14) )
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
        v23 = *((_QWORD *)*a1 + 122);
        v24 = *(_DWORD *)(v23 + 108);
        if ( ((*(_BYTE *)(*((_QWORD *)v323 + 122) + 108LL) ^ *(_BYTE *)(v23 + 108)) & 7) != 0
          && (a9 < 0 && (v24 & 1) != 0 || (v24 & 9) == 9) )
        {
          v165 = *(_DWORD *)(v23 + 308);
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
          v29 = a1;
          v20 = GrepStretchBlt(a1, left, top, v295, a5, (struct SURFACE **)v307, a7, a8, v295, a5, v21, a10, 0);
          goto LABEL_55;
        }
        v25 = a8 + a5;
        v318 = (__int64)v323;
        v26 = a7 + v295;
        v358.x = a7;
        v359 = a7 + v295;
        v358.y = a8;
        v360 = a8 + a5;
        if ( (*((_BYTE *)v330 + 32) & 0x43) == 0x43
          || (v27 = bCvtPts1(v330, &v358, 2), v25 = v360, v26 = v359, y = v358.y, x = v358.x, v27) )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(v318 + 976) + 108LL) & 1) != 0 )
          {
            ++x;
            ++v26;
            v358.x = x;
            v359 = v26;
          }
        }
        if ( x > v26 )
        {
          v358.x = v26;
          v359 = x;
        }
        if ( y > v25 )
        {
          v358.y = v25;
          v360 = y;
        }
        right = v295 + left;
        v29 = a1;
        v357.bottom = top + a5;
        v357.left = left;
        v357.top = top;
        v30 = *a1;
        v357.right = v295 + left;
        if ( (*(_BYTE *)(v320 + 32) & 0x43) == 0x43
          || (v31 = bCvtPts1(v320, &v357, 2), right = v357.right, top = v357.top, left = v357.left, v31) )
        {
          if ( (*(_DWORD *)(*((_QWORD *)v30 + 122) + 108LL) & 1) != 0 )
          {
            ++left;
            ++right;
            v357.left = left;
            v357.right = right;
          }
        }
        if ( left > right )
        {
          v32 = left;
          v357.left = right;
          left = right;
          v357.right = v32;
          right = v32;
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
          v20 = 1;
          goto LABEL_55;
        }
        v34 = *a1;
        v35 = *((_DWORD *)*a1 + 9);
        if ( (v35 & 0xE0) != 0 )
        {
          if ( (v35 & 0x20) != 0 )
          {
            if ( left < *((_DWORD *)v34 + 266) )
            {
              *((_DWORD *)v34 + 266) = left;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
            if ( top < *((_DWORD *)v34 + 267) )
            {
              *((_DWORD *)v34 + 267) = top;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
            if ( right > *((_DWORD *)v34 + 268) )
            {
              *((_DWORD *)v34 + 268) = right;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
            if ( v357.bottom > *((_DWORD *)v34 + 269) )
            {
              *((_DWORD *)v34 + 269) = v357.bottom;
              right = v357.right;
              top = v357.top;
              left = v357.left;
            }
          }
          v36 = *a1;
          if ( (*((_DWORD *)*a1 + 9) & 0x80u) != 0 )
          {
            if ( left < *((_DWORD *)v36 + 274) )
            {
              *((_DWORD *)v36 + 274) = left;
              right = v357.right;
              top = v357.top;
            }
            if ( top < *((_DWORD *)v36 + 275) )
            {
              *((_DWORD *)v36 + 275) = top;
              right = v357.right;
            }
            if ( right > *((_DWORD *)v36 + 276) )
              *((_DWORD *)v36 + 276) = right;
            if ( v357.bottom > *((_DWORD *)v36 + 277) )
              *((_DWORD *)v36 + 277) = v357.bottom;
          }
        }
        SURFMEM::SURFMEM(v333, 2);
        v336 = 0;
        v337 = 0;
        v38 = Gre::Base::Globals(v37);
        v339 = 0;
        v338 = v38;
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
        v40 = Gre::Base::Globals(v39);
        v346 = 0;
        v345 = v40;
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
          v41 = (unsigned int)XDCOBJ::bFullScreen((XDCOBJ *)a1);
          v166 = !*((_QWORD *)v323 + 62) || (unsigned int)DC::bInFullScreen(v323);
          v293 = v41 | v166;
          goto LABEL_54;
        }
        v43 = (__int64)*a1;
        v44 = *((_QWORD *)*a1 + 62);
        v321 = (SURFACE *)v44;
        if ( !v44 )
        {
          v293 = 1;
          goto LABEL_54;
        }
        v45 = *(_QWORD *)(v43 + 88);
        v46 = *(_QWORD *)(v44 + 160);
        v311 = v45;
        v47 = (a9 & 0x5FFFFFFFu) >> 16;
        v315 = v47 | (v47 << 8);
        if ( ((v47 ^ (unsigned __int8)(16 * v47)) & 0xF0) != 0 )
        {
          v153 = *(_QWORD *)(v43 + 976);
          v154 = v43 + 1200;
          v318 = v43 + 1200;
          if ( (*(_DWORD *)(v153 + 152) & 0x1000) != 0 )
            GreDCSelectBrush(v43, *(_QWORD *)(v153 + 160));
          v43 = (__int64)*a1;
          v41 = *((_QWORD *)*a1 + 122);
          v155 = *(_DWORD *)(v41 + 152);
          if ( (v155 & 1) != 0 || (*(_DWORD *)(v43 + 316) & 1) != 0 )
          {
            *(_DWORD *)(v41 + 152) = v155 & 0xFFFFFFFE;
            *((_DWORD *)*a1 + 79) &= ~1u;
            EBRUSHOBJ::vInitBrush(v154, *a1, *((_QWORD *)*a1 + 17), v45, v46, v44, 1);
            v43 = (__int64)*a1;
          }
        }
        else
        {
          v318 = 0;
        }
        v48 = (Gre::Base *)(*(_DWORD *)(v43 + 40) & 1);
        v357.left += *(_DWORD *)(v43 + 8LL * (_QWORD)v48 + 1016);
        v357.right += *(_DWORD *)(v43 + 8LL * (_QWORD)v48 + 1016);
        v357.top += *(_DWORD *)(v43 + 8LL * (_QWORD)v48 + 1020);
        v357.bottom += *(_DWORD *)(v43 + 8LL * (_QWORD)v48 + 1020);
        if ( !*((_QWORD *)v323 + 62) )
          goto LABEL_53;
        v57 = Gre::Base::Globals(v48);
        v58 = *((_QWORD *)v323 + 62);
        if ( v58 )
        {
          if ( v326 )
            v58 = v326;
        }
        else
        {
          v58 = *((_QWORD *)v57 + 547);
        }
        v312 = v58;
        if ( !v58 )
          goto LABEL_53;
        if ( (a11 & 2) == 0 )
        {
          if ( (v335 & 0x400000) == 0
            || ((*(_DWORD *)(v44 + 148) & 8) != 0 || *(_QWORD *)(v44 + 256))
            && _bittest16((const signed __int16 *)(v44 + 102), 9u) )
          {
            goto LABEL_257;
          }
          v59 = *(_DWORD *)(v44 + 144);
          if ( (v59 & 0x800) != 0 )
          {
            v60 = UserSurfaceAccessCheck(*(_QWORD *)(v44 + 680));
          }
          else
          {
            if ( (v59 & 0x10000000) == 0 )
              goto LABEL_85;
            v60 = UserScreenAccessCheck();
          }
          if ( !v60 )
          {
LABEL_257:
            EngSetLastError(6u);
            v29 = a1;
            goto LABEL_54;
          }
          v58 = v312;
        }
LABEL_85:
        v61 = 0;
        v62 = v357.left;
        v43 = (unsigned int)v357.top;
        v63 = *(_QWORD *)(v58 + 48);
        v64 = *(_QWORD *)(v58 + 160);
        v65 = *((_DWORD *)v323 + 10) & 1;
        v66 = 0;
        v67 = v357.top - *((_DWORD *)v323 + 2 * v65 + 255) - v358.y;
        v68 = v357.left - *((_DWORD *)v323 + 2 * v65 + 254) - v358.x;
        v302 = v67;
        v322 = (SURFOBJ *)(v58 + 24);
        if ( v63 && v58 == *(_QWORD *)(v63 + 2544) && (*(_DWORD *)(v63 + 40) & 0x20000) != 0 )
        {
          v66 = *(_DWORD *)(v63 + 2576);
          v61 = *(_DWORD *)(v63 + 2580);
        }
        if ( v66 + v68 > v357.left )
          v62 = v66 + v68;
        v357.left = v62;
        v294 = v62;
        if ( v67 + v61 > v357.top )
          v43 = (unsigned int)(v67 + v61);
        v357.top = v43;
        v69 = v66 + v68 + *(_DWORD *)(v58 + 56);
        v41 = (unsigned int)v357.right;
        if ( v69 < v357.right )
          v41 = (unsigned int)v69;
        v357.right = v41;
        v70 = v61 + v67 + *(_DWORD *)(v58 + 60);
        v42 = (unsigned int)v357.bottom;
        if ( v70 < v357.bottom )
          v42 = (unsigned int)v70;
        v357.bottom = v42;
        if ( v62 < (int)v41 && (int)v43 < (int)v42 )
        {
          v71 = a1;
          v72 = *a1;
          if ( v62 >= *((_DWORD *)*a1 + 250) && (int)v41 <= *((_DWORD *)v72 + 252) && (int)v43 >= *((_DWORD *)v72 + 251) )
          {
            v319 = 0;
            if ( (int)v42 <= *((_DWORD *)v72 + 253) )
            {
              v73 = (__m128i)v357;
LABEL_102:
              v74 = *v71;
              v75 = *((_DWORD *)v74 + 9);
              if ( (v75 & 0xE0) == 0 )
                goto LABEL_116;
              v361 = v73;
              v76 = *((_DWORD *)v74 + 10) & 1;
              v77 = v62 - *((_DWORD *)v74 + 2 * v76 + 254);
              v361.m128i_i32[0] = v77;
              v78 = v73.m128i_i32[2] - *((_DWORD *)v74 + 2 * v76 + 254);
              v361.m128i_i32[2] = v78;
              v79 = v73.m128i_i32[1] - *((_DWORD *)v74 + 2 * v76 + 255);
              v361.m128i_i32[1] = v79;
              v361.m128i_i32[3] = v73.m128i_i32[3] - *((_DWORD *)v74 + 2 * v76 + 255);
              if ( (v75 & 0x40) == 0 )
                goto LABEL_116;
              v80 = *((_DWORD *)v74 + 270);
              v81 = *((_DWORD *)v74 + 272);
              if ( v80 == v81 || (v82 = *((_DWORD *)v74 + 273), *((_DWORD *)v74 + 271) == v82) )
              {
                *(__m128i *)((char *)v74 + 1080) = v361;
              }
              else
              {
                if ( v77 < v80 )
                {
                  *((_DWORD *)v74 + 270) = v77;
                  v62 = v357.left;
                  v78 = v361.m128i_i32[2];
                  v79 = v361.m128i_i32[1];
                  v294 = v357.left;
                }
                if ( v79 < *((_DWORD *)v74 + 271) )
                {
                  *((_DWORD *)v74 + 271) = v79;
                  v62 = v357.left;
                  v78 = v361.m128i_i32[2];
                  v294 = v357.left;
                }
                if ( v78 > v81 )
                {
                  *((_DWORD *)v74 + 272) = v78;
                  v62 = v357.left;
                  v294 = v357.left;
                }
                if ( v361.m128i_i32[3] <= v82 )
                  goto LABEL_115;
                *((_DWORD *)v74 + 273) = v361.m128i_i32[3];
              }
              v62 = v357.left;
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
                v62 = v357.left;
                v294 = v357.left;
              }
LABEL_116:
              v358.x = v62 - v68;
              v298 = v62 - v68;
              v43 = (__int64)*a1;
              v83 = (unsigned int)(v357.top - v67);
              v358.y = v357.top - v67;
              v304 = v357.top - v67;
              if ( v312 == *(_QWORD *)(v43 + 496) )
              {
                v100 = 0;
                v293 = 1;
                v29 = a1;
                goto LABEL_165;
              }
              v84 = a10;
              v299 = a10;
              if ( a10 == -1 )
              {
                v83 = *((_QWORD *)v323 + 122);
                v84 = *(_DWORD *)(v83 + 180);
                v299 = v84;
              }
              if ( v64 )
              {
                if ( v46 )
                {
                  v85 = v64;
                  if ( *(_QWORD *)(v64 + 120) != v64 )
                    v85 = *(_QWORD *)(v64 + 120);
                  v83 = *(_QWORD *)(v46 + 120);
                  v86 = *(_DWORD *)(v85 + 32);
                  v87 = v46;
                  if ( v83 != v46 )
                    v87 = *(_QWORD *)(v46 + 120);
                  v88 = v86 == *(_DWORD *)(v87 + 32);
LABEL_126:
                  if ( !v88 )
                    goto LABEL_127;
LABEL_159:
                  v100 = (XLATEOBJ *)((char *)Gre::Base::Globals((Gre::Base *)v83) + 4664);
                  goto LABEL_160;
                }
                if ( (*(_DWORD *)(v64 + 24) & 0x800) != 0 )
                {
LABEL_214:
                  v142 = *(_QWORD *)(v45 + 80);
                  if ( !v142 )
                    goto LABEL_159;
                  v88 = v142 == *(_QWORD *)(v45 + 72);
                  goto LABEL_126;
                }
              }
              else
              {
                if ( !v46 )
                  goto LABEL_159;
                if ( (*(_DWORD *)(v46 + 24) & 0x800) != 0 )
                  goto LABEL_214;
              }
LABEL_127:
              v89 = *(_DWORD *)(v43 + 120);
              LODWORD(v308) = v89;
              v90 = (XLATEOBJ *)*((_QWORD *)v323 + 11);
              v91 = *(_QWORD *)(v43 + 976);
              v306 = v90;
              v92 = (Gre::Base *)*(unsigned int *)(v91 + 176);
              v93 = *(_DWORD *)(v91 + 184);
              v305 = v93;
              v300 = (int)v92;
              if ( v64 && v46 )
              {
                v94 = *(_DWORD *)(v64 + 56);
                v95 = Gre::Base::Globals(v92);
                v361.m128i_i64[0] = *(_QWORD *)v95 + 312LL;
                GreAcquireSemaphoreInternal((HSEMAPHORE)v361.m128i_i64[0]);
                GrepAcquireLockValidate<13>();
                for ( i = 0; ; ++i )
                {
                  if ( i >= 8 )
                  {
                    SEMOBJ<13>::vUnlock(&v361);
                    LODWORD(v92) = v300;
                    v93 = v305;
                    v89 = v308;
                    v84 = v299;
                    v90 = v306;
                    v45 = v311;
                    goto LABEL_136;
                  }
                  v97 = v64;
                  if ( *(_QWORD *)(v64 + 120) != v64 )
                    v97 = *(_QWORD *)(v64 + 120);
                  if ( *((_DWORD *)v95 + 8 * v94 + 1104) != *(_DWORD *)(v97 + 32) )
                    goto LABEL_134;
                  v148 = v46;
                  if ( *(_QWORD *)(v46 + 120) != v46 )
                    v148 = *(_QWORD *)(v46 + 120);
                  v149 = 32LL * v94;
                  if ( *(_DWORD *)((char *)v95 + v149 + 4420) != *(_DWORD *)(v148 + 32) )
                    goto LABEL_134;
                  v150 = v311;
                  if ( *(_QWORD *)(v311 + 120) != v311 )
                    v150 = *(_QWORD *)(v311 + 120);
                  if ( *(_DWORD *)((char *)v95 + v149 + 4428) != *(_DWORD *)(v150 + 32) )
                    goto LABEL_134;
                  v100 = *(XLATEOBJ **)((char *)v95 + v149 + 4408);
                  if ( (v100[3].flXlate & 0x6000) != 0 )
                    goto LABEL_134;
                  v151 = v100[3].flXlate & 0x100;
                  if ( (v100->flXlate & 4) == 0 )
                    break;
                  if ( v299 == v100[1].iUniq )
                  {
                    v152 = v306;
                    if ( *(XLATEOBJ **)&v306[5].iUniq != v306 )
                      v152 = *(XLATEOBJ **)&v306[5].iUniq;
                    if ( *(_DWORD *)((char *)v95 + v149 + 4424) == *(_DWORD *)&v152[1].iSrcType )
                    {
LABEL_245:
                      _InterlockedIncrement((volatile signed __int32 *)((char *)v95 + v149 + 4400));
                      *(_DWORD *)(v64 + 56) = v94;
                      SEMOBJ<13>::vUnlock(&v361);
                      goto LABEL_160;
                    }
                  }
                  if ( v151 )
                    goto LABEL_243;
LABEL_134:
                  v94 = ((_BYTE)v94 + 1) & 7;
                }
                if ( !v151 )
                  goto LABEL_245;
LABEL_243:
                if ( v305 == v100[1].flXlate && v300 == *(_DWORD *)&v100[1].iSrcType )
                  goto LABEL_245;
                goto LABEL_134;
              }
LABEL_136:
              LODWORD(v292) = v93;
              XlateObject = (XLATEOBJ *)CreateXlateObject(0, v89, v64, v46, v90, v45, v292, (_DWORD)v92, v84, 0);
              v100 = XlateObject;
              if ( XlateObject )
              {
                if ( v64 && v46 && (XlateObject[3].flXlate & 0x200) == 0 )
                {
                  v101 = Gre::Base::Globals(v99);
                  v306 = (XLATEOBJ *)(*(_QWORD *)v101 + 312LL);
                  GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(
                    (void (__fastcall *)(__int64))GreAcquireSemaphoreInternal,
                    (__int64)v306);
                  for ( j = 0; j < 8; ++j )
                  {
                    v103 = *((_DWORD *)v101 + 1164);
                    v104 = 32LL * v103;
                    v105 = *(_QWORD *)((char *)v101 + v104 + 4408);
                    if ( !v105 )
                      goto LABEL_145;
                    if ( !*(_DWORD *)((char *)v101 + v104 + 4400) )
                    {
                      FreeThreadBufferWithTag(v105);
LABEL_145:
                      PopThreadGuardedObject(&v100[-2].pulXlate);
                      v106 = v64;
                      *((_DWORD *)v101 + 8 * *((unsigned int *)v101 + 1164) + 1100) = 1;
                      *((_QWORD *)v101 + 4 * *((unsigned int *)v101 + 1164) + 551) = v100;
                      if ( *(_QWORD *)(v64 + 120) != v64 )
                        v106 = *(_QWORD *)(v64 + 120);
                      v107 = *(_DWORD *)(v106 + 32);
                      v108 = v311;
                      *((_DWORD *)v101 + 8 * *((unsigned int *)v101 + 1164) + 1104) = v107;
                      if ( *(_QWORD *)(v46 + 120) != v46 )
                        v46 = *(_QWORD *)(v46 + 120);
                      *((_DWORD *)v101 + 8 * *((unsigned int *)v101 + 1164) + 1105) = *(_DWORD *)(v46 + 32);
                      if ( *(XLATEOBJ **)&v90[5].iUniq != v90 )
                        v90 = *(XLATEOBJ **)&v90[5].iUniq;
                      *((_DWORD *)v101 + 8 * *((unsigned int *)v101 + 1164) + 1106) = *(_DWORD *)&v90[1].iSrcType;
                      if ( *(_QWORD *)(v108 + 120) != v108 )
                        v108 = *(_QWORD *)(v108 + 120);
                      *((_DWORD *)v101 + 8 * *((unsigned int *)v101 + 1164) + 1107) = *(_DWORD *)(v108 + 32);
                      v100[1].cEntries = *((_DWORD *)v101 + 1164);
                      *(_DWORD *)(v64 + 56) = *((_DWORD *)v101 + 1164);
                      *((_DWORD *)v101 + 1164) = ((unsigned __int8)*((_DWORD *)v101 + 1164) + 1) & 7;
                      break;
                    }
                    *((_DWORD *)v101 + 1164) = ((_BYTE)v103 + 1) & 7;
                  }
                  SEMOBJ<13>::vUnlock(&v306);
                }
LABEL_160:
                v109 = 1;
              }
              else
              {
                v109 = 0;
              }
              v29 = a1;
              v293 = v109;
              v43 = (__int64)*a1;
              if ( (*((_DWORD *)*a1 + 9) & 1) == 0 )
              {
                v359 = v357.right - v68;
                v360 = v357.bottom - v302;
              }
              if ( !(_DWORD)v109 )
              {
LABEL_209:
                if ( v100 )
                {
                  cEntries = v100[1].cEntries;
                  if ( cEntries >= 0 )
                  {
                    _InterlockedDecrement(
                      (volatile signed __int32 *)Gre::Base::Globals((Gre::Base *)v109)
                    + 8 * (int)v100[1].cEntries
                    + 1100);
                  }
                  else if ( cEntries == -1 )
                  {
                    FreeThreadBufferWithTag(v100);
                  }
                }
                goto LABEL_54;
              }
              v62 = v357.left;
              v304 = v358.y;
              v298 = v358.x;
              v294 = v357.left;
LABEL_165:
              LODWORD(v110) = 0;
              LODWORD(v111) = 0;
              v303 = v357.top;
              v309 = v357.right;
              v306 = v100;
              v296 = v357.bottom;
              v314 = 0;
              v313 = 0;
              if ( *((int *)v321 + 36) < 0 )
              {
                v167 = (_DWORD *)*((_QWORD *)v321 + 6);
                if ( v167 )
                {
                  if ( (v167[10] & 0x20000) != 0 )
                  {
                    LODWORD(v110) = v167[644];
                    v111 = (unsigned int)v167[645];
                    v314 = (unsigned int)v110;
                    v313 = v111;
                  }
                }
              }
              LODWORD(v112) = 0;
              v113 = 0;
              LODWORD(v114) = v111 + *((_DWORD *)v321 + 15);
              v311 = (unsigned int)(v110 + *((_DWORD *)v321 + 14));
              v307 = 0;
              v361.m128i_i64[0] = 0;
              if ( *(int *)(v312 + 144) < 0 )
              {
                v168 = *(_DWORD **)(v312 + 48);
                if ( v168 )
                {
                  if ( (v168[10] & 0x20000) != 0 )
                  {
                    v113 = v168[644];
                    v112 = (unsigned int)v168[645];
                    v307 = (OPTAPIDCOBJ *)v113;
                    v361.m128i_i64[0] = v112;
                  }
                }
              }
              v115 = v113 + *(_DWORD *)(v312 + 56);
              LODWORD(v308) = v112 + *(_DWORD *)(v312 + 60);
              if ( v29 && (v116 = *(_DWORD *)(v43 + 520), (v116 & 1) != 0) && (v116 & 2) == 0 )
              {
                v170 = (__m128i)LODWORD(FLOAT_1_0);
                *(float *)v170.m128i_i32 = 1.0 / *(float *)(v43 + 524);
                v171 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v110);
                v172 = (__m128i)LODWORD(FLOAT_1_0);
                *(float *)v172.m128i_i32 = 1.0 / *(float *)(v43 + 528);
                *(float *)v171.m128i_i32 = *(float *)v171.m128i_i32 * *(float *)v170.m128i_i32;
                v173 = _mm_cvtsi128_si32(v171);
                v174 = (unsigned __int8)(v173 >> 23);
                if ( v174 > 0x9E )
                  goto LABEL_357;
                v175 = v173 & 0x7FFFFF | 0x800000LL;
                if ( v174 < 0x76 )
                  v176 = v175 >> (118 - (unsigned __int8)v174);
                else
                  v176 = v175 << ((unsigned __int8)v174 - 118);
                v110 = (v176 + 0x80000000LL) >> 32;
                if ( v173 < 0 )
                  v110 = (unsigned int)-(int)v110;
                v177 = _mm_cvtsi128_si32(v172);
                v314 = v110;
                v178 = (unsigned __int8)(v177 >> 23);
                if ( v178 > 0x9E )
                  goto LABEL_357;
                v179 = v177 & 0x7FFFFF | 0x800000LL;
                if ( v178 < 0x76 )
                  v180 = v179 >> (118 - (unsigned __int8)v178);
                else
                  v180 = v179 << ((unsigned __int8)v178 - 118);
                v111 = (v180 + 0x80000000LL) >> 32;
                if ( v177 < 0 )
                  v111 = (unsigned int)-(int)v111;
                v181 = _mm_cvtsi128_si32(v170);
                v313 = v111;
                v182 = (unsigned __int8)(v181 >> 23);
                if ( v182 > 0x9E )
                  goto LABEL_357;
                v183 = v181 & 0x7FFFFF | 0x800000LL;
                if ( v182 < 0x76 )
                  v184 = v183 >> (118 - (unsigned __int8)v182);
                else
                  v184 = v183 << ((unsigned __int8)v182 - 118);
                v185 = (v184 + 0x80000000LL) >> 32;
                if ( v181 < 0 )
                  v185 = (unsigned int)-(int)v185;
                v186 = _mm_cvtsi128_si32(v172);
                v311 = v185;
                v187 = (unsigned __int8)(v186 >> 23);
                if ( v187 > 0x9E )
                {
LABEL_357:
                  LODWORD(v114) = 0;
                  LODWORD(v111) = 0;
                  LODWORD(v110) = 0;
                  LODWORD(v311) = 0;
                  v314 = 0;
                  v313 = 0;
                }
                else
                {
                  v188 = v186 & 0x7FFFFF | 0x800000LL;
                  if ( v187 < 0x76 )
                    v189 = v188 >> (118 - (unsigned __int8)v187);
                  else
                    v189 = v188 << ((unsigned __int8)v187 - 118);
                  v114 = (v189 + 0x80000000LL) >> 32;
                  if ( v186 < 0 )
                    LODWORD(v114) = -(int)v114;
                }
                v190 = (__m128i)COERCE_UNSIGNED_INT((float)v62);
                *(float *)v190.m128i_i32 = *(float *)v190.m128i_i32 * *(float *)v170.m128i_i32;
                v191 = _mm_cvtsi128_si32(v190);
                v192 = (unsigned __int8)(v191 >> 23);
                if ( v192 > 0x9E )
                  goto LABEL_358;
                v193 = v172;
                v194 = v191 & 0x7FFFFF | 0x800000LL;
                if ( v192 < 0x76 )
                  v195 = v194 >> (118 - (unsigned __int8)v192);
                else
                  v195 = v194 << ((unsigned __int8)v192 - 118);
                v118 = (v195 + 0x80000000LL) >> 32;
                if ( v191 < 0 )
                  LODWORD(v118) = -(int)v118;
                *(float *)v193.m128i_i32 = *(float *)v172.m128i_i32 * (float)v357.top;
                v196 = _mm_cvtsi128_si32(v193);
                v197 = (unsigned __int8)(v196 >> 23);
                if ( v197 > 0x9E )
                  goto LABEL_358;
                *(float *)v170.m128i_i32 = *(float *)v170.m128i_i32 * (float)v309;
                v198 = v196 & 0x7FFFFF | 0x800000LL;
                if ( v197 < 0x76 )
                  v199 = v198 >> (118 - (unsigned __int8)v197);
                else
                  v199 = v198 << ((unsigned __int8)v197 - 118);
                v119 = (v199 + 0x80000000LL) >> 32;
                if ( v196 < 0 )
                  LODWORD(v119) = -(int)v119;
                v200 = _mm_cvtsi128_si32(v170);
                v201 = (unsigned __int8)(v200 >> 23);
                if ( v201 > 0x9E )
                  goto LABEL_358;
                *(float *)v172.m128i_i32 = *(float *)v172.m128i_i32 * (float)v357.bottom;
                v202 = v200 & 0x7FFFFF | 0x800000LL;
                if ( v201 < 0x76 )
                  v203 = v202 >> (118 - (unsigned __int8)v201);
                else
                  v203 = v202 << ((unsigned __int8)v201 - 118);
                v120 = (v203 + 0x80000000LL) >> 32;
                if ( v200 < 0 )
                  LODWORD(v120) = -(int)v120;
                v204 = _mm_cvtsi128_si32(v172);
                v205 = (unsigned __int8)(v204 >> 23);
                if ( v205 > 0x9E )
                {
LABEL_358:
                  LODWORD(v117) = 0;
                  LODWORD(v120) = 0;
                  LODWORD(v119) = 0;
                  LODWORD(v118) = 0;
                }
                else
                {
                  v206 = v204 & 0x7FFFFF | 0x800000LL;
                  if ( v205 < 0x76 )
                    v207 = v206 >> (118 - (unsigned __int8)v205);
                  else
                    v207 = v206 << ((unsigned __int8)v205 - 118);
                  v117 = (v207 + 0x80000000LL) >> 32;
                  if ( v204 < 0 )
                    LODWORD(v117) = -(int)v117;
                }
              }
              else
              {
                LODWORD(v117) = v357.bottom;
                LODWORD(v118) = v62;
                LODWORD(v119) = v357.top;
                LODWORD(v120) = v309;
              }
              v121 = *((_DWORD *)v323 + 130);
              LODWORD(v310) = v121;
              v301 = v121 & 1;
              if ( (v121 & 1) == 0 || (v121 & 2) != 0 )
              {
                LODWORD(v122) = v308;
                LODWORD(v123) = v115;
                LODWORD(v124) = v304;
                LODWORD(v125) = v298;
              }
              else
              {
                v208 = (__m128i)LODWORD(FLOAT_1_0);
                *(float *)v208.m128i_i32 = 1.0 / *((float *)v323 + 131);
                v209 = 1.0 / *((float *)v323 + 132);
                v210 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v307);
                *(float *)v210.m128i_i32 = *(float *)v210.m128i_i32 * *(float *)v208.m128i_i32;
                v211 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v112);
                v212 = _mm_cvtsi128_si32(v210);
                v213 = (unsigned __int8)(v212 >> 23);
                v214 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v308);
                if ( v213 > 0x9E )
                  goto LABEL_398;
                *(float *)v211.m128i_i32 = *(float *)v211.m128i_i32 * v209;
                v215 = v212 & 0x7FFFFF | 0x800000LL;
                if ( v213 < 0x76 )
                  v216 = v215 >> (118 - (unsigned __int8)v213);
                else
                  v216 = v215 << ((unsigned __int8)v213 - 118);
                v217 = (v216 + 0x80000000LL) >> 32;
                if ( v212 < 0 )
                  v217 = (unsigned int)-(int)v217;
                v307 = (OPTAPIDCOBJ *)v217;
                v218 = _mm_cvtsi128_si32(v211);
                v219 = (unsigned __int8)(v218 >> 23);
                if ( v219 > 0x9E )
                  goto LABEL_398;
                v220 = v218 & 0x7FFFFF | 0x800000LL;
                if ( v219 < 0x76 )
                  v221 = v220 >> (118 - (unsigned __int8)v219);
                else
                  v221 = v220 << ((unsigned __int8)v219 - 118);
                v222 = (v221 + 0x80000000LL) >> 32;
                if ( v218 < 0 )
                  v222 = (unsigned int)-(int)v222;
                v223 = _mm_cvtsi128_si32(v208);
                v361.m128i_i64[0] = v222;
                v224 = (unsigned __int8)(v223 >> 23);
                if ( v224 > 0x9E )
                  goto LABEL_398;
                *(float *)v214.m128i_i32 = *(float *)v214.m128i_i32 * v209;
                v225 = v223 & 0x7FFFFF | 0x800000LL;
                if ( v224 < 0x76 )
                  v226 = v225 >> (118 - (unsigned __int8)v224);
                else
                  v226 = v225 << ((unsigned __int8)v224 - 118);
                v123 = (v226 + 0x80000000LL) >> 32;
                if ( v223 < 0 )
                  LODWORD(v123) = -(int)v123;
                v227 = _mm_cvtsi128_si32(v214);
                v228 = (unsigned __int8)(v227 >> 23);
                if ( v228 > 0x9E )
                {
LABEL_398:
                  LODWORD(v123) = 0;
                  LODWORD(v122) = 0;
                  v361.m128i_i32[0] = 0;
                  v307 = 0;
                }
                else
                {
                  v229 = v227 & 0x7FFFFF | 0x800000LL;
                  if ( v228 < 0x76 )
                    v230 = v229 >> (118 - (unsigned __int8)v228);
                  else
                    v230 = v229 << ((unsigned __int8)v228 - 118);
                  v122 = (v230 + 0x80000000LL) >> 32;
                  if ( v227 < 0 )
                    LODWORD(v122) = -(int)v122;
                }
                v231 = (__m128i)COERCE_UNSIGNED_INT((float)v298);
                v232 = (__m128i)COERCE_UNSIGNED_INT((float)v304);
                *(float *)v231.m128i_i32 = *(float *)v231.m128i_i32 * *(float *)v208.m128i_i32;
                v233 = _mm_cvtsi128_si32(v231);
                v234 = (__m128i)COERCE_UNSIGNED_INT((float)v360);
                v235 = (unsigned __int8)(v233 >> 23);
                if ( v235 > 0x9E )
                  goto LABEL_399;
                *(float *)v232.m128i_i32 = *(float *)v232.m128i_i32 * v209;
                v236 = v233 & 0x7FFFFF | 0x800000LL;
                if ( v235 < 0x76 )
                  v237 = v236 >> (118 - (unsigned __int8)v235);
                else
                  v237 = v236 << ((unsigned __int8)v235 - 118);
                v125 = (v237 + 0x80000000LL) >> 32;
                if ( v233 < 0 )
                  LODWORD(v125) = -(int)v125;
                v238 = _mm_cvtsi128_si32(v232);
                v239 = (unsigned __int8)(v238 >> 23);
                if ( v239 > 0x9E )
                  goto LABEL_399;
                *(float *)v208.m128i_i32 = *(float *)v208.m128i_i32 * (float)v359;
                v240 = v238 & 0x7FFFFF | 0x800000LL;
                if ( v239 < 0x76 )
                  v241 = v240 >> (118 - (unsigned __int8)v239);
                else
                  v241 = v240 << ((unsigned __int8)v239 - 118);
                v124 = (v241 + 0x80000000LL) >> 32;
                if ( v238 < 0 )
                  LODWORD(v124) = -(int)v124;
                if ( (unsigned __int8)(_mm_cvtsi128_si32(v208) >> 23) > 0x9Eu
                  || (*(float *)v234.m128i_i32 = *(float *)v234.m128i_i32 * v209,
                      (unsigned __int8)(_mm_cvtsi128_si32(v234) >> 23) > 0x9Eu) )
                {
LABEL_399:
                  LODWORD(v110) = v314;
                  LODWORD(v124) = 0;
                  LODWORD(v111) = v313;
                  LODWORD(v125) = 0;
                }
                else
                {
                  LODWORD(v110) = v314;
                  LODWORD(v111) = v313;
                }
              }
              v43 = (unsigned int)(v125 - v118);
              v126 = v124 - v119;
              if ( (int)v110 > (int)v118 )
                LODWORD(v118) = v110;
              if ( (int)v111 > (int)v119 )
                LODWORD(v119) = v111;
              if ( (int)v311 < (int)v120 )
                LODWORD(v120) = v311;
              if ( (int)v114 < (int)v117 )
                LODWORD(v117) = v114;
              if ( (int)v120 < (int)v118 )
              {
                LODWORD(v118) = v120;
              }
              else if ( (int)v117 < (int)v119 )
              {
                LODWORD(v119) = v117;
              }
              LODWORD(v127) = v43 + v118;
              v128 = v43 + v120;
              v129 = v126 + v119;
              LODWORD(v117) = v126 + v117;
              if ( (int)v307 > (int)v43 + (int)v118 )
                LODWORD(v127) = (_DWORD)v307;
              if ( v361.m128i_i32[0] > v129 )
                v129 = v361.m128i_i32[0];
              if ( (int)v123 < v128 )
                v128 = v123;
              if ( (int)v122 < (int)v117 )
                LODWORD(v117) = v122;
              if ( v128 < (int)v127 )
              {
                LODWORD(v127) = v128;
              }
              else if ( (int)v117 < v129 )
              {
                v129 = v117;
              }
              LODWORD(v130) = v127 - v43;
              v42 = (unsigned int)(v128 - v43);
              if ( (int)v127 - (int)v43 >= (int)v42
                || (LODWORD(v131) = v129 - v126, v43 = (unsigned int)(v117 - v126), v129 - v126 >= (int)v43) )
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
                    v242 = *((float *)v132 + 131);
                    v243 = _mm_cvtsi32_si128(v42);
                    v244 = _mm_cvtsi32_si128(v43);
                    v245 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v130);
                    *(float *)v245.m128i_i32 = *(float *)v245.m128i_i32 * v242;
                    v246 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v131);
                    v247 = _mm_cvtsi128_si32(v245);
                    v248 = (__m128i)_mm_cvtepi32_ps(v243);
                    v249 = (unsigned __int8)(v247 >> 23);
                    v250 = (__m128i)_mm_cvtepi32_ps(v244);
                    if ( v249 > 0x9E )
                      goto LABEL_424;
                    v251 = *((float *)v132 + 132);
                    *(float *)v246.m128i_i32 = *(float *)v246.m128i_i32 * v251;
                    v252 = v247 & 0x7FFFFF | 0x800000LL;
                    if ( v249 < 0x76 )
                      v253 = v252 >> (118 - (unsigned __int8)v249);
                    else
                      v253 = v252 << ((unsigned __int8)v249 - 118);
                    v130 = (v253 + 0x80000000LL) >> 32;
                    if ( v247 < 0 )
                      LODWORD(v130) = -(int)v130;
                    v254 = _mm_cvtsi128_si32(v246);
                    v255 = (unsigned __int8)(v254 >> 23);
                    if ( v255 > 0x9E )
                      goto LABEL_424;
                    *(float *)v248.m128i_i32 = *(float *)v248.m128i_i32 * v242;
                    v256 = v254 & 0x7FFFFF | 0x800000LL;
                    if ( v255 < 0x76 )
                      v257 = v256 >> (118 - (unsigned __int8)v255);
                    else
                      v257 = v256 << ((unsigned __int8)v255 - 118);
                    v131 = (v257 + 0x80000000LL) >> 32;
                    if ( v254 < 0 )
                      LODWORD(v131) = -(int)v131;
                    v258 = _mm_cvtsi128_si32(v248);
                    v259 = (unsigned __int8)(v258 >> 23);
                    if ( v259 > 0x9E )
                      goto LABEL_424;
                    *(float *)v250.m128i_i32 = *(float *)v250.m128i_i32 * v251;
                    v260 = v258 & 0x7FFFFF | 0x800000LL;
                    if ( v259 < 0x76 )
                      v261 = v260 >> (118 - (unsigned __int8)v259);
                    else
                      v261 = v260 << ((unsigned __int8)v259 - 118);
                    v42 = (v261 + 0x80000000LL) >> 32;
                    if ( v258 < 0 )
                      v42 = (unsigned int)-(int)v42;
                    v262 = _mm_cvtsi128_si32(v250);
                    v263 = (unsigned __int8)(v262 >> 23);
                    if ( v263 > 0x9E )
                    {
LABEL_424:
                      v43 = 0;
                      v42 = 0;
                      LODWORD(v131) = 0;
                      LODWORD(v130) = 0;
                    }
                    else
                    {
                      v264 = v262 & 0x7FFFFF | 0x800000LL;
                      if ( v263 < 0x76 )
                        v265 = v264 >> (118 - (unsigned __int8)v263);
                      else
                        v265 = v264 << ((unsigned __int8)v263 - 118);
                      v43 = (v265 + 0x80000000LL) >> 32;
                      if ( v262 < 0 )
                        v43 = (unsigned int)-(int)v43;
                    }
                  }
                }
                if ( v301 && (v310 & 2) == 0 )
                {
                  v266 = _mm_cvtsi32_si128(v128);
                  v267 = _mm_cvtsi32_si128(v117);
                  v268 = (__m128i)*((unsigned int *)v323 + 131);
                  v269 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v127);
                  *(float *)v269.m128i_i32 = *(float *)v269.m128i_i32 * *(float *)v268.m128i_i32;
                  v270 = _mm_cvtsi128_si32(v269);
                  LODWORD(v271) = _mm_cvtepi32_ps(v266).m128_u32[0];
                  v272 = (unsigned __int8)(v270 >> 23);
                  LODWORD(v273) = _mm_cvtepi32_ps(v267).m128_u32[0];
                  if ( v272 > 0x9E )
                    goto LABEL_449;
                  v274 = (__m128i)*((unsigned int *)v323 + 132);
                  v275 = v270 & 0x7FFFFF | 0x800000LL;
                  v276 = v274;
                  if ( v272 < 0x76 )
                    v277 = v275 >> (118 - (unsigned __int8)v272);
                  else
                    v277 = v275 << ((unsigned __int8)v272 - 118);
                  v127 = (v277 + 0x80000000LL) >> 32;
                  if ( v270 < 0 )
                    LODWORD(v127) = -(int)v127;
                  *(float *)v276.m128i_i32 = *(float *)v274.m128i_i32 * (float)v129;
                  v278 = _mm_cvtsi128_si32(v276);
                  v279 = (unsigned __int8)(v278 >> 23);
                  if ( v279 > 0x9E )
                    goto LABEL_449;
                  *(float *)v268.m128i_i32 = *(float *)v268.m128i_i32 * v271;
                  v280 = v278 & 0x7FFFFF | 0x800000LL;
                  if ( v279 < 0x76 )
                    v281 = v280 >> (118 - (unsigned __int8)v279);
                  else
                    v281 = v280 << ((unsigned __int8)v279 - 118);
                  v282 = (v281 + 0x80000000LL) >> 32;
                  if ( v278 < 0 )
                    LODWORD(v282) = -(int)v282;
                  v283 = _mm_cvtsi128_si32(v268);
                  v129 = v282;
                  v284 = (unsigned __int8)(v283 >> 23);
                  if ( v284 > 0x9E )
                    goto LABEL_449;
                  *(float *)v274.m128i_i32 = *(float *)v274.m128i_i32 * v273;
                  v285 = v283 & 0x7FFFFF | 0x800000LL;
                  if ( v284 < 0x76 )
                    v286 = v285 >> (118 - (unsigned __int8)v284);
                  else
                    v286 = v285 << ((unsigned __int8)v284 - 118);
                  v287 = (v286 + 0x80000000LL) >> 32;
                  if ( v283 < 0 )
                    LODWORD(v287) = -(int)v287;
                  v288 = _mm_cvtsi128_si32(v274);
                  v128 = v287;
                  v289 = (unsigned __int8)(v288 >> 23);
                  if ( v289 > 0x9E )
                  {
LABEL_449:
                    LODWORD(v117) = 0;
                    v128 = 0;
                    v129 = 0;
                    LODWORD(v127) = 0;
                  }
                  else
                  {
                    v290 = v288 & 0x7FFFFF | 0x800000LL;
                    if ( v289 < 0x76 )
                      v291 = v290 >> (118 - (unsigned __int8)v289);
                    else
                      v291 = v290 << ((unsigned __int8)v289 - 118);
                    v117 = (v291 + 0x80000000LL) >> 32;
                    if ( v288 < 0 )
                      LODWORD(v117) = -(int)v117;
                  }
                }
                v358.y = v129;
                v134 = v321;
                v357.left = v130;
                v135 = 1;
                v358.x = v127;
                v359 = v128;
                v360 = v117;
                v357.top = v131;
                v357.right = v42;
                v357.bottom = v43;
                ++*((_DWORD *)v321 + 23);
              }
              v29 = a1;
              v136 = *a1;
              v109 = *((_QWORD *)v323 + 6);
              if ( *((_QWORD *)*a1 + 6) == v109
                || (unsigned int)XDCOBJ::bRedirHooked((XDCOBJ *)a1)
                && (v136 = *a1, v109 = *((_QWORD *)v323 + 6), *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) == v109) )
              {
                v41 = v312;
              }
              else
              {
                v41 = v312;
                if ( *(_WORD *)(v312 + 100) )
                  goto LABEL_271;
                v156 = (SURFOBJ *)(v312 + 24);
                if ( *(_QWORD *)(v312 + 24) )
                  goto LABEL_272;
                v136 = *a1;
                v109 = *(unsigned int *)(*((_QWORD *)*a1 + 6) + 40LL);
                if ( (v109 & 0x80u) != 0LL )
                {
LABEL_271:
                  v156 = v322;
LABEL_272:
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
                  goto LABEL_209;
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
              goto LABEL_209;
            }
          }
          v143 = (char *)v72 + 1768;
          v319 = (char *)v72 + 1768;
          v144 = XDCOBJ::prgnEffRao((XDCOBJ *)a1);
          XCLIPOBJ::vSetup((XCLIPOBJ *)v143, v144, (const struct ERECTL *)&v357, 2);
          v73 = *(__m128i *)(v143 + 4);
          v62 = _mm_cvtsi128_si32(v73);
          v41 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v73, 8));
          v357 = (RECTL)v73;
          v294 = v62;
          v357.right = v41;
          if ( v62 != (_DWORD)v41 && v73.m128i_i32[1] != _mm_srli_si128(v73, 8).m128i_i32[1] )
          {
            v71 = a1;
            v357.bottom = _mm_cvtsi128_si32(_mm_srli_si128(v73, 12));
            v357.top = _mm_cvtsi128_si32(_mm_srli_si128(v73, 4));
            goto LABEL_102;
          }
        }
LABEL_53:
        v29 = a1;
        v293 = 1;
LABEL_54:
        DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v331, v41, v43, v42);
        v20 = v293;
LABEL_55:
        if ( v316 )
          DC::dwSetLayout(*v29, -1, v317);
        v49 = v323;
        if ( !v329 )
          v49 = 0;
        v323 = v49;
        PopThreadGuardedObject(v328);
        v50 = v323;
        if ( v323 )
        {
          if ( v324 && (*((_DWORD *)v323 + 11) & 2) != 0 )
          {
            CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
            v53 = v323;
            v54 = CurrentProcessId & 0xFFFFFFFC;
            if ( *(_QWORD *)v323 )
            {
              v55 = (char *)HmgPentryFromPobj(v325, v323);
            }
            else
            {
              v55 = (char *)v323 + 2152;
              *(_OWORD *)((char *)v323 + 2152) = 0;
              *((_QWORD *)v53 + 271) = 0;
              *((_DWORD *)v53 + 540) = -2147483630;
              *((_QWORD *)v53 + 271) = GreEncodeUserModePointer(0);
            }
            if ( v54 == (*((_DWORD *)v55 + 2) & 0xFFFFFFFE) )
            {
              UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v323);
              if ( UserAttr )
                DC::RestoreAttributes(v323, UserAttr);
            }
            *((_DWORD *)v323 + 11) &= ~2u;
            v50 = v323;
            v324 = 0;
          }
          _InterlockedDecrement16((volatile signed __int16 *)v50 + 6);
          v323 = 0;
        }
        PopThreadGuardedObject(v327);
        goto LABEL_61;
      }
      v20 = 0;
    }
LABEL_61:
    if ( v18 )
    {
      v163 = GreGetCurrentThread();
      *((_DWORD *)v163 + 84) &= ~8u;
    }
    return v20;
  }
  v158 = GrepStretchBlt(
           (struct SURFACE **)v11,
           left,
           top,
           a4,
           v14,
           (struct SURFACE **)v17,
           a7,
           a8,
           a4,
           v14,
           v19,
           a10,
           ((unsigned int)a9 >> 28) & 2);
  if ( v18 )
  {
    v169 = GreGetCurrentThread();
    *((_DWORD *)v169 + 84) &= ~8u;
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
