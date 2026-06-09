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
  unsigned int v60; // r11d
  unsigned int j; // eax
  __int64 v62; // rdx
  __int64 XlateObject; // rax
  Gre::Base *v64; // rcx
  int v65; // r9d
  int v66; // r12d
  int v67; // r8d
  int v68; // edx
  int v69; // ebx
  LONG y; // r11d
  int v71; // r10d
  int v72; // r9d
  SURFACE *v73; // r12
  unsigned int v74; // r15d
  LONG v75; // r8d
  LONG v76; // edx
  int v77; // r9d
  struct SURFACE *v78; // rbx
  int v79; // ebx
  struct OPTAPIDCOBJ *v80; // rbx
  unsigned int v81; // eax
  __int64 v83; // rax
  ULONG v84; // ecx
  struct Gre::Base::SESSION_GLOBALS *v85; // r12
  unsigned int i; // ecx
  unsigned int v87; // r8d
  __int64 v88; // rax
  __int64 v89; // rdx
  int v90; // eax
  __int64 v91; // rdx
  int v92; // eax
  __int64 v93; // rdx
  int v94; // eax
  struct SURFACE *v95; // rdx
  struct OPTAPIDCOBJ *v96; // rbx
  struct SURFACE *v97; // rax
  struct SURFACE *v98; // rax
  __int64 v99; // rcx
  char v100; // bl
  __int64 v101; // rcx
  __int64 v102; // r8
  struct SURFACE *v103; // rcx
  char *v104; // r9
  int v105; // r10d
  __int64 v106; // rcx
  __int64 v107; // rcx
  struct SURFACE *v108; // r8
  HSEMAPHORE v109; // rbx
  __int64 v110; // rdx
  __int64 v111; // rcx
  __int64 v112; // r8
  __int64 v113; // r9
  __int64 v114; // rcx
  struct SURFACE *v115; // rcx
  SURFACE *v116; // rbx
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rcx
  struct SURFACE *v122; // rdx
  __int64 v123; // r8
  int v124; // ecx
  __int64 v125; // rax
  SURFACE *v126; // rcx
  __int64 v127; // rbx
  int v128; // eax
  int v129; // [rsp+50h] [rbp-B0h]
  int v130; // [rsp+58h] [rbp-A8h]
  unsigned int v131; // [rsp+5Ch] [rbp-A4h]
  int v132; // [rsp+60h] [rbp-A0h]
  BOOL v133; // [rsp+64h] [rbp-9Ch]
  unsigned int v134; // [rsp+68h] [rbp-98h]
  unsigned int v135; // [rsp+6Ch] [rbp-94h]
  __int64 v136; // [rsp+70h] [rbp-90h] BYREF
  int v137; // [rsp+78h] [rbp-88h]
  struct SURFACE *v138; // [rsp+80h] [rbp-80h]
  __int64 v139; // [rsp+88h] [rbp-78h] BYREF
  int v140; // [rsp+90h] [rbp-70h]
  int v141; // [rsp+94h] [rbp-6Ch]
  int v142; // [rsp+98h] [rbp-68h]
  LONG v143; // [rsp+9Ch] [rbp-64h]
  int v144; // [rsp+A0h] [rbp-60h]
  __int64 v145; // [rsp+A8h] [rbp-58h]
  struct OPTAPIDCOBJ *v146; // [rsp+B0h] [rbp-50h]
  __int64 v147; // [rsp+B8h] [rbp-48h]
  struct Gre::Base::SESSION_GLOBALS *v148; // [rsp+C0h] [rbp-40h]
  unsigned int v149; // [rsp+C8h] [rbp-38h]
  unsigned int v150; // [rsp+CCh] [rbp-34h]
  struct Gre::Base::SESSION_GLOBALS *v151; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v152; // [rsp+D8h] [rbp-28h]
  struct SURFACE *v153; // [rsp+E0h] [rbp-20h] BYREF
  int v154; // [rsp+E8h] [rbp-18h]
  struct SURFACE *v155; // [rsp+F0h] [rbp-10h]
  __int64 v156; // [rsp+F8h] [rbp-8h]
  _OWORD v157[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v158[2]; // [rsp+120h] [rbp+20h] BYREF
  char v159; // [rsp+140h] [rbp+40h]
  __int64 v160; // [rsp+148h] [rbp+48h]
  DC *v161; // [rsp+150h] [rbp+50h] BYREF
  int v162; // [rsp+158h] [rbp+58h]
  struct SURFACE *v163; // [rsp+160h] [rbp+60h]
  __int64 v164; // [rsp+168h] [rbp+68h]
  _OWORD v165[2]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v166[2]; // [rsp+190h] [rbp+90h] BYREF
  char v167; // [rsp+1B0h] [rbp+B0h]
  __int64 v168; // [rsp+1C0h] [rbp+C0h] BYREF
  int v169; // [rsp+1C8h] [rbp+C8h]
  __int64 v170; // [rsp+1D0h] [rbp+D0h]
  __int64 v171; // [rsp+1D8h] [rbp+D8h]
  _BYTE v172[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v173[32]; // [rsp+200h] [rbp+100h] BYREF
  char v174; // [rsp+220h] [rbp+120h]
  __int64 v175; // [rsp+228h] [rbp+128h]
  _BYTE v176[80]; // [rsp+230h] [rbp+130h] BYREF
  int v177; // [rsp+280h] [rbp+180h]
  HSEMAPHORE v178; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v179; // [rsp+3C8h] [rbp+2C8h]
  struct MATRIX *inited; // [rsp+3D0h] [rbp+2D0h] BYREF
  struct MATRIX *v181; // [rsp+3D8h] [rbp+2D8h]
  __int64 v182; // [rsp+3E0h] [rbp+2E0h]
  Gre::Base *v183; // [rsp+3E8h] [rbp+2E8h]
  __int64 v184; // [rsp+3F0h] [rbp+2F0h]
  __int64 v185; // [rsp+3F8h] [rbp+2F8h]
  struct SURFACE *v186; // [rsp+400h] [rbp+300h]
  __int64 v187; // [rsp+408h] [rbp+308h]
  __int64 v188; // [rsp+410h] [rbp+310h]
  char *v189; // [rsp+418h] [rbp+318h]
  __int64 v190; // [rsp+420h] [rbp+320h]
  struct _POINTFIX v191; // [rsp+430h] [rbp+330h] BYREF
  struct _POINTL v192; // [rsp+450h] [rbp+350h] BYREF
  int v193; // [rsp+458h] [rbp+358h]
  LONG v194; // [rsp+45Ch] [rbp+35Ch]
  LONG v195; // [rsp+460h] [rbp+360h]
  int v196; // [rsp+464h] [rbp+364h]
  int v197; // [rsp+468h] [rbp+368h] BYREF
  int v198; // [rsp+46Ch] [rbp+36Ch]
  int v199; // [rsp+470h] [rbp+370h]
  int v200; // [rsp+474h] [rbp+374h]
  __int64 v201; // [rsp+488h] [rbp+388h]
  unsigned int v202; // [rsp+490h] [rbp+390h]
  int v203; // [rsp+494h] [rbp+394h]

  v14 = 0;
  v143 = a3;
  v137 = a4;
  v144 = a5;
  v146 = (struct OPTAPIDCOBJ *)a6;
  v188 = 0;
  v203 = 0;
  v17 = a11 & ((a11 & 0x40000000) != 0 ? 0x3FFFFFFF : 0x7FFFFFFF);
  v133 = (a11 & 0x40000000) != 0;
  v202 = ((v17 >> 8) | v17 & 0xFF0000) >> 8;
  v19 = *((unsigned __int8 *)gajRop3 + ((unsigned __int64)v202 >> 8));
  v132 = v19 | *((unsigned __int8 *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8));
  v20 = ((unsigned __int8)v19 | *((_BYTE *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8))) & 0xD4;
  v129 = v20;
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
    v155 = a6[2];
    v156 = 0;
    v153 = 0;
    memset(v157, 0, sizeof(v157));
    v154 = 0;
    PushThreadGuardedObject(
      v157,
      &v153,
      UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
    memset(v158, 0, sizeof(v158));
    PushThreadGuardedObject(
      v158,
      &v153,
      UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
    v153 = *a6;
    v159 = 0;
    bSpDwmValidateSurface((struct XDCOBJ *)&v153, a7, a8, a9, a10);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v153);
  }
  v163 = a6[2];
  v164 = 0;
  v161 = 0;
  memset(v165, 0, sizeof(v165));
  v162 = 0;
  PushThreadGuardedObject(
    v165,
    &v161,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v166, 0, sizeof(v166));
  PushThreadGuardedObject(
    v166,
    &v161,
    UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v21 = *a1;
  v22 = *a6;
  v167 = 0;
  v161 = v22;
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
  DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(v176);
  if ( v20 )
  {
    DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v176, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v161);
    Gre::Base::Globals(v24);
  }
  else
  {
    DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v176, (struct XDCOBJ *)a1);
  }
  v25 = 1;
  if ( (v177 & 1) == 0 )
  {
    EngSetLastError(8u);
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v176);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v161);
LABEL_164:
    v25 = 0;
    goto LABEL_135;
  }
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v26 = (Gre::Base *)*((_QWORD *)*a1 + 6);
    if ( (*((_DWORD *)v26 + 10) & 0x8000) != 0 )
    {
      v148 = Gre::Base::Globals(v26);
      GreAcquireSemaphoreShared<1,>(v148);
      v27 = v148;
      v28 = 1;
    }
    else
    {
      v27 = Gre::Base::Globals(v26);
      v28 = 0;
    }
    if ( v161 && *((_QWORD *)v161 + 62) && ((v29 = *((_DWORD *)v161 + 9), (v29 & 0x1000) == 0) || (v29 & 0x4000) != 0) )
    {
      v30 = 1;
      v31 = (v177 & 0x800000) != 0;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    v14 = *((_BYTE *)v161 + 36) & 1;
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
      DC::QuickInitXform(v32, &v139, 516);
      v75 = v143;
      v76 = x + v137;
      v77 = v143 + v144;
      v78 = *a1;
      LODWORD(v179) = x + v137;
      HIDWORD(v179) = v143 + v144;
      v178 = (HSEMAPHORE)__PAIR64__(v143, x);
      if ( (*(_BYTE *)(v139 + 32) & 0x43) == 0x43 )
      {
LABEL_102:
        if ( (*(_DWORD *)(*((_QWORD *)v78 + 122) + 108LL) & 1) != 0 )
        {
          ++x;
          ++v76;
          LODWORD(v178) = x;
          LODWORD(v179) = v76;
        }
        if ( x > v76 )
        {
          LODWORD(v178) = v76;
          LODWORD(v179) = x;
        }
        if ( v75 > v77 )
        {
          HIDWORD(v178) = v77;
          HIDWORD(v179) = v75;
        }
        XDCOBJ::vAccumulate((XDCOBJ *)a1, (struct ERECTL *)&v178);
        goto LABEL_109;
      }
      if ( (unsigned int)bCvtPts1(v139, &v178, 2) )
      {
        v77 = HIDWORD(v179);
        v76 = v179;
        v75 = HIDWORD(v178);
        x = (int)v178;
        goto LABEL_102;
      }
    }
