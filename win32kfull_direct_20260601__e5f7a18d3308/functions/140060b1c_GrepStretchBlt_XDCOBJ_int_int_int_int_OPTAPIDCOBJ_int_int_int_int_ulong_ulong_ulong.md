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
  unsigned int v62; // r11d
  unsigned int j; // eax
  __int64 v64; // rdx
  __int64 XlateObject; // rax
  Gre::Base *v66; // rcx
  int v67; // r12d
  int v68; // ebx
  LONG y; // r11d
  int v70; // r10d
  int v71; // r9d
  SURFACE *v72; // r12
  unsigned int v73; // r15d
  LONG v74; // r8d
  LONG v75; // edx
  int v76; // r9d
  struct SURFACE *v77; // rbx
  unsigned int v78; // ebx
  struct OPTAPIDCOBJ *v79; // rbx
  unsigned int v80; // eax
  __int64 v82; // rax
  ULONG v83; // ecx
  struct Gre::Base::SESSION_GLOBALS *v84; // r12
  unsigned int i; // ecx
  unsigned int v86; // r8d
  __int64 v87; // rax
  __int64 v88; // rdx
  int v89; // eax
  __int64 v90; // rdx
  int v91; // eax
  __int64 v92; // rdx
  int v93; // eax
  struct SURFACE *v94; // rdx
  struct OPTAPIDCOBJ *v95; // rbx
  struct SURFACE *v96; // rax
  struct SURFACE *v97; // rax
  __int64 v98; // rcx
  char v99; // bl
  __int64 v100; // rcx
  __int64 v101; // r8
  struct SURFACE *v102; // rcx
  char *v103; // r9
  int v104; // r10d
  __int64 v105; // rcx
  __int64 v106; // rcx
  HSEMAPHORE v107; // rbx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rcx
  struct SURFACE *v111; // rcx
  SURFACE *v112; // rbx
  __int64 v113; // rdx
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
  HSEMAPHORE v175; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v176; // [rsp+3A8h] [rbp+2A8h]
  struct MATRIX *inited; // [rsp+3B0h] [rbp+2B0h] BYREF
  struct MATRIX *v178; // [rsp+3B8h] [rbp+2B8h]
  __int64 v179; // [rsp+3C0h] [rbp+2C0h]
  Gre::Base *v180; // [rsp+3C8h] [rbp+2C8h]
  __int64 v181; // [rsp+3D0h] [rbp+2D0h]
  __int64 v182; // [rsp+3D8h] [rbp+2D8h]
  struct SURFACE *v183; // [rsp+3E0h] [rbp+2E0h]
  __int64 v184; // [rsp+3E8h] [rbp+2E8h]
  __int64 v185; // [rsp+3F0h] [rbp+2F0h]
  char *v186; // [rsp+3F8h] [rbp+2F8h]
  __int64 v187; // [rsp+400h] [rbp+300h]
  struct _POINTFIX v188; // [rsp+410h] [rbp+310h] BYREF
  struct _POINTL v189; // [rsp+430h] [rbp+330h] BYREF
  int v190; // [rsp+438h] [rbp+338h]
  LONG v191; // [rsp+43Ch] [rbp+33Ch]
  LONG v192; // [rsp+440h] [rbp+340h]
  int v193; // [rsp+444h] [rbp+344h]
  unsigned int v194; // [rsp+448h] [rbp+348h] BYREF
  int v195; // [rsp+44Ch] [rbp+34Ch]
  unsigned int v196; // [rsp+450h] [rbp+350h]
  unsigned int v197; // [rsp+454h] [rbp+354h]
  __int64 v198; // [rsp+468h] [rbp+368h]
  unsigned int v199; // [rsp+470h] [rbp+370h]
  int v200; // [rsp+474h] [rbp+374h]

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
  DEVLOCKBLTOBJ::DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173);
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
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173, v121, v122, v123);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
LABEL_164:
    v25 = 0;
    goto LABEL_135;
  }
  if ( OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v29 = (Gre::Base *)*((_QWORD *)*a1 + 6);
    if ( (*((_DWORD *)v29 + 10) & 0x8000) != 0 )
    {
      v145 = Gre::Base::Globals(v29);
      GreAcquireSemaphoreShared<1,>(v145);
      v30 = v145;
      LOBYTE(v27) = 1;
    }
    else
    {
      v30 = Gre::Base::Globals(v29);
      LOBYTE(v27) = 0;
    }
    if ( v158
      && *((_QWORD *)v158 + 62)
      && ((v26 = *((unsigned int *)v158 + 9), (v26 & 0x1000) == 0) || (v26 & 0x4000) != 0) )
    {
      v31 = 1;
      v32 = (v174 & 0x800000) != 0;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v14 = *((_BYTE *)v158 + 36) & 1;
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
      DC::QuickInitXform(v33, &v136, 516);
      v74 = v140;
      v75 = x + v134;
      v76 = v140 + v141;
      v77 = *a1;
      LODWORD(v176) = x + v134;
      HIDWORD(v176) = v140 + v141;
      v175 = (HSEMAPHORE)__PAIR64__(v140, x);
      if ( (*(_BYTE *)(v136 + 32) & 0x43) == 0x43 )
      {
LABEL_102:
        if ( (*(_DWORD *)(*((_QWORD *)v77 + 122) + 108LL) & 1) != 0 )
        {
          ++x;
          ++v75;
          LODWORD(v175) = x;
          LODWORD(v176) = v75;
        }
        if ( x > v75 )
        {
          LODWORD(v175) = v75;
          LODWORD(v176) = x;
        }
        if ( v74 > v76 )
        {
          HIDWORD(v175) = v76;
          HIDWORD(v176) = v74;
        }
        XDCOBJ::vAccumulate((XDCOBJ *)a1, (struct ERECTL *)&v175);
        goto LABEL_109;
      }
      if ( (unsigned int)bCvtPts1(v136, &v175, 2) )
      {
        v76 = HIDWORD(v176);
        v75 = v176;
        v74 = HIDWORD(v175);
        x = (int)v175;
        goto LABEL_102;
      }
    }
LABEL_109:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173, v26, v27, v28);
LABEL_110:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
LABEL_135:
    BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
    return v25;
  }
  if ( !v14 )
    goto LABEL_134;
