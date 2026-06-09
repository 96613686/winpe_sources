# EngStretchBltNew(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong)

- ea: `0x140077920`
- end: `0x140079b3d`
- name: `?EngStretchBltNew@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54K@Z`
- size: `8733`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140077380`

## callees

- `0x140075244`
- `0x140077348`
- `0x140077920`
- `0x140079b44`
- `0x140079b84`
- `0x140079bb0`
- `0x14007a258`
- `0x14007a4e0`
- `0x14007a918`
- `0x14008cfa0`
- `0x1400fc340`
- `0x1401478f0`
- `0x140158f00`
- `0x140161b5c`
- `0x1401acf04`
- `0x1401b3a90`
- `0x140298e04`
- `0x14032a720`
- `0x14032a910`
- `0x14032a980`
- `0x14032aa00`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!Win32AllocPool` at `0x140078453`
- `win32kbase!Win32AllocPool` at `0x140078453`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400787a0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400789fb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140079709`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400787a0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400789fb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140079709`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140077f5d`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140077f7e`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140077f92`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140078ccb`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140078cec`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140077f5d`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140077f7e`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140077f92`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140078ccb`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140078cec`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140079278`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140079626`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140079278`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140079626`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140079007`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400796a0`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14007996c`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14007998a`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140079007`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400796a0`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14007996c`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14007998a`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14007902e`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400796c7`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14007902e`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400796c7`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400799ad`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400799ad`
- `win32kbase!EngLockSurface` at `0x1400780b2`
- `win32kbase!EngLockSurface` at `0x1400780b2`
- `win32kbase!EngUnlockSurface` at `0x14007814e`
- `win32kbase!EngUnlockSurface` at `0x14007814e`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140077c97`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x14007819b`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400796fd`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140077c97`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x14007819b`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400796fd`
- `win32kbase!EngCreateBitmap` at `0x14007809b`
- `win32kbase!EngCreateBitmap` at `0x14007809b`
- `win32kbase!EngDeleteSurface` at `0x140078162`
- `win32kbase!EngDeleteSurface` at `0x140078162`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x1400799fc`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x1400799fc`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400781f8`
- `win32kbase!AllocFreeTmpBuffer` at `0x140078579`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400781f8`
- `win32kbase!AllocFreeTmpBuffer` at `0x140078579`
- `win32kbase!FreeTmpBuffer` at `0x140078b45`
- `win32kbase!FreeTmpBuffer` at `0x140078b7d`
- `win32kbase!FreeTmpBuffer` at `0x140078b45`
- `win32kbase!FreeTmpBuffer` at `0x140078b7d`
- `win32kbase!Win32FreePool` at `0x140078b91`
- `win32kbase!Win32FreePool` at `0x140078d18`
- `win32kbase!Win32FreePool` at `0x140078b91`
- `win32kbase!Win32FreePool` at `0x140078d18`

## pseudocode

