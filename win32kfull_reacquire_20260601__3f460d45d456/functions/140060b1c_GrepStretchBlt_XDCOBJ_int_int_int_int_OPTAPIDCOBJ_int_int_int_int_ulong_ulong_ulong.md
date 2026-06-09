# GrepStretchBlt(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,int,int,ulong,ulong,ulong)

- ea: `0x140060b1c`
- end: `0x14006212f`
- name: `?GrepStretchBlt@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHHHKKK@Z`
- size: `5651`
- prototype: `__int64 __usercall@<rax>(struct XDCOBJ *@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int, struct OPTAPIDCOBJ *, int, int, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140053cf0`
- `0x140058784`
- `0x140062340`
- `0x140067830`
- `0x1400a55dc`
- `0x1401a0c80`

## callees

- `0x1400512b0`
- `0x140051df0`
- `0x140051efc`
- `0x140052618`
- `0x140057fe0`
- `0x14005b820`
- `0x140060b1c`
- `0x140062138`
- `0x14006487c`
- `0x140065000`
- `0x140067498`
- `0x1400677c0`
- `0x140068674`
- `0x1400686bc`
- `0x140069870`
- `0x14006d0d0`
- `0x14008aa50`
- `0x14009b35c`
- `0x14009b890`
- `0x14009bdbc`
- `0x14009bf24`
- `0x1400a997c`
- `0x1400ab040`
- `0x1400ab648`
- `0x1400acc04`
- `0x140112314`
- `0x1401a04a4`
- `0x1401ab400`
- `0x14021a750`
- `0x140252b28`
- `0x140283008`
- `0x140342fa0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060dd0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060e13`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060ebe`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060f60`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060f7c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060fe8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140061161`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006166f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006170a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006189b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060dd0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060e13`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060ebe`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060f60`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060f7c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060fe8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140061161`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006166f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006170a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006189b`
- `win32kbase!PopThreadGuardedObject` at `0x140061784`
- `win32kbase!PopThreadGuardedObject` at `0x140061784`
- `win32kbase!PushThreadGuardedObject` at `0x140060c64`
- `win32kbase!PushThreadGuardedObject` at `0x140060c8a`
- `win32kbase!PushThreadGuardedObject` at `0x140060d03`
- `win32kbase!PushThreadGuardedObject` at `0x140060d32`
- `win32kbase!PushThreadGuardedObject` at `0x140060c64`
- `win32kbase!PushThreadGuardedObject` at `0x140060c8a`
- `win32kbase!PushThreadGuardedObject` at `0x140060d03`
- `win32kbase!PushThreadGuardedObject` at `0x140060d32`
- `win32kbase!FreeThreadBufferWithTag` at `0x14006176d`
- `win32kbase!FreeThreadBufferWithTag` at `0x14006176d`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140061182`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140061c63`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140061182`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140061716`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140061c63`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140061d92`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140061c54`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreExclusive` at `0x140061c54`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140061d49`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140061ebf`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140061f25`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140062099`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140061d49`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140061ebf`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140061f25`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140062099`
- `win32kbase!EngSetLastError` at `0x1400613a8`
- `win32kbase!EngSetLastError` at `0x1400613c4`
- `win32kbase!EngSetLastError` at `0x1400616bc`
- `win32kbase!EngSetLastError` at `0x140061f87`
- `win32kbase!EngSetLastError` at `0x1400613a8`
- `win32kbase!EngSetLastError` at `0x1400613c4`
- `win32kbase!EngSetLastError` at `0x1400616bc`
- `win32kbase!EngSetLastError` at `0x140061f87`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140061409`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140061409`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x1400619ca`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x1400619ca`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140061e4d`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140061e4d`
- `win32kbase!GreDCSelectBrush` at `0x140060d76`
- `win32kbase!GreDCSelectBrush` at `0x140060d76`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x140060fd5`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x14006104c`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x140060fd5`
- `win32kbase!?InitXform@DC@@QEAAPEAUMATRIX@@K@Z` at `0x14006104c`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140062026`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x1400620e8`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x140062026`
- `win32kbase!?dwSetLayout@DC@@QEAAKJK@Z` at `0x1400620e8`
- `win32kbase!?vSetIncludeSprites@SURFACE@@SAXXZ` at `0x140061cad`
- `win32kbase!?vSetIncludeSprites@SURFACE@@SAXXZ` at `0x140061cad`
- `win32kbase!?vClearIncludeSprites@SURFACE@@SAXXZ` at `0x140061d01`
- `win32kbase!?vClearIncludeSprites@SURFACE@@SAXXZ` at `0x140061d01`
- `WIN32K!W32GetUserSessionState` at `0x1400620aa`
- `WIN32K!W32GetUserSessionState` at `0x1400620f9`
- `WIN32K!W32GetUserSessionState` at `0x1400620aa`
- `WIN32K!W32GetUserSessionState` at `0x1400620f9`

## pseudocode

