# EngStretchBltNew(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong)

- ea: `0x1400f9438`
- end: `0x1400fb655`
- name: `?EngStretchBltNew@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54K@Z`
- size: `8733`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400f8e90`

## callees

- `0x14006ec10`
- `0x1400f6d54`
- `0x1400f8e58`
- `0x1400f9438`
- `0x1400fb65c`
- `0x1400fb69c`
- `0x1400fb6c8`
- `0x1400fbd70`
- `0x1400fbff0`
- `0x1400fc428`
- `0x14012a770`
- `0x14013c30c`
- `0x140156d5c`
- `0x1401643b0`
- `0x1401b1e94`
- `0x1401b77d0`
- `0x140296924`
- `0x140329310`
- `0x140329500`
- `0x140329570`
- `0x1403295f0`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!Win32AllocPool` at `0x1400f9f6b`
- `win32kbase!Win32AllocPool` at `0x1400f9f6b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fa2b8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fa513`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fb221`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fa2b8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fa513`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400fb221`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400f9a75`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400f9a96`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400f9aaa`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400fa7e3`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400fa804`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400f9a75`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400f9a96`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400f9aaa`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400fa7e3`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400fa804`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fad90`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb13e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fad90`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400fb13e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fab1f`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fb1b8`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fb484`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fb4a2`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fab1f`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fb1b8`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fb484`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1400fb4a2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400fab46`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400fb1df`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400fab46`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400fb1df`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400fb4c5`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1400fb4c5`
- `win32kbase!EngLockSurface` at `0x1400f9bca`
- `win32kbase!EngLockSurface` at `0x1400f9bca`
- `win32kbase!EngUnlockSurface` at `0x1400f9c66`
- `win32kbase!EngUnlockSurface` at `0x1400f9c66`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400f97af`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400f9cb3`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400fb215`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400f97af`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400f9cb3`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1400fb215`
- `win32kbase!EngCreateBitmap` at `0x1400f9bb3`
- `win32kbase!EngCreateBitmap` at `0x1400f9bb3`
- `win32kbase!EngDeleteSurface` at `0x1400f9c7a`
- `win32kbase!EngDeleteSurface` at `0x1400f9c7a`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x1400fb514`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x1400fb514`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400f9d10`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400fa091`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400f9d10`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400fa091`
- `win32kbase!FreeTmpBuffer` at `0x1400fa65d`
- `win32kbase!FreeTmpBuffer` at `0x1400fa695`
- `win32kbase!FreeTmpBuffer` at `0x1400fa65d`
- `win32kbase!FreeTmpBuffer` at `0x1400fa695`
- `win32kbase!Win32FreePool` at `0x1400fa6a9`
- `win32kbase!Win32FreePool` at `0x1400fa830`
- `win32kbase!Win32FreePool` at `0x1400fa6a9`
- `win32kbase!Win32FreePool` at `0x1400fa830`

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
  __int64 v50; // rdx
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
  __int64 v83; // rdx
  __int64 v84; // rax
  unsigned int v85; // r9d
  struct _RECTL *v86; // r11
  LONG v87; // edi
  __int64 v88; // rdx
  __int64 v89; // r8
  unsigned int v90; // ecx
  XCLIPOBJ *v91; // rax
  _DWORD *v92; // r11
  LONG v93; // r9d
  struct _RECTL *v94; // r10
  unsigned __int64 v95; // rdi
  __int64 v96; // rax
  unsigned int v97; // r10d
  LONG v98; // ecx
  unsigned __int64 v99; // r8
  unsigned int *v100; // r9
  LONG v101; // ecx
  LONG v102; // edx
  LONG v103; // eax
  XCLIPOBJ *v104; // rsi
  int v105; // edi
  LONG v106; // ecx
  LONG v107; // edx
  LONG v108; // eax
  int v109; // eax
  unsigned int v110; // edx
  unsigned int v111; // ecx
  int v112; // r11d
  LONG v113; // r10d
  LONG v114; // r9d
  LONG v115; // r8d
  LONG v116; // ecx
  LONG v117; // eax
  LONG v118; // edx
  int v119; // eax
  BOOL (__stdcall *v120)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  unsigned __int64 v121; // r9
  stretch *v122; // rdi
  int v123; // eax
  unsigned int v124; // ecx
  __m128i si128; // xmm2
  unsigned int (__fastcall *v126)(struct _SURFOBJ *, SIZEL, _QWORD, XCLIPOBJ *, _QWORD, stretch *, struct _POINTL *, struct _RECTL *, __int128 *, Gre::Base *, unsigned int); // rax
  Gre::Base *v127; // rcx
  struct _SURFOBJ *v128; // r15
  struct Gre::Base::SESSION_GLOBALS *v129; // r9
  BOOL (__stdcall *v130)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  PVOID *v131; // r15
  int v132; // eax
  int v133; // ecx
  __int64 v134; // rcx
  XCLIPOBJ *v135; // rdi
  BOOL (__stdcall *v136)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  struct _RECTL *pvBits; // [rsp+20h] [rbp-5A8h]
  struct _RECTL *v138; // [rsp+28h] [rbp-5A0h]
  void *v139; // [rsp+30h] [rbp-598h]
  struct _RECTL *v140; // [rsp+60h] [rbp-568h]
  unsigned int v141; // [rsp+68h] [rbp-560h]
  unsigned int v142; // [rsp+70h] [rbp-558h]
  __int16 v143; // [rsp+78h] [rbp-550h]
  LONG v144; // [rsp+78h] [rbp-550h]
  unsigned int v145; // [rsp+7Ch] [rbp-54Ch]
  unsigned int v146; // [rsp+80h] [rbp-548h]
  LONG v147; // [rsp+84h] [rbp-544h]
  int v148; // [rsp+88h] [rbp-540h]
  int v149; // [rsp+90h] [rbp-538h]
  LONG v150; // [rsp+90h] [rbp-538h]
  unsigned int v151; // [rsp+98h] [rbp-530h]
  struct REGION *v152; // [rsp+A0h] [rbp-528h] BYREF
  __int64 v153; // [rsp+A8h] [rbp-520h] BYREF
  LONG v154; // [rsp+B0h] [rbp-518h]
  LONG v155; // [rsp+B4h] [rbp-514h]
  __int64 p_lDelta; // [rsp+B8h] [rbp-510h]
  struct REGION *v157; // [rsp+C0h] [rbp-508h] BYREF
  SIZEL sizl; // [rsp+C8h] [rbp-500h]
  unsigned int v159; // [rsp+D0h] [rbp-4F8h]
  LONG v160; // [rsp+D4h] [rbp-4F4h]
  HSURF hsurf; // [rsp+D8h] [rbp-4F0h] BYREF
  LONG v162; // [rsp+E0h] [rbp-4E8h]
  LONG v163; // [rsp+E4h] [rbp-4E4h]
  LONG v164; // [rsp+F0h] [rbp-4D8h]
  _DWORD *v165; // [rsp+100h] [rbp-4C8h]
  struct _RECTL *v166; // [rsp+108h] [rbp-4C0h]
  unsigned __int64 v167; // [rsp+110h] [rbp-4B8h]
  struct REGION *v168; // [rsp+118h] [rbp-4B0h] BYREF
  PVOID *v169; // [rsp+120h] [rbp-4A8h]
  XCLIPOBJ *v170; // [rsp+128h] [rbp-4A0h]
  __int64 v171; // [rsp+130h] [rbp-498h]
  char *v172; // [rsp+138h] [rbp-490h]
  struct _SURFOBJ *p_right; // [rsp+140h] [rbp-488h]
  unsigned __int64 v174; // [rsp+148h] [rbp-480h]
  struct _SURFOBJ *v175; // [rsp+150h] [rbp-478h]
  __int64 v176; // [rsp+158h] [rbp-470h]
  XCLIPOBJ *v177; // [rsp+160h] [rbp-468h]
  unsigned int v178; // [rsp+168h] [rbp-460h]
  unsigned int v179; // [rsp+16Ch] [rbp-45Ch]
  struct _POINTL *v180; // [rsp+170h] [rbp-458h]
  stretch *v181; // [rsp+178h] [rbp-450h]
  unsigned int v182; // [rsp+180h] [rbp-448h]
  PVOID *v183; // [rsp+188h] [rbp-440h]
  Gre::Base *v184; // [rsp+190h] [rbp-438h]
  void (*const near *v185)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *); // [rsp+198h] [rbp-430h]
  _QWORD v186[3]; // [rsp+1A0h] [rbp-428h] BYREF
  stretch *v187[3]; // [rsp+1B8h] [rbp-410h] BYREF
  _DWORD *v188; // [rsp+1D0h] [rbp-3F8h]
  struct _SURFOBJ *v189; // [rsp+1D8h] [rbp-3F0h]
  __int64 v190; // [rsp+1E0h] [rbp-3E8h]
  unsigned int *v191; // [rsp+1E8h] [rbp-3E0h]
  LONG *v192; // [rsp+1F0h] [rbp-3D8h]
  stretch *v193; // [rsp+1F8h] [rbp-3D0h]
  struct _SURFOBJ *v194; // [rsp+200h] [rbp-3C8h]
  struct _CLIPOBJ *v195; // [rsp+208h] [rbp-3C0h]
  struct _POINTL *v196; // [rsp+210h] [rbp-3B8h]
  __int64 v197; // [rsp+218h] [rbp-3B0h]
  struct _RECTL *v198; // [rsp+220h] [rbp-3A8h]
  _DWORD v199[4]; // [rsp+228h] [rbp-3A0h] BYREF
  __int64 v200; // [rsp+238h] [rbp-390h]
  int v201; // [rsp+240h] [rbp-388h]
  int v202; // [rsp+244h] [rbp-384h]
  _DWORD v203[4]; // [rsp+248h] [rbp-380h] BYREF
  __int64 v204; // [rsp+258h] [rbp-370h]
  int v205; // [rsp+260h] [rbp-368h]
  int v206; // [rsp+264h] [rbp-364h]
  LONG *p_bottom; // [rsp+268h] [rbp-360h]
  LONG *v208; // [rsp+270h] [rbp-358h]
  struct _POINTL *v209; // [rsp+278h] [rbp-350h]
  _DWORD *v210; // [rsp+280h] [rbp-348h]
  _QWORD *v211; // [rsp+288h] [rbp-340h]
  void (*const near *v212)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *); // [rsp+290h] [rbp-338h]
  int *v213; // [rsp+298h] [rbp-330h]
  _DWORD *v214; // [rsp+2A0h] [rbp-328h]
  _DWORD *v215; // [rsp+2A8h] [rbp-320h]
  int *v216; // [rsp+2B0h] [rbp-318h]
  struct REGION *v217; // [rsp+2B8h] [rbp-310h]
  _QWORD v218[4]; // [rsp+2C0h] [rbp-308h] BYREF
  struct _RECTL v219; // [rsp+2E0h] [rbp-2E8h] BYREF
  unsigned __int128 v220; // [rsp+2F0h] [rbp-2D8h] BYREF
  struct _RECTL v221; // [rsp+300h] [rbp-2C8h] BYREF
  struct _RECTL v222; // [rsp+310h] [rbp-2B8h] BYREF
  struct _RECTL v223; // [rsp+320h] [rbp-2A8h] BYREF
  int v224; // [rsp+330h] [rbp-298h]
  __int128 v225; // [rsp+338h] [rbp-290h] BYREF
  __m128i v226; // [rsp+348h] [rbp-280h] BYREF
  __int128 v227; // [rsp+358h] [rbp-270h] BYREF
  struct _RECTL v228; // [rsp+368h] [rbp-260h] BYREF
  struct _RECTL v229; // [rsp+378h] [rbp-250h] BYREF
  _BYTE v230[160]; // [rsp+390h] [rbp-238h] BYREF
  _BYTE v231[160]; // [rsp+430h] [rbp-198h] BYREF
  _BYTE v232[4]; // [rsp+4D0h] [rbp-F8h] BYREF
  char v233[156]; // [rsp+4D4h] [rbp-F4h] BYREF

  v170 = (XCLIPOBJ *)a4;
  v175 = a3;
  p_right = a1;
  v167 = (unsigned __int64)a5;
  v184 = (Gre::Base *)a10;
  v209 = a10;
  v12 = a8;
  v13 = a9;
  v194 = a3;
  v195 = a4;
  v181 = (stretch *)a6;
  v180 = a7;
  v196 = a10;
  v142 = a11;
  if ( a11 - 1 > 3 )
    return 0;
  p_pvScan0 = &a1[-1].pvScan0;
  if ( !a1 )
    p_pvScan0 = 0;
  v169 = p_pvScan0;
  v15 = (stretch *)&a2[-1].pvScan0;
  if ( !a2 )
    v15 = 0;
  if ( a3 )
  {
    v172 = (char *)&a3[-1].pvScan0;
    p_lDelta = (__int64)&a3->lDelta;
    v171 = (__int64)&a3->pvScan0;
  }
  else
  {
    v172 = 0;
    p_lDelta = 88;
    v171 = 80;
  }
  if ( !p_pvScan0 )
    return 0;
  if ( !v15 )
    return 0;
  v189 = (struct _SURFOBJ *)(p_pvScan0 + 3);
  v16 = *((_DWORD *)p_pvScan0 + 24);
  if ( (unsigned int)(v16 - 7) <= 2 )
    return 0;
  v17 = *((_DWORD *)v15 + 24);
  if ( v17 == 9 || v16 == 10 || v17 == 10 )
    return 0;
  if ( a9->left != a9->right && a9->top != a9->bottom && a8->left != a8->right && a8->top != a8->bottom )
  {
    v152 = (struct REGION *)p_pvScan0[6];
    v18 = *((_QWORD *)v15 + 6);
    SURFMEM::SURFMEM(v218, 2);
    v229 = *a9;
    v24 = v23 - 1;
    if ( a2->iType == (_WORD)v23 - 1 && v18 && (*(_DWORD *)(v18 + 40) & 0x20000) != 0 )
    {
      if ( !(unsigned int)MulCopyDeviceToDIB(a2, (struct SURFMEM *)v218, &v229) )
        goto LABEL_189;
      if ( !v218[0] )
        goto LABEL_78;
      v13 = &v229;
      a2 = (struct _SURFOBJ *)((v218[0] + 24LL) & -(__int64)(v218[0] != 0));
      v15 = (stretch *)&a2[-1].pvScan0;
      if ( !a2 )
        v15 = 0;
      v18 = *((_QWORD *)v15 + 6);
      v21 = p_right;
      v19 = (struct tagCOLORADJUSTMENT *)v181;
      v20 = (__int64 *)v180;
      v22 = (CLIPOBJ *)v170;
    }
    if ( v167 && (*(_DWORD *)(v167 + 4) & 8) != 0 )
    {
      if ( a2->iType )
        goto LABEL_189;
      if ( v21->iType != (_WORD)v24 )
        goto LABEL_189;
      v25 = v24;
      v146 = v24;
      v179 = v24;
      v26 = (__int64)v175;
      if ( v175 )
        goto LABEL_189;
    }
    else
    {
      v25 = 0;
      v146 = 0;
      v179 = 0;
      v26 = (__int64)v175;
    }
    v27 = a11;
    if ( a11 == 4 )
    {
      if ( v25 )
        goto LABEL_189;
      v109 = EngHTBlt(v21, a2, v26, v22, (struct XLATE *)v167, v19, v20, (XLATEOBJ *)a8, (POINTL)v13, v184, 0, 0);
      if ( v109 == -1 )
        goto LABEL_189;
      if ( v109 )
      {
        if ( v109 == v24 )
          goto LABEL_78;
        v27 = 4;
      }
      else
      {
        v27 = 3;
        v142 = 3;
      }
    }
    top = a8->top;
    bottom = a8->bottom;
    if ( bottom < top )
    {
      a8->top = bottom;
      a8->bottom = top;
      v30 = 2;
      v149 = 2;
      v31 = bottom;
    }
    else
    {
      v30 = 0;
      v149 = 0;
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
      v149 = v30;
      v34 = right;
    }
    else
    {
      v34 = a8->left;
      left = a8->right;
    }
    if ( v27 >= 3 || v172 )
    {
      v35 = 0;
      v145 = 0;
      goto LABEL_28;
    }
    v145 = v24;
    if ( left - v34 < v13->right - v13->left )
    {
      v27 = v142;
    }
    else
    {
      v27 = v142;
      if ( top - v31 >= v13->bottom - v13->top )
      {
        v145 = 0;
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
      v142 = v27;
    }
    v188 = v169 + 20;
    v36 = *((_DWORD *)v169 + 40);
    if ( (v36 & 0x40000) == 0
      && (v167 && ((unsigned __int8)*(_DWORD *)(v167 + 4) & (unsigned __int8)v24) == 0 || a2->iType) )
    {
      if ( *((_WORD *)v169 + 50) )
      {
        if ( (v36 & 2) != 0 && !v30 && !v175 )
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
                  v227 = 0;
                  v155 = v60 - v58;
                  sizl.cx = v60 - v58;
                  v62 = v61 - v59;
                  v163 = v62;
                  sizl.cy = v62;
                  if ( v60 - v58 <= a8->right - a8->left && v62 <= a8->bottom - a8->top )
                  {
                    hsurf = (HSURF)EngCreateBitmap(sizl, 0, p_right->iBitmapFormat, 0, 0);
                    v63 = EngLockSurface(hsurf);
                    sizl = (SIZEL)v63;
                    if ( v63 )
                    {
                      v63->iUniq = 0;
                      *(_QWORD *)&v227 = 0;
                      *((_QWORD *)&v227 + 1) = __PAIR64__(v163, v155);
                      if ( (*((_DWORD *)v15 + 40) & 0x400) != 0 )
                        v64 = (*(__int64 (__fastcall **)(SURFOBJ *, struct _SURFOBJ *, _QWORD, unsigned __int64, __int128 *, struct _RECTL *))(v18 + 2832))(
                                v63,
                                a2,
                                0,
                                v167,
                                &v227,
                                v13);
                      else
                        v64 = ((__int64 (__fastcall *)(SURFOBJ *, struct _SURFOBJ *, _QWORD, unsigned __int64, __int128 *, struct _RECTL *))EngCopyBits)(
                                v63,
                                a2,
                                0,
                                v167,
                                &v227,
                                v13);
                      if ( !v64
                        || (v126 = (unsigned int (__fastcall *)(struct _SURFOBJ *, SIZEL, _QWORD, XCLIPOBJ *, _QWORD, stretch *, struct _POINTL *, struct _RECTL *, __int128 *, Gre::Base *, unsigned int))*((_QWORD *)v152 + 355)) == 0
                        || !((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v126)(
                              p_right,
                              sizl,
                              0,
                              v170,
                              0,
                              v181,
                              v180,
                              a8,
                              &v227,
                              v184,
                              v142) )
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
    v217 = v152;
    SURFMEM::SURFMEM(v186, 2);
    v226 = 0;
    ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v230);
    v221 = 0;
    v153 = 0;
    v37 = *((_DWORD *)v15 + 15);
    v38 = *((_DWORD *)v15 + 14);
    *(_QWORD *)&v219.left = 0;
    v219.right = v38;
    v219.bottom = v37;
    v220 = 0;
    RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v157);
    v143 = *((_WORD *)v169 + 50);
    if ( v143 || v169[4] == *((PVOID *)v15 + 4) )
    {
      v226 = *(__m128i *)a8;
      v112 = _mm_cvtsi128_si32(v226);
      v113 = v112 - 1;
      v155 = a8->right;
      v114 = v155 + 1;
      v115 = v24 + HIDWORD(*(_QWORD *)&a8->right);
      v116 = *((_DWORD *)v169 + 15);
      v117 = *((_DWORD *)v169 + 14);
      if ( v112 - 1 < 0 )
        v113 = 0;
      v221.left = v113;
      v118 = v226.m128i_i32[1] - v24;
      if ( (int)(v226.m128i_i32[1] - v24) < 0 )
        v118 = 0;
      v221.top = v118;
      if ( v117 < v114 )
        v114 = v117;
      v221.right = v114;
      if ( v116 < v115 )
        v115 = v116;
      v221.bottom = v115;
      if ( v114 < v113 )
      {
        v113 = v114;
        v221.left = v114;
      }
      else
      {
        if ( v115 < v118 )
          v118 = v115;
        v221.top = v118;
      }
      if ( v118 == v115 || v113 == v114 )
        goto LABEL_77;
      if ( v143 || v113 <= v13->right && v114 >= v13->left && v118 <= v13->bottom && v115 >= v13->top )
      {
        v226.m128i_i32[0] = v112 - v113;
        v226.m128i_i32[1] -= v118;
        v226.m128i_i32[2] = v155 - v113;
        v226.m128i_i32[3] -= v118;
        v199[3] = 0;
        v202 = 0;
        v199[1] = v24 + v114 - v113;
        v199[2] = v24 + v115 - v118;
        v200 = 0;
        v131 = v169;
        if ( v146 )
          v132 = *((_DWORD *)v15 + 24);
        else
          v132 = *((_DWORD *)v169 + 24);
        v199[0] = v132;
        v201 = *v188 & 0x40000;
        SURFMEM::bCreateDIB((SURFMEM *)v186, (struct _DEVBITMAPINFO *)v199, 0, 0, 0, 0, 0, 0, v24, 0);
        if ( !v186[0] )
          goto LABEL_188;
        v153 = *(_QWORD *)&v221.left;
        if ( !v157 )
          goto LABEL_188;
        *(_QWORD *)&v221.left = 0;
        v221.right -= v153;
        v221.bottom -= HIDWORD(v153);
        RGNOBJ::vSet((RGNOBJ *)&v157, &v221);
        XCLIPOBJ::vSetup((XCLIPOBJ *)v230, v157, (const struct ERECTL *)&v221, v24);
        hsurf = (HSURF)v131[6];
        v128 = v189;
        if ( hsurf )
          PDEVOBJ::vSync((PDEVOBJ *)&hsurf, v189, 0, 0);
        v129 = Gre::Base::Globals(v127);
        if ( v172 )
        {
          if ( (*v188 & 0x400) != 0 )
            v130 = (BOOL (__stdcall *)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))*((_QWORD *)v152 + 354);
          else
            v130 = EngCopyBits;
          v138 = (struct _RECTL *)&v153;
          ((void (__fastcall *)(__int64, struct _SURFOBJ *, _QWORD, char *, struct _RECTL *))v130)(
            (v186[0] + 24LL) & -(__int64)(v186[0] != 0),
            v128,
            0,
            (char *)v129 + 4664,
            &v221);
        }
        v183 = (PVOID *)v186[0];
        v12 = (struct _RECTL *)&v226;
        v177 = (XCLIPOBJ *)v230;
LABEL_34:
        v172 = (char *)v12;
        hsurf = (HSURF)*((_QWORD *)v15 + 6);
        if ( hsurf )
          PDEVOBJ::vSync((PDEVOBJ *)&hsurf, a2, 0, 0);
        v39 = v219.left;
        if ( v13->left > v219.left )
          v39 = v13->left;
        v219.left = v39;
        v40 = v219.top;
        if ( v13->top > v219.top )
          v40 = v13->top;
        v219.top = v40;
        v41 = v219.right;
        if ( v13->right < v219.right )
          v41 = v13->right;
        v219.right = v41;
        v42 = v219.bottom;
        if ( v13->bottom < v219.bottom )
          v42 = v13->bottom;
        v219.bottom = v42;
        if ( v41 < v39 )
        {
          v39 = v41;
          v219.left = v41;
        }
        else
        {
          if ( v42 < v40 )
            v40 = v42;
          v219.top = v40;
        }
        if ( v40 == v42 || v39 == v41 )
          goto LABEL_77;
        SURFMEM::SURFMEM(v187, 2);
        v225 = 0;
        if ( v149 || *((_WORD *)v15 + 50) || *((_DWORD *)v15 + 24) - 7 <= v24 )
        {
          v203[3] = 0;
          v206 = 0;
          v203[1] = v45 - v46;
          v203[2] = v44 - v43;
          v204 = 0;
          if ( v146 )
            v119 = *((_DWORD *)v15 + 24);
          else
            v119 = *((_DWORD *)v183 + 24);
          v203[0] = v119;
          v205 = *((_DWORD *)v15 + 40) & 0x40000;
          SURFMEM::bCreateDIB((SURFMEM *)v187, (struct _DEVBITMAPINFO *)v203, 0, 0, 0, 0, 0, 0, v24, 0);
          if ( !v187[0] )
            goto LABEL_187;
          *(_QWORD *)&v225 = 0;
          DWORD2(v225) = v219.right - v219.left;
          HIDWORD(v225) = v219.bottom - v219.top;
          if ( (*((_DWORD *)v15 + 40) & 0x400) != 0 )
            v120 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v18 + 2832);
          else
            v120 = EngCopyBits;
          v121 = 0;
          if ( !v146 )
            v121 = v167;
          v138 = &v219;
          ((void (__fastcall *)(unsigned __int64, char *, _QWORD, unsigned __int64, __int128 *))v120)(
            ((unsigned __int64)v187[0] + 24) & -(__int64)(v187[0] != 0),
            (char *)v15 + 24,
            0,
            v121,
            &v225);
          LODWORD(v225) = v13->left - v219.left;
          DWORD1(v225) = v13->top - v219.top;
          DWORD2(v225) = v13->right - v219.left;
          HIDWORD(v225) = v13->bottom - v219.top;
          v122 = v187[0];
          v15 = v187[0];
          v181 = v187[0];
          v13 = (struct _RECTL *)&v225;
          v180 = (struct _POINTL *)&v225;
          v174 = 0;
          v219.right -= v219.left;
          v123 = v219.bottom - v219.top;
          v219.bottom -= v219.top;
          *(_QWORD *)&v219.left = 0;
          if ( (v149 & 2) != 0 )
          {
            v133 = *((_DWORD *)v187[0] + 22);
            if ( v133 <= 0 )
              v134 = *((_QWORD *)v187[0] + 9);
            else
              v134 = *((_QWORD *)v187[0] + 9) + v133 * (v123 - 1);
            *((_QWORD *)v187[0] + 10) = v134;
            *((_DWORD *)v187[0] + 22) = -*((_DWORD *)v187[0] + 22);
            v122 = v187[0];
          }
          if ( ((unsigned __int8)v149 & (unsigned __int8)v24) != 0 )
          {
            v124 = *((_DWORD *)v122 + 24);
            if ( v124 - 1 > 5 )
              goto LABEL_187;
            ((void (__fastcall *)(stretch *))funcs_14007E20E[v124 - 1])(v122);
          }
          v47 = 0;
        }
        else
        {
          v181 = v15;
          v180 = (struct _POINTL *)v13;
          v47 = 0;
          if ( !v146 )
            v47 = v167;
          v174 = v47;
        }
        v48 = v183;
        hsurf = (HSURF)v183[6];
        if ( hsurf )
          PDEVOBJ::vSync(
            (PDEVOBJ *)&hsurf,
            (struct _SURFOBJ *)((unsigned __int64)(v183 + 3)
                              & ((unsigned __int128)-(__int128)(unsigned __int64)v183 >> 64)),
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
        v50 = (unsigned int)(v12->bottom - v12->top);
        if ( (int)v50 >= 128000000 || v49 <= -128000000 || (int)v50 <= -128000000 )
          goto LABEL_187;
        if ( v142 == 3 && !v175 && (!v47 || ((unsigned __int8)*(_DWORD *)(v47 + 4) & (unsigned __int8)v24) != 0) )
        {
          v51 = *((_DWORD *)v15 + 24);
          v50 = *((unsigned int *)v48 + 24);
          if ( (_DWORD)v50 == v51 && ((v51 - 3) & 0xFFFFFFFC) == 0 && v51 != 5 )
          {
            if ( v177 && *((_BYTE *)v177 + 20) == 3 )
            {
              v222 = 0;
              *(_QWORD *)&v219.right = 0;
              *(_QWORD *)&v219.left = 0;
              v223 = 0;
              v224 = 0;
              v104 = v170;
              XCLIPOBJ::cEnumStart(v170, 0, 0, 4u, 0);
              do
              {
                v105 = XCLIPOBJ::bEnum(v104, 0x14u, &v223, 0);
                if ( v223.left )
                {
                  LODWORD(v140) = *((_DWORD *)v48 + 24);
                  LODWORD(v139) = *((_DWORD *)v15 + 22);
                  stretch::StretchDIBDirect(
                    (stretch *)v48[10],
                    (void *)*((unsigned int *)v48 + 22),
                    *((_DWORD *)v48 + 14),
                    *((_DWORD *)v48 + 15),
                    (unsigned int)v12,
                    *((struct _RECTL **)v15 + 10),
                    v139,
                    *((_DWORD *)v15 + 14),
                    *((_DWORD *)v15 + 15),
                    (unsigned int)v13,
                    &v222,
                    (struct _RECTL *)&v223.top,
                    v140,
                    v141);
                  v106 = v219.left;
                  v107 = v219.right;
                  if ( v219.left == v219.right || (v108 = v219.top, v219.top == v219.bottom) )
                  {
                    si128 = _mm_load_si128((const __m128i *)&v222);
                    v219.bottom = _mm_cvtsi128_si32(_mm_srli_si128(si128, 12));
                    v219.right = _mm_cvtsi128_si32(_mm_srli_si128(si128, 8));
                    v219.top = _mm_cvtsi128_si32(_mm_srli_si128(si128, 4));
                    v219.left = si128.m128i_i32[0];
                  }
                  else
                  {
                    if ( v222.left < v219.left )
                      v106 = v222.left;
                    v219.left = v106;
                    if ( v222.top < v219.top )
                      v108 = v222.top;
                    v219.top = v108;
                    if ( v222.right > v219.right )
                      v107 = v222.right;
                    v219.right = v107;
                    if ( v222.bottom > v219.bottom )
                      v219.bottom = v222.bottom;
                  }
                }
              }
              while ( v105 );
              v24 = 1;
            }
            else
            {
              v52 = v12;
              if ( v177 && *((_BYTE *)v177 + 20) == (_BYTE)v24 )
                v52 = (struct _RECTL *)((char *)v177 + 4);
              LODWORD(v140) = *((_DWORD *)v48 + 24);
              LODWORD(v139) = *((_DWORD *)v15 + 22);
              stretch::StretchDIBDirect(
                (stretch *)v48[10],
                (void *)*((unsigned int *)v48 + 22),
                *((_DWORD *)v48 + 14),
                *((_DWORD *)v48 + 15),
                (unsigned int)v12,
                *((struct _RECTL **)v15 + 10),
                v139,
                *((_DWORD *)v15 + 14),
                *((_DWORD *)v15 + 15),
                (unsigned int)v13,
                &v219,
                v52,
                v140,
                v141);
            }
            v53 = v219.left;
            v220 = (unsigned __int128)v219;
            v54 = v219.right;
            v55 = v219.top;
            v56 = v219.bottom;
LABEL_75:
            if ( v48 == v169 )
            {
LABEL_76:
              SURFMEM::~SURFMEM((SURFMEM *)v187);
LABEL_77:
              RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v157);
              SURFMEM::~SURFMEM((SURFMEM *)v186);
LABEL_78:
              SURFMEM::~SURFMEM((SURFMEM *)v218);
              return v24;
            }
            LODWORD(v220) = v153 + v53;
            DWORD1(v220) = HIDWORD(v153) + v55;
            DWORD2(v220) = v153 + v54;
            HIDWORD(v220) = HIDWORD(v153) + v56;
            RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v168);
            if ( !v168 )
              goto LABEL_271;
            v135 = v170;
            if ( v170 )
            {
              RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v152);
              if ( !v152
                || (RGNOBJ::vSet((RGNOBJ *)&v152, (const struct _RECTL *const)&v220),
                    !RGNOBJ::bMerge((RGNOBJ *)&v168, (struct RGNOBJ *)&v152, (XCLIPOBJ *)((char *)v135 + 56), 8u)) )
              {
                RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v152);
LABEL_271:
                RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v168);
                goto LABEL_187;
              }
              RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v152);
            }
            else
            {
              RGNOBJ::vSet((RGNOBJ *)&v168, (const struct _RECTL *const)&v220);
            }
            v228 = *(struct _RECTL *)((char *)v168 + 52);
            if ( !v135 || bIntersect(&v228, (const struct _RECTL *)((char *)v135 + 4), &v228) )
            {
              ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v232, v168, (struct ERECTL *)&v228, v24);
              if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)v233) )
              {
                v221.left += v153;
                v221.top += HIDWORD(v153);
                v221.right += v153;
                v221.bottom += HIDWORD(v153);
                v153 = 0;
                if ( (*v188 & 0x400) != 0 )
                  v136 = (BOOL (__stdcall *)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))*((_QWORD *)v217 + 354);
                else
                  v136 = EngCopyBits;
                ((void (__fastcall *)(struct _SURFOBJ *, __int64, _BYTE *, unsigned __int64, struct _RECTL *, __int64 *))v136)(
                  v189,
                  (v186[0] + 24LL) & -(__int64)(v186[0] != 0),
                  v232,
                  v167 & -(__int64)(v146 != 0),
                  &v221,
                  &v153);
              }
            }
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v168);
            goto LABEL_76;
          }
        }
        v65 = (unsigned int *)AllocFreeTmpBuffer(324, v50, 3);
        v191 = v65;
        if ( v65 )
        {
          v211 = (_QWORD *)v171;
          v210 = (_DWORD *)p_lDelta;
          v216 = (int *)p_lDelta;
          v182 = v142;
          v66 = v177;
          v67 = 0;
          v151 = 0;
          if ( v177 )
          {
            if ( *((_BYTE *)v177 + 20) )
            {
              v111 = *((unsigned __int8 *)v177 + 20) - v24;
              if ( v111 )
              {
                if ( v111 == 2 )
                {
                  v151 = v24;
                  XCLIPOBJ::cEnumStart(v177, 0, 0, 4u, 0x14u);
                  v67 = v24;
                  v65 = v191;
                }
LABEL_110:
                v163 = v145;
                v192 = &v13->right;
                p_bottom = &v13->bottom;
                hsurf = (HSURF)&v13->top;
                v208 = &v12->right;
                v193 = v15;
                v220 = 0u;
                if ( v67 )
                  goto LABEL_308;
                while ( 1 )
                {
                  for ( i = 0; ; i = v24 + v155 )
                  {
                    v155 = i;
                    v65 = v191;
                    if ( (unsigned int)i >= *v191 )
                      break;
                    p_lDelta = (__int64)&v191[4 * i + 1];
                    v223 = 0;
                    stretch::vInitStrDDAClip((stretch *)&v219, v13, v12, (struct _RECTL *)p_lDelta, &v223, v138);
                    if ( v223.left != v223.right && v223.top != v223.bottom )
                    {
                      v70 = v223.left - v24;
                      v71 = v223.top - v24;
                      v72 = v24 + v223.right;
                      v73 = v24 + v223.bottom;
                      if ( v219.left > (int)(v223.left - v24) )
                        v70 = v219.left;
                      v154 = v70;
                      v223.left = v70;
                      if ( v219.top > v71 )
                        v71 = v219.top;
                      v147 = v71;
                      v223.top = v71;
                      if ( v219.right < v72 )
                        v72 = v219.right;
                      v162 = v72;
                      v223.right = v72;
                      if ( v219.bottom < v73 )
                        v73 = v219.bottom;
                      v144 = v73;
                      v223.bottom = v73;
                      if ( v72 < v70 )
                      {
                        v154 = v72;
                        v223.left = v72;
                      }
                      else
                      {
                        if ( v73 < v71 )
                          v71 = v73;
                        v147 = v71;
                        v223.top = v71;
                      }
                      if ( SLODWORD(p_right->dhsurf) >= v13->left && *p_bottom >= *(_DWORD *)sizl.cx )
                      {
                        v74 = LODWORD(p_right->dhsurf) - v13->left;
                        v75 = *p_bottom + v74 - *(_DWORD *)sizl.cx;
                        if ( v75 >= v74 && v75 < 0x3FFFFFF5 )
                        {
                          v76 = 4 * v75 + 40;
                          v77 = v76 ? (struct _RECTL *)Win32AllocPool(v76, 1752462151) : 0LL;
                          v166 = v77;
                          if ( v77 )
                          {
                            stretch::vInitStrDDA((stretch *)v77, (struct stretch::_STRDDA *)&v223, v13, v12, pvBits);
                            v78 = *(__m128i *)v77;
                            v222 = *v77;
                            v79 = v174;
                            if ( v174 )
                            {
                              if ( ((unsigned __int8)v24 & *(_BYTE *)(v174 + 4)) != 0 )
                                v79 = 0;
                              v174 = v79;
                            }
                            v80 = *((unsigned int *)v48 + 24);
                            if ( v145 )
                              v77[1].top = (v182 != v24) - v24;
                            v150 = _mm_cvtsi128_si32(_mm_srli_si128(v78, 8));
                            v164 = _mm_cvtsi128_si32(v78);
                            v81 = v150 - v164;
                            if ( LODWORD(p_right->dhsurf) - v13->left > *v208 - v12->left )
                            {
                              if ( v81 >= 0x15555553 )
                                goto LABEL_192;
                              v82 = v150 - v164;
                            }
                            else if ( v81 + 3 < v81 || (v82 = (v81 + 3) >> 1, v82 >= 0x15555553) )
                            {
LABEL_192:
                              Win32FreePool(v166);
                              continue;
                            }
                            if ( v81 > 0x5F5E100 )
                              goto LABEL_192;
                            if ( 12 * (v82 + 2) > 0x2710000 )
                              goto LABEL_192;
                            v185 = (&stretch::apfnWrite)[v80];
                            v83 = v142 - 1 + 3LL * *((unsigned int *)v15 + 24);
                            v171 = (__int64)*(&stretch::apfnRead + v83);
                            v84 = AllocFreeTmpBuffer(12 * (v82 + 2), v83, 0x140000000uLL);
                            v165 = (_DWORD *)v84;
                            if ( !v84 )
                              goto LABEL_192;
                            v86 = v166;
                            v198 = v166;
                            v160 = *((_DWORD *)v193 + 22);
                            v190 = *((_QWORD *)v193 + 10);
                            v197 = 0;
                            v87 = v147;
                            if ( v175 )
                            {
                              LODWORD(v197) = v209->x + v154 - v13->left;
                              v176 = *v211 + *v210 * (v147 + *((_DWORD *)v184 + 1) - *(_DWORD *)sizl.cx);
                              v84 = (__int64)v165;
                            }
                            else
                            {
                              v176 = 0;
                            }
                            v159 = 0;
                            v178 = 0;
                            if ( v145 )
                            {
                              v110 = -1;
                              if ( v182 != v24 )
                                v110 = 0;
                              v159 = v110;
                              stretch::vInitBuffer(
                                (stretch *)(v84 + 8),
                                (struct stretch::_XRUNLEN *)&v222,
                                (struct _RECTL *)v110,
                                v85);
                              v178 = v159;
                            }
                            *v165 = v86->top;
                            RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v152);
                            ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v231);
                            v90 = 0;
                            v91 = v177;
                            if ( !v177 )
                              goto LABEL_147;
                            if ( v152 )
                            {
                              RGNOBJ::vSet((RGNOBJ *)&v152, (const struct _RECTL *const)p_lDelta);
                              XCLIPOBJ::vSetup((XCLIPOBJ *)v231, v152, (const struct ERECTL *)p_lDelta, v24);
                              v90 = v24;
                              v91 = v177;
                            }
                            if ( !v91 || v152 )
                            {
LABEL_147:
                              v213 = (int *)((char *)v193 + 88);
                              v212 = v185;
                              v185 = (void (*const near *)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *))v171;
                              v92 = v165;
                              v215 = v165;
                              p_lDelta = v190 + v147 * v160;
                              LODWORD(v190) = v90;
                              v89 = 0;
                              v93 = v144;
                              while ( 1 )
                              {
                                v148 = v89;
                                v160 = v87;
                                if ( v87 >= v93 )
                                  goto LABEL_167;
                                v94 = v166;
                                v88 = *(unsigned int *)(*(_QWORD *)&v166[1].right + 4LL * (int)v89);
                                v214 = v92 + 1;
                                v92[1] = v88;
                                if ( (_DWORD)v88 )
                                  break;
                                if ( v145 )
                                {
                                  LODWORD(v138) = v154;
                                  ((void (__fastcall *)(struct _RECTL *, _DWORD *, __int64, _QWORD, unsigned __int64))v171)(
                                    v94,
                                    v92,
                                    p_lDelta,
                                    0,
                                    v174);
                                  v92 = v165;
                                  LODWORD(v89) = v148;
                                  v93 = v144;
                                }
LABEL_157:
                                p_lDelta += *v213;
                                *v215 += *v214;
                                if ( v176 )
                                  v176 += *v216;
                                v87 += v24;
                                v147 = v87;
                                v89 = v24 + (unsigned int)v89;
                                v48 = v183;
                              }
                              v95 = (unsigned __int64)v231 & -(__int64)((_DWORD)v190 != 0);
                              LODWORD(v138) = v154;
                              v96 = ((__int64 (__fastcall *)(struct _RECTL *, _DWORD *, __int64, __int64, unsigned __int64))v171)(
                                      v94,
                                      v92,
                                      p_lDelta,
                                      v176,
                                      v174);
                              ((void (__fastcall *)(_DWORD *, __int64, PVOID *, unsigned __int64))v212)(
                                v165,
                                v96,
                                v48,
                                v95);
                              v87 = v147;
                              v97 = v159;
                              v93 = v144;
                              v98 = v164;
                              v88 = (unsigned int)v150;
                              v92 = v165;
                              if ( v145 )
                              {
                                v165[2] = v164;
                                v92[3] = v150 - v98;
                                v99 = (v150 - v98) & 0x3FFFFFFFFFFFFFFFLL;
                                if ( v99 )
                                {
                                  v100 = v92 + 4;
                                  if ( (((_BYTE)v92 + 16) & 4) != 0 )
                                  {
                                    *v100 = v97;
                                    if ( --v99 )
                                    {
                                      v100 = v92 + 5;
                                      goto LABEL_153;
                                    }
                                  }
                                  else
                                  {
LABEL_153:
                                    v88 = v97;
                                    memset64(v100, v97 | ((unsigned __int64)v97 << 32), v99 >> 1);
                                    v87 = v147;
                                    if ( ((unsigned __int8)v99 & (unsigned __int8)v24) != 0 )
                                      v100[v99 - 1] = v97;
                                  }
                                  v93 = v144;
                                }
                              }
                              LODWORD(v89) = v148;
                              goto LABEL_157;
                            }
                            v92 = v165;
LABEL_167:
                            FreeTmpBuffer(v92, v88, v89);
                            Win32FreePool(v166);
                            v101 = v220;
                            v102 = DWORD2(v220);
                            if ( (_DWORD)v220 == DWORD2(v220) || (v103 = DWORD1(v220), DWORD1(v220) == HIDWORD(v220)) )
                            {
                              v220 = (unsigned __int128)v78;
                            }
                            else
                            {
                              if ( v164 < (int)v220 )
                                v101 = v164;
                              LODWORD(v220) = v101;
                              if ( v222.top < SDWORD1(v220) )
                                v103 = v222.top;
                              DWORD1(v220) = v103;
                              if ( v150 > SDWORD2(v220) )
                                v102 = v150;
                              DWORD2(v220) = v102;
                              if ( v222.bottom > SHIDWORD(v220) )
                                HIDWORD(v220) = v222.bottom;
                            }
                            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v152);
                          }
                        }
                      }
                    }
                  }
                  v66 = v177;
                  if ( !v151 )
                  {
                    FreeTmpBuffer(v191, 0, v191);
                    v56 = HIDWORD(v220);
                    v54 = DWORD2(v220);
                    v55 = DWORD1(v220);
                    v53 = v220;
                    goto LABEL_75;
                  }
LABEL_308:
                  v151 = XCLIPOBJ::bEnum(v66, 0x144u, v65, 0);
                }
              }
              v151 = 0;
              *v65 = v24;
              v68 = *(struct _RECTL *)((char *)v66 + 4);