LABEL_29:
  if ( v126 && (v174 & 0x400000) == 0 )
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
    v83 = 5;
LABEL_133:
    EngSetLastError(v83);
LABEL_134:
    DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173, v26, v27, v28);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
    v25 = 0;
    goto LABEL_135;
  }
  if ( (unsigned __int8)v199 != BYTE1(v199) || (a11 & 0x40000000) != 0 && !OPTAPIDCOBJ::bValid((OPTAPIDCOBJ *)a6) )
  {
    v83 = 87;
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
    v132 = DC::dwSetLayout(v39, -1, 0);
    x = v124 - v134 - x;
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
    v43 = Gre::Base::Globals(v40);
    v44 = (__int64)v158;
    v45 = *((_QWORD *)v158 + 62);
    if ( v45 )
    {
      if ( v161 )
        v45 = v161;
    }
    else
    {
      v45 = *((_QWORD *)v43 + 547);
    }
    v46 = *(_QWORD *)(v45 + 48);
  }
  else
  {
    v44 = (__int64)v158;
    v45 = 0;
    v46 = 0;
  }
  LODWORD(v47) = 0;
  v144 = v46;
  v145 = 0;
  if ( (a11 & 0x40000000) != 0 )
  {
    if ( (*(_DWORD *)(v44 + 36) & 1) != 0 && (v106 = *(_QWORD *)(v44 + 48), (*(_DWORD *)(v106 + 40) & 0x80u) == 0) )
    {
      v41 = (__int64)*a1;
      if ( v106 == *((_QWORD *)*a1 + 6) )
      {
        v72 = 0;
      }
      else
      {
        v125 = XDCOBJ::bRedirHooked((XDCOBJ *)a1);
        v44 = (__int64)v158;
        v72 = 0;
        if ( !v125 )
          goto LABEL_184;
        v41 = (__int64)*a1;
        if ( *((_QWORD *)v158 + 6) != *(_QWORD *)(*((_QWORD *)*a1 + 6) + 3512LL) )
          goto LABEL_184;
      }
      if ( v46 )
      {
        v135 = 0;
        if ( v126 )
        {
          if ( (*(_DWORD *)(v44 + 36) & 0x4000) != 0 )
          {
            v120 = *(SURFACE **)(v44 + 496);
            if ( v120 != *(SURFACE **)(v41 + 496) )
            {
              v135 = *(struct SURFACE **)(v44 + 496);
              SURFACE::bUnMap(v120);
              v46 = v144;
            }
          }
        }
        if ( (*((_DWORD *)*a1 + 9) & 0x4000) != 0 )
        {
          v72 = (SURFACE *)*((_QWORD *)*a1 + 62);
          SURFACE::bUnMap(v72);
        }
        v107 = *(HSEMAPHORE *)(v46 + 56);
        EtwTraceGreLockAcquireSemaphoreExclusive(L"Pointer", v107, 0);
        GreAcquireSemaphoreInternal(v107);
        GrepAcquireLockValidate<4>();
        v47 = *(struct Gre::Base::SESSION_GLOBALS **)(v144 + 64);
        v145 = v47;
        UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v175);
        if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v109, v108) + 36124) )
          GreMovePointer(*(_QWORD *)(v45 + 48), 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
        SURFACE::vSetIncludeSprites();
        v110 = v176;
        if ( v176 )
        {
          *(_DWORD *)(v176 + 340) = (_DWORD)v175;
          *(_DWORD *)(v110 + 344) = HIDWORD(v175);
        }
        GrepStretchReMapSurface((struct XDCOBJ *)a1, v72);
        GrepStretchReMapSurface((struct XDCOBJ *)&v158, v135);
        v44 = (__int64)v158;
        v72 = 0;
LABEL_185:
        if ( (*(_DWORD *)(v44 + 44) & 1) != 0 || (*((_DWORD *)*a1 + 11) & 1) != 0 )
          goto LABEL_93;
        goto LABEL_48;
      }
    }
    else
    {
      v72 = 0;
    }