```c
__int64 __fastcall GrepStretchBlt(
        struct SURFACE **a1,
        LONG x,
        int a3,
        int a4,
        int a5,
        struct SURFACE **a6,
        unsigned int a7,
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
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  Gre::Base *v29; // rcx
  struct Gre::Base::SESSION_GLOBALS *v30; // rax
  char v31; // di
  bool v32; // bl
  struct SURFACE *v33; // rcx
  _QWORD *v34; // rax
  struct Gre::Base::SESSION_GLOBALS *v35; // rax
  struct SURFACE *v36; // rcx
  struct SURFACE *v37; // rbx
  Gre::Base *v38; // rcx
  DC *v39; // r9
  Gre::Base *v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  struct Gre::Base::SESSION_GLOBALS *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r13
  __int64 v46; // rbx
  struct Gre::Base::SESSION_GLOBALS *v47; // rdi
  Gre::Base *v48; // rcx
  struct Gre::Base::SESSION_GLOBALS *v49; // rax
  struct SURFACE *v50; // rdx
  struct SURFACE *v51; // rcx
  __int64 v52; // rbx
  __int64 v53; // r8
  Gre::Base *v54; // rcx
  __int64 v55; // r12
  __int64 v56; // rcx
  int v57; // edx
  bool v58; // zf
  Gre::Base *v59; // rcx
  __int64 v60; // rax
  int v61; // edx
  struct Gre::Base::SESSION_GLOBALS *v62; // rdx
  __int64 v63; // r8
  unsigned int v64; // r11d
  unsigned int j; // eax
  __int64 v66; // rdx
  int v67; // eax
  __int64 XlateObject; // rax
  Gre::Base *v69; // rcx
  int v70; // r12d
  int v71; // ebx
  LONG y; // r11d
  int v73; // r10d
  int v74; // r9d
  SURFACE *v75; // r12
  unsigned int v76; // r15d
  LONG v77; // r8d
  LONG v78; // edx
  int v79; // r9d
  struct SURFACE *v80; // rbx
  unsigned int v81; // ebx
  struct OPTAPIDCOBJ *v82; // rbx
  unsigned int v83; // eax
  __int64 v85; // rax
  ULONG v86; // ecx
  struct Gre::Base::SESSION_GLOBALS *v87; // r12
  struct SURFACE *v88; // rdx
  __int64 v89; // r8
  unsigned int i; // ecx
  __int64 v91; // rax
  __int64 v92; // rdx
  int v93; // eax
  __int64 v94; // rdx
  int v95; // eax
  __int64 v96; // rdx
  int v97; // eax
  struct OPTAPIDCOBJ *v98; // rbx
  struct SURFACE *v99; // rax
  struct SURFACE *v100; // rax
  __int64 v101; // rcx
  char v102; // bl
  __int64 v103; // rcx
  struct SURFACE *v104; // rcx
  char *v105; // r9
  int v106; // r10d
  __int64 v107; // rcx
  __int64 v108; // rcx
  HSEMAPHORE v109; // rbx
  __int64 v110; // rcx
  __int64 v111; // rcx
  struct SURFACE *v112; // rcx
  SURFACE *v113; // rbx
  __int64 v114; // rcx
  __int64 v115; // rcx
  struct SURFACE *v116; // rdx
  __int64 v117; // r8
  int v118; // ecx
  __int64 v119; // rax
  SURFACE *v120; // rcx
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // r9
  __int64 v124; // rbx
  int v125; // eax
  int v126; // [rsp+50h] [rbp-B0h]
  unsigned int v127; // [rsp+58h] [rbp-A8h]
  int v128; // [rsp+58h] [rbp-A8h]
  unsigned int v129; // [rsp+5Ch] [rbp-A4h]
  int v130; // [rsp+60h] [rbp-A0h]
  BOOL v131; // [rsp+64h] [rbp-9Ch]
  unsigned int v132; // [rsp+68h] [rbp-98h]
  unsigned int v133; // [rsp+6Ch] [rbp-94h]
  __int64 v134; // [rsp+70h] [rbp-90h] BYREF
  int v135; // [rsp+78h] [rbp-88h]
  struct SURFACE *v136; // [rsp+80h] [rbp-80h]
  __int64 v137; // [rsp+88h] [rbp-78h] BYREF
  int v138; // [rsp+90h] [rbp-70h]
  int v139; // [rsp+94h] [rbp-6Ch]
  int v140; // [rsp+98h] [rbp-68h]
  LONG v141; // [rsp+9Ch] [rbp-64h]
  int v142; // [rsp+A0h] [rbp-60h]
  __int64 v143; // [rsp+A8h] [rbp-58h]
  struct OPTAPIDCOBJ *v144; // [rsp+B0h] [rbp-50h]
  __int64 v145; // [rsp+B8h] [rbp-48h]
  struct Gre::Base::SESSION_GLOBALS *v146; // [rsp+C0h] [rbp-40h]
  unsigned int v147; // [rsp+C8h] [rbp-38h]
  unsigned int v148; // [rsp+CCh] [rbp-34h]
  struct Gre::Base::SESSION_GLOBALS *v149; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v150; // [rsp+D8h] [rbp-28h]
  struct SURFACE *v151; // [rsp+E0h] [rbp-20h] BYREF
  int v152; // [rsp+E8h] [rbp-18h]
  struct SURFACE *v153; // [rsp+F0h] [rbp-10h]
  __int64 v154; // [rsp+F8h] [rbp-8h]
  _OWORD v155[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v156[2]; // [rsp+120h] [rbp+20h] BYREF
  char v157; // [rsp+140h] [rbp+40h]
  __int64 v158; // [rsp+148h] [rbp+48h]
  DC *v159; // [rsp+150h] [rbp+50h] BYREF
  int v160; // [rsp+158h] [rbp+58h]
  struct SURFACE *v161; // [rsp+160h] [rbp+60h]
  __int64 v162; // [rsp+168h] [rbp+68h]
  _OWORD v163[2]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v164[2]; // [rsp+190h] [rbp+90h] BYREF
  char v165; // [rsp+1B0h] [rbp+B0h]
  __int64 v166; // [rsp+1C0h] [rbp+C0h] BYREF
  int v167; // [rsp+1C8h] [rbp+C8h]
  __int64 v168; // [rsp+1D0h] [rbp+D0h]
  __int64 v169; // [rsp+1D8h] [rbp+D8h]
  _BYTE v170[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v171[32]; // [rsp+200h] [rbp+100h] BYREF
  char v172; // [rsp+220h] [rbp+120h]
  __int64 v173; // [rsp+228h] [rbp+128h]
  _BYTE v174[80]; // [rsp+230h] [rbp+130h] BYREF
  int v175; // [rsp+280h] [rbp+180h]
  HSEMAPHORE v176; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v177; // [rsp+3A8h] [rbp+2A8h]
  struct MATRIX *inited; // [rsp+3B0h] [rbp+2B0h] BYREF
  struct MATRIX *v179; // [rsp+3B8h] [rbp+2B8h]
  __int64 v180; // [rsp+3C0h] [rbp+2C0h]
  Gre::Base *v181; // [rsp+3C8h] [rbp+2C8h]
  __int64 v182; // [rsp+3D0h] [rbp+2D0h]
  __int64 v183; // [rsp+3D8h] [rbp+2D8h]
  struct SURFACE *v184; // [rsp+3E0h] [rbp+2E0h]
  __int64 v185; // [rsp+3E8h] [rbp+2E8h]
  __int64 v186; // [rsp+3F0h] [rbp+2F0h]
  char *v187; // [rsp+3F8h] [rbp+2F8h]
  __int64 v188; // [rsp+400h] [rbp+300h]
  struct _POINTFIX v189; // [rsp+410h] [rbp+310h] BYREF
  struct _POINTL v190; // [rsp+430h] [rbp+330h] BYREF
  int v191; // [rsp+438h] [rbp+338h]
  LONG v192; // [rsp+43Ch] [rbp+33Ch]
  LONG v193; // [rsp+440h] [rbp+340h]
  int v194; // [rsp+444h] [rbp+344h]
  unsigned int v195; // [rsp+448h] [rbp+348h] BYREF
  int v196; // [rsp+44Ch] [rbp+34Ch]
  unsigned int v197; // [rsp+450h] [rbp+350h]
  unsigned int v198; // [rsp+454h] [rbp+354h]
  __int64 v199; // [rsp+468h] [rbp+368h]
  unsigned int v200; // [rsp+470h] [rbp+370h]
  int v201; // [rsp+474h] [rbp+374h]

  v14 = 0;
  v141 = a3;
  v135 = a4;
  v142 = a5;
  v144 = (struct OPTAPIDCOBJ *)a6;
  v186 = 0;
  v201 = 0;
  v17 = a11 & ((a11 & 0x40000000) != 0 ? 0x3FFFFFFF : 0x7FFFFFFF);
  v131 = (a11 & 0x40000000) != 0;
  v200 = ((v17 >> 8) | v17 & 0xFF0000) >> 8;
  v19 = *((unsigned __int8 *)gajRop3 + ((unsigned __int64)v200 >> 8));
  v130 = v19 | *((unsigned __int8 *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8));
  v20 = ((unsigned __int8)v19 | *((_BYTE *)gajRop3 + (unsigned __int8)((unsigned __int16)(v17 >> 8) >> 8))) & 0xD4;
  v126 = v20;
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
    v153 = a6[2];
    v154 = 0;
    v151 = 0;
    memset(v155, 0, sizeof(v155));
    v152 = 0;
    PushThreadGuardedObject(
      v155,
      &v151,
      UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
    memset(v156, 0, sizeof(v156));
    PushThreadGuardedObject(
      v156,
      &v151,
      UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
    v151 = *a6;
    v157 = 0;
    bSpDwmValidateSurface((struct XDCOBJ *)&v151, a7, a8, a9, a10);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v151);
  }
  v161 = a6[2];
  v162 = 0;
  v159 = 0;
  memset(v163, 0, sizeof(v163));
  v160 = 0;
  PushThreadGuardedObject(
    v163,
    &v159,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v164, 0, sizeof(v164));
  PushThreadGuardedObject(
    v164,
    &v159,
    UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v21 = *a1;
  v22 = *a6;
  v165 = 0;
  v159 = v22;
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
  DEVLOCKBLTOBJ::DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v174);
  if ( v20 )
  {
    DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v174, (struct XDCOBJ *)a1, (struct XDCOBJ *)&v159);
    Gre::Base::Globals(v24);
  }
  else
  {
    DEVLOCKBLTOBJ::bLock((DEVLOCKBLTOBJ *)v174, (struct XDCOBJ *)a1);
  }
  v25 = 1;
  if ( (v175 & 1) == 0 )
  {
    EngSetLastError(8u);
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v174, v121, v122, v123);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v159);
LABEL_164:
    v25 = 0;
    goto LABEL_135;
  }
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v29 = (Gre::Base *)*((_QWORD *)*a1 + 6);
    if ( (*((_DWORD *)v29 + 10) & 0x8000) != 0 )
    {
      v146 = Gre::Base::Globals(v29);
      GreAcquireSemaphoreShared<1,>(v146);
      v30 = v146;
      LOBYTE(v27) = 1;
    }
    else
    {
      v30 = Gre::Base::Globals(v29);
      LOBYTE(v27) = 0;
    }
    if ( v159
      && *((_QWORD *)v159 + 62)
      && ((v26 = *((unsigned int *)v159 + 9), (v26 & 0x1000) == 0) || (v26 & 0x4000) != 0) )
    {
      v31 = 1;
      v32 = (v175 & 0x800000) != 0;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v14 = *((_BYTE *)v159 + 36) & 1;
    if ( (_BYTE)v27 )
      GreReleaseSemaphoreShared<1,>(v30);
  }
  else
  {
    v31 = 0;
    v32 = 0;
  }
  v33 = *a1;
  if ( *a1
    && (v34 = (_QWORD *)((char *)v33 + 496), *((_QWORD *)v33 + 62))
    && ((v26 = *((unsigned int *)v33 + 9), (v26 & 0x1000) == 0) || (v26 & 0x4000) != 0) )
  {
    if ( !v31 )
      goto LABEL_98;
    if ( v32 )
      goto LABEL_29;
  }
  else
  {
    v34 = (_QWORD *)((char *)v33 + 496);
  }
  if ( !*v34 || !v31 )
  {
LABEL_98:
    if ( (*((_DWORD *)v33 + 9) & 0xE0) != 0 )
    {
      DC::QuickInitXform(v33, &v137, 516);
      v77 = v141;
      v78 = x + v135;
      v79 = v141 + v142;
      v80 = *a1;
      LODWORD(v177) = x + v135;
      HIDWORD(v177) = v141 + v142;
      v176 = (HSEMAPHORE)__PAIR64__(v141, x);
      if ( (*(_BYTE *)(v137 + 32) & 0x43) == 0x43 )
      {
LABEL_102:
        if ( (*(_DWORD *)(*((_QWORD *)v80 + 122) + 108LL) & 1) != 0 )
        {
          ++x;
          ++v78;
          LODWORD(v176) = x;
          LODWORD(v177) = v78;
        }
        if ( x > v78 )
        {
          LODWORD(v176) = v78;
          LODWORD(v177) = x;
        }
        if ( v77 > v79 )
        {
          HIDWORD(v176) = v79;
          HIDWORD(v177) = v77;
        }
        XDCOBJ::vAccumulate((XDCOBJ *)a1, (struct ERECTL *)&v176);
        goto LABEL_109;
      }
      if ( (unsigned int)bCvtPts1(v137, &v176, 2) )
      {
        v79 = HIDWORD(v177);
        v78 = v177;
        v77 = HIDWORD(v176);
        x = (int)v176;
        goto LABEL_102;
      }
    }
LABEL_109:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v174, v26, v27, v28);
LABEL_110:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v159);
LABEL_135:
    BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
    return v25;
  }
  if ( !v14 )
    goto LABEL_134;
LABEL_29:
  if ( v126 && (v175 & 0x400000) == 0 )
    goto LABEL_132;
  v35 = Gre::Base::Globals(v33);
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
    v86 = 5;
LABEL_133:
    EngSetLastError(v86);
LABEL_134:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v174, v26, v27, v28);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v159);
    v25 = 0;
    goto LABEL_135;
  }
  if ( (unsigned __int8)v200 != BYTE1(v200) || (a11 & 0x40000000) != 0 && !OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v86 = 87;
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
    v124 = *(_QWORD *)(*((_QWORD *)v39 + 122) + 308LL);
    v133 = DC::dwSetLayout(v39, -1, 0);
    x = v124 - v135 - x;
    v132 = 0x80000000;
  }
  else
  {
    v133 = 0;
    v132 = 0;
  }
  Gre::Base::Globals(v38);
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v43 = Gre::Base::Globals(v40);
    v44 = (__int64)v159;
    v45 = *((_QWORD *)v159 + 62);
    if ( v45 )
    {
      if ( v162 )
        v45 = v162;
    }
    else
    {
      v45 = *((_QWORD *)v43 + 547);
    }
    v46 = *(_QWORD *)(v45 + 48);
  }
  else
  {
    v44 = (__int64)v159;
    v45 = 0;
    v46 = 0;
  }
  LODWORD(v47) = 0;
  v145 = v46;
  v146 = 0;
  if ( (a11 & 0x40000000) != 0 )
  {
    if ( (*(_DWORD *)(v44 + 36) & 1) != 0 && (v108 = *(_QWORD *)(v44 + 48), (*(_DWORD *)(v108 + 40) & 0x80u) == 0) )
    {
      v41 = (__int64)*a1;
      if ( v108 == *((_QWORD *)*a1 + 6) )
      {
        v75 = 0;
      }
      else
      {
        v125 = XDCOBJ::bRedirHooked((XDCOBJ *)a1);
        v44 = (__int64)v159;
        v75 = 0;
        if ( !v125 )
          goto LABEL_184;
        v41 = (__int64)*a1;
        if ( *((_QWORD *)v159 + 6) != *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) )
          goto LABEL_184;
      }
      if ( v46 )
      {
        v136 = 0;
        if ( v126 )
        {
          if ( (*(_DWORD *)(v44 + 36) & 0x4000) != 0 )
          {
            v120 = *(SURFACE **)(v44 + 496);
            if ( v120 != *(SURFACE **)(v41 + 496) )
            {
              v136 = *(struct SURFACE **)(v44 + 496);
              SURFACE::bUnMap(v120);
              v46 = v145;
            }
          }
        }
        if ( (*((_DWORD *)*a1 + 9) & 0x4000) != 0 )
        {
          v75 = (SURFACE *)*((_QWORD *)*a1 + 62);
          SURFACE::bUnMap(v75);
        }
        v109 = *(HSEMAPHORE *)(v46 + 56);
        EtwTraceGreLockAcquireSemaphoreExclusive(L"Pointer", v109, 0);
        GreAcquireSemaphoreInternal(v109);
        GrepAcquireLockValidate<4>();
        v47 = *(struct Gre::Base::SESSION_GLOBALS **)(v145 + 64);
        v146 = v47;
        UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v176);
        if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v110) + 36124) )
          GreMovePointer(*(_QWORD *)(v45 + 48), 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
        SURFACE::vSetIncludeSprites();
        v111 = v177;
        if ( v177 )
        {
          *(_DWORD *)(v177 + 340) = (_DWORD)v176;
          *(_DWORD *)(v111 + 344) = HIDWORD(v176);
        }
        GrepStretchReMapSurface((struct XDCOBJ *)a1, v75);
        GrepStretchReMapSurface((struct XDCOBJ *)&v159, v136);
        v44 = (__int64)v159;
        v75 = 0;
LABEL_185:
        if ( (*(_DWORD *)(v44 + 44) & 1) != 0 || (*((_DWORD *)*a1 + 11) & 1) != 0 )
          goto LABEL_93;
        goto LABEL_48;
      }
    }
    else
    {
      v75 = 0;
    }
LABEL_184:
    v131 = 0;
    goto LABEL_185;
  }
LABEL_48:
  v134 = 0;
  inited = DC::InitXform(*a1, 0x204u);
  v49 = Gre::Base::Globals(v48);
  v50 = *a1;
  v51 = (struct SURFACE *)*((_QWORD *)*a1 + 62);
  if ( v51 )
  {
    if ( a1[3] )
      v51 = a1[3];
  }
  else
  {
    v51 = (struct SURFACE *)*((_QWORD *)v49 + 547);
  }
  v184 = v51;
  v180 = *((_QWORD *)v51 + 20);
  v181 = (Gre::Base *)*((_QWORD *)v50 + 11);
  if ( OPTAPIDCOBJ::bValid(v144) )
  {
    v179 = DC::InitXform(v159, 0x204u);
    v185 = v45;
    v52 = *(_QWORD *)(v45 + 160);
    v182 = v52;
    v143 = *((_QWORD *)v159 + 11);
    v183 = v143;
    v129 = a12;
    if ( a12 == -1 )
      v129 = *(_DWORD *)(*((_QWORD *)v159 + 122) + 180LL);
  }
  else
  {
    v52 = v182;
    v129 = a12;
    v143 = v183;
  }
  if ( (a13 & 1) != 0 )
  {
    v53 = *(_QWORD *)(*((_QWORD *)*a1 + 122) + 248LL);
    v134 = v53;
  }
  else
  {
    v53 = v134;
  }
  v54 = v181;
  v55 = v180;
  v136 = v181;
  v137 = v180;
  if ( !v52 )
  {
    if ( v180 )
    {
      if ( (*(_DWORD *)(v180 + 24) & 0x800) == 0 )
        goto LABEL_64;
      v119 = *((_QWORD *)v181 + 10);
      if ( v119 )
      {
        if ( v119 != *((_QWORD *)v181 + 9) )
          goto LABEL_64;
      }
    }
    goto LABEL_127;
  }
  if ( v180 )
  {
    v56 = v52;
    if ( *(_QWORD *)(v52 + 120) != v52 )
      v56 = *(_QWORD *)(v52 + 120);
    v57 = *(_DWORD *)(v56 + 32);
    v54 = (Gre::Base *)v180;
    if ( *(_QWORD *)(v180 + 120) != v180 )
      v54 = *(Gre::Base **)(v180 + 120);
    v58 = v57 == *((_DWORD *)v54 + 8);
LABEL_63:
    if ( !v58 )
      goto LABEL_64;
LABEL_127:
    v187 = (char *)Gre::Base::Globals(v54) + 4664;
    goto LABEL_79;
  }
  if ( (*(_DWORD *)(v52 + 24) & 0x800) != 0 )
  {
    v85 = *((_QWORD *)v181 + 10);
    if ( !v85 )
      goto LABEL_127;
    v58 = v85 == *((_QWORD *)v181 + 9);
    goto LABEL_63;
  }
LABEL_64:
  v59 = *a1;
  v60 = *((_QWORD *)*a1 + 122);
  v61 = *(_DWORD *)(v60 + 176);
  v139 = *(_DWORD *)(v60 + 184);
  LODWORD(v60) = *((_DWORD *)v59 + 30);
  v138 = v61;
  v148 = v60;
  if ( (v60 & 7) != 0 && v53 )
  {
    v140 = 0;
    goto LABEL_76;
  }
  v140 = 1;
  if ( !v52 || !v180 )
  {
LABEL_76:
    XlateObject = CreateXlateObject(v134, v148, v52, v55, v143, v136, v139, v61, v129, 0);
    v187 = (char *)XlateObject;
    if ( XlateObject )
    {
      if ( v140 && v52 && v55 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
      {
        v87 = Gre::Base::Globals(v69);
        v134 = *(_QWORD *)v87 + 312LL;
        GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
        for ( i = 0; i < 8; ++i )
        {
          v89 = *((unsigned int *)v87 + 1164);
          v91 = 32 * v89;
          v88 = (struct SURFACE *)*((_QWORD *)v87 + 4 * v89 + 551);
          if ( !v88 )
            goto LABEL_143;
          if ( !*(_DWORD *)((char *)v87 + v91 + 4400) )
          {
            FreeThreadBufferWithTag(*(_QWORD *)((char *)v87 + v91 + 4408));
LABEL_143:
            PopThreadGuardedObject(v187 - 32);
            v92 = v52;
            *((_DWORD *)v87 + 8 * *((unsigned int *)v87 + 1164) + 1100) = 1;
            *((_QWORD *)v87 + 4 * *((unsigned int *)v87 + 1164) + 551) = v187;
            if ( *(_QWORD *)(v52 + 120) != v52 )
              v92 = *(_QWORD *)(v52 + 120);
            v93 = *(_DWORD *)(v92 + 32);
            v94 = v137;
            *((_DWORD *)v87 + 8 * *((unsigned int *)v87 + 1164) + 1104) = v93;
            if ( *(_QWORD *)(v94 + 120) != v94 )
              v94 = *(_QWORD *)(v94 + 120);
            v95 = *(_DWORD *)(v94 + 32);
            v96 = v143;
            *((_DWORD *)v87 + 8 * *((unsigned int *)v87 + 1164) + 1105) = v95;
            if ( *(_QWORD *)(v96 + 120) != v96 )
              v96 = *(_QWORD *)(v96 + 120);
            v97 = *(_DWORD *)(v96 + 32);
            v88 = v136;
            *((_DWORD *)v87 + 8 * *((unsigned int *)v87 + 1164) + 1106) = v97;
            if ( *((struct SURFACE **)v88 + 15) != v88 )
              v88 = (struct SURFACE *)*((_QWORD *)v88 + 15);
            *((_DWORD *)v87 + 8 * *((unsigned int *)v87 + 1164) + 1107) = *((_DWORD *)v88 + 8);
            *((_DWORD *)v187 + 9) = *((_DWORD *)v87 + 1164);
            *(_DWORD *)(v52 + 56) = *((_DWORD *)v87 + 1164);
            *((_DWORD *)v87 + 1164) = ((unsigned __int8)*((_DWORD *)v87 + 1164) + 1) & 7;
            break;
          }
          *((_DWORD *)v87 + 1164) = ((_BYTE)v89 + 1) & 7;
        }
        SEMOBJ<13>::vUnlock(&v134, v88, v89);
      }
      goto LABEL_79;
    }
    goto LABEL_92;
  }
  v147 = *(_DWORD *)(v52 + 56);
  v149 = Gre::Base::Globals(v59);
  v176 = (HSEMAPHORE)(*(_QWORD *)v149 + 312LL);
  GreAcquireSemaphoreInternal(v176);
  GrepAcquireLockValidate<13>();
  v64 = v147;
  for ( j = 0; ; j = v127 + 1 )
  {
    v127 = j;
    if ( j >= 8 )
    {
      v187 = 0;
      v128 = 0;
      goto LABEL_74;
    }
    v66 = v52;
    v63 = v64;
    if ( *(_QWORD *)(v52 + 120) != v52 )
      v66 = *(_QWORD *)(v52 + 120);
    v67 = *(_DWORD *)(v66 + 32);
    v62 = v149;
    if ( *((_DWORD *)v149 + 8 * v64 + 1104) != v67 )
      goto LABEL_72;
    v103 = v55;
    if ( *(_QWORD *)(v55 + 120) != v55 )
      v103 = *(_QWORD *)(v55 + 120);
    v63 = 32LL * v64;
    if ( *(_DWORD *)((char *)v149 + v63 + 4420) != *(_DWORD *)(v103 + 32) )
      goto LABEL_72;
    v104 = v136;
    if ( *((struct SURFACE **)v136 + 15) != v136 )
      v104 = (struct SURFACE *)*((_QWORD *)v136 + 15);
    if ( *(_DWORD *)((char *)v149 + v63 + 4428) != *((_DWORD *)v104 + 8) )
      goto LABEL_72;
    v105 = *(char **)((char *)v149 + v63 + 4408);
    v187 = v105;
    if ( (*((_DWORD *)v105 + 19) & 0x6000) != 0 )
      goto LABEL_72;
    v106 = *((_DWORD *)v105 + 19) & 0x100;
    if ( (*((_DWORD *)v105 + 1) & 4) != 0 )
      break;
    if ( !v106 )
      goto LABEL_181;
LABEL_179:
    if ( v139 == *((_DWORD *)v105 + 7) && v138 == *((_DWORD *)v105 + 8) )
      goto LABEL_181;
LABEL_72:
    v64 = ((_BYTE)v64 + 1) & 7;
  }
  if ( v129 != *((_DWORD *)v105 + 6) )
    goto LABEL_178;
  v107 = v143;
  if ( *(_QWORD *)(v143 + 120) != v143 )
    v107 = *(_QWORD *)(v143 + 120);
  if ( *(_DWORD *)((char *)v149 + v63 + 4424) != *(_DWORD *)(v107 + 32) )
  {
LABEL_178:
    if ( !v106 )
      goto LABEL_72;
    goto LABEL_179;
  }
LABEL_181:
  _InterlockedAdd((volatile signed __int32 *)((char *)v149 + v63 + 4400), 1u);
  *(_DWORD *)(v52 + 56) = v64;
  v128 = 1;
LABEL_74:
  SEMOBJ<13>::vUnlock(&v176, v62, v63);
  if ( !v128 )
  {
    v61 = v138;
    goto LABEL_76;
  }
LABEL_79:
  v201 |= 2u;
  if ( (v130 & 0xE8) != 0 )
  {
    v116 = *a1;
    v188 = (__int64)*a1 + 1200;
    v117 = *((_QWORD *)v116 + 122);
    v118 = *(_DWORD *)(v117 + 152);
    if ( (v118 & 1) != 0 || (*((_DWORD *)v116 + 79) & 1) != 0 )
    {
      *(_DWORD *)(v117 + 152) = v118 & 0xFFFFFFFE;
      *((_DWORD *)*a1 + 79) &= ~1u;
      EBRUSHOBJ::vInitBrush(v188, *a1, *((_QWORD *)*a1 + 17), v181, v180, v184, 1);
    }
    v199 = *((_QWORD *)*a1 + 149);
  }
  else
  {
    v188 = 0;
  }
  v186 = 0;
  if ( (*((_BYTE *)v179 + 32) & 1) == 0 )
    goto LABEL_91;
  v42 = a7;
  v70 = a8;
  v41 = a7 + a9;
  v44 = (unsigned int)(a8 + a10);
  v197 = a7 + a9;
  v198 = a8 + a10;
  v195 = a7;
  v196 = a8;
  if ( (*((_BYTE *)v179 + 32) & 0x43) == 0x43 )
  {
LABEL_85:
    v71 = v126;
    if ( v126 && (v70 == (_DWORD)v44 || (_DWORD)v42 == (_DWORD)v41) )
    {
      v76 = 1;
      v75 = 0;
      goto LABEL_121;
    }
    y = v141;
    v73 = x + v135;
    v74 = v141 + v142;
    v58 = (*((_BYTE *)inited + 32) & 1) == 0;
    v190.x = x;
    v190.y = v141;
    v191 = x + v135;
    if ( v58 )
    {
      v194 = v141 + v142;
      v192 = v141;
      v193 = x;
      EXFORMOBJ::bXform((EXFORMOBJ *)&inited, &v190, &v189, 3u);
      APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v166, v144);
      v100 = *a1;
      v75 = 0;
      v173 = v45;
      v154 = 0;
      v151 = 0;
      v101 = *((_QWORD *)v100 + 122);
      v153 = a1[2];
      v152 = 0;
      v102 = *(_BYTE *)(v101 + 215);
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v155);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v156);
      v151 = *a1;
      v157 = 0;
      v158 = 0;
      v83 = BLTRECORD::bRotate(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v151,
              (struct BLTRECORD::PROXYDCOBJ *)&v166,
              v130,
              v102);
    }
    else
    {
      v192 = v141 + v142;
      if ( (*((_BYTE *)inited + 32) & 0x43) == 0x43 )
      {
        v81 = a7;
      }
      else
      {
        if ( !(unsigned int)bCvtPts1(inited, &v190, 2) )
          goto LABEL_91;
        LODWORD(v44) = v198;
        LODWORD(v41) = v197;
        v70 = v196;
        v81 = v195;
        v74 = v192;
        v73 = v191;
        y = v190.y;
        x = v190.x;
      }
      if ( *(_BYTE *)(*((_QWORD *)*a1 + 122) + 215LL) == 4
        || (_DWORD)v41 - v81 != v73 - x
        || (_DWORD)v44 - v70 != v74 - y )
      {
        v98 = v144;
        v75 = 0;
        v169 = 0;
        v166 = 0;
        v168 = *((_QWORD *)v144 + 2);
        v167 = 0;
        UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v170);
        UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v171);
        v166 = *(_QWORD *)v98;
        v99 = *a1;
        v172 = 0;
        v173 = v45;
        v76 = BLTRECORD::bStretch(
                (BLTRECORD *)&inited,
                (struct XDCOBJ *)a1,
                (struct BLTRECORD::PROXYDCOBJ *)&v166,
                v130,
                *(_BYTE *)(*((_QWORD *)v99 + 122) + 215LL));
        goto LABEL_119;
      }
      v82 = v144;
      v75 = 0;
      v169 = 0;
      v166 = 0;
      v168 = *((_QWORD *)v144 + 2);
      v167 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v170);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v171);
      v166 = *(_QWORD *)v82;
      v153 = a1[2];
      v172 = 0;
      v173 = v45;
      v154 = 0;
      v151 = 0;
      v152 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v155);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v156);
      v151 = *a1;
      v157 = 0;
      v158 = 0;
      v83 = BLTRECORD::bBitBlt(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v151,
              (struct BLTRECORD::PROXYDCOBJ *)&v166,
              v130);
    }
    v76 = v83;
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v151);
LABEL_119:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v166);
    goto LABEL_120;
  }
  if ( (unsigned int)bCvtPts1(v179, &v195, 2) )
  {
    v42 = v195;
    v44 = v198;
    v41 = v197;
    v70 = v196;
    a7 = v195;
    goto LABEL_85;
  }
LABEL_91:
  EngSetLastError(0x57u);
LABEL_92:
  v75 = 0;
LABEL_93:
  v76 = 0;
LABEL_120:
  v71 = v126;
LABEL_121:
  if ( v132 )
    DC::dwSetLayout(*a1, -1, v133);
  if ( v131 )
  {
    SURFACE::vClearIncludeSprites();
    if ( v71
      && (*((_DWORD *)v159 + 11) & 1) == 0
      && (*((_DWORD *)v159 + 9) & 0x4000) != 0
      && v45 != *((_QWORD *)*a1 + 62)
      && (*(_DWORD *)(v45 + 144) & 0x800) != 0 )
    {
      v75 = (SURFACE *)*((_QWORD *)v159 + 62);
      SURFACE::bUnMap(v75);
    }
    v112 = *a1;
    v113 = 0;
    if ( (*((_DWORD *)*a1 + 11) & 1) == 0 && (*((_DWORD *)v112 + 9) & 0x4000) != 0 )
    {
      v113 = (SURFACE *)*((_QWORD *)v112 + 62);
      SURFACE::bUnMap(v113);
    }
    UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v149);
    if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v114) + 36124) )
      GreMovePointer(*(_QWORD *)(v45 + 48), (unsigned int)v47, HIDWORD(v146), 0);
    GreReleaseSemaphoreCommon<4,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal, *(_QWORD *)(v145 + 56));
    v115 = v150;
    if ( v150 )
    {
      *(_DWORD *)(v150 + 340) = (_DWORD)v149;
      *(_DWORD *)(v115 + 344) = HIDWORD(v149);
    }
    GrepStretchReMapSurface((struct XDCOBJ *)a1, v113);
    GrepStretchReMapSurface((struct XDCOBJ *)&v159, v75);
  }
  DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v174, v44, v41, v42);
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v159);
  BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
  return v76;
}

```

