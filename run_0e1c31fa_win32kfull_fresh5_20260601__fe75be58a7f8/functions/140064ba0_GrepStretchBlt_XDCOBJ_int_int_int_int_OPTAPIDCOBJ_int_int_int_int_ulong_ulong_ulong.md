# GrepStretchBlt(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,int,int,ulong,ulong,ulong)

- ea: `0x140064ba0`
- end: `0x1400661b3`
- name: `?GrepStretchBlt@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHHHKKK@Z`
- size: `5651`
- prototype: `__int64 __usercall@<rax>(struct XDCOBJ *@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int, struct OPTAPIDCOBJ *, int, int, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140063fb4`
- `0x140064280`
- `0x1400663c0`
- `0x14007be5c`
- `0x140151b9c`
- `0x14019ef40`

## callees

- `0x1400615f4`
- `0x140062d70`
- `0x140062db8`
- `0x140063f70`
- `0x140064524`
- `0x140064ba0`
- `0x1400661bc`
- `0x14006876c`
- `0x140068f04`
- `0x140069888`
- `0x14006ba5c`
- `0x14006d614`
- `0x1400797f8`
- `0x14007aed0`
- `0x14007ba10`
- `0x14007bb1c`
- `0x14007bc10`
- `0x14007eef8`
- `0x14008d8bc`
- `0x140093378`
- `0x140094a30`
- `0x140095038`
- `0x140096604`
- `0x140134f38`
- `0x140137980`
- `0x14019e768`
- `0x1401adee0`
- `0x14021b220`
- `0x140251428`
- `0x140280dd8`
- `0x140302ddc`
- `0x140341ff0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064e54`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064e97`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064f42`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064fe4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065000`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006506c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400651e5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400656f3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006578e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006591f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064e54`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064e97`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064f42`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140064fe4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065000`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006506c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400651e5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400656f3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006578e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006591f`
- `win32kbase!PopThreadGuardedObject` at `0x140065808`
- `win32kbase!PopThreadGuardedObject` at `0x140065808`
- `win32kbase!PushThreadGuardedObject` at `0x140064ce8`
- `win32kbase!PushThreadGuardedObject` at `0x140064d0e`
- `win32kbase!PushThreadGuardedObject` at `0x140064d87`
- `win32kbase!PushThreadGuardedObject` at `0x140064db6`
- `win32kbase!PushThreadGuardedObject` at `0x140064ce8`
- `win32kbase!PushThreadGuardedObject` at `0x140064d0e`
- `win32kbase!PushThreadGuardedObject` at `0x140064d87`
- `win32kbase!PushThreadGuardedObject` at `0x140064db6`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400657f1`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400657f1`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140065206`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140065ce7`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140065206`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14006579a`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140065ce7`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140065e16`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140065cd8`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140065cd8`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140065dcd`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140065f43`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140065fa9`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x14006611d`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140065dcd`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140065f43`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140065fa9`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x14006611d`
- `win32kbase!EngSetLastError` at `0x14006542c`
- `win32kbase!EngSetLastError` at `0x140065448`
- `win32kbase!EngSetLastError` at `0x140065740`
- `win32kbase!EngSetLastError` at `0x14006600b`
- `win32kbase!EngSetLastError` at `0x14006542c`
- `win32kbase!EngSetLastError` at `0x140065448`
- `win32kbase!EngSetLastError` at `0x140065740`
- `win32kbase!EngSetLastError` at `0x14006600b`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14006548d`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14006548d`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140065a4e`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140065a4e`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140065ed1`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140065ed1`
- `win32kbase!GreDCSelectBrush` at `0x140064dfa`
- `win32kbase!GreDCSelectBrush` at `0x140064dfa`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x1400660aa`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x14006616c`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x1400660aa`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x14006616c`
- `win32kbase!?vSetIncludeSprites@SURFACE@@SAXXZ` at `0x140065d31`
- `win32kbase!?vSetIncludeSprites@SURFACE@@SAXXZ` at `0x140065d31`
- `win32kbase!?vClearIncludeSprites@SURFACE@@SAXXZ` at `0x140065d85`
- `win32kbase!?vClearIncludeSprites@SURFACE@@SAXXZ` at `0x140065d85`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x140065059`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x1400650d0`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x140065059`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x1400650d0`
- `WIN32K!W32GetUserSessionState` at `0x14006612e`
- `WIN32K!W32GetUserSessionState` at `0x14006617d`
- `WIN32K!W32GetUserSessionState` at `0x14006612e`
- `WIN32K!W32GetUserSessionState` at `0x14006617d`

## pseudocode