LABEL_109:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v176);
LABEL_110:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v161);
LABEL_135:
    BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
    return v25;
  }
  if ( !v14 )
    goto LABEL_134;
LABEL_29:
  if ( v129 && (v177 & 0x400000) == 0 )
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
    v84 = 5;
LABEL_133:
    EngSetLastError(v84);
LABEL_134:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v176);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v161);
    v25 = 0;
    goto LABEL_135;
  }
  if ( (unsigned __int8)v202 != BYTE1(v202) || (a11 & 0x40000000) != 0 && !OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v84 = 87;
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
    v127 = *(_QWORD *)(*((_QWORD *)v39 + 122) + 308LL);
    v135 = DC::dwSetLayout(v39, -1, 0);
    x = v127 - v137 - x;
    v134 = 0x80000000;
  }
  else
  {
    v135 = 0;
    v134 = 0;
  }
  Gre::Base::Globals(v38);
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v41 = Gre::Base::Globals(v40);
    v42 = v161;
    v43 = *((_QWORD *)v161 + 62);
    if ( v43 )
    {
      if ( v164 )
        v43 = v164;
    }
    else
    {
      v43 = *((_QWORD *)v41 + 547);
    }
    v44 = *(_QWORD *)(v43 + 48);
  }
  else
  {
    v42 = v161;
    v43 = 0;
    v44 = 0;
  }
  LODWORD(v45) = 0;
  v147 = v44;
  v148 = 0;
  if ( (a11 & 0x40000000) != 0 )
  {
    if ( (*((_DWORD *)v42 + 9) & 1) != 0 && (v107 = *((_QWORD *)v42 + 6), (*(_DWORD *)(v107 + 40) & 0x80u) == 0) )
    {
      v108 = *a1;
      if ( v107 == *((_QWORD *)*a1 + 6) )
      {
        v73 = 0;
      }
      else
      {
        v128 = XDCOBJ::bRedirHooked((XDCOBJ *)a1);
        v42 = v161;
        v73 = 0;
        if ( !v128 )
          goto LABEL_184;
        v108 = *a1;
        if ( *((_QWORD *)v161 + 6) != *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) )
          goto LABEL_184;
      }
      if ( v44 )
      {
        v138 = 0;
        if ( v129 )
        {
          if ( (*((_DWORD *)v42 + 9) & 0x4000) != 0 )
          {
            v126 = (SURFACE *)*((_QWORD *)v42 + 62);
            if ( v126 != *((SURFACE **)v108 + 62) )
            {
              v138 = (struct SURFACE *)*((_QWORD *)v42 + 62);
              SURFACE::bUnMap(v126);
              v44 = v147;
            }
          }
        }
        if ( (*((_DWORD *)*a1 + 9) & 0x4000) != 0 )
        {
          v73 = (SURFACE *)*((_QWORD *)*a1 + 62);
          SURFACE::bUnMap(v73);
        }
        v109 = *(HSEMAPHORE *)(v44 + 56);
        EtwTraceGreLockAcquireSemaphoreExclusive(L"Pointer", v109, 0);
        GreAcquireSemaphoreInternal(v109);
        GrepAcquireLockValidate<4>();
        v45 = *(struct Gre::Base::SESSION_GLOBALS **)(v147 + 64);
        v148 = v45;
        UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v178);
        if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v111, v110, v112, v113) + 36124) )
          GreMovePointer(*(_QWORD *)(v43 + 48), 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
        SURFACE::vSetIncludeSprites();
        v114 = v179;
        if ( v179 )
        {
          *(_DWORD *)(v179 + 340) = (_DWORD)v178;
          *(_DWORD *)(v114 + 344) = HIDWORD(v178);
        }
        GrepStretchReMapSurface((struct XDCOBJ *)a1, v73);
        GrepStretchReMapSurface((struct XDCOBJ *)&v161, v138);
        v42 = v161;
        v73 = 0;
LABEL_185:
        if ( (*((_DWORD *)v42 + 11) & 1) != 0 || (*((_DWORD *)*a1 + 11) & 1) != 0 )
          goto LABEL_93;
        goto LABEL_48;
      }
    }
    else
    {
      v73 = 0;
    }