LABEL_184:
    v130 = 0;
    goto LABEL_185;
  }
LABEL_48:
  v133 = 0;
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
  v183 = v51;
  v179 = *((_QWORD *)v51 + 20);
  v180 = (Gre::Base *)*((_QWORD *)v50 + 11);
  if ( OPTAPIDCOBJ::bValid(v143) )
  {
    v178 = DC::InitXform(v158, 0x204u);
    v184 = v45;
    v52 = *(_QWORD *)(v45 + 160);
    v181 = v52;
    v142 = *((_QWORD *)v158 + 11);
    v182 = v142;
    v128 = a12;
    if ( a12 == -1 )
      v128 = *(_DWORD *)(*((_QWORD *)v158 + 122) + 180LL);
  }
  else
  {
    v52 = v181;
    v128 = a12;
    v142 = v182;
  }
  if ( (a13 & 1) != 0 )
  {
    v53 = *(_QWORD *)(*((_QWORD *)*a1 + 122) + 248LL);
    v133 = v53;
  }
  else
  {
    v53 = v133;
  }
  v54 = v180;
  v55 = v179;
  v135 = v180;
  v136 = v179;
  if ( !v52 )
  {
    if ( v179 )
    {
      if ( (*(_DWORD *)(v179 + 24) & 0x800) == 0 )
        goto LABEL_64;
      v119 = *((_QWORD *)v180 + 10);
      if ( v119 )
      {
        if ( v119 != *((_QWORD *)v180 + 9) )
          goto LABEL_64;
      }
    }
    goto LABEL_127;
  }
  if ( v179 )
  {
    v56 = v52;
    if ( *(_QWORD *)(v52 + 120) != v52 )
      v56 = *(_QWORD *)(v52 + 120);
    v57 = *(_DWORD *)(v56 + 32);
    v54 = (Gre::Base *)v179;
    if ( *(_QWORD *)(v179 + 120) != v179 )
      v54 = *(Gre::Base **)(v179 + 120);
    v58 = v57 == *((_DWORD *)v54 + 8);
LABEL_63:
    if ( !v58 )
      goto LABEL_64;
LABEL_127:
    v186 = (char *)Gre::Base::Globals(v54) + 4664;
    goto LABEL_79;
  }
  if ( (*(_DWORD *)(v52 + 24) & 0x800) != 0 )
  {
    v82 = *((_QWORD *)v180 + 10);
    if ( !v82 )
      goto LABEL_127;
    v58 = v82 == *((_QWORD *)v180 + 9);
    goto LABEL_63;
  }