```c
__int64 __fastcall EngStretchBltNew(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _CLIPOBJ *a4,
        struct _XLATEOBJ *a5,
        struct tagCOLORADJUSTMENT *a6,
        struct _POINTL *a7,
        struct _RECTL *a8,
        struct _RECTL *a9,
        struct _POINTL *a10,
        unsigned int a11)
{
  struct _RECTL *v12; // r15
  struct _RECTL *v13; // r12
  PVOID *p_pvScan0; // rdx
  stretch *v15; // r14
  int v16; // ecx
  int v17; // eax
  __int64 v18; // rdi
  struct tagCOLORADJUSTMENT *v19; // r8
  __int64 *v20; // r9
  SURFOBJ *v21; // r10
  CLIPOBJ *v22; // r11
  int v23; // edx
  unsigned int v24; // esi
  unsigned int v25; // edx
  __int64 v26; // rax
  unsigned int v27; // ecx
  LONG top; // r8d
  LONG bottom; // eax
  int v30; // r11d
  LONG v31; // r10d
  LONG left; // edx
  LONG right; // eax
  LONG v34; // r9d
  unsigned int v35; // edx
  int v36; // ecx
  LONG v37; // ecx
  LONG v38; // eax
  LONG v39; // r11d
  LONG v40; // r8d
  LONG v41; // r10d
  LONG v42; // r9d
  int v43; // r8d
  int v44; // r9d
  int v45; // r10d
  int v46; // r11d
  unsigned __int64 v47; // rdi
  PVOID *v48; // r13
  int v49; // ecx
  int v50; // edx
  int v51; // ecx
  struct _RECTL *v52; // rax
  LONG v53; // eax
  LONG v54; // ecx
  LONG v55; // edx
  LONG v56; // edi
  LONG v58; // ecx
  int v59; // eax
  LONG v60; // r8d
  LONG v61; // edx
  LONG v62; // edx
  SURFOBJ *v63; // rax
  int v64; // eax
  unsigned int *v65; // r8
  XCLIPOBJ *v66; // rdi
  unsigned int v67; // edx
  struct _RECTL v68; // xmm0
  __int64 i; // rax
  LONG v70; // edi
  LONG v71; // eax
  LONG v72; // edx
  LONG v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // edx
  unsigned int v76; // edx
  struct _RECTL *v77; // rdi
  __m128i v78; // xmm6
  unsigned __int64 v79; // rcx
  __int64 v80; // r9
  unsigned int v81; // r8d
  unsigned int v82; // edi
  __int64 v83; // rax
  unsigned int v84; // r9d
  struct _RECTL *v85; // r11
  LONG v86; // edi
  unsigned int v87; // ecx
  XCLIPOBJ *v88; // rax
  _DWORD *v89; // r11
  int v90; // r8d
  LONG v91; // r9d
  struct _RECTL *v92; // r10
  int v93; // edx
  unsigned __int64 v94; // rdi
  __int64 v95; // rax
  unsigned int v96; // r10d
  LONG v97; // ecx
  unsigned __int64 v98; // r8
  unsigned int *v99; // r9
  LONG v100; // ecx
  LONG v101; // edx
  LONG v102; // eax
  XCLIPOBJ *v103; // rsi
  int v104; // edi
  LONG v105; // ecx
  LONG v106; // edx
  LONG v107; // eax
  int v108; // eax
  unsigned int v109; // edx
  unsigned int v110; // ecx
  int v111; // r11d
  LONG v112; // r10d
  LONG v113; // r9d
  LONG v114; // r8d
  LONG v115; // ecx
  LONG v116; // eax
  LONG v117; // edx
  int v118; // eax
  BOOL (__stdcall *v119)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  unsigned __int64 v120; // r9
  stretch *v121; // rdi
  int v122; // eax
  unsigned int v123; // ecx
  __m128i si128; // xmm2
  unsigned int (__fastcall *v125)(struct _SURFOBJ *, SIZEL, _QWORD, XCLIPOBJ *, _QWORD, stretch *, struct _POINTL *, struct _RECTL *, __int128 *, Gre::Base *, unsigned int); // rax
  Gre::Base *v126; // rcx
  struct _SURFOBJ *v127; // r15
  struct Gre::Base::SESSION_GLOBALS *v128; // r9
  BOOL (__stdcall *v129)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  PVOID *v130; // r15
  int v131; // eax
  int v132; // ecx
  __int64 v133; // rcx
  XCLIPOBJ *v134; // rdi
  BOOL (__stdcall *v135)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  struct _RECTL *pvBits; // [rsp+20h] [rbp-5A8h]
  struct _RECTL *v137; // [rsp+28h] [rbp-5A0h]
  void *v138; // [rsp+30h] [rbp-598h]
  struct _RECTL *v139; // [rsp+60h] [rbp-568h]
  unsigned int v140; // [rsp+68h] [rbp-560h]
  unsigned int v141; // [rsp+70h] [rbp-558h]
  __int16 v142; // [rsp+78h] [rbp-550h]
  LONG v143; // [rsp+78h] [rbp-550h]
  unsigned int v144; // [rsp+7Ch] [rbp-54Ch]
  unsigned int v145; // [rsp+80h] [rbp-548h]
  LONG v146; // [rsp+84h] [rbp-544h]
  int v147; // [rsp+88h] [rbp-540h]
  int v148; // [rsp+90h] [rbp-538h]
  LONG v149; // [rsp+90h] [rbp-538h]
  unsigned int v150; // [rsp+98h] [rbp-530h]
  struct REGION *v151; // [rsp+A0h] [rbp-528h] BYREF
  __int64 v152; // [rsp+A8h] [rbp-520h] BYREF
  LONG v153; // [rsp+B0h] [rbp-518h]
  LONG v154; // [rsp+B4h] [rbp-514h]
  __int64 p_lDelta; // [rsp+B8h] [rbp-510h]
  struct REGION *v156; // [rsp+C0h] [rbp-508h] BYREF
  SIZEL sizl; // [rsp+C8h] [rbp-500h]
  unsigned int v158; // [rsp+D0h] [rbp-4F8h]
  LONG v159; // [rsp+D4h] [rbp-4F4h]
  HSURF hsurf; // [rsp+D8h] [rbp-4F0h] BYREF
  LONG v161; // [rsp+E0h] [rbp-4E8h]
  LONG v162; // [rsp+E4h] [rbp-4E4h]
  LONG v163; // [rsp+F0h] [rbp-4D8h]
  _DWORD *v164; // [rsp+100h] [rbp-4C8h]
  struct _RECTL *v165; // [rsp+108h] [rbp-4C0h]
  unsigned __int64 v166; // [rsp+110h] [rbp-4B8h]
  struct REGION *v167; // [rsp+118h] [rbp-4B0h] BYREF
  PVOID *v168; // [rsp+120h] [rbp-4A8h]
  XCLIPOBJ *v169; // [rsp+128h] [rbp-4A0h]
  __int64 v170; // [rsp+130h] [rbp-498h]
  char *v171; // [rsp+138h] [rbp-490h]
  struct _SURFOBJ *p_right; // [rsp+140h] [rbp-488h]
  unsigned __int64 v173; // [rsp+148h] [rbp-480h]
  struct _SURFOBJ *v174; // [rsp+150h] [rbp-478h]
  __int64 v175; // [rsp+158h] [rbp-470h]
  XCLIPOBJ *v176; // [rsp+160h] [rbp-468h]
  unsigned int v177; // [rsp+168h] [rbp-460h]
  unsigned int v178; // [rsp+16Ch] [rbp-45Ch]
  struct _POINTL *v179; // [rsp+170h] [rbp-458h]
  stretch *v180; // [rsp+178h] [rbp-450h]
  unsigned int v181; // [rsp+180h] [rbp-448h]
  PVOID *v182; // [rsp+188h] [rbp-440h]
  Gre::Base *v183; // [rsp+190h] [rbp-438h]
  void (*const near *v184)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *); // [rsp+198h] [rbp-430h]
  _QWORD v185[3]; // [rsp+1A0h] [rbp-428h] BYREF
  stretch *v186[3]; // [rsp+1B8h] [rbp-410h] BYREF
  _DWORD *v187; // [rsp+1D0h] [rbp-3F8h]
  struct _SURFOBJ *v188; // [rsp+1D8h] [rbp-3F0h]
  __int64 v189; // [rsp+1E0h] [rbp-3E8h]
  unsigned int *v190; // [rsp+1E8h] [rbp-3E0h]
  LONG *v191; // [rsp+1F0h] [rbp-3D8h]
  stretch *v192; // [rsp+1F8h] [rbp-3D0h]
  struct _SURFOBJ *v193; // [rsp+200h] [rbp-3C8h]
  struct _CLIPOBJ *v194; // [rsp+208h] [rbp-3C0h]
  struct _POINTL *v195; // [rsp+210h] [rbp-3B8h]
  __int64 v196; // [rsp+218h] [rbp-3B0h]
  struct _RECTL *v197; // [rsp+220h] [rbp-3A8h]
  _DWORD v198[4]; // [rsp+228h] [rbp-3A0h] BYREF
  __int64 v199; // [rsp+238h] [rbp-390h]
  int v200; // [rsp+240h] [rbp-388h]
  int v201; // [rsp+244h] [rbp-384h]
  _DWORD v202[4]; // [rsp+248h] [rbp-380h] BYREF
  __int64 v203; // [rsp+258h] [rbp-370h]
  int v204; // [rsp+260h] [rbp-368h]
  int v205; // [rsp+264h] [rbp-364h]
  LONG *p_bottom; // [rsp+268h] [rbp-360h]
  LONG *v207; // [rsp+270h] [rbp-358h]
  struct _POINTL *v208; // [rsp+278h] [rbp-350h]
  _DWORD *v209; // [rsp+280h] [rbp-348h]
  _QWORD *v210; // [rsp+288h] [rbp-340h]
  void (*const near *v211)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *); // [rsp+290h] [rbp-338h]
  int *v212; // [rsp+298h] [rbp-330h]
  _DWORD *v213; // [rsp+2A0h] [rbp-328h]
  _DWORD *v214; // [rsp+2A8h] [rbp-320h]
  int *v215; // [rsp+2B0h] [rbp-318h]
  struct REGION *v216; // [rsp+2B8h] [rbp-310h]
  _QWORD v217[4]; // [rsp+2C0h] [rbp-308h] BYREF
  struct _RECTL v218; // [rsp+2E0h] [rbp-2E8h] BYREF
  unsigned __int128 v219; // [rsp+2F0h] [rbp-2D8h] BYREF
  struct _RECTL v220; // [rsp+300h] [rbp-2C8h] BYREF
  struct _RECTL v221; // [rsp+310h] [rbp-2B8h] BYREF
  struct _RECTL v222; // [rsp+320h] [rbp-2A8h] BYREF
  int v223; // [rsp+330h] [rbp-298h]
  __int128 v224; // [rsp+338h] [rbp-290h] BYREF
  __m128i v225; // [rsp+348h] [rbp-280h] BYREF
  __int128 v226; // [rsp+358h] [rbp-270h] BYREF
  struct _RECTL v227; // [rsp+368h] [rbp-260h] BYREF
  struct _RECTL v228; // [rsp+378h] [rbp-250h] BYREF
  _BYTE v229[160]; // [rsp+390h] [rbp-238h] BYREF
  _BYTE v230[160]; // [rsp+430h] [rbp-198h] BYREF
  _BYTE v231[4]; // [rsp+4D0h] [rbp-F8h] BYREF
  char v232[156]; // [rsp+4D4h] [rbp-F4h] BYREF

  v169 = (XCLIPOBJ *)a4;
  v174 = a3;
  p_right = a1;
  v166 = (unsigned __int64)a5;
  v183 = (Gre::Base *)a10;
  v208 = a10;
  v12 = a8;
  v13 = a9;
  v193 = a3;
  v194 = a4;
  v180 = (stretch *)a6;
  v179 = a7;
  v195 = a10;
  v141 = a11;
  if ( a11 - 1 > 3 )
    return 0;
  p_pvScan0 = &a1[-1].pvScan0;
  if ( !a1 )
    p_pvScan0 = 0;
  v168 = p_pvScan0;
  v15 = (stretch *)&a2[-1].pvScan0;
  if ( !a2 )
    v15 = 0;
  if ( a3 )
  {
    v171 = (char *)&a3[-1].pvScan0;
    p_lDelta = (__int64)&a3->lDelta;
    v170 = (__int64)&a3->pvScan0;
  }
  else
  {
    v171 = 0;
    p_lDelta = 88;
    v170 = 80;
  }
  if ( !p_pvScan0 )
    return 0;
  if ( !v15 )
    return 0;
  v188 = (struct _SURFOBJ *)(p_pvScan0 + 3);
  v16 = *((_DWORD *)p_pvScan0 + 24);
  if ( (unsigned int)(v16 - 7) <= 2 )
    return 0;
  v17 = *((_DWORD *)v15 + 24);
  if ( v17 == 9 || v16 == 10 || v17 == 10 )
    return 0;
  if ( a9->left != a9->right && a9->top != a9->bottom && a8->left != a8->right && a8->top != a8->bottom )
  {
    v151 = (struct REGION *)p_pvScan0[6];
    v18 = *((_QWORD *)v15 + 6);
    SURFMEM::SURFMEM(v217, 2);
    v228 = *a9;
    v24 = v23 - 1;
    if ( a2->iType == (_WORD)v23 - 1 && v18 && (*(_DWORD *)(v18 + 40) & 0x20000) != 0 )
    {
      if ( !(unsigned int)MulCopyDeviceToDIB(a2, (struct SURFMEM *)v217, &v228) )
        goto LABEL_189;
      if ( !v217[0] )
        goto LABEL_78;
      v13 = &v228;
      a2 = (struct _SURFOBJ *)((v217[0] + 24LL) & -(__int64)(v217[0] != 0));
      v15 = (stretch *)&a2[-1].pvScan0;
      if ( !a2 )
        v15 = 0;
      v18 = *((_QWORD *)v15 + 6);
      v21 = p_right;
      v19 = (struct tagCOLORADJUSTMENT *)v180;
      v20 = (__int64 *)v179;
      v22 = (CLIPOBJ *)v169;
    }
    if ( v166 && (*(_DWORD *)(v166 + 4) & 8) != 0 )
    {
      if ( a2->iType )
        goto LABEL_189;
      if ( v21->iType != (_WORD)v24 )
        goto LABEL_189;
      v25 = v24;
      v145 = v24;
      v178 = v24;
      v26 = (__int64)v174;
      if ( v174 )
        goto LABEL_189;
    }
    else
    {
      v25 = 0;
      v145 = 0;
      v178 = 0;
      v26 = (__int64)v174;
    }
    v27 = a11;
    if ( a11 == 4 )
    {
      if ( v25 )
        goto LABEL_189;
      v108 = EngHTBlt(v21, a2, v26, v22, (struct XLATE *)v166, v19, v20, (XLATEOBJ *)a8, (POINTL)v13, v183, 0, 0);
      if ( v108 == -1 )
        goto LABEL_189;
      if ( v108 )
      {
        if ( v108 == v24 )
          goto LABEL_78;
        v27 = 4;
      }
      else
      {
        v27 = 3;
        v141 = 3;
      }
    }
    top = a8->top;
    bottom = a8->bottom;
    if ( bottom < top )
    {
      a8->top = bottom;
      a8->bottom = top;
      v30 = 2;
      v148 = 2;
      v31 = bottom;
    }
    else
    {
      v30 = 0;
      v148 = 0;
      v31 = a8->top;
      top = a8->bottom;
    }
    left = a8->left;
    right = a8->right;
    if ( right < a8->left )
    {
      a8->left = right;
      a8->right = left;
      v30 |= v24;
      v148 = v30;
      v34 = right;
    }
    else
    {
      v34 = a8->left;
      left = a8->right;
    }
    if ( v27 >= 3 || v171 )
    {
      v35 = 0;
      v144 = 0;
      goto LABEL_28;
    }
    v144 = v24;
    if ( left - v34 < v13->right - v13->left )
    {
      v27 = v141;
    }
    else
    {
      v27 = v141;
      if ( top - v31 >= v13->bottom - v13->top )
      {
        v144 = 0;
        v35 = 0;
        goto LABEL_28;
      }
    }
    v35 = v24;
LABEL_28:
    if ( !v35 )
    {
      if ( v27 < 3 )
        v27 = 3;
      v141 = v27;
    }
    v187 = v168 + 18;
    v36 = *((_DWORD *)v168 + 36);
    if ( (v36 & 0x40000) == 0
      && (v166 && ((unsigned __int8)*(_DWORD *)(v166 + 4) & (unsigned __int8)v24) == 0 || a2->iType) )
    {
      if ( *((_WORD *)v168 + 50) )
      {
        if ( (v36 & 2) != 0 && !v30 && !v174 )
        {
          v58 = v13->left;
          if ( v13->left >= 0 )
          {
            v59 = v13->top;
            if ( v59 >= 0 )
            {
              v60 = v13->right;
              if ( v60 <= a2->sizlBitmap.cx )
              {
                v61 = v13->bottom;
                if ( v61 <= a2->sizlBitmap.cy )
                {
                  v226 = 0;
                  v154 = v60 - v58;
                  sizl.cx = v60 - v58;
                  v62 = v61 - v59;
                  v162 = v62;
                  sizl.cy = v62;
                  if ( v60 - v58 <= a8->right - a8->left && v62 <= a8->bottom - a8->top )
                  {
                    hsurf = (HSURF)EngCreateBitmap(sizl, 0, p_right->iBitmapFormat, 0, 0);
                    v63 = EngLockSurface(hsurf);
                    sizl = (SIZEL)v63;
                    if ( v63 )
                    {
                      v63->iUniq = 0;
                      *(_QWORD *)&v226 = 0;
                      *((_QWORD *)&v226 + 1) = __PAIR64__(v162, v154);
                      if ( (*((_DWORD *)v15 + 36) & 0x400) != 0 )
                        v64 = (*(__int64 (__fastcall **)(SURFOBJ *, struct _SURFOBJ *, _QWORD, unsigned __int64, __int128 *, struct _RECTL *))(v18 + 2832))(
                                v63,
                                a2,
                                0,
                                v166,
                                &v226,
                                v13);
                      else
                        v64 = ((__int64 (__fastcall *)(SURFOBJ *, struct _SURFOBJ *, _QWORD, unsigned __int64, __int128 *, struct _RECTL *))EngCopyBits)(
                                v63,
                                a2,
                                0,
                                v166,
                                &v226,
                                v13);
                      if ( !v64
                        || (v125 = (unsigned int (__fastcall *)(struct _SURFOBJ *, SIZEL, _QWORD, XCLIPOBJ *, _QWORD, stretch *, struct _POINTL *, struct _RECTL *, __int128 *, Gre::Base *, unsigned int))*((_QWORD *)v151 + 355)) == 0
                        || !((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v125)(
                              p_right,
                              sizl,
                              0,
                              v169,
                              0,
                              v180,
                              v179,
                              a8,
                              &v226,
                              v183,
                              v141) )
                      {
                        v24 = 0;
                      }
                      EngUnlockSurface(*(SURFOBJ **)&sizl);
                      EngDeleteSurface(hsurf);
                      goto LABEL_78;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v216 = v151;
    SURFMEM::SURFMEM(v185, 2);
    v225 = 0;
    ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v229);
    v220 = 0;
    v152 = 0;
    v37 = *((_DWORD *)v15 + 15);
    v38 = *((_DWORD *)v15 + 14);
    *(_QWORD *)&v218.left = 0;
    v218.right = v38;
    v218.bottom = v37;
    v219 = 0;
    RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v156);
    v142 = *((_WORD *)v168 + 50);
    if ( v142 || v168[4] == *((PVOID *)v15 + 4) )
    {
      v225 = *(__m128i *)a8;
      v111 = _mm_cvtsi128_si32(v225);
      v112 = v111 - 1;
      v154 = a8->right;
      v113 = v154 + 1;
      v114 = v24 + HIDWORD(*(_QWORD *)&a8->right);
      v115 = *((_DWORD *)v168 + 15);
      v116 = *((_DWORD *)v168 + 14);
      if ( v111 - 1 < 0 )
        v112 = 0;
      v220.left = v112;
      v117 = v225.m128i_i32[1] - v24;
      if ( (int)(v225.m128i_i32[1] - v24) < 0 )
        v117 = 0;
      v220.top = v117;
      if ( v116 < v113 )
        v113 = v116;
      v220.right = v113;
      if ( v115 < v114 )
        v114 = v115;
      v220.bottom = v114;
      if ( v113 < v112 )
      {
        v112 = v113;
        v220.left = v113;
      }
      else
      {
        if ( v114 < v117 )
          v117 = v114;
        v220.top = v117;
      }
      if ( v117 == v114 || v112 == v113 )
        goto LABEL_77;
      if ( v142 || v112 <= v13->right && v113 >= v13->left && v117 <= v13->bottom && v114 >= v13->top )
      {
        v225.m128i_i32[0] = v111 - v112;
        v225.m128i_i32[1] -= v117;
        v225.m128i_i32[2] = v154 - v112;
        v225.m128i_i32[3] -= v117;
        v198[3] = 0;
        v201 = 0;
        v198[1] = v24 + v113 - v112;
        v198[2] = v24 + v114 - v117;
        v199 = 0;
        v130 = v168;
        if ( v145 )
          v131 = *((_DWORD *)v15 + 24);
        else
          v131 = *((_DWORD *)v168 + 24);
        v198[0] = v131;
        v200 = *v187 & 0x40000;
        SURFMEM::bCreateDIB((SURFMEM *)v185, (struct _DEVBITMAPINFO *)v198, 0, 0, 0, 0, 0, 0, v24, 0);
        if ( !v185[0] )
          goto LABEL_188;
        v152 = *(_QWORD *)&v220.left;
        if ( !v156 )
          goto LABEL_188;
        *(_QWORD *)&v220.left = 0;
        v220.right -= v152;
        v220.bottom -= HIDWORD(v152);
        RGNOBJ::vSet((RGNOBJ *)&v156, &v220);
        XCLIPOBJ::vSetup((XCLIPOBJ *)v229, v156, (const struct ERECTL *)&v220, v24);
        hsurf = (HSURF)v130[6];
        v127 = v188;
        if ( hsurf )
          PDEVOBJ::vSync((PDEVOBJ *)&hsurf, v188, 0, 0);
        v128 = Gre::Base::Globals(v126);
        if ( v171 )
        {
          if ( (*v187 & 0x400) != 0 )
            v129 = (BOOL (__stdcall *)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))*((_QWORD *)v151 + 354);
          else
            v129 = EngCopyBits;
          v137 = (struct _RECTL *)&v152;
          ((void (__fastcall *)(__int64, struct _SURFOBJ *, _QWORD, char *, struct _RECTL *))v129)(
            (v185[0] + 24LL) & -(__int64)(v185[0] != 0),
            v127,
            0,
            (char *)v128 + 4664,
            &v220);
        }
        v182 = (PVOID *)v185[0];
        v12 = (struct _RECTL *)&v225;
        v176 = (XCLIPOBJ *)v229;
LABEL_34:
        v171 = (char *)v12;
        hsurf = (HSURF)*((_QWORD *)v15 + 6);
        if ( hsurf )
          PDEVOBJ::vSync((PDEVOBJ *)&hsurf, a2, 0, 0);
        v39 = v218.left;
        if ( v13->left > v218.left )
          v39 = v13->left;
        v218.left = v39;
        v40 = v218.top;
        if ( v13->top > v218.top )
          v40 = v13->top;
        v218.top = v40;
        v41 = v218.right;
        if ( v13->right < v218.right )
          v41 = v13->right;
        v218.right = v41;
        v42 = v218.bottom;
        if ( v13->bottom < v218.bottom )
          v42 = v13->bottom;
        v218.bottom = v42;
        if ( v41 < v39 )
        {
          v39 = v41;
          v218.left = v41;
        }
        else
        {
          if ( v42 < v40 )
            v40 = v42;
          v218.top = v40;
        }
        if ( v40 == v42 || v39 == v41 )
          goto LABEL_77;
        SURFMEM::SURFMEM(v186, 2);
        v224 = 0;
        if ( v148 || *((_WORD *)v15 + 50) || *((_DWORD *)v15 + 24) - 7 <= v24 )
        {
          v202[3] = 0;
          v205 = 0;
          v202[1] = v45 - v46;
          v202[2] = v44 - v43;
          v203 = 0;
          if ( v145 )
            v118 = *((_DWORD *)v15 + 24);
          else
            v118 = *((_DWORD *)v182 + 24);
          v202[0] = v118;
          v204 = *((_DWORD *)v15 + 36) & 0x40000;
          SURFMEM::bCreateDIB((SURFMEM *)v186, (struct _DEVBITMAPINFO *)v202, 0, 0, 0, 0, 0, 0, v24, 0);
          if ( !v186[0] )
            goto LABEL_187;
          *(_QWORD *)&v224 = 0;
          DWORD2(v224) = v218.right - v218.left;
          HIDWORD(v224) = v218.bottom - v218.top;
          if ( (*((_DWORD *)v15 + 36) & 0x400) != 0 )
            v119 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v18 + 2832);
          else
            v119 = EngCopyBits;
          v120 = 0;
          if ( !v145 )
            v120 = v166;
          v137 = &v218;
          ((void (__fastcall *)(unsigned __int64, char *, _QWORD, unsigned __int64, __int128 *))v119)(
            ((unsigned __int64)v186[0] + 24) & -(__int64)(v186[0] != 0),
            (char *)v15 + 24,
            0,
            v120,
            &v224);
          LODWORD(v224) = v13->left - v218.left;
          DWORD1(v224) = v13->top - v218.top;
          DWORD2(v224) = v13->right - v218.left;
          HIDWORD(v224) = v13->bottom - v218.top;
          v121 = v186[0];
          v15 = v186[0];
          v180 = v186[0];
          v13 = (struct _RECTL *)&v224;
          v179 = (struct _POINTL *)&v224;
          v173 = 0;
          v218.right -= v218.left;
          v122 = v218.bottom - v218.top;
          v218.bottom -= v218.top;
          *(_QWORD *)&v218.left = 0;
          if ( (v148 & 2) != 0 )
          {
            v132 = *((_DWORD *)v186[0] + 22);
            if ( v132 <= 0 )
              v133 = *((_QWORD *)v186[0] + 9);
            else
              v133 = *((_QWORD *)v186[0] + 9) + v132 * (v122 - 1);
            *((_QWORD *)v186[0] + 10) = v133;
            *((_DWORD *)v186[0] + 22) = -*((_DWORD *)v186[0] + 22);
            v121 = v186[0];
          }
          if ( ((unsigned __int8)v148 & (unsigned __int8)v24) != 0 )
          {
            v123 = *((_DWORD *)v121 + 24);
            if ( v123 - 1 > 5 )
              goto LABEL_187;
            ((void (__fastcall *)(stretch *))funcs_14005AB36[v123 - 1])(v121);
          }
          v47 = 0;
        }
        else
        {
          v180 = v15;
          v179 = (struct _POINTL *)v13;
          v47 = 0;
          if ( !v145 )
            v47 = v166;
          v173 = v47;
        }
        v48 = v182;
        hsurf = (HSURF)v182[6];
        if ( hsurf )
          PDEVOBJ::vSync(
            (PDEVOBJ *)&hsurf,
            (struct _SURFOBJ *)((unsigned __int64)(v182 + 3)
                              & ((unsigned __int128)-(__int128)(unsigned __int64)v182 >> 64)),
            0,
            0);
        p_right = (struct _SURFOBJ *)&v13->right;
        if ( v13->right - v13->left >= 128000000 )
          goto LABEL_187;
        sizl = (SIZEL)&v13->top;
        if ( v13->bottom - v13->top >= 128000000 )
          goto LABEL_187;
        v49 = v12->right - v12->left;
        if ( v49 >= 128000000 )
          goto LABEL_187;
        v50 = v12->bottom - v12->top;
        if ( v50 >= 128000000 || v49 <= -128000000 || v50 <= -128000000 )
          goto LABEL_187;
        if ( v141 == 3 && !v174 && (!v47 || ((unsigned __int8)*(_DWORD *)(v47 + 4) & (unsigned __int8)v24) != 0) )
        {
          v51 = *((_DWORD *)v15 + 24);
          if ( *((_DWORD *)v48 + 24) == v51 && ((v51 - 3) & 0xFFFFFFFC) == 0 && v51 != 5 )
          {
            if ( v176 && *((_BYTE *)v176 + 20) == 3 )
            {
              v221 = 0;
              *(_QWORD *)&v218.right = 0;
              *(_QWORD *)&v218.left = 0;
              v222 = 0;
              v223 = 0;
              v103 = v169;
              XCLIPOBJ::cEnumStart(v169, 0, 0, 4u, 0);
              do
              {
                v104 = XCLIPOBJ::bEnum(v103, 0x14u, &v222, 0);
                if ( v222.left )
                {
                  LODWORD(v139) = *((_DWORD *)v48 + 24);
                  LODWORD(v138) = *((_DWORD *)v15 + 22);
                  stretch::StretchDIBDirect(
                    (stretch *)v48[10],
                    (void *)*((unsigned int *)v48 + 22),
                    *((_DWORD *)v48 + 14),
                    *((_DWORD *)v48 + 15),
                    (unsigned int)v12,
                    *((struct _RECTL **)v15 + 10),
                    v138,
                    *((_DWORD *)v15 + 14),
                    *((_DWORD *)v15 + 15),
                    (unsigned int)v13,
                    &v221,
                    (struct _RECTL *)&v222.top,
                    v139,
                    v140);
                  v105 = v218.left;
                  v106 = v218.right;
                  if ( v218.left == v218.right || (v107 = v218.top, v218.top == v218.bottom) )
                  {
                    si128 = _mm_load_si128((const __m128i *)&v221);
                    v218.bottom = _mm_cvtsi128_si32(_mm_srli_si128(si128, 12));
                    v218.right = _mm_cvtsi128_si32(_mm_srli_si128(si128, 8));
                    v218.top = _mm_cvtsi128_si32(_mm_srli_si128(si128, 4));
                    v218.left = si128.m128i_i32[0];
                  }
                  else
                  {
                    if ( v221.left < v218.left )
                      v105 = v221.left;
                    v218.left = v105;
                    if ( v221.top < v218.top )
                      v107 = v221.top;
                    v218.top = v107;
                    if ( v221.right > v218.right )
                      v106 = v221.right;
                    v218.right = v106;
                    if ( v221.bottom > v218.bottom )
                      v218.bottom = v221.bottom;
                  }
                }
              }
              while ( v104 );
              v24 = 1;
            }
            else
            {
              v52 = v12;
              if ( v176 && *((_BYTE *)v176 + 20) == (_BYTE)v24 )
                v52 = (struct _RECTL *)((char *)v176 + 4);
              LODWORD(v139) = *((_DWORD *)v48 + 24);
              LODWORD(v138) = *((_DWORD *)v15 + 22);
              stretch::StretchDIBDirect(
                (stretch *)v48[10],
                (void *)*((unsigned int *)v48 + 22),
                *((_DWORD *)v48 + 14),
                *((_DWORD *)v48 + 15),
                (unsigned int)v12,
                *((struct _RECTL **)v15 + 10),
                v138,
                *((_DWORD *)v15 + 14),
                *((_DWORD *)v15 + 15),
                (unsigned int)v13,
                &v218,
                v52,
                v139,
                v140);
            }
            v53 = v218.left;
            v219 = (unsigned __int128)v218;
            v54 = v218.right;
            v55 = v218.top;
            v56 = v218.bottom;
LABEL_75:
            if ( v48 == v168 )
            {
LABEL_76:
              SURFMEM::~SURFMEM((SURFMEM *)v186);
LABEL_77:
              RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v156);
              SURFMEM::~SURFMEM((SURFMEM *)v185);
LABEL_78:
              SURFMEM::~SURFMEM((SURFMEM *)v217);
              return v24;
            }
            LODWORD(v219) = v152 + v53;
            DWORD1(v219) = HIDWORD(v152) + v55;
            DWORD2(v219) = v152 + v54;
            HIDWORD(v219) = HIDWORD(v152) + v56;
            RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v167);
            if ( !v167 )
              goto LABEL_271;
            v134 = v169;
            if ( v169 )
            {
              RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v151);
              if ( !v151
                || (RGNOBJ::vSet((RGNOBJ *)&v151, (const struct _RECTL *const)&v219),
                    !RGNOBJ::bMerge((RGNOBJ *)&v167, (struct RGNOBJ *)&v151, (XCLIPOBJ *)((char *)v134 + 56), 8u)) )
              {
                RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v151);
LABEL_271:
                RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v167);
                goto LABEL_187;
              }
              RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v151);
            }
            else
            {
              RGNOBJ::vSet((RGNOBJ *)&v167, (const struct _RECTL *const)&v219);
            }
            v227 = *(struct _RECTL *)((char *)v167 + 52);
            if ( !v134 || bIntersect(&v227, (const struct _RECTL *)((char *)v134 + 4), &v227) )
            {
              ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v231, v167, (struct ERECTL *)&v227, v24);
              if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)v232) )
              {
                v220.left += v152;
                v220.top += HIDWORD(v152);
                v220.right += v152;
                v220.bottom += HIDWORD(v152);
                v152 = 0;
                if ( (*v187 & 0x400) != 0 )
                  v135 = (BOOL (__stdcall *)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))*((_QWORD *)v216 + 354);
                else
                  v135 = EngCopyBits;
                ((void (__fastcall *)(struct _SURFOBJ *, __int64, _BYTE *, unsigned __int64, struct _RECTL *, __int64 *))v135)(
                  v188,
                  (v185[0] + 24LL) & -(__int64)(v185[0] != 0),
                  v231,
                  v166 & -(__int64)(v145 != 0),
                  &v220,
                  &v152);
              }
            }
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v167);
            goto LABEL_76;
          }
        }
        v65 = (unsigned int *)AllocFreeTmpBuffer(324);
        v190 = v65;
        if ( v65 )
        {
          v210 = (_QWORD *)v170;
          v209 = (_DWORD *)p_lDelta;
          v215 = (int *)p_lDelta;
          v181 = v141;
          v66 = v176;
          v67 = 0;
          v150 = 0;
          if ( v176 )
          {
            if ( *((_BYTE *)v176 + 20) )
            {
              v110 = *((unsigned __int8 *)v176 + 20) - v24;
              if ( v110 )
              {
                if ( v110 == 2 )
                {
                  v150 = v24;
                  XCLIPOBJ::cEnumStart(v176, 0, 0, 4u, 0x14u);
                  v67 = v24;
                  v65 = v190;
                }
LABEL_110:
                v162 = v144;
                v191 = &v13->right;
                p_bottom = &v13->bottom;
                hsurf = (HSURF)&v13->top;
                v207 = &v12->right;
                v192 = v15;
                v219 = 0u;
                if ( v67 )
                  goto LABEL_308;
                while ( 1 )
                {
                  for ( i = 0; ; i = v24 + v154 )
                  {
                    v154 = i;
                    v65 = v190;
                    if ( (unsigned int)i >= *v190 )
                      break;
                    p_lDelta = (__int64)&v190[4 * i + 1];
                    v222 = 0;
                    stretch::vInitStrDDAClip((stretch *)&v218, v13, v12, (struct _RECTL *)p_lDelta, &v222, v137);
                    if ( v222.left != v222.right && v222.top != v222.bottom )
                    {
                      v70 = v222.left - v24;
                      v71 = v222.top - v24;
                      v72 = v24 + v222.right;
                      v73 = v24 + v222.bottom;
                      if ( v218.left > (int)(v222.left - v24) )
                        v70 = v218.left;
                      v153 = v70;
                      v222.left = v70;
                      if ( v218.top > v71 )
                        v71 = v218.top;
                      v146 = v71;
                      v222.top = v71;
                      if ( v218.right < v72 )
                        v72 = v218.right;
                      v161 = v72;
                      v222.right = v72;
                      if ( v218.bottom < v73 )
                        v73 = v218.bottom;
                      v143 = v73;
                      v222.bottom = v73;
                      if ( v72 < v70 )
                      {
                        v153 = v72;
                        v222.left = v72;
                      }
                      else
                      {
                        if ( v73 < v71 )
                          v71 = v73;
                        v146 = v71;
                        v222.top = v71;
                      }
                      if ( SLODWORD(p_right->dhsurf) >= v13->left && *p_bottom >= *(_DWORD *)sizl.cx )
                      {
                        v74 = LODWORD(p_right->dhsurf) - v13->left;
                        v75 = *p_bottom + v74 - *(_DWORD *)sizl.cx;
                        if ( v75 >= v74 && v75 < 0x3FFFFFF5 )
                        {
                          v76 = 4 * v75 + 40;
                          v77 = v76 ? (struct _RECTL *)Win32AllocPool(v76, 1752462151) : 0LL;
                          v165 = v77;
                          if ( v77 )
                          {
                            stretch::vInitStrDDA((stretch *)v77, (struct stretch::_STRDDA *)&v222, v13, v12, pvBits);
                            v78 = *(__m128i *)v77;
                            v221 = *v77;
                            v79 = v173;
                            if ( v173 )
                            {
                              if ( ((unsigned __int8)v24 & *(_BYTE *)(v173 + 4)) != 0 )
                                v79 = 0;
                              v173 = v79;
                            }
                            v80 = *((unsigned int *)v48 + 24);
                            if ( v144 )
                              v77[1].top = (v181 != v24) - v24;
                            v149 = _mm_cvtsi128_si32(_mm_srli_si128(v78, 8));
                            v163 = _mm_cvtsi128_si32(v78);
                            v81 = v149 - v163;
                            if ( LODWORD(p_right->dhsurf) - v13->left > *v207 - v12->left )
                            {
                              if ( v81 >= 0x15555553 )
                                goto LABEL_192;
                              v82 = v149 - v163;
                            }
                            else if ( v81 + 3 < v81 || (v82 = (v81 + 3) >> 1, v82 >= 0x15555553) )
                            {
LABEL_192:
                              Win32FreePool(v165);
                              continue;
                            }
                            if ( v81 > 0x5F5E100 )
                              goto LABEL_192;
                            if ( 12 * (v82 + 2) > 0x2710000 )
                              goto LABEL_192;
                            v184 = (&stretch::apfnWrite)[v80];
                            v170 = (__int64)*(&stretch::apfnRead + 3 * *((unsigned int *)v15 + 24) + v141 - 1);
                            v83 = AllocFreeTmpBuffer(12 * (v82 + 2));
                            v164 = (_DWORD *)v83;
                            if ( !v83 )
                              goto LABEL_192;
                            v85 = v165;
                            v197 = v165;
                            v159 = *((_DWORD *)v192 + 22);
                            v189 = *((_QWORD *)v192 + 10);
                            v196 = 0;
                            v86 = v146;
                            if ( v174 )
                            {
                              LODWORD(v196) = v208->x + v153 - v13->left;
                              v175 = *v210 + *v209 * (v146 + *((_DWORD *)v183 + 1) - *(_DWORD *)sizl.cx);
                              v83 = (__int64)v164;
                            }
                            else
                            {
                              v175 = 0;
                            }
                            v158 = 0;
                            v177 = 0;
                            if ( v144 )
                            {
                              v109 = -1;
                              if ( v181 != v24 )
                                v109 = 0;
                              v158 = v109;
                              stretch::vInitBuffer(
                                (stretch *)(v83 + 8),
                                (struct stretch::_XRUNLEN *)&v221,
                                (struct _RECTL *)v109,
                                v84);
                              v177 = v158;
                            }
                            *v164 = v85->top;
                            RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v151);
                            ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v230);
                            v87 = 0;
                            v88 = v176;
                            if ( !v176 )
                              goto LABEL_147;
                            if ( v151 )
                            {
                              RGNOBJ::vSet((RGNOBJ *)&v151, (const struct _RECTL *const)p_lDelta);
                              XCLIPOBJ::vSetup((XCLIPOBJ *)v230, v151, (const struct ERECTL *)p_lDelta, v24);
                              v87 = v24;
                              v88 = v176;
                            }
                            if ( !v88 || v151 )
                            {
LABEL_147:
                              v212 = (int *)((char *)v192 + 88);
                              v211 = v184;
                              v184 = (void (*const near *)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *))v170;
                              v89 = v164;
                              v214 = v164;
                              p_lDelta = v189 + v146 * v159;
                              LODWORD(v189) = v87;
                              v90 = 0;
                              v91 = v143;
                              while ( 1 )
                              {
                                v147 = v90;
                                v159 = v86;
                                if ( v86 >= v91 )
                                  goto LABEL_167;
                                v92 = v165;
                                v93 = *(_DWORD *)(*(_QWORD *)&v165[1].right + 4LL * v90);
                                v213 = v89 + 1;
                                v89[1] = v93;
                                if ( v93 )
                                  break;
                                if ( v144 )
                                {
                                  LODWORD(v137) = v153;
                                  ((void (__fastcall *)(struct _RECTL *, _DWORD *, __int64, _QWORD, unsigned __int64))v170)(
                                    v92,
                                    v89,
                                    p_lDelta,
                                    0,
                                    v173);
                                  v89 = v164;
                                  v90 = v147;
                                  v91 = v143;
                                }
LABEL_157:
                                p_lDelta += *v212;
                                *v214 += *v213;
                                if ( v175 )
                                  v175 += *v215;
                                v86 += v24;
                                v146 = v86;
                                v90 += v24;
                                v48 = v182;
                              }
                              v94 = (unsigned __int64)v230 & -(__int64)((_DWORD)v189 != 0);
                              LODWORD(v137) = v153;
                              v95 = ((__int64 (__fastcall *)(struct _RECTL *, _DWORD *, __int64, __int64, unsigned __int64))v170)(
                                      v92,
                                      v89,
                                      p_lDelta,
                                      v175,
                                      v173);
                              ((void (__fastcall *)(_DWORD *, __int64, PVOID *, unsigned __int64))v211)(
                                v164,
                                v95,
                                v48,
                                v94);
                              v86 = v146;
                              v96 = v158;
                              v91 = v143;
                              v97 = v163;
                              v89 = v164;
                              if ( v144 )
                              {
                                v164[2] = v163;
                                v89[3] = v149 - v97;
                                v98 = (v149 - v97) & 0x3FFFFFFFFFFFFFFFLL;
                                if ( v98 )
                                {
                                  v99 = v89 + 4;
                                  if ( (((_BYTE)v89 + 16) & 4) != 0 )
                                  {
                                    *v99 = v96;
                                    if ( --v98 )
                                    {
                                      v99 = v89 + 5;
                                      goto LABEL_153;
                                    }
                                  }
                                  else
                                  {
LABEL_153:
                                    memset64(v99, v96 | ((unsigned __int64)v96 << 32), v98 >> 1);
                                    v86 = v146;
                                    if ( ((unsigned __int8)v98 & (unsigned __int8)v24) != 0 )
                                      v99[v98 - 1] = v96;
                                  }
                                  v91 = v143;
                                }
                              }
                              v90 = v147;
                              goto LABEL_157;
                            }
                            v89 = v164;
LABEL_167:
                            FreeTmpBuffer(v89);
                            Win32FreePool(v165);
                            v100 = v219;
                            v101 = DWORD2(v219);
                            if ( (_DWORD)v219 == DWORD2(v219) || (v102 = DWORD1(v219), DWORD1(v219) == HIDWORD(v219)) )
                            {
                              v219 = (unsigned __int128)v78;
                            }
                            else
                            {
                              if ( v163 < (int)v219 )
                                v100 = v163;
                              LODWORD(v219) = v100;
                              if ( v221.top < SDWORD1(v219) )
                                v102 = v221.top;
                              DWORD1(v219) = v102;
                              if ( v149 > SDWORD2(v219) )
                                v101 = v149;
                              DWORD2(v219) = v101;
                              if ( v221.bottom > SHIDWORD(v219) )
                                HIDWORD(v219) = v221.bottom;
                            }
                            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v151);
                          }
                        }
                      }
                    }
                  }
                  v66 = v176;
                  if ( !v150 )
                  {
                    FreeTmpBuffer(v190);
                    v56 = HIDWORD(v219);
                    v54 = DWORD2(v219);
                    v55 = DWORD1(v219);
                    v53 = v219;
                    goto LABEL_75;
                  }
LABEL_308:
                  v150 = XCLIPOBJ::bEnum(v66, 0x144u, v65, 0);
                }
              }
              v150 = 0;
              *v65 = v24;
              v68 = *(struct _RECTL *)((char *)v66 + 4);
LABEL_109:
              *(struct _RECTL *)(v65 + 1) = v68;
              goto LABEL_110;
            }
            v150 = 0;
          }
          *v65 = v24;
          v68 = *v12;
          goto LABEL_109;
        }
LABEL_187:
        SURFMEM::~SURFMEM((SURFMEM *)v186);
LABEL_188:
        RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v156);
        SURFMEM::~SURFMEM((SURFMEM *)v185);
LABEL_189:
        v24 = 0;
        goto LABEL_78;
      }
      v182 = v168;
    }
    else
    {
      v182 = v168;
    }
    v176 = v169;
    goto LABEL_34;
  }
  return 1;
}

```