LABEL_184:
    v133 = 0;
    goto LABEL_185;
  }
LABEL_48:
  v136 = 0;
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
  v186 = v49;
  v182 = *((_QWORD *)v49 + 22);
  v183 = (Gre::Base *)*((_QWORD *)v48 + 11);
  if ( OPTAPIDCOBJ::bValid(v146) )
  {
    v181 = DC::InitXform(v161, 0x204u);
    v187 = v43;
    v50 = *(_QWORD *)(v43 + 176);
    v184 = v50;
    v145 = *((_QWORD *)v161 + 11);
    v185 = v145;
    v131 = a12;
    if ( a12 == -1 )
      v131 = *(_DWORD *)(*((_QWORD *)v161 + 122) + 180LL);
  }
  else
  {
    v50 = v184;
    v131 = a12;
    v145 = v185;
  }
  if ( (a13 & 1) != 0 )
  {
    v51 = *(_QWORD *)(*((_QWORD *)*a1 + 122) + 248LL);
    v136 = v51;
  }
  else
  {
    v51 = v136;
  }
  v52 = v183;
  v53 = v182;
  v138 = v183;
  v139 = v182;
  if ( !v50 )
  {
    if ( v182 )
    {
      if ( (*(_DWORD *)(v182 + 24) & 0x800) == 0 )
        goto LABEL_64;
      v125 = *((_QWORD *)v183 + 10);
      if ( v125 )
      {
        if ( v125 != *((_QWORD *)v183 + 9) )
          goto LABEL_64;
      }
    }
    goto LABEL_127;
  }
  if ( v182 )
  {
    v54 = v50;
    if ( *(_QWORD *)(v50 + 120) != v50 )
      v54 = *(_QWORD *)(v50 + 120);
    v55 = *(_DWORD *)(v54 + 32);
    v52 = (Gre::Base *)v182;
    if ( *(_QWORD *)(v182 + 120) != v182 )
      v52 = *(Gre::Base **)(v182 + 120);
    v56 = v55 == *((_DWORD *)v52 + 8);
LABEL_63:
    if ( !v56 )
      goto LABEL_64;
LABEL_127:
    v189 = (char *)Gre::Base::Globals(v52) + 4664;
    goto LABEL_79;
  }
  if ( (*(_DWORD *)(v50 + 24) & 0x800) != 0 )
  {
    v83 = *((_QWORD *)v183 + 10);
    if ( !v83 )
      goto LABEL_127;
    v56 = v83 == *((_QWORD *)v183 + 9);
    goto LABEL_63;
  }