```c
__int64 __fastcall GrepStretchBlt(
        struct SURFACE **a1,
        LONG x,
        int a3,
        int a4,
        int a5,
        struct SURFACE **a6,
        int a7,
        int a8,
        int a9,
        int a10,
        signed int a11,
        unsigned int a12,
        char a13)
{
  char v14; // r12
  unsigned int v17; // r8d
  unsigned int v18; // edx
  int v19; // eax
  int v20; // ebx
  struct SURFACE *v21; // rcx
  DC *v22; // rax
  __int64 v23; // rdx
  Gre::Base *v24; // rcx
  unsigned int v25; // r14d
  Gre::Base *v26; // rcx
  struct Gre::Base::SESSION_GLOBALS *v27; // rax
  char v28; // r8
  int v29; // edx
  char v30; // di
  bool v31; // bl
  struct SURFACE *v32; // rcx
  _QWORD *v33; // rax
  int v34; // edx
  struct Gre::Base::SESSION_GLOBALS *v35; // rax
  struct SURFACE *v36; // rcx
  struct SURFACE *v37; // rbx
  Gre::Base *v38; // rcx
  DC *v39; // r9
  Gre::Base *v40; // rcx
  struct Gre::Base::SESSION_GLOBALS *v41; // rax
  DC *v42; // rdx
  __int64 v43; // r13
  __int64 v44; // rbx
  struct Gre::Base::SESSION_GLOBALS *v45; // rdi
  Gre::Base *v46; // rcx
  struct Gre::Base::SESSION_GLOBALS *v47; // rax
  struct SURFACE *v48; // rdx
  struct SURFACE *v49; // rcx
  __int64 v50; // rbx
  __int64 v51; // r8
  Gre::Base *v52; // rcx
  __int64 v53; // r12
  __int64 v54; // rcx
  int v55; // edx
  bool v56; // zf
  Gre::Base *v57; // rcx
  __int64 v58; // rax
  int v59; // edx
  struct Gre::Base::SESSION_GLOBALS *v60; // rdx
  __int64 v61; // r8
  unsigned int v62; // r11d
  unsigned int j; // eax
  __int64 v64; // rdx
  int v65; // eax
  __int64 XlateObject; // rax
  Gre::Base *v67; // rcx
  int v68; // r9d
  int v69; // r12d
  int v70; // r8d
  int v71; // edx
  int v72; // ebx
  LONG y; // r11d
  int v74; // r10d
  int v75; // r9d
  SURFACE *v76; // r12
  unsigned int v77; // r15d
  LONG v78; // r8d
  LONG v79; // edx
  int v80; // r9d
  struct SURFACE *v81; // rbx
  int v82; // ebx
  struct OPTAPIDCOBJ *v83; // rbx
  unsigned int v84; // eax
  __int64 v86; // rax
  ULONG v87; // ecx
  struct Gre::Base::SESSION_GLOBALS *v88; // r12
  struct SURFACE *v89; // rdx
  __int64 v90; // r8
  unsigned int i; // ecx
  __int64 v92; // rax
  __int64 v93; // rdx
  int v94; // eax
  __int64 v95; // rdx
  int v96; // eax
  __int64 v97; // rdx
  int v98; // eax
  struct OPTAPIDCOBJ *v99; // rbx
  struct SURFACE *v100; // rax
  struct SURFACE *v101; // rax
  __int64 v102; // rcx
  char v103; // bl
  __int64 v104; // rcx
  struct SURFACE *v105; // rcx
  char *v106; // r9
  int v107; // r10d
  __int64 v108; // rcx
  __int64 v109; // rcx
  struct SURFACE *v110; // r8
  HSEMAPHORE v111; // rbx
  __int64 v112; // rcx
  __int64 v113; // rcx
  struct SURFACE *v114; // rcx
  SURFACE *v115; // rbx
  __int64 v116; // rcx
  __int64 v117; // rcx
  struct SURFACE *v118; // rdx
  __int64 v119; // r8
  int v120; // ecx
  __int64 v121; // rax
  SURFACE *v122; // rcx
  __int64 v123; // rbx
  int v124; // eax
  int v125; // [rsp+50h] [rbp-B0h]
  unsigned int v126; // [rsp+58h] [rbp-A8h]
  int v127; // [rsp+58h] [rbp-A8h]
  unsigned int v128; // [rsp+5Ch] [rbp-A4h]
  int v129; // [rsp+60h] [rbp-A0h]
  BOOL v130; // [rsp+64h] [rbp-9Ch]
  unsigned int v131; // [rsp+68h] [rbp-98h]
  unsigned int v132; // [rsp+6Ch] [rbp-94h]
  __int64 v133; // [rsp+70h] [rbp-90h] BYREF
  int v134; // [rsp+78h] [rbp-88h]
  struct SURFACE *v135; // [rsp+80h] [rbp-80h]
  __int64 v136; // [rsp+88h] [rbp-78h] BYREF
  int v137; // [rsp+90h] [rbp-70h]
  int v138; // [rsp+94h] [rbp-6Ch]
  int v139; // [rsp+98h] [rbp-68h]
  LONG v140; // [rsp+9Ch] [rbp-64h]
  int v141; // [rsp+A0h] [rbp-60h]
  __int64 v142; // [rsp+A8h] [rbp-58h]
  struct OPTAPIDCOBJ *v143; // [rsp+B0h] [rbp-50h]
  __int64 v144; // [rsp+B8h] [rbp-48h]
  struct Gre::Base::SESSION_GLOBALS *v145; // [rsp+C0h] [rbp-40h]
  unsigned int v146; // [rsp+C8h] [rbp-38h]
  unsigned int v147; // [rsp+CCh] [rbp-34h]
  struct Gre::Base::SESSION_GLOBALS *v148; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v149; // [rsp+D8h] [rbp-28h]
  struct SURFACE *v150; // [rsp+E0h] [rbp-20h] BYREF
  int v151; // [rsp+E8h] [rbp-18h]
  struct SURFACE *v152; // [rsp+F0h] [rbp-10h]
  __int64 v153; // [rsp+F8h] [rbp-8h]
  _OWORD v154[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v155[2]; // [rsp+120h] [rbp+20h] BYREF
  char v156; // [rsp+140h] [rbp+40h]
  __int64 v157; // [rsp+148h] [rbp+48h]
  DC *v158; // [rsp+150h] [rbp+50h] BYREF
  int v159; // [rsp+158h] [rbp+58h]
  struct SURFACE *v160; // [rsp+160h] [rbp+60h]
  __int64 v161; // [rsp+168h] [rbp+68h]
  _OWORD v162[2]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v163[2]; // [rsp+190h] [rbp+90h] BYREF
  char v164; // [rsp+1B0h] [rbp+B0h]
  __int64 v165; // [rsp+1C0h] [rbp+C0h] BYREF
  int v166; // [rsp+1C8h] [rbp+C8h]
  __int64 v167; // [rsp+1D0h] [rbp+D0h]
  __int64 v168; // [rsp+1D8h] [rbp+D8h]
  _BYTE v169[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v170[32]; // [rsp+200h] [rbp+100h] BYREF
  char v171; // [rsp+220h] [rbp+120h]
  __int64 v172; // [rsp+228h] [rbp+128h]
  _BYTE v173[80]; // [rsp+230h] [rbp+130h] BYREF
  int v174; // [rsp+280h] [rbp+180h]
  HSEMAPHORE v175; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v176; // [rsp+3C8h] [rbp+2C8h]
  struct MATRIX *inited; // [rsp+3D0h] [rbp+2D0h] BYREF
  struct MATRIX *v178; // [rsp+3D8h] [rbp+2D8h]
  __int64 v179; // [rsp+3E0h] [rbp+2E0h]
  Gre::Base *v180; // [rsp+3E8h] [rbp+2E8h]
  __int64 v181; // [rsp+3F0h] [rbp+2F0h]
  __int64 v182; // [rsp+3F8h] [rbp+2F8h]
  struct SURFACE *v183; // [rsp+400h] [rbp+300h]
  __int64 v184; // [rsp+408h] [rbp+308h]
  __int64 v185; // [rsp+410h] [rbp+310h]
  char *v186; // [rsp+418h] [rbp+318h]
  __int64 v187; // [rsp+420h] [rbp+320h]
  struct _POINTFIX v188; // [rsp+430h] [rbp+330h] BYREF
  struct _POINTL v189; // [rsp+450h] [rbp+350h] BYREF
  int v190; // [rsp+458h] [rbp+358h]
  LONG v191; // [rsp+45Ch] [rbp+35Ch]
  LONG v192; // [rsp+460h] [rbp+360h]
  int v193; // [rsp+464h] [rbp+364h]
  int v194; // [rsp+468h] [rbp+368h] BYREF
  int v195; // [rsp+46Ch] [rbp+36Ch]
  int v196; // [rsp+470h] [rbp+370h]
  int v197; // [rsp+474h] [rbp+374h]
  __int64 v198; // [rsp+488h] [rbp+388h]
  unsigned int v199; // [rsp+490h] [rbp+390h]
  int v200; // [rsp+494h] [rbp+394h]

  v14 = 0;
  v140 = a3;
  v134 = a4;
  v141 = a5;
  v143 = (struct OPTAPIDCOBJ *)a6;
  v185 = 0;
  v200 = 0;
  v17 = a11 & ((a11 & 0x40000000) != 0 ? 0x3FFFFFFF : 0x7FFFFFFF);
  v130 = (a11 & 0x40000000) != 0;
  v199 = ((v17 >> 8) | v17 & 0xFF0000) >> 8;
  v19 = *((unsigned __int8 *)gajRop3 + ((unsigned __int64)v199 >> 8));
  v129 = v19 | *((unsigned __int8 *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8));
  v20 = ((unsigned __int8)v19 | *((_BYTE *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8))) & 0xD4;
  v125 = v20;
  if ( (((unsigned __int8)v19 | *((_BYTE *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8))) & 0xD4) == 0 )
  {
    v18 = (((unsigned int)(a11 & ((a11 & 0x40000000) != 0 ? 0x3FFFFFFF : 0x7FFFFFFF)) >> 8)
         | a11 & ((a11 & 0x40000000) != 0 ? 0x3FFFFFFF : 0x7FFFFFFF) & 0xFF0000) >> 8;
    if ( (unsigned __int8)v18 == v18 >> 8 )
    {
      if ( *a1 )
      {
        v25 = GrepPatBlt((struct XDCOBJ *)a1, x, a3, a4, a5, v17);
        goto LABEL_135;
      }
      goto LABEL_164;
    }
  }
  if ( ((*((_BYTE *)gajRop3 + (unsigned __int8)v17) | *((_BYTE *)gajRop3 + BYTE1(v17))) & 2) != 0
    && v17 != 16711778
    && v17 != 66
    && *a1 )
  {
    bSpDwmValidateSurface((struct XDCOBJ *)a1, x, a3, a4, a5);
  }
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v152 = a6[2];
    v153 = 0;
    v150 = 0;
    memset(v154, 0, sizeof(v154));
    v151 = 0;
    PushThreadGuardedObject(
      v154,
      &v150,
      UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
    memset(v155, 0, sizeof(v155));
    PushThreadGuardedObject(
      v155,
      &v150,
      UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
    v150 = *a6;
    v156 = 0;
    bSpDwmValidateSurface((struct XDCOBJ *)&v150, a7, a8, a9, a10);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v150);
  }
  v160 = a6[2];
  v161 = 0;
  v158 = 0;
  memset(v162, 0, sizeof(v162));
  v159 = 0;
  PushThreadGuardedObject(
    v162,
    &v158,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v163, 0, sizeof(v163));
  PushThreadGuardedObject(
    v163,
    &v158,
    UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v21 = *a1;
  v22 = *a6;
  v164 = 0;
  v158 = v22;
  if ( v21 )
  {
    if ( !_bittest((const signed __int32 *)v21 + 9, 0x10u) )
    {
      v23 = *((_QWORD *)v21 + 122);
      if ( (*(_DWORD *)(v23 + 152) & 0x1000) != 0 )
        GreDCSelectBrush(v21, *(_QWORD *)(v23 + 160));
    }
  }
  if ( !*a1 || _bittest((const signed __int32 *)*a1 + 9, 0x10u) || !OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) && v20 )
  {
    EngSetLastError(6u);
    if ( !v20 || (v25 = 0, OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6)) )
      v25 = 1;
    goto LABEL_110;
  }
  DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(v173);
  if ( v20 )
  {
    DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v173, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v158);
    Gre::Base::Globals(v24);
  }
  else
  {
    DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v173, (struct XDCOBJ *)a1);
  }
  v25 = 1;
  if ( (v174 & 1) == 0 )
  {
    EngSetLastError(8u);
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
LABEL_164:
    v25 = 0;
    goto LABEL_135;
  }
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v26 = (Gre::Base *)*((_QWORD *)*a1 + 6);
    if ( (*((_DWORD *)v26 + 10) & 0x8000) != 0 )
    {
      v145 = Gre::Base::Globals(v26);
      GreAcquireSemaphoreShared<1,>(v145);
      v27 = v145;
      v28 = 1;
    }
    else
    {
      v27 = Gre::Base::Globals(v26);
      v28 = 0;
    }
    if ( v158 && *((_QWORD *)v158 + 62) && ((v29 = *((_DWORD *)v158 + 9), (v29 & 0x1000) == 0) || (v29 & 0x4000) != 0) )
    {
      v30 = 1;
      v31 = (v174 & 0x800000) != 0;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    v14 = *((_BYTE *)v158 + 36) & 1;
    if ( v28 )
      GreReleaseSemaphoreShared<1,>(v27);
  }
  else
  {
    v30 = 0;
    v31 = 0;
  }
  v32 = *a1;
  if ( *a1
    && (v33 = (_QWORD *)((char *)v32 + 496), *((_QWORD *)v32 + 62))
    && ((v34 = *((_DWORD *)v32 + 9), (v34 & 0x1000) == 0) || (v34 & 0x4000) != 0) )
  {
    if ( !v30 )
      goto LABEL_98;
    if ( v31 )
      goto LABEL_29;
  }
  else
  {
    v33 = (_QWORD *)((char *)v32 + 496);
  }
  if ( !*v33 || !v30 )
  {
LABEL_98:
    if ( (*((_DWORD *)v32 + 9) & 0xE0) != 0 )
    {
      DC::QuickInitXform(v32, &v136, 516);
      v78 = v140;
      v79 = x + v134;
      v80 = v140 + v141;
      v81 = *a1;
      LODWORD(v176) = x + v134;
      HIDWORD(v176) = v140 + v141;
      v175 = (HSEMAPHORE)__PAIR64__(v140, x);
      if ( (*(_BYTE *)(v136 + 32) & 0x43) == 0x43 )
      {
LABEL_102:
        if ( (*(_DWORD *)(*((_QWORD *)v81 + 122) + 108LL) & 1) != 0 )
        {
          ++x;
          ++v79;
          LODWORD(v175) = x;
          LODWORD(v176) = v79;
        }
        if ( x > v79 )
        {
          LODWORD(v175) = v79;
          LODWORD(v176) = x;
        }
        if ( v78 > v80 )
        {
          HIDWORD(v175) = v80;
          HIDWORD(v176) = v78;
        }
        XDCOBJ::vAccumulate((XDCOBJ *)a1, (struct ERECTL *)&v175);
        goto LABEL_109;
      }
      if ( (unsigned int)bCvtPts1(v136, &v175, 2) )
      {
        v80 = HIDWORD(v176);
        v79 = v176;
        v78 = HIDWORD(v175);
        x = (int)v175;
        goto LABEL_102;
      }
    }
LABEL_109:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173);
LABEL_110:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
LABEL_135:
    BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
    return v25;
  }
  if ( !v14 )
    goto LABEL_134;
LABEL_29:
  if ( v125 && (v174 & 0x400000) == 0 )
    goto LABEL_132;
  v35 = Gre::Base::Globals(v32);
  v36 = (struct SURFACE *)*((_QWORD *)*a1 + 62);
  if ( v36 )
  {
    if ( a1[3] )
      v36 = a1[3];
  }
  else
  {
    v36 = (struct SURFACE *)*((_QWORD *)v35 + 547);
  }
  if ( !(unsigned int)DestSurfaceAccessCheck(v36) )
  {
LABEL_132:
    v87 = 5;
LABEL_133:
    EngSetLastError(v87);
LABEL_134:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
    v25 = 0;
    goto LABEL_135;
  }
  if ( (unsigned __int8)v199 != BYTE1(v199) || (a11 & 0x40000000) != 0 && !OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v87 = 87;
    goto LABEL_133;
  }
  v37 = 0;
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
    v37 = a6[12];
  if ( (a11 < 0
     && (v39 = *a1, v38 = (Gre::Base *)*(unsigned int *)(*((_QWORD *)*a1 + 122) + 108LL),
                    ((unsigned __int8)v38 & 1) != 0)
     || (v39 = *a1, (*(_BYTE *)(*((_QWORD *)*a1 + 122) + 108LL) & 9) == 9))
    && v37 != *(struct SURFACE **)v39 )
  {
    v123 = *(_QWORD *)(*((_QWORD *)v39 + 122) + 308LL);
    v132 = DC::dwSetLayout(v39, -1, 0);
    x = v123 - v134 - x;
    v131 = 0x80000000;
  }
  else
  {
    v132 = 0;
    v131 = 0;
  }
  Gre::Base::Globals(v38);
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v41 = Gre::Base::Globals(v40);
    v42 = v158;
    v43 = *((_QWORD *)v158 + 62);
    if ( v43 )
    {
      if ( v161 )
        v43 = v161;
    }
    else
    {
      v43 = *((_QWORD *)v41 + 547);
    }
    v44 = *(_QWORD *)(v43 + 48);
  }
  else
  {
    v42 = v158;
    v43 = 0;
    v44 = 0;
  }
  LODWORD(v45) = 0;
  v144 = v44;
  v145 = 0;
  if ( (a11 & 0x40000000) != 0 )
  {
    if ( (*((_DWORD *)v42 + 9) & 1) != 0 && (v109 = *((_QWORD *)v42 + 6), (*(_DWORD *)(v109 + 40) & 0x80u) == 0) )
    {
      v110 = *a1;
      if ( v109 == *((_QWORD *)*a1 + 6) )
      {
        v76 = 0;
      }
      else
      {
        v124 = XDCOBJ::bRedirHooked((XDCOBJ *)a1);
        v42 = v158;
        v76 = 0;
        if ( !v124 )
          goto LABEL_184;
        v110 = *a1;
        if ( *((_QWORD *)v158 + 6) != *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) )
          goto LABEL_184;
      }
      if ( v44 )
      {
        v135 = 0;
        if ( v125 )
        {
          if ( (*((_DWORD *)v42 + 9) & 0x4000) != 0 )
          {
            v122 = (SURFACE *)*((_QWORD *)v42 + 62);
            if ( v122 != *((SURFACE **)v110 + 62) )
            {
              v135 = (struct SURFACE *)*((_QWORD *)v42 + 62);
              SURFACE::bUnMap(v122);
              v44 = v144;
            }
          }
        }
        if ( (*((_DWORD *)*a1 + 9) & 0x4000) != 0 )
        {
          v76 = (SURFACE *)*((_QWORD *)*a1 + 62);
          SURFACE::bUnMap(v76);
        }
        v111 = *(HSEMAPHORE *)(v44 + 56);
        EtwTraceGreLockAcquireSemaphoreExclusive(L"Pointer", v111, 0);
        GreAcquireSemaphoreInternal(v111);
        GrepAcquireLockValidate<4>();
        v45 = *(struct Gre::Base::SESSION_GLOBALS **)(v144 + 64);
        v145 = v45;
        UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v175);
        if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v112) + 36124) )
          GreMovePointer(*(_QWORD *)(v43 + 48), 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
        SURFACE::vSetIncludeSprites();
        v113 = v176;
        if ( v176 )
        {
          *(_DWORD *)(v176 + 340) = (_DWORD)v175;
          *(_DWORD *)(v113 + 344) = HIDWORD(v175);
        }
        GrepStretchReMapSurface((struct XDCOBJ *)a1, v76);
        GrepStretchReMapSurface((struct XDCOBJ *)&v158, v135);
        v42 = v158;
        v76 = 0;
LABEL_185:
        if ( (*((_DWORD *)v42 + 11) & 1) != 0 || (*((_DWORD *)*a1 + 11) & 1) != 0 )
          goto LABEL_93;
        goto LABEL_48;
      }
    }
    else
    {
      v76 = 0;
    }
LABEL_184:
    v130 = 0;
    goto LABEL_185;
  }
LABEL_48:
  v133 = 0;
  inited = DC::InitXform(*a1, 0x204u);
  v47 = Gre::Base::Globals(v46);
  v48 = *a1;
  v49 = (struct SURFACE *)*((_QWORD *)*a1 + 62);
  if ( v49 )
  {
    if ( a1[3] )
      v49 = a1[3];
  }
  else
  {
    v49 = (struct SURFACE *)*((_QWORD *)v47 + 547);
  }
  v183 = v49;
  v179 = *((_QWORD *)v49 + 22);
  v180 = (Gre::Base *)*((_QWORD *)v48 + 11);
  if ( OPTAPIDCOBJ::bValid(v143) )
  {
    v178 = DC::InitXform(v158, 0x204u);
    v184 = v43;
    v50 = *(_QWORD *)(v43 + 176);
    v181 = v50;
    v142 = *((_QWORD *)v158 + 11);
    v182 = v142;
    v128 = a12;
    if ( a12 == -1 )
      v128 = *(_DWORD *)(*((_QWORD *)v158 + 122) + 180LL);
  }
  else
  {
    v50 = v181;
    v128 = a12;
    v142 = v182;
  }
  if ( (a13 & 1) != 0 )
  {
    v51 = *(_QWORD *)(*((_QWORD *)*a1 + 122) + 248LL);
    v133 = v51;
  }
  else
  {
    v51 = v133;
  }
  v52 = v180;
  v53 = v179;
  v135 = v180;
  v136 = v179;
  if ( !v50 )
  {
    if ( v179 )
    {
      if ( (*(_DWORD *)(v179 + 24) & 0x800) == 0 )
        goto LABEL_64;
      v121 = *((_QWORD *)v180 + 10);
      if ( v121 )
      {
        if ( v121 != *((_QWORD *)v180 + 9) )
          goto LABEL_64;
      }
    }
    goto LABEL_127;
  }
  if ( v179 )
  {
    v54 = v50;
    if ( *(_QWORD *)(v50 + 120) != v50 )
      v54 = *(_QWORD *)(v50 + 120);
    v55 = *(_DWORD *)(v54 + 32);
    v52 = (Gre::Base *)v179;
    if ( *(_QWORD *)(v179 + 120) != v179 )
      v52 = *(Gre::Base **)(v179 + 120);
    v56 = v55 == *((_DWORD *)v52 + 8);
LABEL_63:
    if ( !v56 )
      goto LABEL_64;
LABEL_127:
    v186 = (char *)Gre::Base::Globals(v52) + 4664;
    goto LABEL_79;
  }
  if ( (*(_DWORD *)(v50 + 24) & 0x800) != 0 )
  {
    v86 = *((_QWORD *)v180 + 10);
    if ( !v86 )
      goto LABEL_127;
    v56 = v86 == *((_QWORD *)v180 + 9);
    goto LABEL_63;
  }
LABEL_64:
  v57 = *a1;
  v58 = *((_QWORD *)*a1 + 122);
  v59 = *(_DWORD *)(v58 + 176);
  v138 = *(_DWORD *)(v58 + 184);
  LODWORD(v58) = *((_DWORD *)v57 + 30);
  v137 = v59;
  v147 = v58;
  if ( (v58 & 7) != 0 && v51 )
  {
    v139 = 0;
    goto LABEL_76;
  }
  v139 = 1;
  if ( !v50 || !v179 )
  {
LABEL_76:
    XlateObject = CreateXlateObject(v133, v147, v50, v53, v142, v135, v138, v59, v128, 0);
    v186 = (char *)XlateObject;
    if ( XlateObject )
    {
      if ( v139 && v50 && v53 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
      {
        v88 = Gre::Base::Globals(v67);
        v133 = *(_QWORD *)v88 + 312LL;
        GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
        for ( i = 0; i < 8; ++i )
        {
          v90 = *((unsigned int *)v88 + 1164);
          v92 = 32 * v90;
          v89 = (struct SURFACE *)*((_QWORD *)v88 + 4 * v90 + 551);
          if ( !v89 )
            goto LABEL_143;
          if ( !*(_DWORD *)((char *)v88 + v92 + 4400) )
          {
            FreeThreadBufferWithTag(*(_QWORD *)((char *)v88 + v92 + 4408));
LABEL_143:
            PopThreadGuardedObject(v186 - 32);
            v93 = v50;
            *((_DWORD *)v88 + 8 * *((unsigned int *)v88 + 1164) + 1100) = 1;
            *((_QWORD *)v88 + 4 * *((unsigned int *)v88 + 1164) + 551) = v186;
            if ( *(_QWORD *)(v50 + 120) != v50 )
              v93 = *(_QWORD *)(v50 + 120);
            v94 = *(_DWORD *)(v93 + 32);
            v95 = v136;
            *((_DWORD *)v88 + 8 * *((unsigned int *)v88 + 1164) + 1104) = v94;
            if ( *(_QWORD *)(v95 + 120) != v95 )
              v95 = *(_QWORD *)(v95 + 120);
            v96 = *(_DWORD *)(v95 + 32);
            v97 = v142;
            *((_DWORD *)v88 + 8 * *((unsigned int *)v88 + 1164) + 1105) = v96;
            if ( *(_QWORD *)(v97 + 120) != v97 )
              v97 = *(_QWORD *)(v97 + 120);
            v98 = *(_DWORD *)(v97 + 32);
            v89 = v135;
            *((_DWORD *)v88 + 8 * *((unsigned int *)v88 + 1164) + 1106) = v98;
            if ( *((struct SURFACE **)v89 + 15) != v89 )
              v89 = (struct SURFACE *)*((_QWORD *)v89 + 15);
            *((_DWORD *)v88 + 8 * *((unsigned int *)v88 + 1164) + 1107) = *((_DWORD *)v89 + 8);
            *((_DWORD *)v186 + 9) = *((_DWORD *)v88 + 1164);
            *(_DWORD *)(v50 + 56) = *((_DWORD *)v88 + 1164);
            *((_DWORD *)v88 + 1164) = ((unsigned __int8)*((_DWORD *)v88 + 1164) + 1) & 7;
            break;
          }
          *((_DWORD *)v88 + 1164) = ((_BYTE)v90 + 1) & 7;
        }
        SEMOBJ<13>::vUnlock(&v133, v89, v90);
      }
      goto LABEL_79;
    }
    goto LABEL_92;
  }
  v146 = *(_DWORD *)(v50 + 56);
  v148 = Gre::Base::Globals(v57);
  v175 = (HSEMAPHORE)(*(_QWORD *)v148 + 312LL);
  GreAcquireSemaphoreInternal(v175);
  GrepAcquireLockValidate<13>();
  v62 = v146;
  for ( j = 0; ; j = v126 + 1 )
  {
    v126 = j;
    if ( j >= 8 )
    {
      v186 = 0;
      v127 = 0;
      goto LABEL_74;
    }
    v64 = v50;
    v61 = v62;
    if ( *(_QWORD *)(v50 + 120) != v50 )
      v64 = *(_QWORD *)(v50 + 120);
    v65 = *(_DWORD *)(v64 + 32);
    v60 = v148;
    if ( *((_DWORD *)v148 + 8 * v62 + 1104) != v65 )
      goto LABEL_72;
    v104 = v53;
    if ( *(_QWORD *)(v53 + 120) != v53 )
      v104 = *(_QWORD *)(v53 + 120);
    v61 = 32LL * v62;
    if ( *(_DWORD *)((char *)v148 + v61 + 4420) != *(_DWORD *)(v104 + 32) )
      goto LABEL_72;
    v105 = v135;
    if ( *((struct SURFACE **)v135 + 15) != v135 )
      v105 = (struct SURFACE *)*((_QWORD *)v135 + 15);
    if ( *(_DWORD *)((char *)v148 + v61 + 4428) != *((_DWORD *)v105 + 8) )
      goto LABEL_72;
    v106 = *(char **)((char *)v148 + v61 + 4408);
    v186 = v106;
    if ( (*((_DWORD *)v106 + 19) & 0x6000) != 0 )
      goto LABEL_72;
    v107 = *((_DWORD *)v106 + 19) & 0x100;
    if ( (*((_DWORD *)v106 + 1) & 4) != 0 )
      break;
    if ( !v107 )
      goto LABEL_181;
LABEL_179:
    if ( v138 == *((_DWORD *)v106 + 7) && v137 == *((_DWORD *)v106 + 8) )
      goto LABEL_181;
LABEL_72:
    v62 = ((_BYTE)v62 + 1) & 7;
  }
  if ( v128 != *((_DWORD *)v106 + 6) )
    goto LABEL_178;
  v108 = v142;
  if ( *(_QWORD *)(v142 + 120) != v142 )
    v108 = *(_QWORD *)(v142 + 120);
  if ( *(_DWORD *)((char *)v148 + v61 + 4424) != *(_DWORD *)(v108 + 32) )
  {
LABEL_178:
    if ( !v107 )
      goto LABEL_72;
    goto LABEL_179;
  }
LABEL_181:
  _InterlockedAdd((volatile signed __int32 *)((char *)v148 + v61 + 4400), 1u);
  *(_DWORD *)(v50 + 56) = v62;
  v127 = 1;
LABEL_74:
  SEMOBJ<13>::vUnlock(&v175, v60, v61);
  if ( !v127 )
  {
    v59 = v137;
    goto LABEL_76;
  }
LABEL_79:
  v200 |= 2u;
  if ( (v129 & 0xE8) != 0 )
  {
    v118 = *a1;
    v187 = (__int64)*a1 + 1200;
    v119 = *((_QWORD *)v118 + 122);
    v120 = *(_DWORD *)(v119 + 152);
    if ( (v120 & 1) != 0 || (*((_DWORD *)v118 + 79) & 1) != 0 )
    {
      *(_DWORD *)(v119 + 152) = v120 & 0xFFFFFFFE;
      *((_DWORD *)*a1 + 79) &= ~1u;
      EBRUSHOBJ::vInitBrush(v187, *a1, *((_QWORD *)*a1 + 17), v180, v179, v183, 1);
    }
    v198 = *((_QWORD *)*a1 + 149);
  }
  else
  {
    v187 = 0;
  }
  v185 = 0;
  if ( (*((_BYTE *)v178 + 32) & 1) == 0 )
    goto LABEL_91;
  v68 = a7;
  v69 = a8;
  v70 = a7 + a9;
  v71 = a8 + a10;
  v196 = a7 + a9;
  v197 = a8 + a10;
  v194 = a7;
  v195 = a8;
  if ( (*((_BYTE *)v178 + 32) & 0x43) == 0x43 )
  {
LABEL_85:
    v72 = v125;
    if ( v125 && (v69 == v71 || v68 == v70) )
    {
      v77 = 1;
      v76 = 0;
      goto LABEL_121;
    }
    y = v140;
    v74 = x + v134;
    v75 = v140 + v141;
    v56 = (*((_BYTE *)inited + 32) & 1) == 0;
    v189.x = x;
    v189.y = v140;
    v190 = x + v134;
    if ( v56 )
    {
      v193 = v140 + v141;
      v191 = v140;
      v192 = x;
      EXFORMOBJ::bXform((EXFORMOBJ *)&inited, &v189, &v188, 3u);
      APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v165, v143);
      v101 = *a1;
      v76 = 0;
      v172 = v43;
      v153 = 0;
      v150 = 0;
      v102 = *((_QWORD *)v101 + 122);
      v152 = a1[2];
      v151 = 0;
      v103 = *(_BYTE *)(v102 + 215);
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v154);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v155);
      v150 = *a1;
      v156 = 0;
      v157 = 0;
      v84 = BLTRECORD::bRotate(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v150,
              (struct BLTRECORD::PROXYDCOBJ *)&v165,
              v129,
              v103);
    }
    else
    {
      v191 = v140 + v141;
      if ( (*((_BYTE *)inited + 32) & 0x43) == 0x43 )
      {
        v82 = a7;
      }
      else
      {
        if ( !(unsigned int)bCvtPts1(inited, &v189, 2) )
          goto LABEL_91;
        v71 = v197;
        v70 = v196;
        v69 = v195;
        v82 = v194;
        v75 = v191;
        v74 = v190;
        y = v189.y;
        x = v189.x;
      }
      if ( *(_BYTE *)(*((_QWORD *)*a1 + 122) + 215LL) == 4 || v70 - v82 != v74 - x || v71 - v69 != v75 - y )
      {
        v99 = v143;
        v76 = 0;
        v168 = 0;
        v165 = 0;
        v167 = *((_QWORD *)v143 + 2);
        v166 = 0;
        UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v169);
        UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v170);
        v165 = *(_QWORD *)v99;
        v100 = *a1;
        v171 = 0;
        v172 = v43;
        v77 = BLTRECORD::bStretch(
                (BLTRECORD *)&inited,
                (struct XDCOBJ *)a1,
                (struct BLTRECORD::PROXYDCOBJ *)&v165,
                v129,
                *(_BYTE *)(*((_QWORD *)v100 + 122) + 215LL));
        goto LABEL_119;
      }
      v83 = v143;
      v76 = 0;
      v168 = 0;
      v165 = 0;
      v167 = *((_QWORD *)v143 + 2);
      v166 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v169);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v170);
      v165 = *(_QWORD *)v83;
      v152 = a1[2];
      v171 = 0;
      v172 = v43;
      v153 = 0;
      v150 = 0;
      v151 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v154);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v155);
      v150 = *a1;
      v156 = 0;
      v157 = 0;
      v84 = BLTRECORD::bBitBlt(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v150,
              (struct BLTRECORD::PROXYDCOBJ *)&v165,
              v129);
    }
    v77 = v84;
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v150);
LABEL_119:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v165);
    goto LABEL_120;
  }
  if ( (unsigned int)bCvtPts1(v178, &v194, 2) )
  {
    v68 = v194;
    v71 = v197;
    v70 = v196;
    v69 = v195;
    a7 = v194;
    goto LABEL_85;
  }
LABEL_91:
  EngSetLastError(0x57u);
LABEL_92:
  v76 = 0;
LABEL_93:
  v77 = 0;
LABEL_120:
  v72 = v125;
LABEL_121:
  if ( v131 )
    DC::dwSetLayout(*a1, -1, v132);
  if ( v130 )
  {
    SURFACE::vClearIncludeSprites();
    if ( v72
      && (*((_DWORD *)v158 + 11) & 1) == 0
      && (*((_DWORD *)v158 + 9) & 0x4000) != 0
      && v43 != *((_QWORD *)*a1 + 62)
      && (*(_DWORD *)(v43 + 160) & 0x800) != 0 )
    {
      v76 = (SURFACE *)*((_QWORD *)v158 + 62);
      SURFACE::bUnMap(v76);
    }
    v114 = *a1;
    v115 = 0;
    if ( (*((_DWORD *)*a1 + 11) & 1) == 0 && (*((_DWORD *)v114 + 9) & 0x4000) != 0 )
    {
      v115 = (SURFACE *)*((_QWORD *)v114 + 62);
      SURFACE::bUnMap(v115);
    }
    UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v148);
    if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v116) + 36124) )
      GreMovePointer(*(_QWORD *)(v43 + 48), (unsigned int)v45, HIDWORD(v145), 0);
    GreReleaseSemaphoreCommon<4,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal, *(_QWORD *)(v144 + 56));
    v117 = v149;
    if ( v149 )
    {
      *(_DWORD *)(v149 + 340) = (_DWORD)v148;
      *(_DWORD *)(v117 + 344) = HIDWORD(v148);
    }
    GrepStretchReMapSurface((struct XDCOBJ *)a1, v115);
    GrepStretchReMapSurface((struct XDCOBJ *)&v158, v76);
  }
  DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173);
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
  BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
  return v77;
}

```