## disassembly

```asm
0x140077920  mov     rax, rsp
0x140077923  push    rbx
0x140077924  push    rsi
0x140077925  push    rdi
0x140077926  push    r12
0x140077928  push    r13
0x14007792a  push    r14
0x14007792c  push    r15
0x14007792e  sub     rsp, 590h
0x140077935  movaps  xmmword ptr [rax-48h], xmm6
0x140077939  mov     rax, cs:__security_cookie
0x140077940  xor     rax, rsp
0x140077943  mov     [rsp+5C8h+var_58], rax
0x14007794b  mov     r11, r9
0x14007794e  mov     [rsp+5C8h+var_4A0], r9
0x140077956  mov     rdi, r8
0x140077959  mov     [rsp+5C8h+var_478], r8
0x140077961  mov     r13, rdx
0x140077964  mov     r10, rcx
0x140077967  mov     [rsp+5C8h+var_488], rcx
0x14007796f  mov     rax, [rsp+5C8h+arg_20]
0x140077977  mov     [rsp+5C8h+var_4B8], rax
0x14007797f  mov     rax, [rsp+5C8h+arg_48]
0x140077987  mov     [rsp+5C8h+var_438], rax
0x14007798f  mov     [rsp+5C8h+var_350], rax
0x140077997  mov     r15, [rsp+5C8h+arg_38]
0x14007799f  mov     r12, [rsp+5C8h+arg_40]
0x1400779a7  mov     [rsp+5C8h+var_3C8], r8
0x1400779af  mov     [rsp+5C8h+var_3C0], r9
0x1400779b7  mov     r8, [rsp+5C8h+arg_28]
0x1400779bf  mov     [rsp+5C8h+var_450], r8
0x1400779c7  mov     r9, [rsp+5C8h+arg_30]
0x1400779cf  mov     [rsp+5C8h+var_458], r9
0x1400779d7  mov     [rsp+5C8h+var_3B8], rax
0x1400779df  mov     eax, [rsp+5C8h+arg_50]
0x1400779e6  mov     [rsp+5C8h+var_558], eax
0x1400779ea  dec     eax
0x1400779ec  cmp     eax, 3
0x1400779ef  ja      loc_140079072
0x1400779f5  xor     ebx, ebx
0x1400779f7  test    rcx, rcx
0x1400779fa  lea     rdx, [rcx-18h]
0x1400779fe  jz      loc_14007906A
0x140077a04  mov     [rsp+5C8h+var_4A8], rdx
0x140077a0c  test    r13, r13
0x140077a0f  lea     r14, [r13-18h]
0x140077a13  jz      loc_140079054
0x140077a19  test    rdi, rdi
0x140077a1c  jnz     loc_140079079
0x140077a22  mov     [rsp+5C8h+var_490], rbx
0x140077a2a  mov     [rsp+5C8h+var_510], 58h ; 'X'
0x140077a36  mov     [rsp+5C8h+var_498], 50h ; 'P'
0x140077a42  test    rdx, rdx
0x140077a45  jz      loc_140079072
0x140077a4b  test    r14, r14
0x140077a4e  jz      loc_140079072
0x140077a54  lea     rax, [rdx+18h]
0x140077a58  mov     [rsp+5C8h+var_3F0], rax
0x140077a60  mov     ecx, [rax+48h]
0x140077a63  lea     eax, [rcx-7]
0x140077a66  cmp     eax, 2
0x140077a69  jbe     loc_140079072
0x140077a6f  mov     eax, [r14+60h]
0x140077a73  cmp     eax, 9
0x140077a76  jz      loc_140079072
0x140077a7c  cmp     ecx, 0Ah
0x140077a7f  jz      loc_140079072
0x140077a85  cmp     eax, 0Ah
0x140077a88  jz      loc_140079072
0x140077a8e  mov     eax, [r12+8]
0x140077a93  cmp     [r12], eax
0x140077a97  jz      loc_140079B0B
0x140077a9d  mov     eax, [r12+0Ch]
0x140077aa2  cmp     [r12+4], eax
0x140077aa7  jz      loc_140079B0B
0x140077aad  mov     eax, [r15+8]
0x140077ab1  cmp     [r15], eax
0x140077ab4  jz      loc_140079B0B
0x140077aba  mov     eax, [r15+0Ch]
0x140077abe  cmp     [r15+4], eax
0x140077ac2  jz      loc_140079B0B
0x140077ac8  mov     rax, [rdx+30h]
0x140077acc  mov     [rsp+5C8h+var_528], rax
0x140077ad4  mov     rdi, [r14+30h]
0x140077ad8  mov     edx, 2
0x140077add  lea     rcx, [rsp+5C8h+var_308]
0x140077ae5  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x140077aea  movups  xmm0, xmmword ptr [r12]
0x140077aef  movdqu  xmmword ptr [rsp+5C8h+var_250.left], xmm0
0x140077af8  lea     esi, [rdx-1]
0x140077afb  cmp     [r13+4Ch], si
0x140077b00  jz      loc_1400794C5
0x140077b06  mov     rax, [rsp+5C8h+var_4B8]
0x140077b0e  test    rax, rax
0x140077b11  jnz     loc_1400781AC
0x140077b17  mov     edx, ebx
0x140077b19  mov     [rsp+5C8h+var_548], ebx
0x140077b20  mov     [rsp+5C8h+var_45C], ebx
0x140077b27  mov     rax, [rsp+5C8h+var_478]
0x140077b2f  mov     ecx, [rsp+5C8h+var_558]
0x140077b33  cmp     ecx, 4
0x140077b36  jz      loc_140078EED
0x140077b3c  mov     r8d, [r15+4]
0x140077b40  mov     eax, [r15+0Ch]
0x140077b44  cmp     eax, r8d
0x140077b47  jl      loc_140079789
0x140077b4d  mov     r11d, ebx
0x140077b50  mov     [rsp+5C8h+var_538], ebx
0x140077b57  mov     r10d, r8d
0x140077b5a  mov     r8d, eax
0x140077b5d  mov     edx, [r15]
0x140077b60  mov     eax, [r15+8]
0x140077b64  cmp     eax, edx
0x140077b66  jl      loc_140078C3B
0x140077b6c  mov     r9d, edx
0x140077b6f  mov     edx, eax
0x140077b71  mov     eax, 3
0x140077b76  cmp     ecx, eax
0x140077b78  jb      loc_140078C55
0x140077b7e  mov     edx, ebx
0x140077b80  mov     [rsp+5C8h+var_54C], ebx
0x140077b84  test    edx, edx
0x140077b86  jz      loc_140078173
0x140077b8c  mov     rdx, [rsp+5C8h+var_4A8]
0x140077b94  lea     rax, [rdx+90h]
0x140077b9b  mov     [rsp+5C8h+var_3F8], rax
0x140077ba3  mov     ecx, [rax]
0x140077ba5  bt      ecx, 12h
0x140077ba9  jnb     loc_140077FA6
0x140077baf  mov     rax, [rsp+5C8h+var_528]
0x140077bb7  mov     [rsp+5C8h+var_310], rax
0x140077bbf  mov     edx, 2
0x140077bc4  lea     rcx, [rsp+5C8h+var_428]
0x140077bcc  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x140077bd1  xorps   xmm0, xmm0
0x140077bd4  movups  [rsp+5C8h+var_280], xmm0
0x140077bdc  lea     rcx, [rsp+5C8h+var_238]; this
0x140077be4  call    ??0ECLIPOBJ@@QEAA@XZ; ECLIPOBJ::ECLIPOBJ(void)
0x140077be9  movdqu  [rsp+5C8h+var_2C8], xmm0
0x140077bf2  mov     [rsp+5C8h+var_520], rbx
0x140077bfa  mov     ecx, [r14+3Ch]
0x140077bfe  mov     eax, [r14+38h]
0x140077c02  mov     qword ptr [rsp+5C8h+var_2E8.left], rbx
0x140077c0a  mov     [rsp+5C8h+var_2E8.right], eax
0x140077c11  mov     [rsp+5C8h+var_2E8.bottom], ecx
0x140077c18  movups  [rsp+5C8h+var_2D8], xmm0
0x140077c20  lea     rcx, [rsp+5C8h+var_508]; this
0x140077c28  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x140077c2d  mov     rcx, [rsp+5C8h+var_4A8]
0x140077c35  movzx   eax, word ptr [rcx+64h]
0x140077c39  mov     word ptr [rsp+5C8h+var_550], ax
0x140077c3e  test    ax, ax
0x140077c41  jnz     loc_1400790A2
0x140077c47  mov     rax, [r14+20h]
0x140077c4b  cmp     [rcx+20h], rax
0x140077c4f  jz      loc_1400790A2
0x140077c55  mov     [rsp+5C8h+var_440], rcx
0x140077c5d  mov     rcx, [rsp+5C8h+var_4A0]
0x140077c65  mov     [rsp+5C8h+var_468], rcx
0x140077c6d  mov     [rsp+5C8h+var_490], r15
0x140077c75  mov     rax, [r14+30h]
0x140077c79  mov     [rsp+5C8h+hsurf], rax
0x140077c81  test    rax, rax
0x140077c84  jz      short loc_140077CA3
0x140077c86  xor     r9d, r9d
0x140077c89  xor     r8d, r8d
0x140077c8c  mov     rdx, r13
0x140077c8f  lea     rcx, [rsp+5C8h+hsurf]
0x140077c97  call    cs:__imp_?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z; PDEVOBJ::vSync(_SURFOBJ *,_RECTL *,ulong)
0x140077c9e  nop     dword ptr [rax+rax+00h]
0x140077ca3  mov     eax, [r12]
0x140077ca7  mov     r11d, [rsp+5C8h+var_2E8.left]
0x140077caf  cmp     eax, r11d
0x140077cb2  cmovg   r11d, eax
0x140077cb6  mov     [rsp+5C8h+var_2E8.left], r11d
0x140077cbe  mov     eax, [r12+4]
0x140077cc3  mov     r8d, [rsp+5C8h+var_2E8.top]
0x140077ccb  cmp     eax, r8d
0x140077cce  cmovg   r8d, eax
0x140077cd2  mov     [rsp+5C8h+var_2E8.top], r8d
0x140077cda  mov     eax, [r12+8]
0x140077cdf  mov     r10d, [rsp+5C8h+var_2E8.right]
0x140077ce7  cmp     eax, r10d
0x140077cea  cmovl   r10d, eax
0x140077cee  mov     [rsp+5C8h+var_2E8.right], r10d
0x140077cf6  mov     eax, [r12+0Ch]
0x140077cfb  mov     r9d, [rsp+5C8h+var_2E8.bottom]
0x140077d03  cmp     eax, r9d
0x140077d06  cmovl   r9d, eax
0x140077d0a  mov     [rsp+5C8h+var_2E8.bottom], r9d
0x140077d12  cmp     r10d, r11d
0x140077d15  jl      loc_140078CA0
0x140077d1b  cmp     r9d, r8d
0x140077d1e  cmovl   r8d, r9d
0x140077d22  mov     [rsp+5C8h+var_2E8.top], r8d
0x140077d2a  cmp     r8d, r9d
0x140077d2d  jz      loc_140077F69
0x140077d33  cmp     r11d, r10d
0x140077d36  jz      loc_140077F69
0x140077d3c  mov     edx, 2
0x140077d41  lea     rcx, [rsp+5C8h+var_410]
0x140077d49  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x140077d4e  xorps   xmm0, xmm0
0x140077d51  movups  [rsp+5C8h+var_290], xmm0
0x140077d59  mov     r13d, [rsp+5C8h+var_538]
0x140077d61  test    r13d, r13d
0x140077d64  jnz     loc_1400791EA
0x140077d6a  cmp     [r14+64h], bx
0x140077d6f  jnz     loc_1400791EA
0x140077d75  mov     eax, [r14+60h]
0x140077d79  sub     eax, 7
0x140077d7c  cmp     eax, esi
0x140077d7e  jbe     loc_1400791EA
0x140077d84  mov     [rsp+5C8h+var_450], r14
0x140077d8c  mov     [rsp+5C8h+var_458], r12
0x140077d94  mov     rdi, rbx
0x140077d97  cmp     [rsp+5C8h+var_548], ebx
0x140077d9e  cmovz   rdi, [rsp+5C8h+var_4B8]
0x140077da7  mov     [rsp+5C8h+var_480], rdi
0x140077daf  mov     r13, [rsp+5C8h+var_440]
0x140077db7  lea     rcx, [r13+18h]
0x140077dbb  mov     rax, [rcx+18h]
0x140077dbf  mov     [rsp+5C8h+hsurf], rax
0x140077dc7  test    rax, rax
0x140077dca  jnz     loc_140078181
0x140077dd0  lea     rcx, [r12+8]
0x140077dd5  mov     [rsp+5C8h+var_488], rcx
0x140077ddd  mov     ecx, [rcx]
0x140077ddf  sub     ecx, [r12]
0x140077de3  mov     r8d, 7A12000h
0x140077de9  cmp     ecx, r8d
0x140077dec  jge     loc_140078CC3
0x140077df2  lea     rax, [r12+4]
0x140077df7  mov     qword ptr [rsp+5C8h+sizl.cx], rax
0x140077dff  mov     ecx, [r12+0Ch]
0x140077e04  sub     ecx, [rax]
0x140077e06  cmp     ecx, r8d
0x140077e09  jge     loc_140078CC3
0x140077e0f  mov     ecx, [r15+8]
0x140077e13  sub     ecx, [r15]
0x140077e16  cmp     ecx, r8d
0x140077e19  jge     loc_140078CC3
0x140077e1f  mov     edx, [r15+0Ch]
0x140077e23  sub     edx, [r15+4]
0x140077e27  cmp     edx, r8d
0x140077e2a  jge     loc_140078CC3
0x140077e30  mov     eax, 0F85EE000h
0x140077e35  cmp     ecx, eax
0x140077e37  jle     loc_140078CC3
0x140077e3d  cmp     edx, eax
0x140077e3f  jle     loc_140078CC3
0x140077e45  mov     r8d, 3
0x140077e4b  cmp     [rsp+5C8h+var_558], r8d
0x140077e50  jnz     loc_1400781F3
0x140077e56  cmp     [rsp+5C8h+var_478], rbx
0x140077e5e  jnz     loc_1400781F3
0x140077e64  test    rdi, rdi
0x140077e67  jz      short loc_140077E75
0x140077e69  mov     eax, [rdi+4]
0x140077e6c  test    sil, al
0x140077e6f  jz      loc_1400781F3
0x140077e75  mov     ecx, [r14+60h]
0x140077e79  mov     edx, [r13+60h]
0x140077e7d  cmp     edx, ecx
0x140077e7f  jnz     loc_1400781F3
0x140077e85  lea     eax, [rcx-3]
0x140077e88  test    eax, 0FFFFFFFCh
0x140077e8d  jnz     loc_1400781F3
0x140077e93  cmp     ecx, 5
0x140077e96  jz      loc_1400781F3
0x140077e9c  mov     rcx, [rsp+5C8h+var_468]
0x140077ea4  test    rcx, rcx
0x140077ea7  jnz     loc_140078D29
0x140077ead  mov     rax, r15
0x140077eb0  test    rcx, rcx
0x140077eb3  jnz     loc_140078CB0
0x140077eb9  mov     dword ptr [rsp+5C8h+var_568], edx; struct _RECTL *
0x140077ebd  mov     [rsp+5C8h+var_570], rax; struct _RECTL *
0x140077ec2  lea     rax, [rsp+5C8h+var_2E8]
0x140077eca  mov     [rsp+5C8h+var_578], rax; struct _RECTL *
0x140077ecf  mov     qword ptr [rsp+5C8h+var_580], r12; unsigned int
0x140077ed4  mov     eax, [r14+3Ch]
0x140077ed8  mov     [rsp+5C8h+var_588], eax; unsigned int
0x140077edc  mov     eax, [r14+38h]
0x140077ee0  mov     [rsp+5C8h+var_590], eax; int
0x140077ee4  mov     eax, [r14+58h]
0x140077ee8  mov     dword ptr [rsp+5C8h+var_598], eax; void *
0x140077eec  mov     rax, [r14+50h]
0x140077ef0  mov     [rsp+5C8h+var_5A0], rax; struct _RECTL *
0x140077ef5  mov     [rsp+5C8h+pvBits], r15; unsigned int
0x140077efa  mov     r9d, [r13+3Ch]; unsigned int
0x140077efe  mov     r8d, [r13+38h]; int
0x140077f02  mov     edx, [r13+58h]; void *
0x140077f06  mov     rcx, [r13+50h]; this
0x140077f0a  call    ?StretchDIBDirect@stretch@@YAHPEAXJKKPEAU_RECTL@@0JKK111K@Z; stretch::StretchDIBDirect(void *,long,ulong,ulong,_RECTL *,void *,long,ulong,ulong,_RECTL *,_RECTL *,_RECTL *,ulong)
0x140077f0f  mov     eax, [rsp+5C8h+var_2E8.left]
0x140077f16  mov     dword ptr [rsp+5C8h+var_2D8], eax
0x140077f1d  mov     ecx, [rsp+5C8h+var_2E8.right]
0x140077f24  mov     dword ptr [rsp+5C8h+var_2D8+8], ecx
0x140077f2b  mov     edx, [rsp+5C8h+var_2E8.top]
  ... truncated ...
```