LABEL_64:
  v57 = *a1;
  v58 = *((_QWORD *)*a1 + 122);
  v59 = *(_DWORD *)(v58 + 176);
  v141 = *(_DWORD *)(v58 + 184);
  LODWORD(v58) = *((_DWORD *)v57 + 30);
  v140 = v59;
  v150 = v58;
  if ( (v58 & 7) != 0 && v51 )
  {
    v142 = 0;
    goto LABEL_76;
  }
  v142 = 1;
  if ( !v50 || !v182 )
  {
LABEL_76:
    XlateObject = CreateXlateObject(v136, v150, v50, v53, v145, v138, v141, v59, v131, 0);
    v189 = (char *)XlateObject;
    if ( XlateObject )
    {
      if ( v142 && v50 && v53 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
      {
        v85 = Gre::Base::Globals(v64);
        v136 = *(_QWORD *)v85 + 312LL;
        GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
        for ( i = 0; i < 8; ++i )
        {
          v87 = *((_DWORD *)v85 + 1164);
          v88 = 32LL * v87;
          if ( !*(_QWORD *)((char *)v85 + v88 + 4408) )
            goto LABEL_143;
          if ( !*(_DWORD *)((char *)v85 + v88 + 4400) )
          {
            FreeThreadBufferWithTag(*(_QWORD *)((char *)v85 + v88 + 4408));
LABEL_143:
            PopThreadGuardedObject(v189 - 32);
            v89 = v50;
            *((_DWORD *)v85 + 8 * *((unsigned int *)v85 + 1164) + 1100) = 1;
            *((_QWORD *)v85 + 4 * *((unsigned int *)v85 + 1164) + 551) = v189;
            if ( *(_QWORD *)(v50 + 120) != v50 )
              v89 = *(_QWORD *)(v50 + 120);
            v90 = *(_DWORD *)(v89 + 32);
            v91 = v139;
            *((_DWORD *)v85 + 8 * *((unsigned int *)v85 + 1164) + 1104) = v90;
            if ( *(_QWORD *)(v91 + 120) != v91 )
              v91 = *(_QWORD *)(v91 + 120);
            v92 = *(_DWORD *)(v91 + 32);
            v93 = v145;
            *((_DWORD *)v85 + 8 * *((unsigned int *)v85 + 1164) + 1105) = v92;
            if ( *(_QWORD *)(v93 + 120) != v93 )
              v93 = *(_QWORD *)(v93 + 120);
            v94 = *(_DWORD *)(v93 + 32);
            v95 = v138;
            *((_DWORD *)v85 + 8 * *((unsigned int *)v85 + 1164) + 1106) = v94;
            if ( *((struct SURFACE **)v95 + 15) != v95 )
              v95 = (struct SURFACE *)*((_QWORD *)v95 + 15);
            *((_DWORD *)v85 + 8 * *((unsigned int *)v85 + 1164) + 1107) = *((_DWORD *)v95 + 8);
            *((_DWORD *)v189 + 9) = *((_DWORD *)v85 + 1164);
            *(_DWORD *)(v50 + 56) = *((_DWORD *)v85 + 1164);
            *((_DWORD *)v85 + 1164) = ((unsigned __int8)*((_DWORD *)v85 + 1164) + 1) & 7;
            break;
          }
          *((_DWORD *)v85 + 1164) = ((_BYTE)v87 + 1) & 7;
        }
        SEMOBJ<13>::vUnlock(&v136);
      }
      goto LABEL_79;
    }
    goto LABEL_92;
  }
  v149 = *(_DWORD *)(v50 + 56);
  v151 = Gre::Base::Globals(v57);
  v178 = (HSEMAPHORE)(*(_QWORD *)v151 + 312LL);
  GreAcquireSemaphoreInternal(v178);
  GrepAcquireLockValidate<13>();
  v60 = v149;
  for ( j = 0; ; ++j )
  {
    if ( j >= 8 )
    {
      v189 = 0;
      v130 = 0;
      goto LABEL_74;
    }
    v62 = v50;
    if ( *(_QWORD *)(v50 + 120) != v50 )
      v62 = *(_QWORD *)(v50 + 120);
    if ( *((_DWORD *)v151 + 8 * v60 + 1104) != *(_DWORD *)(v62 + 32) )
      goto LABEL_72;
    v101 = v53;
    if ( *(_QWORD *)(v53 + 120) != v53 )
      v101 = *(_QWORD *)(v53 + 120);
    v102 = 32LL * v60;
    if ( *(_DWORD *)((char *)v151 + v102 + 4420) != *(_DWORD *)(v101 + 32) )
      goto LABEL_72;
    v103 = v138;
    if ( *((struct SURFACE **)v138 + 15) != v138 )
      v103 = (struct SURFACE *)*((_QWORD *)v138 + 15);
    if ( *(_DWORD *)((char *)v151 + v102 + 4428) != *((_DWORD *)v103 + 8) )
      goto LABEL_72;
    v104 = *(char **)((char *)v151 + v102 + 4408);
    v189 = v104;
    if ( (*((_DWORD *)v104 + 19) & 0x6000) != 0 )
      goto LABEL_72;
    v105 = *((_DWORD *)v104 + 19) & 0x100;
    if ( (*((_DWORD *)v104 + 1) & 4) != 0 )
      break;
    if ( !v105 )
      goto LABEL_181;
LABEL_179:
    if ( v141 == *((_DWORD *)v104 + 7) && v140 == *((_DWORD *)v104 + 8) )
      goto LABEL_181;
LABEL_72:
    v60 = ((_BYTE)v60 + 1) & 7;
  }
  if ( v131 != *((_DWORD *)v104 + 6) )
    goto LABEL_178;
  v106 = v145;
  if ( *(_QWORD *)(v145 + 120) != v145 )
    v106 = *(_QWORD *)(v145 + 120);
  if ( *(_DWORD *)((char *)v151 + v102 + 4424) != *(_DWORD *)(v106 + 32) )
  {
LABEL_178:
    if ( !v105 )
      goto LABEL_72;
    goto LABEL_179;
  }
LABEL_181:
  _InterlockedAdd((volatile signed __int32 *)((char *)v151 + v102 + 4400), 1u);
  *(_DWORD *)(v50 + 56) = v60;
  v130 = 1;
LABEL_74:
  SEMOBJ<13>::vUnlock(&v178);
  if ( !v130 )
  {
    v59 = v140;
    goto LABEL_76;
  }
LABEL_79:
  v203 |= 2u;
  if ( (v132 & 0xE8) != 0 )
  {
    v122 = *a1;
    v190 = (__int64)*a1 + 1200;
    v123 = *((_QWORD *)v122 + 122);
    v124 = *(_DWORD *)(v123 + 152);
    if ( (v124 & 1) != 0 || (*((_DWORD *)v122 + 79) & 1) != 0 )
    {
      *(_DWORD *)(v123 + 152) = v124 & 0xFFFFFFFE;
      *((_DWORD *)*a1 + 79) &= ~1u;
      EBRUSHOBJ::vInitBrush(v190, *a1, *((_QWORD *)*a1 + 17), v183, v182);
    }
    v201 = *((_QWORD *)*a1 + 149);
  }
  else
  {
    v190 = 0;
  }
  v188 = 0;
  if ( (*((_BYTE *)v181 + 32) & 1) == 0 )
    goto LABEL_91;
  v65 = a7;
  v66 = a8;
  v67 = a7 + a9;
  v68 = a8 + a10;
  v199 = a7 + a9;
  v200 = a8 + a10;
  v197 = a7;
  v198 = a8;
  if ( (*((_BYTE *)v181 + 32) & 0x43) == 0x43 )
  {
LABEL_85:
    v69 = v129;
    if ( v129 && (v66 == v68 || v65 == v67) )
    {
      v74 = 1;
      v73 = 0;
      goto LABEL_121;
    }
    y = v143;
    v71 = x + v137;
    v72 = v143 + v144;
    v56 = (*((_BYTE *)inited + 32) & 1) == 0;
    v192.x = x;
    v192.y = v143;
    v193 = x + v137;
    if ( v56 )
    {
      v196 = v143 + v144;
      v194 = v143;
      v195 = x;
      EXFORMOBJ::bXform((EXFORMOBJ *)&inited, &v192, &v191, 3u);
      APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v168, v146);
      v98 = *a1;
      v73 = 0;
      v175 = v43;
      v156 = 0;
      v153 = 0;
      v99 = *((_QWORD *)v98 + 122);
      v155 = a1[2];
      v154 = 0;
      v100 = *(_BYTE *)(v99 + 215);
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v157);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v158);
      v153 = *a1;
      v159 = 0;
      v160 = 0;
      v81 = BLTRECORD::bRotate(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v153,
              (struct BLTRECORD::PROXYDCOBJ *)&v168,
              v132,
              v100);
    }
    else
    {
      v194 = v143 + v144;
      if ( (*((_BYTE *)inited + 32) & 0x43) == 0x43 )
      {
        v79 = a7;
      }
      else
      {
        if ( !(unsigned int)bCvtPts1(inited, &v192, 2) )
          goto LABEL_91;
        v68 = v200;
        v67 = v199;
        v66 = v198;
        v79 = v197;
        v72 = v194;
        v71 = v193;
        y = v192.y;
        x = v192.x;
      }
      if ( *(_BYTE *)(*((_QWORD *)*a1 + 122) + 215LL) == 4 || v67 - v79 != v71 - x || v68 - v66 != v72 - y )
      {
        v96 = v146;
        v73 = 0;
        v171 = 0;
        v168 = 0;
        v170 = *((_QWORD *)v146 + 2);
        v169 = 0;
        UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v172);
        UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v173);
        v168 = *(_QWORD *)v96;
        v97 = *a1;
        v174 = 0;
        v175 = v43;
        v74 = BLTRECORD::bStretch(
                (BLTRECORD *)&inited,
                (struct XDCOBJ *)a1,
                (struct BLTRECORD::PROXYDCOBJ *)&v168,
                v132,
                *(_BYTE *)(*((_QWORD *)v97 + 122) + 215LL));
        goto LABEL_119;
      }
      v80 = v146;
      v73 = 0;
      v171 = 0;
      v168 = 0;
      v170 = *((_QWORD *)v146 + 2);
      v169 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v172);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v173);
      v168 = *(_QWORD *)v80;
      v155 = a1[2];
      v174 = 0;
      v175 = v43;
      v156 = 0;
      v153 = 0;
      v154 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v157);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v158);
      v153 = *a1;
      v159 = 0;
      v160 = 0;
      v81 = BLTRECORD::bBitBlt(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v153,
              (struct BLTRECORD::PROXYDCOBJ *)&v168,
              v132);
    }
    v74 = v81;
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v153);
LABEL_119:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v168);
    goto LABEL_120;
  }
  if ( (unsigned int)bCvtPts1(v181, &v197, 2) )
  {
    v65 = v197;
    v68 = v200;
    v67 = v199;
    v66 = v198;
    a7 = v197;
    goto LABEL_85;
  }