LABEL_64:
  v59 = *a1;
  v60 = *((_QWORD *)*a1 + 122);
  v61 = *(_DWORD *)(v60 + 176);
  v138 = *(_DWORD *)(v60 + 184);
  LODWORD(v60) = *((_DWORD *)v59 + 30);
  v137 = v61;
  v147 = v60;
  if ( (v60 & 7) != 0 && v53 )
  {
    v139 = 0;
    goto LABEL_76;
  }
  v139 = 1;
  if ( !v52 || !v179 )
  {
LABEL_76:
    XlateObject = CreateXlateObject(v133, v147, v52, v55, v142, v135, v138, v61, v128, 0);
    v186 = (char *)XlateObject;
    if ( XlateObject )
    {
      if ( v139 && v52 && v55 && (*(_DWORD *)(XlateObject + 76) & 0x200) == 0 )
      {
        v84 = Gre::Base::Globals(v66);
        v133 = *(_QWORD *)v84 + 312LL;
        GreAcquireSemaphoreCommon<13,void (*)(HSEMAPHORE__ *)>(GreAcquireSemaphoreInternal);
        for ( i = 0; i < 8; ++i )
        {
          v86 = *((_DWORD *)v84 + 1164);
          v87 = 32LL * v86;
          if ( !*(_QWORD *)((char *)v84 + v87 + 4408) )
            goto LABEL_143;
          if ( !*(_DWORD *)((char *)v84 + v87 + 4400) )
          {
            FreeThreadBufferWithTag(*(_QWORD *)((char *)v84 + v87 + 4408));
LABEL_143:
            PopThreadGuardedObject(v186 - 32);
            v88 = v52;
            *((_DWORD *)v84 + 8 * *((unsigned int *)v84 + 1164) + 1100) = 1;
            *((_QWORD *)v84 + 4 * *((unsigned int *)v84 + 1164) + 551) = v186;
            if ( *(_QWORD *)(v52 + 120) != v52 )
              v88 = *(_QWORD *)(v52 + 120);
            v89 = *(_DWORD *)(v88 + 32);
            v90 = v136;
            *((_DWORD *)v84 + 8 * *((unsigned int *)v84 + 1164) + 1104) = v89;
            if ( *(_QWORD *)(v90 + 120) != v90 )
              v90 = *(_QWORD *)(v90 + 120);
            v91 = *(_DWORD *)(v90 + 32);
            v92 = v142;
            *((_DWORD *)v84 + 8 * *((unsigned int *)v84 + 1164) + 1105) = v91;
            if ( *(_QWORD *)(v92 + 120) != v92 )
              v92 = *(_QWORD *)(v92 + 120);
            v93 = *(_DWORD *)(v92 + 32);
            v94 = v135;
            *((_DWORD *)v84 + 8 * *((unsigned int *)v84 + 1164) + 1106) = v93;
            if ( *((struct SURFACE **)v94 + 15) != v94 )
              v94 = (struct SURFACE *)*((_QWORD *)v94 + 15);
            *((_DWORD *)v84 + 8 * *((unsigned int *)v84 + 1164) + 1107) = *((_DWORD *)v94 + 8);
            *((_DWORD *)v186 + 9) = *((_DWORD *)v84 + 1164);
            *(_DWORD *)(v52 + 56) = *((_DWORD *)v84 + 1164);
            *((_DWORD *)v84 + 1164) = ((unsigned __int8)*((_DWORD *)v84 + 1164) + 1) & 7;
            break;
          }
          *((_DWORD *)v84 + 1164) = ((_BYTE)v86 + 1) & 7;
        }
        SEMOBJ<13>::vUnlock(&v133);
      }
      goto LABEL_79;
    }
    goto LABEL_92;
  }
  v146 = *(_DWORD *)(v52 + 56);
  v148 = Gre::Base::Globals(v59);
  v175 = (HSEMAPHORE)(*(_QWORD *)v148 + 312LL);
  GreAcquireSemaphoreInternal(v175);
  GrepAcquireLockValidate<13>();
  v62 = v146;
  for ( j = 0; ; ++j )
  {
    if ( j >= 8 )
    {
      v186 = 0;
      v127 = 0;
      goto LABEL_74;
    }
    v64 = v52;
    if ( *(_QWORD *)(v52 + 120) != v52 )
      v64 = *(_QWORD *)(v52 + 120);
    if ( *((_DWORD *)v148 + 8 * v62 + 1104) != *(_DWORD *)(v64 + 32) )
      goto LABEL_72;
    v100 = v55;
    if ( *(_QWORD *)(v55 + 120) != v55 )
      v100 = *(_QWORD *)(v55 + 120);
    v101 = 32LL * v62;
    if ( *(_DWORD *)((char *)v148 + v101 + 4420) != *(_DWORD *)(v100 + 32) )
      goto LABEL_72;
    v102 = v135;
    if ( *((struct SURFACE **)v135 + 15) != v135 )
      v102 = (struct SURFACE *)*((_QWORD *)v135 + 15);
    if ( *(_DWORD *)((char *)v148 + v101 + 4428) != *((_DWORD *)v102 + 8) )
      goto LABEL_72;
    v103 = *(char **)((char *)v148 + v101 + 4408);
    v186 = v103;
    if ( (*((_DWORD *)v103 + 19) & 0x6000) != 0 )
      goto LABEL_72;
    v104 = *((_DWORD *)v103 + 19) & 0x100;
    if ( (*((_DWORD *)v103 + 1) & 4) != 0 )
      break;
    if ( !v104 )
      goto LABEL_181;
LABEL_179:
    if ( v138 == *((_DWORD *)v103 + 7) && v137 == *((_DWORD *)v103 + 8) )
      goto LABEL_181;
LABEL_72:
    v62 = ((_BYTE)v62 + 1) & 7;
  }
  if ( v128 != *((_DWORD *)v103 + 6) )
    goto LABEL_178;
  v105 = v142;
  if ( *(_QWORD *)(v142 + 120) != v142 )
    v105 = *(_QWORD *)(v142 + 120);
  if ( *(_DWORD *)((char *)v148 + v101 + 4424) != *(_DWORD *)(v105 + 32) )
  {
LABEL_178:
    if ( !v104 )
      goto LABEL_72;
    goto LABEL_179;
  }