LABEL_109:
              *(struct _RECTL *)(v65 + 1) = v68;
              goto LABEL_110;
            }
            v151 = 0;
          }
          *v65 = v24;
          v68 = *v12;
          goto LABEL_109;
        }
LABEL_187:
        SURFMEM::~SURFMEM((SURFMEM *)v187);
LABEL_188:
        RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v157);
        SURFMEM::~SURFMEM((SURFMEM *)v186);
LABEL_189:
        v24 = 0;
        goto LABEL_78;
      }
      v183 = v169;
    }
    else
    {
      v183 = v169;
    }
    v177 = v170;
    goto LABEL_34;
  }
  return 1;
}

```

## disassembly

```asm
0x1400f9438  mov     rax, rsp
0x1400f943b  push    rbx
0x1400f943c  push    rsi
0x1400f943d  push    rdi
0x1400f943e  push    r12
0x1400f9440  push    r13
0x1400f9442  push    r14
0x1400f9444  push    r15
0x1400f9446  sub     rsp, 590h
0x1400f944d  movaps  xmmword ptr [rax-48h], xmm6
0x1400f9451  mov     rax, cs:__security_cookie
0x1400f9458  xor     rax, rsp
0x1400f945b  mov     [rsp+5C8h+var_58], rax
0x1400f9463  mov     r11, r9
0x1400f9466  mov     [rsp+5C8h+var_4A0], r9
0x1400f946e  mov     rdi, r8
0x1400f9471  mov     [rsp+5C8h+var_478], r8
0x1400f9479  mov     r13, rdx
0x1400f947c  mov     r10, rcx
0x1400f947f  mov     [rsp+5C8h+var_488], rcx
0x1400f9487  mov     rax, [rsp+5C8h+arg_20]
0x1400f948f  mov     [rsp+5C8h+var_4B8], rax
0x1400f9497  mov     rax, [rsp+5C8h+arg_48]
0x1400f949f  mov     [rsp+5C8h+var_438], rax
0x1400f94a7  mov     [rsp+5C8h+var_350], rax
0x1400f94af  mov     r15, [rsp+5C8h+arg_38]
0x1400f94b7  mov     r12, [rsp+5C8h+arg_40]
0x1400f94bf  mov     [rsp+5C8h+var_3C8], r8
0x1400f94c7  mov     [rsp+5C8h+var_3C0], r9
0x1400f94cf  mov     r8, [rsp+5C8h+arg_28]
0x1400f94d7  mov     [rsp+5C8h+var_450], r8
0x1400f94df  mov     r9, [rsp+5C8h+arg_30]
0x1400f94e7  mov     [rsp+5C8h+var_458], r9
0x1400f94ef  mov     [rsp+5C8h+var_3B8], rax
0x1400f94f7  mov     eax, [rsp+5C8h+arg_50]
0x1400f94fe  mov     [rsp+5C8h+var_558], eax
0x1400f9502  dec     eax
0x1400f9504  cmp     eax, 3
0x1400f9507  ja      loc_1400FAB8A
0x1400f950d  xor     ebx, ebx
0x1400f950f  test    rcx, rcx
0x1400f9512  lea     rdx, [rcx-18h]
0x1400f9516  jz      loc_1400FAB82
0x1400f951c  mov     [rsp+5C8h+var_4A8], rdx
0x1400f9524  test    r13, r13
0x1400f9527  lea     r14, [r13-18h]
0x1400f952b  jz      loc_1400FAB6C
0x1400f9531  test    rdi, rdi
0x1400f9534  jnz     loc_1400FAB91
0x1400f953a  mov     [rsp+5C8h+var_490], rbx
0x1400f9542  mov     [rsp+5C8h+var_510], 58h ; 'X'
0x1400f954e  mov     [rsp+5C8h+var_498], 50h ; 'P'
0x1400f955a  test    rdx, rdx
0x1400f955d  jz      loc_1400FAB8A
0x1400f9563  test    r14, r14
0x1400f9566  jz      loc_1400FAB8A
0x1400f956c  lea     rax, [rdx+18h]
0x1400f9570  mov     [rsp+5C8h+var_3F0], rax
0x1400f9578  mov     ecx, [rax+48h]
0x1400f957b  lea     eax, [rcx-7]
0x1400f957e  cmp     eax, 2
0x1400f9581  jbe     loc_1400FAB8A
0x1400f9587  mov     eax, [r14+60h]
0x1400f958b  cmp     eax, 9
0x1400f958e  jz      loc_1400FAB8A
0x1400f9594  cmp     ecx, 0Ah
0x1400f9597  jz      loc_1400FAB8A
0x1400f959d  cmp     eax, 0Ah
0x1400f95a0  jz      loc_1400FAB8A
0x1400f95a6  mov     eax, [r12+8]
0x1400f95ab  cmp     [r12], eax
0x1400f95af  jz      loc_1400FB623
0x1400f95b5  mov     eax, [r12+0Ch]
0x1400f95ba  cmp     [r12+4], eax
0x1400f95bf  jz      loc_1400FB623
0x1400f95c5  mov     eax, [r15+8]
0x1400f95c9  cmp     [r15], eax
0x1400f95cc  jz      loc_1400FB623
0x1400f95d2  mov     eax, [r15+0Ch]
0x1400f95d6  cmp     [r15+4], eax
0x1400f95da  jz      loc_1400FB623
0x1400f95e0  mov     rax, [rdx+30h]
0x1400f95e4  mov     [rsp+5C8h+var_528], rax
0x1400f95ec  mov     rdi, [r14+30h]
0x1400f95f0  mov     edx, 2
0x1400f95f5  lea     rcx, [rsp+5C8h+var_308]
0x1400f95fd  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x1400f9602  movups  xmm0, xmmword ptr [r12]
0x1400f9607  movdqu  xmmword ptr [rsp+5C8h+var_250.left], xmm0
0x1400f9610  lea     esi, [rdx-1]
0x1400f9613  cmp     [r13+4Ch], si
0x1400f9618  jz      loc_1400FAFDD
0x1400f961e  mov     rax, [rsp+5C8h+var_4B8]
0x1400f9626  test    rax, rax
0x1400f9629  jnz     loc_1400F9CC4
0x1400f962f  mov     edx, ebx
0x1400f9631  mov     [rsp+5C8h+var_548], ebx
0x1400f9638  mov     [rsp+5C8h+var_45C], ebx
0x1400f963f  mov     rax, [rsp+5C8h+var_478]
0x1400f9647  mov     ecx, [rsp+5C8h+var_558]
0x1400f964b  cmp     ecx, 4
0x1400f964e  jz      loc_1400FAA05
0x1400f9654  mov     r8d, [r15+4]
0x1400f9658  mov     eax, [r15+0Ch]
0x1400f965c  cmp     eax, r8d
0x1400f965f  jl      loc_1400FB2A1
0x1400f9665  mov     r11d, ebx
0x1400f9668  mov     [rsp+5C8h+var_538], ebx
0x1400f966f  mov     r10d, r8d
0x1400f9672  mov     r8d, eax
0x1400f9675  mov     edx, [r15]
0x1400f9678  mov     eax, [r15+8]
0x1400f967c  cmp     eax, edx
0x1400f967e  jl      loc_1400FA753
0x1400f9684  mov     r9d, edx
0x1400f9687  mov     edx, eax
0x1400f9689  mov     eax, 3
0x1400f968e  cmp     ecx, eax
0x1400f9690  jb      loc_1400FA76D
0x1400f9696  mov     edx, ebx
0x1400f9698  mov     [rsp+5C8h+var_54C], ebx
0x1400f969c  test    edx, edx
0x1400f969e  jz      loc_1400F9C8B
0x1400f96a4  mov     rdx, [rsp+5C8h+var_4A8]
0x1400f96ac  lea     rax, [rdx+0A0h]
0x1400f96b3  mov     [rsp+5C8h+var_3F8], rax
0x1400f96bb  mov     ecx, [rax]
0x1400f96bd  bt      ecx, 12h
0x1400f96c1  jnb     loc_1400F9ABE
0x1400f96c7  mov     rax, [rsp+5C8h+var_528]
0x1400f96cf  mov     [rsp+5C8h+var_310], rax
0x1400f96d7  mov     edx, 2
0x1400f96dc  lea     rcx, [rsp+5C8h+var_428]
0x1400f96e4  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x1400f96e9  xorps   xmm0, xmm0
0x1400f96ec  movups  [rsp+5C8h+var_280], xmm0
0x1400f96f4  lea     rcx, [rsp+5C8h+var_238]; this
0x1400f96fc  call    ??0ECLIPOBJ@@QEAA@XZ; ECLIPOBJ::ECLIPOBJ(void)
0x1400f9701  movdqu  [rsp+5C8h+var_2C8], xmm0
0x1400f970a  mov     [rsp+5C8h+var_520], rbx
0x1400f9712  mov     ecx, [r14+3Ch]
0x1400f9716  mov     eax, [r14+38h]
0x1400f971a  mov     qword ptr [rsp+5C8h+var_2E8.left], rbx
0x1400f9722  mov     [rsp+5C8h+var_2E8.right], eax
0x1400f9729  mov     [rsp+5C8h+var_2E8.bottom], ecx
0x1400f9730  movups  [rsp+5C8h+var_2D8], xmm0
0x1400f9738  lea     rcx, [rsp+5C8h+var_508]; this
0x1400f9740  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1400f9745  mov     rcx, [rsp+5C8h+var_4A8]
0x1400f974d  movzx   eax, word ptr [rcx+64h]
0x1400f9751  mov     word ptr [rsp+5C8h+var_550], ax
0x1400f9756  test    ax, ax
0x1400f9759  jnz     loc_1400FABBA
0x1400f975f  mov     rax, [r14+20h]
0x1400f9763  cmp     [rcx+20h], rax
0x1400f9767  jz      loc_1400FABBA
0x1400f976d  mov     [rsp+5C8h+var_440], rcx
0x1400f9775  mov     rcx, [rsp+5C8h+var_4A0]
0x1400f977d  mov     [rsp+5C8h+var_468], rcx
0x1400f9785  mov     [rsp+5C8h+var_490], r15
0x1400f978d  mov     rax, [r14+30h]
0x1400f9791  mov     [rsp+5C8h+hsurf], rax
0x1400f9799  test    rax, rax
0x1400f979c  jz      short loc_1400F97BB
0x1400f979e  xor     r9d, r9d
0x1400f97a1  xor     r8d, r8d
0x1400f97a4  mov     rdx, r13
0x1400f97a7  lea     rcx, [rsp+5C8h+hsurf]
0x1400f97af  call    cs:__imp_?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z; PDEVOBJ::vSync(_SURFOBJ *,_RECTL *,ulong)
0x1400f97b6  nop     dword ptr [rax+rax+00h]
0x1400f97bb  mov     eax, [r12]
0x1400f97bf  mov     r11d, [rsp+5C8h+var_2E8.left]
0x1400f97c7  cmp     eax, r11d
0x1400f97ca  cmovg   r11d, eax
0x1400f97ce  mov     [rsp+5C8h+var_2E8.left], r11d
0x1400f97d6  mov     eax, [r12+4]
0x1400f97db  mov     r8d, [rsp+5C8h+var_2E8.top]
0x1400f97e3  cmp     eax, r8d
0x1400f97e6  cmovg   r8d, eax
0x1400f97ea  mov     [rsp+5C8h+var_2E8.top], r8d
0x1400f97f2  mov     eax, [r12+8]
0x1400f97f7  mov     r10d, [rsp+5C8h+var_2E8.right]
0x1400f97ff  cmp     eax, r10d
0x1400f9802  cmovl   r10d, eax
0x1400f9806  mov     [rsp+5C8h+var_2E8.right], r10d
0x1400f980e  mov     eax, [r12+0Ch]
0x1400f9813  mov     r9d, [rsp+5C8h+var_2E8.bottom]
0x1400f981b  cmp     eax, r9d
0x1400f981e  cmovl   r9d, eax
0x1400f9822  mov     [rsp+5C8h+var_2E8.bottom], r9d
0x1400f982a  cmp     r10d, r11d
0x1400f982d  jl      loc_1400FA7B8
0x1400f9833  cmp     r9d, r8d
0x1400f9836  cmovl   r8d, r9d
0x1400f983a  mov     [rsp+5C8h+var_2E8.top], r8d
0x1400f9842  cmp     r8d, r9d
0x1400f9845  jz      loc_1400F9A81
0x1400f984b  cmp     r11d, r10d
0x1400f984e  jz      loc_1400F9A81
0x1400f9854  mov     edx, 2
0x1400f9859  lea     rcx, [rsp+5C8h+var_410]
0x1400f9861  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x1400f9866  xorps   xmm0, xmm0
0x1400f9869  movups  [rsp+5C8h+var_290], xmm0
0x1400f9871  mov     r13d, [rsp+5C8h+var_538]
0x1400f9879  test    r13d, r13d
0x1400f987c  jnz     loc_1400FAD02
0x1400f9882  cmp     [r14+64h], bx
0x1400f9887  jnz     loc_1400FAD02
0x1400f988d  mov     eax, [r14+60h]
0x1400f9891  sub     eax, 7
0x1400f9894  cmp     eax, esi
0x1400f9896  jbe     loc_1400FAD02
0x1400f989c  mov     [rsp+5C8h+var_450], r14
0x1400f98a4  mov     [rsp+5C8h+var_458], r12
0x1400f98ac  mov     rdi, rbx
0x1400f98af  cmp     [rsp+5C8h+var_548], ebx
0x1400f98b6  cmovz   rdi, [rsp+5C8h+var_4B8]
0x1400f98bf  mov     [rsp+5C8h+var_480], rdi
0x1400f98c7  mov     r13, [rsp+5C8h+var_440]
0x1400f98cf  lea     rcx, [r13+18h]
0x1400f98d3  mov     rax, [rcx+18h]
0x1400f98d7  mov     [rsp+5C8h+hsurf], rax
0x1400f98df  test    rax, rax
0x1400f98e2  jnz     loc_1400F9C99
0x1400f98e8  lea     rcx, [r12+8]
0x1400f98ed  mov     [rsp+5C8h+var_488], rcx
0x1400f98f5  mov     ecx, [rcx]
0x1400f98f7  sub     ecx, [r12]
0x1400f98fb  mov     r8d, 7A12000h
0x1400f9901  cmp     ecx, r8d
0x1400f9904  jge     loc_1400FA7DB
0x1400f990a  lea     rax, [r12+4]
0x1400f990f  mov     qword ptr [rsp+5C8h+sizl.cx], rax
0x1400f9917  mov     ecx, [r12+0Ch]
0x1400f991c  sub     ecx, [rax]
0x1400f991e  cmp     ecx, r8d
0x1400f9921  jge     loc_1400FA7DB
0x1400f9927  mov     ecx, [r15+8]
0x1400f992b  sub     ecx, [r15]
0x1400f992e  cmp     ecx, r8d
0x1400f9931  jge     loc_1400FA7DB
0x1400f9937  mov     edx, [r15+0Ch]
0x1400f993b  sub     edx, [r15+4]
0x1400f993f  cmp     edx, r8d
0x1400f9942  jge     loc_1400FA7DB
0x1400f9948  mov     eax, 0F85EE000h
0x1400f994d  cmp     ecx, eax
0x1400f994f  jle     loc_1400FA7DB
0x1400f9955  cmp     edx, eax
0x1400f9957  jle     loc_1400FA7DB
0x1400f995d  mov     r8d, 3
0x1400f9963  cmp     [rsp+5C8h+var_558], r8d
0x1400f9968  jnz     loc_1400F9D0B
0x1400f996e  cmp     [rsp+5C8h+var_478], rbx
0x1400f9976  jnz     loc_1400F9D0B
0x1400f997c  test    rdi, rdi
0x1400f997f  jz      short loc_1400F998D
0x1400f9981  mov     eax, [rdi+4]
0x1400f9984  test    sil, al
0x1400f9987  jz      loc_1400F9D0B
0x1400f998d  mov     ecx, [r14+60h]
0x1400f9991  mov     edx, [r13+60h]
0x1400f9995  cmp     edx, ecx
0x1400f9997  jnz     loc_1400F9D0B
0x1400f999d  lea     eax, [rcx-3]
0x1400f99a0  test    eax, 0FFFFFFFCh
0x1400f99a5  jnz     loc_1400F9D0B
0x1400f99ab  cmp     ecx, 5
0x1400f99ae  jz      loc_1400F9D0B
0x1400f99b4  mov     rcx, [rsp+5C8h+var_468]
0x1400f99bc  test    rcx, rcx
0x1400f99bf  jnz     loc_1400FA841
0x1400f99c5  mov     rax, r15
0x1400f99c8  test    rcx, rcx
0x1400f99cb  jnz     loc_1400FA7C8
0x1400f99d1  mov     dword ptr [rsp+5C8h+var_568], edx; struct _RECTL *
0x1400f99d5  mov     [rsp+5C8h+var_570], rax; struct _RECTL *
0x1400f99da  lea     rax, [rsp+5C8h+var_2E8]
0x1400f99e2  mov     [rsp+5C8h+var_578], rax; struct _RECTL *
0x1400f99e7  mov     qword ptr [rsp+5C8h+var_580], r12; unsigned int
0x1400f99ec  mov     eax, [r14+3Ch]
0x1400f99f0  mov     [rsp+5C8h+var_588], eax; unsigned int
0x1400f99f4  mov     eax, [r14+38h]
0x1400f99f8  mov     [rsp+5C8h+var_590], eax; int
0x1400f99fc  mov     eax, [r14+58h]
0x1400f9a00  mov     dword ptr [rsp+5C8h+var_598], eax; void *
0x1400f9a04  mov     rax, [r14+50h]
0x1400f9a08  mov     [rsp+5C8h+var_5A0], rax; struct _RECTL *
0x1400f9a0d  mov     [rsp+5C8h+pvBits], r15; unsigned int
0x1400f9a12  mov     r9d, [r13+3Ch]; unsigned int
0x1400f9a16  mov     r8d, [r13+38h]; int
0x1400f9a1a  mov     edx, [r13+58h]; void *
0x1400f9a1e  mov     rcx, [r13+50h]; this
0x1400f9a22  call    ?StretchDIBDirect@stretch@@YAHPEAXJKKPEAU_RECTL@@0JKK111K@Z; stretch::StretchDIBDirect(void *,long,ulong,ulong,_RECTL *,void *,long,ulong,ulong,_RECTL *,_RECTL *,_RECTL *,ulong)
0x1400f9a27  mov     eax, [rsp+5C8h+var_2E8.left]
0x1400f9a2e  mov     dword ptr [rsp+5C8h+var_2D8], eax
0x1400f9a35  mov     ecx, [rsp+5C8h+var_2E8.right]
0x1400f9a3c  mov     dword ptr [rsp+5C8h+var_2D8+8], ecx
0x1400f9a43  mov     edx, [rsp+5C8h+var_2E8.top]
  ... truncated ...
```