LABEL_91:
  EngSetLastError(0x57u);
LABEL_92:
  v73 = 0;
LABEL_93:
  v74 = 0;
LABEL_120:
  v69 = v129;
LABEL_121:
  if ( v134 )
    DC::dwSetLayout(*a1, -1, v135);
  if ( v133 )
  {
    SURFACE::vClearIncludeSprites();
    if ( v69
      && (*((_DWORD *)v161 + 11) & 1) == 0
      && (*((_DWORD *)v161 + 9) & 0x4000) != 0
      && v43 != *((_QWORD *)*a1 + 62)
      && (*(_DWORD *)(v43 + 160) & 0x800) != 0 )
    {
      v73 = (SURFACE *)*((_QWORD *)v161 + 62);
      SURFACE::bUnMap(v73);
    }
    v115 = *a1;
    v116 = 0;
    if ( (*((_DWORD *)*a1 + 11) & 1) == 0 && (*((_DWORD *)v115 + 9) & 0x4000) != 0 )
    {
      v116 = (SURFACE *)*((_QWORD *)v115 + 62);
      SURFACE::bUnMap(v116);
    }
    UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v151);
    if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v118, v117, v119, v120) + 36124) )
      GreMovePointer(*(_QWORD *)(v43 + 48), (unsigned int)v45, HIDWORD(v148), 0);
    GreReleaseSemaphoreCommon<4,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal);
    v121 = v152;
    if ( v152 )
    {
      *(_DWORD *)(v152 + 340) = (_DWORD)v151;
      *(_DWORD *)(v121 + 344) = HIDWORD(v151);
    }
    GrepStretchReMapSurface((struct XDCOBJ *)a1, v116);
    GrepStretchReMapSurface((struct XDCOBJ *)&v161, v73);
  }
  DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v176);
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v161);
  BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
  return v74;
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