LABEL_181:
  _InterlockedAdd((volatile signed __int32 *)((char *)v148 + v101 + 4400), 1u);
  *(_DWORD *)(v52 + 56) = v62;
  v127 = 1;
LABEL_74:
  SEMOBJ<13>::vUnlock(&v175);
  if ( !v127 )
  {
    v61 = v137;
    goto LABEL_76;
  }
LABEL_79:
  v200 |= 2u;
  if ( (v129 & 0xE8) != 0 )
  {
    v116 = *a1;
    v187 = (__int64)*a1 + 1200;
    v117 = *((_QWORD *)v116 + 122);
    v118 = *(_DWORD *)(v117 + 152);
    if ( (v118 & 1) != 0 || (*((_DWORD *)v116 + 79) & 1) != 0 )
    {
      *(_DWORD *)(v117 + 152) = v118 & 0xFFFFFFFE;
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
  v42 = a7;
  v67 = a8;
  v41 = a7 + a9;
  v44 = (unsigned int)(a8 + a10);
  v196 = a7 + a9;
  v197 = a8 + a10;
  v194 = a7;
  v195 = a8;
  if ( (*((_BYTE *)v178 + 32) & 0x43) == 0x43 )
  {
LABEL_85:
    v68 = v126;
    if ( v126 && (v67 == (_DWORD)v44 || (_DWORD)v42 == (_DWORD)v41) )
    {
      v73 = 1;
      v72 = 0;
      goto LABEL_121;
    }
    y = v140;
    v70 = x + v134;
    v71 = v140 + v141;
    v58 = (*((_BYTE *)inited + 32) & 1) == 0;
    v189.x = x;
    v189.y = v140;
    v190 = x + v134;
    if ( v58 )
    {
      v193 = v140 + v141;
      v191 = v140;
      v192 = x;
      EXFORMOBJ::bXform((EXFORMOBJ *)&inited, &v189, &v188, 3u);
      APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v165, v143);
      v97 = *a1;
      v72 = 0;
      v172 = v45;
      v153 = 0;
      v150 = 0;
      v98 = *((_QWORD *)v97 + 122);
      v152 = a1[2];
      v151 = 0;
      v99 = *(_BYTE *)(v98 + 215);
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v154);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v155);
      v150 = *a1;
      v156 = 0;
      v157 = 0;
      v80 = BLTRECORD::bRotate(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v150,
              (struct BLTRECORD::PROXYDCOBJ *)&v165,
              v129,
              v99);
    }
    else
    {
      v191 = v140 + v141;
      if ( (*((_BYTE *)inited + 32) & 0x43) == 0x43 )
      {
        v78 = a7;
      }
      else
      {
        if ( !(unsigned int)bCvtPts1(inited, &v189, 2) )
          goto LABEL_91;
        LODWORD(v44) = v197;
        LODWORD(v41) = v196;
        v67 = v195;
        v78 = v194;
        v71 = v191;
        v70 = v190;
        y = v189.y;
        x = v189.x;
      }
      if ( *(_BYTE *)(*((_QWORD *)*a1 + 122) + 215LL) == 4
        || (_DWORD)v41 - v78 != v70 - x
        || (_DWORD)v44 - v67 != v71 - y )
      {
        v95 = v143;
        v72 = 0;
        v168 = 0;
        v165 = 0;
        v167 = *((_QWORD *)v143 + 2);
        v166 = 0;
        UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v169);
        UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v170);
        v165 = *(_QWORD *)v95;
        v96 = *a1;
        v171 = 0;
        v172 = v45;
        v73 = BLTRECORD::bStretch(
                (BLTRECORD *)&inited,
                (struct XDCOBJ *)a1,
                (struct BLTRECORD::PROXYDCOBJ *)&v165,
                v129,
                *(_BYTE *)(*((_QWORD *)v96 + 122) + 215LL));
        goto LABEL_119;
      }
      v79 = v143;
      v72 = 0;
      v168 = 0;
      v165 = 0;
      v167 = *((_QWORD *)v143 + 2);
      v166 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v169);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v170);
      v165 = *(_QWORD *)v79;
      v152 = a1[2];
      v171 = 0;
      v172 = v45;
      v153 = 0;
      v150 = 0;
      v151 = 0;
      UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v154);
      UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v155);
      v150 = *a1;
      v156 = 0;
      v157 = 0;
      v80 = BLTRECORD::bBitBlt(
              (BLTRECORD *)&inited,
              (struct BLTRECORD::PROXYDCOBJ *)&v150,
              (struct BLTRECORD::PROXYDCOBJ *)&v165,
              v129);
    }
    v73 = v80;
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v150);
LABEL_119:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v165);
    goto LABEL_120;
  }
  if ( (unsigned int)bCvtPts1(v178, &v194, 2) )
  {
    v42 = v194;
    v44 = v197;
    v41 = v196;
    v67 = v195;
    a7 = v194;
    goto LABEL_85;
  }