## disassembly

```asm
0x140060b1c  push    rbp
0x140060b1e  push    rbx
0x140060b1f  push    rsi
0x140060b20  push    rdi
0x140060b21  push    r12
0x140060b23  push    r13
0x140060b25  push    r14
0x140060b27  push    r15
0x140060b29  lea     rbp, [rsp-398h]
0x140060b31  sub     rsp, 498h
0x140060b38  mov     rax, cs:__security_cookie
0x140060b3f  xor     rax, rsp
0x140060b42  mov     [rbp+3D0h+var_50], rax
0x140060b49  mov     r13, [rbp+3D0h+arg_28]
0x140060b50  lea     rdi, gajRop3
0x140060b57  mov     r11d, [rbp+3D0h+arg_20]
0x140060b5e  mov     rsi, rcx
0x140060b61  xor     r12d, r12d
0x140060b64  mov     [rbp+3D0h+var_434], r8d
0x140060b68  mov     r10d, r8d
0x140060b6b  mov     [rsp+4D0h+var_458], r9d
0x140060b70  mov     r15d, edx
0x140060b73  mov     [rbp+3D0h+var_430], r11d
0x140060b77  mov     edx, [rbp+3D0h+arg_50]
0x140060b7d  mov     ecx, edx
0x140060b7f  and     ecx, 40000000h
0x140060b85  mov     [rsp+4D0h+var_468], edx
0x140060b89  mov     eax, ecx
0x140060b8b  mov     [rsp+4D0h+var_464], ecx
0x140060b8f  neg     eax
0x140060b91  mov     [rbp+3D0h+var_420], r13
0x140060b95  mov     eax, r12d
0x140060b98  mov     [rbp+3D0h+var_E0], r12
0x140060b9f  sbb     r8d, r8d
0x140060ba2  mov     [rbp+3D0h+var_5C], r12d
0x140060ba9  and     r8d, 0C0000000h
0x140060bb0  add     r8d, 7FFFFFFFh
0x140060bb7  and     r8d, edx
0x140060bba  test    ecx, ecx
0x140060bbc  mov     ecx, r8d
0x140060bbf  setnz   al
0x140060bc2  and     ecx, 0FF0000h
0x140060bc8  mov     [rsp+4D0h+var_46C], eax
0x140060bcc  mov     eax, r8d
0x140060bcf  shr     eax, 8
0x140060bd2  or      ecx, eax
0x140060bd4  shr     ecx, 8
0x140060bd7  mov     edx, ecx
0x140060bd9  movzx   eax, cl
0x140060bdc  mov     [rbp+3D0h+var_60], edx
0x140060be2  movzx   ecx, byte ptr [rax+rdi]
0x140060be6  mov     eax, edx
0x140060be8  shr     rax, 8
0x140060bec  movzx   eax, byte ptr [rax+rdi]
0x140060bf0  or      ecx, eax
0x140060bf2  mov     ebx, ecx
0x140060bf4  mov     [rsp+4D0h+var_470], ecx
0x140060bf8  and     ebx, 0D4h
0x140060bfe  mov     [rsp+4D0h+var_480], ebx
0x140060c02  jz      loc_140061A5A
0x140060c08  mov     eax, r8d
0x140060c0b  shr     rax, 8
0x140060c0f  movzx   edx, al
0x140060c12  movzx   eax, r8b
0x140060c16  mov     cl, [rax+rdi]
0x140060c19  mov     al, [rdx+rdi]
0x140060c1c  or      al, cl
0x140060c1e  test    al, 2
0x140060c20  jnz     loc_140061958
0x140060c26  mov     rcx, r13; this
0x140060c29  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140060c2e  test    al, al
0x140060c30  jz      loc_140060CD2
0x140060c36  mov     rax, [r13+10h]
0x140060c3a  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140060c41  xorps   xmm0, xmm0
0x140060c44  mov     [rbp+3D0h+var_3E0], rax
0x140060c48  lea     rdx, [rbp+3D0h+var_3F0]
0x140060c4c  mov     [rbp+3D0h+var_3D8], r12
0x140060c50  lea     rcx, [rbp+3D0h+var_3D0]
0x140060c54  mov     [rbp+3D0h+var_3F0], r12
0x140060c58  movups  [rbp+3D0h+var_3D0], xmm0
0x140060c5c  mov     [rbp+3D0h+var_3E8], r12d
0x140060c60  movups  [rbp+3D0h+var_3C0], xmm0
0x140060c64  call    cs:__imp_PushThreadGuardedObject
0x140060c6b  nop     dword ptr [rax+rax+00h]
0x140060c70  xorps   xmm0, xmm0
0x140060c73  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140060c7a  lea     rdx, [rbp+3D0h+var_3F0]
0x140060c7e  lea     rcx, [rbp+3D0h+var_3B0]
0x140060c82  movups  [rbp+3D0h+var_3B0], xmm0
0x140060c86  movups  [rbp+3D0h+var_3A0], xmm0
0x140060c8a  call    cs:__imp_PushThreadGuardedObject
0x140060c91  nop     dword ptr [rax+rax+00h]
0x140060c96  mov     rax, [r13+0]
0x140060c9a  lea     rcx, [rbp+3D0h+var_3F0]; struct XDCOBJ *
0x140060c9e  mov     r9d, [rbp+3D0h+arg_40]; int
0x140060ca5  mov     r8d, [rbp+3D0h+arg_38]; int
0x140060cac  mov     edx, [rbp+3D0h+arg_30]; int
0x140060cb2  mov     [rbp+3D0h+var_3F0], rax
0x140060cb6  mov     eax, [rbp+3D0h+arg_48]
0x140060cbc  mov     dword ptr [rsp+4D0h+var_4B0], eax; int
0x140060cc0  mov     [rbp+3D0h+var_390], r12b
0x140060cc4  call    ?bSpDwmValidateSurface@@YAHAEAVXDCOBJ@@HHHH@Z; bSpDwmValidateSurface(XDCOBJ &,int,int,int,int)
0x140060cc9  lea     rcx, [rbp+3D0h+var_3F0]; this
0x140060ccd  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140060cd2  mov     rax, [r13+10h]
0x140060cd6  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140060cdd  xorps   xmm0, xmm0
0x140060ce0  mov     [rbp+3D0h+var_370], rax
0x140060ce4  lea     rdx, [rbp+3D0h+var_380]
0x140060ce8  mov     [rbp+3D0h+var_368], r12
0x140060cec  lea     rcx, [rbp+3D0h+var_360]
0x140060cf0  mov     [rbp+3D0h+var_380], r12
0x140060cf4  movups  [rbp+3D0h+var_360], xmm0
0x140060cf8  mov     [rbp+3D0h+var_378], r12d
0x140060cfc  movups  [rbp+3D0h+var_350], xmm0
0x140060d03  call    cs:__imp_PushThreadGuardedObject
0x140060d0a  nop     dword ptr [rax+rax+00h]
0x140060d0f  xorps   xmm0, xmm0
0x140060d12  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140060d19  lea     rdx, [rbp+3D0h+var_380]
0x140060d1d  lea     rcx, [rbp+3D0h+var_340]
0x140060d24  movups  [rbp+3D0h+var_340], xmm0
0x140060d2b  movups  [rbp+3D0h+var_330], xmm0
0x140060d32  call    cs:__imp_PushThreadGuardedObject
0x140060d39  nop     dword ptr [rax+rax+00h]
0x140060d3e  mov     rcx, [rsi]
0x140060d41  mov     rax, [r13+0]
0x140060d45  mov     [rbp+3D0h+var_320], r12b
0x140060d4c  mov     [rbp+3D0h+var_380], rax
0x140060d50  test    rcx, rcx
0x140060d53  jz      short loc_140060D82
0x140060d55  bt      dword ptr [rcx+24h], 10h
0x140060d5a  jb      short loc_140060D82
0x140060d5c  mov     rdx, [rcx+3D0h]
0x140060d63  test    dword ptr [rdx+98h], 1000h
0x140060d6d  jz      short loc_140060D82
0x140060d6f  mov     rdx, [rdx+0A0h]
0x140060d76  call    cs:__imp_GreDCSelectBrush
0x140060d7d  nop     dword ptr [rax+rax+00h]
0x140060d82  mov     rax, [rsi]
0x140060d85  test    rax, rax
0x140060d88  jz      loc_1400613BF
0x140060d8e  bt      dword ptr [rax+24h], 10h
0x140060d93  jb      loc_1400613BF
0x140060d99  mov     rcx, r13; this
0x140060d9c  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140060da1  test    al, al
0x140060da3  jz      loc_140061FBB
0x140060da9  lea     rcx, [rbp+3D0h+var_2A0]; this
0x140060db0  call    ??0DEVLOCKBLTOBJ@@QEAA@XZ; DEVLOCKBLTOBJ::DEVLOCKBLTOBJ(void)
0x140060db5  lea     rcx, [rbp+3D0h+var_2A0]; this
0x140060dbc  mov     rdx, rsi; struct XDCOBJ *
0x140060dbf  test    ebx, ebx
0x140060dc1  jz      loc_140061FC8
0x140060dc7  lea     r8, [rbp+3D0h+var_380]; struct XDCOBJ *
0x140060dcb  call    ?bLock@DEVLOCKBLTOBJ@@QEAAHAEAVXDCOBJ@@0@Z; DEVLOCKBLTOBJ::bLock(XDCOBJ &,XDCOBJ &)
0x140060dd0  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060dd7  nop     dword ptr [rax+rax+00h]
0x140060ddc  mov     r14d, 1
0x140060de2  test    byte ptr [rbp+3D0h+var_250], r14b
0x140060de9  jz      loc_140061F82
0x140060def  mov     rcx, r13; this
0x140060df2  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140060df7  test    al, al
0x140060df9  jz      loc_14006194D
0x140060dff  mov     rax, [rsi]
0x140060e02  mov     rcx, [rax+30h]
0x140060e06  test    dword ptr [rcx+28h], 8000h
0x140060e0d  jnz     loc_14006189B
0x140060e13  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060e1a  nop     dword ptr [rax+rax+00h]
0x140060e1f  mov     r8b, r12b
0x140060e22  mov     rcx, [rbp+3D0h+var_380]
0x140060e26  test    rcx, rcx
0x140060e29  jz      loc_1400616AC
0x140060e2f  cmp     [rcx+1F0h], r12
0x140060e36  jz      loc_1400616AC
0x140060e3c  mov     edx, [rcx+24h]
0x140060e3f  bt      edx, 0Ch
0x140060e43  jb      loc_140061FD2
0x140060e49  mov     ebx, [rbp+3D0h+var_250]
0x140060e4f  mov     dil, r14b
0x140060e52  shr     ebx, 17h
0x140060e55  and     bl, r14b
0x140060e58  mov     r12b, [rcx+24h]
0x140060e5c  and     r12b, r14b
0x140060e5f  test    r8b, r8b
0x140060e62  jz      short loc_140060E6C
0x140060e64  mov     rcx, rax
0x140060e67  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x140060e6c  mov     rcx, [rsi]
0x140060e6f  test    rcx, rcx
0x140060e72  jz      loc_1400613E3
0x140060e78  lea     rax, [rcx+1F0h]
0x140060e7f  cmp     qword ptr [rax], 0
0x140060e83  jz      loc_1400613E3
0x140060e89  mov     edx, [rcx+24h]
0x140060e8c  bt      edx, 0Ch
0x140060e90  jb      loc_140061FE1
0x140060e96  test    dil, dil
0x140060e99  jz      loc_1400613F4
0x140060e9f  test    bl, bl
0x140060ea1  jz      loc_1400613EA
0x140060ea7  cmp     [rsp+4D0h+var_480], 0
0x140060eac  jz      short loc_140060EBE
0x140060eae  test    [rbp+3D0h+var_250], 400000h
0x140060eb8  jz      loc_1400616B7
0x140060ebe  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060ec5  nop     dword ptr [rax+rax+00h]
0x140060eca  mov     rcx, [rsi]
0x140060ecd  mov     rcx, [rcx+1F0h]
0x140060ed4  test    rcx, rcx
0x140060ed7  jz      loc_1400614E5
0x140060edd  mov     rax, [rsi+18h]
0x140060ee1  test    rax, rax
0x140060ee4  cmovnz  rcx, rax; struct SURFACE *
0x140060ee8  call    ?DestSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; DestSurfaceAccessCheck(SURFACE *)
0x140060eed  test    eax, eax
0x140060eef  jz      loc_1400616B7
0x140060ef5  mov     eax, [rbp+3D0h+var_60]
0x140060efb  shr     eax, 8
0x140060efe  xor     eax, [rbp+3D0h+var_60]
0x140060f04  test    al, al
0x140060f06  jnz     loc_140061F04
0x140060f0c  mov     r12d, [rsp+4D0h+var_464]
0x140060f11  test    r12d, r12d
0x140060f14  jnz     loc_140061EF4
0x140060f1a  mov     rcx, r13; this
0x140060f1d  xor     ebx, ebx
0x140060f1f  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140060f24  test    al, al
0x140060f26  jz      short loc_140060F2C
0x140060f28  mov     rbx, [r13+60h]
0x140060f2c  cmp     [rsp+4D0h+var_468], 0
0x140060f31  jl      loc_140061FF0
0x140060f37  mov     r9, [rsi]
0x140060f3a  mov     rax, [r9+3D0h]
0x140060f41  mov     edx, [rax+6Ch]
0x140060f44  and     edx, 9
0x140060f47  cmp     dl, 9
0x140060f4a  jz      loc_140062006
0x140060f50  mov     [rsp+4D0h+var_464], 0
0x140060f58  mov     [rsp+4D0h+var_468], 0
0x140060f60  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060f67  nop     dword ptr [rax+rax+00h]
0x140060f6c  mov     rcx, r13; this
0x140060f6f  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x140060f74  test    al, al
0x140060f76  jz      loc_14006204D
0x140060f7c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060f83  nop     dword ptr [rax+rax+00h]
0x140060f88  mov     rdx, [rbp+3D0h+var_380]
0x140060f8c  mov     r13, [rdx+1F0h]
0x140060f93  test    r13, r13
0x140060f96  jz      loc_1400614F1
0x140060f9c  mov     rax, [rbp+3D0h+var_368]
0x140060fa0  test    rax, rax
0x140060fa3  cmovnz  r13, rax
0x140060fa7  mov     rbx, [r13+30h]
0x140060fab  xor     edi, edi
0x140060fad  mov     [rbp+3D0h+var_418], rbx
0x140060fb1  mov     [rbp+3D0h+var_410], rdi
0x140060fb5  test    r12d, r12d
0x140060fb8  jnz     loc_140061B5E
0x140060fbe  mov     ebx, [rsp+4D0h+var_46C]
0x140060fc2  mov     [rsp+4D0h+var_46C], ebx
0x140060fc6  xor     ecx, ecx
0x140060fc8  mov     edx, 204h
0x140060fcd  mov     [rsp+4D0h+var_460], rcx
0x140060fd2  mov     rcx, [rsi]
0x140060fd5  call    cs:__imp_?InitXform@DC@@QEAAPEAUMATRIX@@K@Z; DC::InitXform(ulong)
0x140060fdc  nop     dword ptr [rax+rax+00h]
0x140060fe1  mov     [rbp+3D0h+var_120], rax
0x140060fe8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060fef  nop     dword ptr [rax+rax+00h]
0x140060ff4  mov     rdx, [rsi]
0x140060ff7  mov     rcx, [rdx+1F0h]
0x140060ffe  test    rcx, rcx
0x140061001  jz      loc_14006165A
0x140061007  mov     rax, [rsi+18h]
0x14006100b  test    rax, rax
0x14006100e  cmovnz  rcx, rax
0x140061012  mov     [rbp+3D0h+var_F0], rcx
0x140061019  mov     rax, [rcx+0A0h]
0x140061020  mov     rcx, [rbp+3D0h+var_420]; this
0x140061024  mov     [rbp+3D0h+var_110], rax
0x14006102b  mov     rax, [rdx+58h]
0x14006102f  mov     [rbp+3D0h+var_108], rax
0x140061036  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x14006103b  test    al, al
0x14006103d  jz      loc_140061F36
0x140061043  mov     rcx, [rbp+3D0h+var_380]
0x140061047  mov     edx, 204h
0x14006104c  call    cs:__imp_?InitXform@DC@@QEAAPEAUMATRIX@@K@Z; DC::InitXform(ulong)
0x140061053  nop     dword ptr [rax+rax+00h]
0x140061058  mov     ecx, [rbp+3D0h+arg_58]
0x14006105e  mov     [rbp+3D0h+var_118], rax
0x140061065  mov     rax, [rbp+3D0h+var_380]
  ... truncated ...
```