## disassembly

```asm
0x140064ba0  push    rbp
0x140064ba2  push    rbx
0x140064ba3  push    rsi
0x140064ba4  push    rdi
0x140064ba5  push    r12
0x140064ba7  push    r13
0x140064ba9  push    r14
0x140064bab  push    r15
0x140064bad  lea     rbp, [rsp-3B8h]
0x140064bb5  sub     rsp, 4B8h
0x140064bbc  mov     rax, cs:__security_cookie
0x140064bc3  xor     rax, rsp
0x140064bc6  mov     [rbp+3F0h+var_50], rax
0x140064bcd  mov     r13, [rbp+3F0h+arg_28]
0x140064bd4  lea     rdi, gajRop3
0x140064bdb  mov     r11d, [rbp+3F0h+arg_20]
0x140064be2  mov     rsi, rcx
0x140064be5  xor     r12d, r12d
0x140064be8  mov     [rbp+3F0h+var_454], r8d
0x140064bec  mov     r10d, r8d
0x140064bef  mov     [rsp+4F0h+var_478], r9d
0x140064bf4  mov     r15d, edx
0x140064bf7  mov     [rbp+3F0h+var_450], r11d
0x140064bfb  mov     edx, [rbp+3F0h+arg_50]
0x140064c01  mov     ecx, edx
0x140064c03  and     ecx, 40000000h
0x140064c09  mov     [rsp+4F0h+var_488], edx
0x140064c0d  mov     eax, ecx
0x140064c0f  mov     [rsp+4F0h+var_484], ecx
0x140064c13  neg     eax
0x140064c15  mov     [rbp+3F0h+var_440], r13
0x140064c19  mov     eax, r12d
0x140064c1c  mov     [rbp+3F0h+var_E0], r12
0x140064c23  sbb     r8d, r8d
0x140064c26  mov     [rbp+3F0h+var_5C], r12d
0x140064c2d  and     r8d, 0C0000000h
0x140064c34  add     r8d, 7FFFFFFFh
0x140064c3b  and     r8d, edx
0x140064c3e  test    ecx, ecx
0x140064c40  mov     ecx, r8d
0x140064c43  setnz   al
0x140064c46  and     ecx, 0FF0000h
0x140064c4c  mov     [rsp+4F0h+var_48C], eax
0x140064c50  mov     eax, r8d
0x140064c53  shr     eax, 8
0x140064c56  or      ecx, eax
0x140064c58  shr     ecx, 8
0x140064c5b  mov     edx, ecx
0x140064c5d  movzx   eax, cl
0x140064c60  mov     [rbp+3F0h+var_60], edx
0x140064c66  movzx   ecx, byte ptr [rax+rdi]
0x140064c6a  mov     eax, edx
0x140064c6c  shr     rax, 8
0x140064c70  movzx   eax, byte ptr [rax+rdi]
0x140064c74  or      ecx, eax
0x140064c76  mov     ebx, ecx
0x140064c78  mov     [rsp+4F0h+var_490], ecx
0x140064c7c  and     ebx, 0D4h
0x140064c82  mov     [rsp+4F0h+var_4A0], ebx
0x140064c86  jz      loc_140065ADE
0x140064c8c  mov     eax, r8d
0x140064c8f  shr     rax, 8
0x140064c93  movzx   edx, al
0x140064c96  movzx   eax, r8b
0x140064c9a  mov     cl, [rax+rdi]
0x140064c9d  mov     al, [rdx+rdi]
0x140064ca0  or      al, cl
0x140064ca2  test    al, 2
0x140064ca4  jnz     loc_1400659DC
0x140064caa  mov     rcx, r13; this
0x140064cad  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140064cb2  test    al, al
0x140064cb4  jz      loc_140064D56
0x140064cba  mov     rax, [r13+10h]
0x140064cbe  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140064cc5  xorps   xmm0, xmm0
0x140064cc8  mov     [rbp+3F0h+var_400], rax
0x140064ccc  lea     rdx, [rbp+3F0h+var_410]
0x140064cd0  mov     [rbp+3F0h+var_3F8], r12
0x140064cd4  lea     rcx, [rbp+3F0h+var_3F0]
0x140064cd8  mov     [rbp+3F0h+var_410], r12
0x140064cdc  movups  [rbp+3F0h+var_3F0], xmm0
0x140064ce0  mov     [rbp+3F0h+var_408], r12d
0x140064ce4  movups  [rbp+3F0h+var_3E0], xmm0
0x140064ce8  call    cs:__imp_PushThreadGuardedObject
0x140064cef  nop     dword ptr [rax+rax+00h]
0x140064cf4  xorps   xmm0, xmm0
0x140064cf7  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140064cfe  lea     rdx, [rbp+3F0h+var_410]
0x140064d02  lea     rcx, [rbp+3F0h+var_3D0]
0x140064d06  movups  [rbp+3F0h+var_3D0], xmm0
0x140064d0a  movups  [rbp+3F0h+var_3C0], xmm0
0x140064d0e  call    cs:__imp_PushThreadGuardedObject
0x140064d15  nop     dword ptr [rax+rax+00h]
0x140064d1a  mov     rax, [r13+0]
0x140064d1e  lea     rcx, [rbp+3F0h+var_410]; struct XDCOBJ *
0x140064d22  mov     r9d, [rbp+3F0h+arg_40]; int
0x140064d29  mov     r8d, [rbp+3F0h+arg_38]; int
0x140064d30  mov     edx, [rbp+3F0h+arg_30]; int
0x140064d36  mov     [rbp+3F0h+var_410], rax
0x140064d3a  mov     eax, [rbp+3F0h+arg_48]
0x140064d40  mov     dword ptr [rsp+4F0h+var_4D0], eax; int
0x140064d44  mov     [rbp+3F0h+var_3B0], r12b
0x140064d48  call    ?bSpDwmValidateSurface@@YAHAEAVXDCOBJ@@HHHH@Z; bSpDwmValidateSurface(XDCOBJ &,int,int,int,int)
0x140064d4d  lea     rcx, [rbp+3F0h+var_410]; this
0x140064d51  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140064d56  mov     rax, [r13+10h]
0x140064d5a  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140064d61  xorps   xmm0, xmm0
0x140064d64  mov     [rbp+3F0h+var_390], rax
0x140064d68  lea     rdx, [rbp+3F0h+var_3A0]
0x140064d6c  mov     [rbp+3F0h+var_388], r12
0x140064d70  lea     rcx, [rbp+3F0h+var_380]
0x140064d74  mov     [rbp+3F0h+var_3A0], r12
0x140064d78  movups  [rbp+3F0h+var_380], xmm0
0x140064d7c  mov     [rbp+3F0h+var_398], r12d
0x140064d80  movups  [rbp+3F0h+var_370], xmm0
0x140064d87  call    cs:__imp_PushThreadGuardedObject
0x140064d8e  nop     dword ptr [rax+rax+00h]
0x140064d93  xorps   xmm0, xmm0
0x140064d96  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140064d9d  lea     rdx, [rbp+3F0h+var_3A0]
0x140064da1  lea     rcx, [rbp+3F0h+var_360]
0x140064da8  movups  [rbp+3F0h+var_360], xmm0
0x140064daf  movups  [rbp+3F0h+var_350], xmm0
0x140064db6  call    cs:__imp_PushThreadGuardedObject
0x140064dbd  nop     dword ptr [rax+rax+00h]
0x140064dc2  mov     rcx, [rsi]
0x140064dc5  mov     rax, [r13+0]
0x140064dc9  mov     [rbp+3F0h+var_340], r12b
0x140064dd0  mov     [rbp+3F0h+var_3A0], rax
0x140064dd4  test    rcx, rcx
0x140064dd7  jz      short loc_140064E06
0x140064dd9  bt      dword ptr [rcx+24h], 10h
0x140064dde  jb      short loc_140064E06
0x140064de0  mov     rdx, [rcx+3D0h]
0x140064de7  test    dword ptr [rdx+98h], 1000h
0x140064df1  jz      short loc_140064E06
0x140064df3  mov     rdx, [rdx+0A0h]
0x140064dfa  call    cs:__imp_GreDCSelectBrush
0x140064e01  nop     dword ptr [rax+rax+00h]
0x140064e06  mov     rax, [rsi]
0x140064e09  test    rax, rax
0x140064e0c  jz      loc_140065443
0x140064e12  bt      dword ptr [rax+24h], 10h
0x140064e17  jb      loc_140065443
0x140064e1d  mov     rcx, r13; this
0x140064e20  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140064e25  test    al, al
0x140064e27  jz      loc_14006603F
0x140064e2d  lea     rcx, [rbp+3F0h+var_2C0]
0x140064e34  call    ??0DEVLOCKBLTOBJ@@QEAA@W4U2KMMAPStatus@@0@Z; DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(U2KMMAPStatus,U2KMMAPStatus)
0x140064e39  lea     rcx, [rbp+3F0h+var_2C0]; this
0x140064e40  mov     rdx, rsi; struct XDCOBJ *
0x140064e43  test    ebx, ebx
0x140064e45  jz      loc_14006604C
0x140064e4b  lea     r8, [rbp+3F0h+var_3A0]; struct XDCOBJ *
0x140064e4f  call    ?bLock@DEVLOCKBLTOBJ@@QEAAHAEAVXDCOBJ@@0@Z; DEVLOCKBLTOBJ::bLock(XDCOBJ &,XDCOBJ &)
0x140064e54  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140064e5b  nop     dword ptr [rax+rax+00h]
0x140064e60  mov     r14d, 1
0x140064e66  test    byte ptr [rbp+3F0h+var_270], r14b
0x140064e6d  jz      loc_140066006
0x140064e73  mov     rcx, r13; this
0x140064e76  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140064e7b  test    al, al
0x140064e7d  jz      loc_1400659D1
0x140064e83  mov     rax, [rsi]
0x140064e86  mov     rcx, [rax+30h]
0x140064e8a  test    dword ptr [rcx+28h], 8000h
0x140064e91  jnz     loc_14006591F
0x140064e97  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140064e9e  nop     dword ptr [rax+rax+00h]
0x140064ea3  mov     r8b, r12b
0x140064ea6  mov     rcx, [rbp+3F0h+var_3A0]
0x140064eaa  test    rcx, rcx
0x140064ead  jz      loc_140065730
0x140064eb3  cmp     [rcx+1F0h], r12
0x140064eba  jz      loc_140065730
0x140064ec0  mov     edx, [rcx+24h]
0x140064ec3  bt      edx, 0Ch
0x140064ec7  jb      loc_140066056
0x140064ecd  mov     ebx, [rbp+3F0h+var_270]
0x140064ed3  mov     dil, r14b
0x140064ed6  shr     ebx, 17h
0x140064ed9  and     bl, r14b
0x140064edc  mov     r12b, [rcx+24h]
0x140064ee0  and     r12b, r14b
0x140064ee3  test    r8b, r8b
0x140064ee6  jz      short loc_140064EF0
0x140064ee8  mov     rcx, rax
0x140064eeb  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x140064ef0  mov     rcx, [rsi]
0x140064ef3  test    rcx, rcx
0x140064ef6  jz      loc_140065467
0x140064efc  lea     rax, [rcx+1F0h]
0x140064f03  cmp     qword ptr [rax], 0
0x140064f07  jz      loc_140065467
0x140064f0d  mov     edx, [rcx+24h]
0x140064f10  bt      edx, 0Ch
0x140064f14  jb      loc_140066065
0x140064f1a  test    dil, dil
0x140064f1d  jz      loc_140065478
0x140064f23  test    bl, bl
0x140064f25  jz      loc_14006546E
0x140064f2b  cmp     [rsp+4F0h+var_4A0], 0
0x140064f30  jz      short loc_140064F42
0x140064f32  test    [rbp+3F0h+var_270], 400000h
0x140064f3c  jz      loc_14006573B
0x140064f42  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140064f49  nop     dword ptr [rax+rax+00h]
0x140064f4e  mov     rcx, [rsi]
0x140064f51  mov     rcx, [rcx+1F0h]
0x140064f58  test    rcx, rcx
0x140064f5b  jz      loc_140065569
0x140064f61  mov     rax, [rsi+18h]
0x140064f65  test    rax, rax
0x140064f68  cmovnz  rcx, rax; struct SURFACE *
0x140064f6c  call    ?DestSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; DestSurfaceAccessCheck(SURFACE *)
0x140064f71  test    eax, eax
0x140064f73  jz      loc_14006573B
0x140064f79  mov     eax, [rbp+3F0h+var_60]
0x140064f7f  shr     eax, 8
0x140064f82  xor     eax, [rbp+3F0h+var_60]
0x140064f88  test    al, al
0x140064f8a  jnz     loc_140065F88
0x140064f90  mov     r12d, [rsp+4F0h+var_484]
0x140064f95  test    r12d, r12d
0x140064f98  jnz     loc_140065F78
0x140064f9e  mov     rcx, r13; this
0x140064fa1  xor     ebx, ebx
0x140064fa3  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140064fa8  test    al, al
0x140064faa  jz      short loc_140064FB0
0x140064fac  mov     rbx, [r13+60h]
0x140064fb0  cmp     [rsp+4F0h+var_488], 0
0x140064fb5  jl      loc_140066074
0x140064fbb  mov     r9, [rsi]
0x140064fbe  mov     rax, [r9+3D0h]
0x140064fc5  mov     edx, [rax+6Ch]
0x140064fc8  and     edx, 9
0x140064fcb  cmp     dl, 9
0x140064fce  jz      loc_14006608A
0x140064fd4  mov     [rsp+4F0h+var_484], 0
0x140064fdc  mov     [rsp+4F0h+var_488], 0
0x140064fe4  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140064feb  nop     dword ptr [rax+rax+00h]
0x140064ff0  mov     rcx, r13; this
0x140064ff3  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140064ff8  test    al, al
0x140064ffa  jz      loc_1400660D1
0x140065000  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065007  nop     dword ptr [rax+rax+00h]
0x14006500c  mov     rdx, [rbp+3F0h+var_3A0]
0x140065010  mov     r13, [rdx+1F0h]
0x140065017  test    r13, r13
0x14006501a  jz      loc_140065575
0x140065020  mov     rax, [rbp+3F0h+var_388]
0x140065024  test    rax, rax
0x140065027  cmovnz  r13, rax
0x14006502b  mov     rbx, [r13+30h]
0x14006502f  xor     edi, edi
0x140065031  mov     [rbp+3F0h+var_438], rbx
0x140065035  mov     [rbp+3F0h+var_430], rdi
0x140065039  test    r12d, r12d
0x14006503c  jnz     loc_140065BE2
0x140065042  mov     ebx, [rsp+4F0h+var_48C]
0x140065046  mov     [rsp+4F0h+var_48C], ebx
0x14006504a  xor     ecx, ecx
0x14006504c  mov     edx, 204h
0x140065051  mov     [rsp+4F0h+var_480], rcx
0x140065056  mov     rcx, [rsi]
0x140065059  call    cs:__imp_?InitXform@DC@@QEAAPEAUMATRIX@@K@Z; DC::InitXform(ulong)
0x140065060  nop     dword ptr [rax+rax+00h]
0x140065065  mov     [rbp+3F0h+var_120], rax
0x14006506c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065073  nop     dword ptr [rax+rax+00h]
0x140065078  mov     rdx, [rsi]
0x14006507b  mov     rcx, [rdx+1F0h]
0x140065082  test    rcx, rcx
0x140065085  jz      loc_1400656DE
0x14006508b  mov     rax, [rsi+18h]
0x14006508f  test    rax, rax
0x140065092  cmovnz  rcx, rax
0x140065096  mov     [rbp+3F0h+var_F0], rcx
0x14006509d  mov     rax, [rcx+0B0h]
0x1400650a4  mov     rcx, [rbp+3F0h+var_440]; this
0x1400650a8  mov     [rbp+3F0h+var_110], rax
0x1400650af  mov     rax, [rdx+58h]
0x1400650b3  mov     [rbp+3F0h+var_108], rax
0x1400650ba  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x1400650bf  test    al, al
0x1400650c1  jz      loc_140065FBA
0x1400650c7  mov     rcx, [rbp+3F0h+var_3A0]
0x1400650cb  mov     edx, 204h
0x1400650d0  call    cs:__imp_?InitXform@DC@@QEAAPEAUMATRIX@@K@Z; DC::InitXform(ulong)
0x1400650d7  nop     dword ptr [rax+rax+00h]
0x1400650dc  mov     ecx, [rbp+3F0h+arg_58]
0x1400650e2  mov     [rbp+3F0h+var_118], rax
0x1400650e9  mov     rax, [rbp+3F0h+var_3A0]
  ... truncated ...
```