LABEL_91:
  EngSetLastError(0x57u);
LABEL_92:
  v72 = 0;
LABEL_93:
  v73 = 0;
LABEL_120:
  v68 = v126;
LABEL_121:
  if ( v131 )
    DC::dwSetLayout(*a1, -1, v132);
  if ( v130 )
  {
    SURFACE::vClearIncludeSprites();
    if ( v68
      && (*((_DWORD *)v158 + 11) & 1) == 0
      && (*((_DWORD *)v158 + 9) & 0x4000) != 0
      && v45 != *((_QWORD *)*a1 + 62)
      && (*(_DWORD *)(v45 + 144) & 0x800) != 0 )
    {
      v72 = (SURFACE *)*((_QWORD *)v158 + 62);
      SURFACE::bUnMap(v72);
    }
    v111 = *a1;
    v112 = 0;
    if ( (*((_DWORD *)*a1 + 11) & 1) == 0 && (*((_DWORD *)v111 + 9) & 0x4000) != 0 )
    {
      v112 = (SURFACE *)*((_QWORD *)v111 + 62);
      SURFACE::bUnMap(v112);
    }
    UNDORENDERLOCKCOUNTS::UNDORENDERLOCKCOUNTS((UNDORENDERLOCKCOUNTS *)&v148);
    if ( (a13 & 2) == 0 || !*(_DWORD *)(W32GetUserSessionState(v114, v113) + 36124) )
      GreMovePointer(*(_QWORD *)(v45 + 48), (unsigned int)v47, HIDWORD(v145), 0);
    GreReleaseSemaphoreCommon<4,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal, *(_QWORD *)(v144 + 56));
    v115 = v149;
    if ( v149 )
    {
      *(_DWORD *)(v149 + 340) = (_DWORD)v148;
      *(_DWORD *)(v115 + 344) = HIDWORD(v148);
    }
    GrepStretchReMapSurface((struct XDCOBJ *)a1, v112);
    GrepStretchReMapSurface((struct XDCOBJ *)&v158, v72);
  }
  DEVLOCKBLTOBJ::~DEVLOCKBLTOBJ((DEVLOCKBLTOBJ *)v173, v44, v41, v42);
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v158);
  BLTRECORD::~BLTRECORD((BLTRECORD *)&inited);
  return v73;
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
