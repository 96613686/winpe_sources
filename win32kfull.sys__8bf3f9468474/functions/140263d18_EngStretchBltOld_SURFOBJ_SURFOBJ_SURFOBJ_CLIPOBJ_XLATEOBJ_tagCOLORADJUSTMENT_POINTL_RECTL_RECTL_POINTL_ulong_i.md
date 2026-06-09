# EngStretchBltOld(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int *)

- ea: `0x140263d18`
- end: `0x140265605`
- name: `?EngStretchBltOld@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAH@Z`
- size: `6381`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x1400f8e90`

## callees

- `0x140053654`
- `0x14006ec10`
- `0x1400f6d54`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x1400fb69c`
- `0x1400fb6c8`
- `0x1400fbd70`
- `0x1400fc428`
- `0x14012a770`
- `0x14013c30c`
- `0x14013d844`
- `0x140156d5c`
- `0x1401643b0`
- `0x14017e9c0`
- `0x1401b1e94`
- `0x1401b77d0`
- `0x140263d18`
- `0x140296924`
- `0x140329310`
- `0x140329500`
- `0x140329570`
- `0x1403295f0`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140264715`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402650bd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402651c7`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140264715`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402650bd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402651c7`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140265303`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140265324`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140265338`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1402655a4`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1402655c5`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140265303`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140265324`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140265338`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1402655a4`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1402655c5`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140264628`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1402648f1`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140264628`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1402648f1`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402646a2`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402653bd`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402653f6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402646a2`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402653bd`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402653f6`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1402646c9`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1402646c9`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140265419`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140265419`
- `win32kbase!EngLockSurface` at `0x14026427b`
- `win32kbase!EngLockSurface` at `0x14026427b`
- `win32kbase!EngUnlockSurface` at `0x140264383`
- `win32kbase!EngUnlockSurface` at `0x140264383`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1402646ff`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1402647d6`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140264ac7`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1402646ff`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1402647d6`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140264ac7`
- `win32kbase!EngCreateBitmap` at `0x140264264`
- `win32kbase!EngCreateBitmap` at `0x140264264`
- `win32kbase!EngDeleteSurface` at `0x140264397`
- `win32kbase!EngDeleteSurface` at `0x140264397`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x140265468`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x140265468`
- `win32kbase!AllocFreeTmpBuffer` at `0x140264ee9`
- `win32kbase!AllocFreeTmpBuffer` at `0x140264ee9`
- `win32kbase!FreeTmpBuffer` at `0x1402652b9`
- `win32kbase!FreeTmpBuffer` at `0x1402652b9`
- `win32kbase!Win32FreePool` at `0x1402652c8`
- `win32kbase!Win32FreePool` at `0x140265590`
- `win32kbase!Win32FreePool` at `0x1402652c8`
- `win32kbase!Win32FreePool` at `0x140265590`

## pseudocode

```c
__int64 __fastcall EngStretchBltOld(
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
        unsigned int a11,
        int *a12)
{
  struct _SURFOBJ *v12; // r15
  struct _RECTL *v13; // r12
  struct _RECTL *v14; // r13
  PVOID *p_pvScan0; // rdx
  stretch *v16; // r14
  int v17; // ecx
  int v18; // eax
  __int64 v19; // rbx
  struct tagCOLORADJUSTMENT *v20; // r8
  __int64 *v21; // r9
  SURFOBJ *v22; // r10
  CLIPOBJ *v23; // r11
  int v24; // edx
  unsigned int v25; // esi
  unsigned int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // ecx
  int v29; // eax
  LONG top; // r8d
  LONG bottom; // eax
  int v32; // r11d
  LONG v33; // r10d
  LONG left; // edx
  LONG right; // eax
  LONG v36; // r9d
  unsigned int v37; // eax
  int v38; // ecx
  LONG v39; // ecx
  int v40; // eax
  LONG v41; // r8d
  LONG v42; // edx
  LONG v43; // edx
  SURFOBJ *v44; // rax
  SURFOBJ *v45; // r15
  int v46; // eax
  unsigned int (__fastcall *v47)(struct _SURFOBJ *, SURFOBJ *, _QWORD, XCLIPOBJ *, _QWORD, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, __int128 *, Gre::Base *, unsigned int); // rax
  LONG v48; // ecx
  LONG v49; // eax
  __int64 v50; // r8
  __int64 v51; // r9
  SIZEL v52; // r15
  LONG v53; // r15d
  int v54; // r11d
  SIZEL v55; // r15
  int v56; // eax
  _DWORD *v57; // r12
  Gre::Base *v58; // rcx
  struct _SURFOBJ *v59; // r15
  struct Gre::Base::SESSION_GLOBALS *v60; // r9
  BOOL (__stdcall *v61)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  unsigned __int64 v62; // rbx
  int v63; // eax
  BOOL (__stdcall *v64)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  unsigned __int64 v65; // r9
  stretch *v66; // r8
  int v67; // eax
  int v68; // ecx
  __int64 v69; // rcx
  unsigned int v70; // ecx
  LONG v71; // r10d
  LONG v72; // r11d
  int v73; // edx
  int v74; // r9d
  int v75; // ecx
  int v76; // r8d
  int v77; // ecx
  XCLIPOBJ *v78; // rsi
  int v79; // ebx
  struct _RECTL *v80; // rcx
  LONG v81; // eax
  LONG v82; // ecx
  LONG v83; // edx
  LONG v84; // r8d
  unsigned int v85; // ecx
  __int64 v86; // r13
  __int64 v87; // r9
  unsigned int v88; // r8d
  int v89; // edx
  struct _RECTL *v90; // r12
  unsigned int v91; // eax
  __int64 v92; // rcx
  __int64 v93; // rbx
  _DWORD *v94; // r9
  struct stretch::_XRUNLEN *(**v95)(struct stretch::_STRDDA *, struct stretch::_STRRUN *, unsigned __int8 *, unsigned __int8 *, struct _XLATEOBJ *, int, int, int); // r11
  struct _RECTL *v96; // r8
  struct _SURFOBJ *v97; // r14
  unsigned int v98; // r11d
  unsigned int v99; // r11d
  LONG v100; // r9d
  int v101; // r10d
  unsigned __int64 v102; // r12
  int v103; // edx
  __int64 v104; // rax
  XCLIPOBJ *v106; // rbx
  BOOL (__stdcall *v107)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  struct _RECTL *pvBits; // [rsp+20h] [rbp-3F8h]
  struct _RECTL *v109; // [rsp+28h] [rbp-3F0h]
  void *v110; // [rsp+30h] [rbp-3E8h]
  struct _RECTL *v111; // [rsp+60h] [rbp-3B8h]
  unsigned int v112; // [rsp+68h] [rbp-3B0h]
  unsigned int v113; // [rsp+70h] [rbp-3A8h]
  unsigned int v114; // [rsp+70h] [rbp-3A8h]
  LONG v115; // [rsp+74h] [rbp-3A4h]
  __int16 v116; // [rsp+74h] [rbp-3A4h]
  int v117; // [rsp+74h] [rbp-3A4h]
  unsigned int v118; // [rsp+78h] [rbp-3A0h]
  int v119; // [rsp+7Ch] [rbp-39Ch]
  LONG v120; // [rsp+7Ch] [rbp-39Ch]
  unsigned int v121; // [rsp+7Ch] [rbp-39Ch]
  unsigned int v122; // [rsp+80h] [rbp-398h]
  struct _SURFOBJ *v123; // [rsp+88h] [rbp-390h] BYREF
  __int64 v124; // [rsp+90h] [rbp-388h] BYREF
  LONG v125; // [rsp+98h] [rbp-380h]
  struct REGION *v126; // [rsp+A0h] [rbp-378h] BYREF
  unsigned __int64 v127; // [rsp+A8h] [rbp-370h]
  struct _RECTL *v128; // [rsp+B0h] [rbp-368h]
  struct stretch::_XRUNLEN *(**v129)(struct stretch::_STRDDA *, struct stretch::_STRRUN *, unsigned __int8 *, unsigned __int8 *, struct _XLATEOBJ *, int, int, int); // [rsp+B8h] [rbp-360h]
  struct tagCOLORADJUSTMENT *v130; // [rsp+C0h] [rbp-358h] BYREF
  struct _SURFOBJ *v131; // [rsp+C8h] [rbp-350h]
  SIZEL sizl; // [rsp+D0h] [rbp-348h]
  unsigned __int64 v133; // [rsp+D8h] [rbp-340h]
  struct REGION *v134; // [rsp+E0h] [rbp-338h] BYREF
  XCLIPOBJ *v135; // [rsp+E8h] [rbp-330h]
  unsigned int v136; // [rsp+F0h] [rbp-328h]
  SIZEL v137; // [rsp+F8h] [rbp-320h]
  struct _SURFOBJ *v138; // [rsp+100h] [rbp-318h]
  unsigned int v139[2]; // [rsp+108h] [rbp-310h]
  void (**v140)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *); // [rsp+110h] [rbp-308h]
  struct _POINTL *v141; // [rsp+118h] [rbp-300h]
  _QWORD v142[3]; // [rsp+120h] [rbp-2F8h] BYREF
  __int64 v143; // [rsp+138h] [rbp-2E0h]
  stretch *v144[3]; // [rsp+140h] [rbp-2D8h] BYREF
  Gre::Base *v145; // [rsp+158h] [rbp-2C0h]
  struct _SURFOBJ *v146; // [rsp+160h] [rbp-2B8h]
  struct _CLIPOBJ *v147; // [rsp+168h] [rbp-2B0h]
  _DWORD *v148; // [rsp+170h] [rbp-2A8h]
  _DWORD v149[4]; // [rsp+178h] [rbp-2A0h] BYREF
  __int64 v150; // [rsp+188h] [rbp-290h]
  int v151; // [rsp+190h] [rbp-288h]
  int v152; // [rsp+194h] [rbp-284h]
  _DWORD v153[4]; // [rsp+198h] [rbp-280h] BYREF
  __int64 v154; // [rsp+1A8h] [rbp-270h]
  int v155; // [rsp+1B0h] [rbp-268h]
  int v156; // [rsp+1B4h] [rbp-264h]
  int *v157; // [rsp+1B8h] [rbp-260h]
  unsigned __int64 v158; // [rsp+1C0h] [rbp-258h]
  _QWORD v159[3]; // [rsp+1C8h] [rbp-250h] BYREF
  struct _RECTL v160; // [rsp+1E0h] [rbp-238h] BYREF
  struct _RECTL v161; // [rsp+1F0h] [rbp-228h] BYREF
  struct _RECTL v162; // [rsp+200h] [rbp-218h] BYREF
  struct _RECTL v163; // [rsp+210h] [rbp-208h] BYREF
  struct _RECTL v164; // [rsp+220h] [rbp-1F8h] BYREF
  __m128i v165; // [rsp+230h] [rbp-1E8h] BYREF
  __int128 v166; // [rsp+240h] [rbp-1D8h] BYREF
  struct _RECTL v167; // [rsp+250h] [rbp-1C8h] BYREF
  struct _RECTL v168; // [rsp+260h] [rbp-1B8h] BYREF
  int v169; // [rsp+270h] [rbp-1A8h]
  struct _RECTL v170; // [rsp+278h] [rbp-1A0h] BYREF
  _BYTE v171[160]; // [rsp+290h] [rbp-188h] BYREF
  _BYTE v172[4]; // [rsp+330h] [rbp-E8h] BYREF
  char v173[156]; // [rsp+334h] [rbp-E4h] BYREF

  v135 = (XCLIPOBJ *)a4;
  v123 = a3;
  v12 = a2;
  v138 = a2;
  v131 = a1;
  v133 = (unsigned __int64)a5;
  v145 = (Gre::Base *)a10;
  v13 = a8;
  v14 = a9;
  v128 = a9;
  v147 = a4;
  v130 = a6;
  v141 = a7;
  v113 = a11;
  v140 = (void (**)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *))a12;
  if ( a11 - 1 > 3 )
    return 0;
  p_pvScan0 = &a1[-1].pvScan0;
  if ( !a1 )
    p_pvScan0 = 0;
  v137 = (SIZEL)p_pvScan0;
  v16 = (stretch *)&v12[-1].pvScan0;
  if ( !v12 )
    v16 = 0;
  if ( a3 )
  {
    v129 = (struct stretch::_XRUNLEN *(**)(struct stretch::_STRDDA *, struct stretch::_STRRUN *, unsigned __int8 *, unsigned __int8 *, struct _XLATEOBJ *, int, int, int))&a3[-1].pvScan0;
    *(_QWORD *)v139 = &a3->lDelta;
    v143 = (__int64)&a3->pvScan0;
  }
  else
  {
    v129 = 0;
    *(_QWORD *)v139 = 88;
    v143 = 80;
  }
  if ( !p_pvScan0 )
    return 0;
  if ( !v16 )
    return 0;
  v146 = (struct _SURFOBJ *)(p_pvScan0 + 3);
  v17 = *((_DWORD *)p_pvScan0 + 24);
  if ( (unsigned int)(v17 - 7) <= 2 )
    return 0;
  v18 = *((_DWORD *)v16 + 24);
  if ( v18 == 9 || v17 == 10 || v18 == 10 )
    return 0;
  if ( a9->left != a9->right && a9->top != a9->bottom && a8->left != a8->right && a8->top != a8->bottom )
  {
    v127 = (unsigned __int64)p_pvScan0[6];
    v19 = *((_QWORD *)v16 + 6);
    SURFMEM::SURFMEM(v159, 2);
    v170 = *a9;
    v25 = v24 - 1;
    if ( v12->iType == (_WORD)v24 - 1 && v19 && (*(_DWORD *)(v19 + 40) & 0x20000) != 0 )
    {
      if ( !(unsigned int)MulCopyDeviceToDIB(v12, (struct SURFMEM *)v159, &v170) )
      {
LABEL_221:
        v25 = 0;
        goto LABEL_201;
      }
      if ( !v159[0] )
        goto LABEL_201;
      v14 = &v170;
      v128 = &v170;
      v12 = (struct _SURFOBJ *)((v159[0] + 24LL) & -(__int64)(v159[0] != 0));
      v138 = v12;
      v16 = (stretch *)&v12[-1].pvScan0;
      if ( !v12 )
        v16 = 0;
      v19 = *((_QWORD *)v16 + 6);
      v22 = v131;
      v20 = v130;
      v21 = (__int64 *)v141;
      v23 = (CLIPOBJ *)v135;
    }
    if ( v133 && (*(_DWORD *)(v133 + 4) & 8) != 0 )
    {
      if ( v12->iType )
        goto LABEL_221;
      if ( v22->iType != (_WORD)v25 )
        goto LABEL_221;
      v26 = v25;
      v118 = v25;
      v136 = v25;
      v27 = (__int64)v123;
      if ( v123 )
        goto LABEL_221;
    }
    else
    {
      v26 = 0;
      v118 = 0;
      v136 = 0;
      v27 = (__int64)v123;
    }
    v28 = a11;
    if ( a11 == 4 )
    {
      if ( v26 )
        goto LABEL_221;
      v29 = EngHTBlt(v22, v12, v27, v23, (struct XLATE *)v133, v20, v21, (XLATEOBJ *)a8, (POINTL)v14, v145, 0, 0);
      if ( v29 == -1 )
        goto LABEL_221;
      if ( v29 )
      {
        if ( v29 != v25 )
        {
          v28 = 4;
          goto LABEL_40;
        }
LABEL_201:
        SURFMEM::~SURFMEM((SURFMEM *)v159);
        return v25;
      }
      v28 = 3;
      v113 = 3;
    }
LABEL_40:
    top = a8->top;
    bottom = a8->bottom;
    if ( bottom >= top )
    {
      v32 = 0;
      v119 = 0;
      v33 = a8->top;
      top = a8->bottom;
    }
    else
    {
      a8->top = bottom;
      a8->bottom = top;
      v32 = 2;
      v119 = 2;
      v33 = bottom;
    }
    left = a8->left;
    right = a8->right;
    if ( right >= a8->left )
    {
      v36 = a8->left;
      left = a8->right;
    }
    else
    {
      a8->left = right;
      a8->right = left;
      v32 |= v25;
      v119 = v32;
      v36 = right;
    }
    if ( v28 >= 3 || v129 )
      goto LABEL_51;
    v122 = v25;
    if ( left - v36 < v14->right - v14->left )
    {
      v28 = v113;
    }
    else
    {
      v28 = v113;
      if ( top - v33 >= v14->bottom - v14->top )
      {
LABEL_51:
        v37 = 0;
        v122 = 0;
        goto LABEL_54;
      }
    }
    v37 = v25;
LABEL_54:
    if ( !v37 )
    {
      if ( v28 < 3 )
        v28 = 3;
      v113 = v28;
    }
    v148 = (_DWORD *)(*(_QWORD *)&v137 + 160LL);
    v38 = *(_DWORD *)(*(_QWORD *)&v137 + 160LL);
    if ( (v38 & 0x40000) == 0
      && (v133 && ((unsigned __int8)*(_DWORD *)(v133 + 4) & (unsigned __int8)v25) == 0 || v12->iType) )
    {
      if ( *(_WORD *)(*(_QWORD *)&v137 + 100LL) )
      {
        if ( (v38 & 2) != 0 && !v32 && !v123 )
        {
          v39 = v14->left;
          if ( v14->left >= 0 )
          {
            v40 = v14->top;
            if ( v40 >= 0 )
            {
              v41 = v14->right;
              if ( v41 <= v12->sizlBitmap.cx )
              {
                v42 = v14->bottom;
                if ( v42 <= v12->sizlBitmap.cy )
                {
                  v166 = 0;
                  v125 = v41 - v39;
                  sizl.cx = v41 - v39;
                  v43 = v42 - v40;
                  v115 = v43;
                  sizl.cy = v43;
                  if ( v41 - v39 <= a8->right - a8->left && v43 <= a8->bottom - a8->top )
                  {
                    sizl = (SIZEL)EngCreateBitmap(sizl, 0, v131->iBitmapFormat, 0, 0);
                    v44 = EngLockSurface(*(HSURF *)&sizl);
                    v45 = v44;
                    if ( v44 )
                    {
                      v44->iUniq = 0;
                      *(_QWORD *)&v166 = 0;
                      *((_QWORD *)&v166 + 1) = __PAIR64__(v115, v125);
                      if ( (*((_DWORD *)v16 + 40) & 0x400) != 0 )
                        v46 = (*(__int64 (__fastcall **)(SURFOBJ *, struct _SURFOBJ *, _QWORD, unsigned __int64, __int128 *, struct _RECTL *))(v19 + 2832))(
                                v44,
                                v138,
                                0,
                                v133,
                                &v166,
                                v14);
                      else
                        v46 = ((__int64 (__fastcall *)(SURFOBJ *, struct _SURFOBJ *, _QWORD, unsigned __int64, __int128 *, struct _RECTL *))EngCopyBits)(
                                v44,
                                v138,
                                0,
                                v133,
                                &v166,
                                v14);
                      if ( !v46
                        || (v47 = *(unsigned int (__fastcall **)(struct _SURFOBJ *, SURFOBJ *, _QWORD, XCLIPOBJ *, _QWORD, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, __int128 *, Gre::Base *, unsigned int))(v127 + 2840)) == 0
                        || !v47(v131, v45, 0, v135, 0, v130, v141, a8, &v166, v145, v113) )
                      {
                        v25 = 0;
                      }
                      EngUnlockSurface(v45);
                      EngDeleteSurface(*(HSURF *)&sizl);
                      goto LABEL_201;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v158 = v127;
    SURFMEM::SURFMEM(v142, 2);
    v165 = 0;
    ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v171);
    v161 = 0;
    v124 = 0;
    v48 = *((_DWORD *)v16 + 15);
    v49 = *((_DWORD *)v16 + 14);
    *(_QWORD *)&v160.left = 0;
    v160.right = v49;
    v160.bottom = v48;
    v162 = 0;
    RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v126);
    v116 = *(_WORD *)(*(_QWORD *)&v137 + 100LL);
    if ( v116 || *(_QWORD *)(*(_QWORD *)&v137 + 32LL) == *((_QWORD *)v16 + 4) )
    {
      v165 = *(__m128i *)a8;
      v161.left = _mm_cvtsi128_si32(v165) - 1;
      v161.top = v165.m128i_i32[1] - v25;
      v53 = a8->right;
      v161.right = v53 + 1;
      v161.bottom = v25 + HIDWORD(*(_QWORD *)&a8->right);
      *(_QWORD *)&v164.left = 0;
      v164.right = *(_DWORD *)(*(_QWORD *)&v137 + 56LL);
      v164.bottom = *(_DWORD *)(*(_QWORD *)&v137 + 60LL);
      ERECTL::operator*=(&v161, &v164, v50, v51);
      if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v161) )
      {
LABEL_200:
        RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v126);
        SURFMEM::~SURFMEM((SURFMEM *)v142);
        goto LABEL_201;
      }
      if ( v116
        || v161.left <= v14->right && v161.right >= v14->left && v161.top <= v14->bottom && v161.bottom >= v14->top )
      {
        v165.m128i_i32[0] = v54 - v161.left;
        v165.m128i_i32[1] -= v161.top;
        v165.m128i_i32[2] = v53 - v161.left;
        v165.m128i_i32[3] -= v161.top;
        v149[3] = 0;
        v152 = 0;
        v149[1] = v25 + v161.right - v161.left;
        v149[2] = v25 + v161.bottom - v161.top;
        v150 = 0;
        v55 = v137;
        if ( v118 )
          v56 = *((_DWORD *)v16 + 24);
        else
          v56 = *(_DWORD *)(*(_QWORD *)&v137 + 96LL);
        v149[0] = v56;
        v57 = v148;
        v151 = *v148 & 0x40000;
        SURFMEM::bCreateDIB((SURFMEM *)v142, (struct _DEVBITMAPINFO *)v149, 0, 0, 0, 0, 0, 0, v25, 0);
        if ( !v142[0] )
          goto LABEL_220;
        v124 = *(_QWORD *)&v161.left;
        if ( !v126 )
          goto LABEL_220;
        *(_QWORD *)&v161.left = 0;
        v161.right -= v124;
        v161.bottom -= HIDWORD(v124);
        RGNOBJ::vSet((RGNOBJ *)&v126, &v161);
        XCLIPOBJ::vSetup((XCLIPOBJ *)v171, v126, (const struct ERECTL *)&v161, v25);
        v130 = *(struct tagCOLORADJUSTMENT **)(*(_QWORD *)&v55 + 48LL);
        v59 = v146;
        if ( v130 )
          PDEVOBJ::vSync((PDEVOBJ *)&v130, v146, 0, 0);
        if ( v129 )
        {
          v60 = Gre::Base::Globals(v58);
          if ( (*v57 & 0x400) != 0 )
            v61 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v127 + 2832);
          else
            v61 = EngCopyBits;
          v109 = (struct _RECTL *)&v124;
          pvBits = &v161;
          ((void (__fastcall *)(__int64, struct _SURFOBJ *, _QWORD, char *))v61)(
            (v142[0] + 24LL) & -(__int64)(v142[0] != 0),
            v59,
            0,
            (char *)v60 + 4664);
        }
        v52 = (SIZEL)v142[0];
        v13 = (struct _RECTL *)&v165;
        v127 = (unsigned __int64)v171;
      }
      else
      {
        v52 = v137;
        v127 = (unsigned __int64)v135;
      }
      sizl = v52;
    }
    else
    {
      v52 = v137;
      sizl = v137;
      v127 = (unsigned __int64)v135;
    }
    v130 = (struct tagCOLORADJUSTMENT *)*((_QWORD *)v16 + 6);
    if ( v130 )
      PDEVOBJ::vSync((PDEVOBJ *)&v130, v138, 0, 0);
    ERECTL::operator*=(&v160, v14, v50, v51);
    if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v160) )
      goto LABEL_200;
    SURFMEM::SURFMEM(v144, 2);
    v163 = 0;
    if ( v119 || *((_WORD *)v16 + 50) || *((_DWORD *)v16 + 24) - 7 <= v25 )
    {
      v153[3] = 0;
      v156 = 0;
      v153[1] = v160.right - v160.left;
      v153[2] = v160.bottom - v160.top;
      v154 = 0;
      if ( v118 )
        v63 = *((_DWORD *)v16 + 24);
      else
        v63 = *(_DWORD *)(*(_QWORD *)&v52 + 96LL);
      v153[0] = v63;
      v155 = *((_DWORD *)v16 + 40) & 0x40000;
      SURFMEM::bCreateDIB((SURFMEM *)v144, (struct _DEVBITMAPINFO *)v153, 0, 0, 0, 0, 0, 0, v25, 0);
      if ( !v144[0] )
        goto LABEL_219;
      *(_QWORD *)&v163.left = 0;
      v163.right = v160.right - v160.left;
      v163.bottom = v160.bottom - v160.top;
      if ( (*((_DWORD *)v16 + 40) & 0x400) != 0 )
        v64 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v19 + 2832);
      else
        v64 = EngCopyBits;
      v65 = 0;
      if ( !v118 )
        v65 = v133;
      v109 = &v160;
      pvBits = &v163;
      ((void (__fastcall *)(unsigned __int64, char *, _QWORD, unsigned __int64))v64)(
        ((unsigned __int64)v144[0] + 24) & -(__int64)(v144[0] != 0),
        (char *)v16 + 24,
        0,
        v65);
      v163.left = v14->left - v160.left;
      v163.top = v14->top - v160.top;
      v163.right = v14->right - v160.left;
      v163.bottom = v14->bottom - v160.top;
      v66 = v144[0];
      v16 = v144[0];
      v14 = &v163;
      v128 = &v163;
      v62 = 0;
      v131 = 0;
      v160.right -= v160.left;
      v67 = v160.bottom - v160.top;
      v160.bottom -= v160.top;
      *(_QWORD *)&v160.left = 0;
      if ( (v119 & 2) != 0 )
      {
        v68 = *((_DWORD *)v144[0] + 22);
        if ( v68 <= 0 )
          v69 = *((_QWORD *)v144[0] + 9);
        else
          v69 = *((_QWORD *)v144[0] + 9) + v68 * (v67 - 1);
        *((_QWORD *)v144[0] + 10) = v69;
        *((_DWORD *)v144[0] + 22) = -*((_DWORD *)v144[0] + 22);
        v66 = v144[0];
      }
      if ( ((unsigned __int8)v119 & (unsigned __int8)v25) != 0 )
      {
        v70 = *((_DWORD *)v66 + 24);
        if ( v70 - 1 > 5 )
          goto LABEL_219;
        ((void (__fastcall *)(stretch *))funcs_14007E20E[v70 - 1])(v66);
      }
    }
    else
    {
      v62 = 0;
      if ( !v118 )
        v62 = v133;
      v131 = (struct _SURFOBJ *)v62;
    }
    v130 = *(struct tagCOLORADJUSTMENT **)(*(_QWORD *)&v52 + 48LL);
    if ( v130 )
      PDEVOBJ::vSync(
        (PDEVOBJ *)&v130,
        (struct _SURFOBJ *)((*(_QWORD *)&v52 + 24LL) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)&v52 >> 64)),
        0,
        0);
    v71 = v14->left;
    v72 = v14->right;
    v73 = v72 - v14->left;
    if ( v73 < 128000000 )
    {
      v120 = v14->top;
      v125 = v14->bottom;
      v74 = v125 - v120;
      if ( v125 - v120 < 128000000 )
      {
        v75 = v13->right - v13->left;
        if ( v75 < 128000000 )
        {
          v76 = v13->bottom - v13->top;
          if ( v76 < 128000000 && v75 > -128000000 && v76 > -128000000 )
          {
            if ( v113 == 3 && !v123 && (!v62 || ((unsigned __int8)*(_DWORD *)(v62 + 4) & (unsigned __int8)v25) != 0) )
            {
              v77 = *((_DWORD *)v16 + 24);
              if ( *(_DWORD *)(*(_QWORD *)&v52 + 96LL) == v77 && ((v77 - 3) & 0xFFFFFFFC) == 0 && v77 != 5 )
              {
                if ( v127 && *(_BYTE *)(v127 + 20) == 3 )
                {
                  v164 = 0;
                  *(_QWORD *)&v160.right = 0;
                  *(_QWORD *)&v160.left = 0;
                  v168 = 0;
                  v169 = 0;
                  v78 = v135;
                  XCLIPOBJ::cEnumStart(v135, 0, 0, 4u, 0);
                  do
                  {
                    v79 = XCLIPOBJ::bEnum(v78, 0x14u, &v168, 0);
                    if ( v168.left )
                    {
                      LODWORD(v111) = *(_DWORD *)(*(_QWORD *)&v52 + 96LL);
                      LODWORD(v110) = *((_DWORD *)v16 + 22);
                      stretch::StretchDIBDirect(
                        *(stretch **)(*(_QWORD *)&v52 + 80LL),
                        (void *)*(unsigned int *)(*(_QWORD *)&v52 + 88LL),
                        *(_DWORD *)(*(_QWORD *)&v52 + 56LL),
                        *(_DWORD *)(*(_QWORD *)&v52 + 60LL),
                        (unsigned int)v13,
                        *((struct _RECTL **)v16 + 10),
                        v110,
                        *((_DWORD *)v16 + 14),
                        *((_DWORD *)v16 + 15),
                        (unsigned int)v14,
                        &v164,
                        (struct _RECTL *)&v168.top,
                        v111,
                        v112);
                      ERECTL::operator+=(&v160, &v164);
                    }
                  }
                  while ( v79 );
                  v25 = 1;
                }
                else
                {
                  v80 = v13;
                  if ( v127 && *(_BYTE *)(v127 + 20) == (_BYTE)v25 )
                    v80 = (struct _RECTL *)(v127 + 4);
                  LODWORD(v111) = *(_DWORD *)(*(_QWORD *)&v52 + 96LL);
                  LODWORD(v110) = *((_DWORD *)v16 + 22);
                  stretch::StretchDIBDirect(
                    *(stretch **)(*(_QWORD *)&v52 + 80LL),
                    (void *)*(unsigned int *)(*(_QWORD *)&v52 + 88LL),
                    *(_DWORD *)(*(_QWORD *)&v52 + 56LL),
                    *(_DWORD *)(*(_QWORD *)&v52 + 60LL),
                    (unsigned int)v13,
                    *((struct _RECTL **)v16 + 10),
                    v110,
                    *((_DWORD *)v16 + 14),
                    *((_DWORD *)v16 + 15),
                    (unsigned int)v14,
                    &v160,
                    v80,
                    v111,
                    v112);
                }
                v81 = v160.left;
                v162 = v160;
                v82 = v160.right;
                v83 = v160.top;
                v84 = v160.bottom;
LABEL_198:
                if ( v52 == v137 )
                {
LABEL_199:
                  SURFMEM::~SURFMEM((SURFMEM *)v144);
                  goto LABEL_200;
                }
                v162.left = v124 + v81;
                v162.top = HIDWORD(v124) + v83;
                v162.right = v124 + v82;
                v162.bottom = HIDWORD(v124) + v84;
                RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v134);
                if ( v134 )
                {
                  v106 = v135;
                  if ( !v135 )
                  {
                    RGNOBJ::vSet((RGNOBJ *)&v134, &v162);
LABEL_208:
                    v167 = *(struct _RECTL *)((char *)v134 + 52);
                    if ( !v106 || bIntersect(&v167, (const struct _RECTL *)((char *)v106 + 4), &v167) )
                    {
                      ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v172, v134, (struct ERECTL *)&v167, v25);
                      if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)v173) )
                      {
                        v161.left += v124;
                        v161.top += HIDWORD(v124);
                        v161.right += v124;
                        v161.bottom += HIDWORD(v124);
                        v124 = 0;
                        if ( (*v148 & 0x400) != 0 )
                          v107 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v158 + 2832);
                        else
                          v107 = EngCopyBits;
                        ((void (__fastcall *)(struct _SURFOBJ *, __int64, _BYTE *, unsigned __int64, struct _RECTL *, __int64 *))v107)(
                          v146,
                          (v142[0] + 24LL) & -(__int64)(v142[0] != 0),
                          v172,
                          v133 & -(__int64)(v118 != 0),
                          &v161,
                          &v124);
                      }
                    }
                    RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v134);
                    goto LABEL_199;
                  }
                  RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v123);
                  if ( v123 )
                  {
                    RGNOBJ::vSet((RGNOBJ *)&v123, &v162);
                    if ( RGNOBJ::bMerge((RGNOBJ *)&v134, (struct RGNOBJ *)&v123, (XCLIPOBJ *)((char *)v106 + 56), 8u) )
                    {
                      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v123);
                      goto LABEL_208;
                    }
                  }
                  RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v123);
                }
                RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v134);
                goto LABEL_219;
              }
            }
            if ( v72 >= v71 && v125 >= v120 )
            {
              v85 = v74 + v73;
              if ( v74 + v73 >= (unsigned int)v73 && v85 < 0x3FFFFFF5 )
              {
                v86 = PALLOCNOZ(4 * v85 + 40, 1752462151);
                v130 = (struct tagCOLORADJUSTMENT *)v86;
                if ( v86 )
                {
                  *(_DWORD *)v140 = v25;
                  stretch::vInitStrDDA((stretch *)v86, (struct stretch::_STRDDA *)&v160, v128, v13, pvBits);
                  v162 = *(struct _RECTL *)v86;
                  if ( v62 )
                  {
                    if ( ((unsigned __int8)v25 & *(_BYTE *)(v62 + 4)) != 0 )
                      v62 = 0;
                    v131 = (struct _SURFOBJ *)v62;
                  }
                  if ( v127 )
                    v127 &= -(__int64)(*(_BYTE *)(v127 + 20) != 0);
                  v87 = *(unsigned int *)(*(_QWORD *)&v52 + 96LL);
                  if ( v122 )
                    *(_DWORD *)(v86 + 20) = (v113 != v25) - v25;
                  v88 = v162.right - v162.left;
                  v89 = v13->right - v13->left;
                  v90 = v128;
                  if ( v128->right - v128->left <= v89 )
                  {
                    if ( v88 + 3 >= v88 )
                    {
                      v91 = (v88 + 3) >> 1;
                      if ( v91 < 0x15555553 )
                      {
LABEL_176:
                        if ( v88 <= 0x5F5E100 )
                        {
                          v92 = 12 * (v91 + 2);
                          if ( (unsigned int)v92 <= 0x2710000 )
                          {
                            v140 = (void (**)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *))(&stretch::apfnWrite)[v87];
                            v129 = (struct stretch::_XRUNLEN *(**)(struct stretch::_STRDDA *, struct stretch::_STRRUN *, unsigned __int8 *, unsigned __int8 *, struct _XLATEOBJ *, int, int, int))*(&stretch::apfnRead + 3 * *((unsigned int *)v16 + 24) + v113 - 1);
                            v93 = AllocFreeTmpBuffer(v92);
                            v138 = (struct _SURFOBJ *)v93;
                            if ( v93 )
                            {
                              v125 = v122;
                              v94 = *(_DWORD **)v139;
                              *(_QWORD *)&v164.left = *(_QWORD *)v139;
                              v95 = v129;
                              v141 = (struct _POINTL *)v129;
                              v157 = (int *)((char *)v16 + 88);
                              v96 = (struct _RECTL *)(*((_QWORD *)v16 + 10) + *((_DWORD *)v16 + 22) * v160.top);
                              v128 = v96;
                              *(_QWORD *)v139 = 0;
                              if ( v123 )
                              {
                                v139[0] = v160.left + *(_DWORD *)v145 - v90->left;
                                v97 = (struct _SURFOBJ *)(*(_QWORD *)v143
                                                        + *v94 * (v160.top + *((_DWORD *)v145 + 1) - v90->top));
                              }
                              else
                              {
                                v97 = 0;
                              }
                              v123 = v97;
                              v121 = 0;
                              if ( v122 )
                              {
                                v98 = -1;
                                if ( v113 != v25 )
                                  v98 = 0;
                                stretch::vInitBuffer(
                                  (stretch *)(v93 + 8),
                                  (struct stretch::_XRUNLEN *)&v162,
                                  (struct _RECTL *)v98,
                                  (unsigned int)v94);
                                v121 = v99;
                                v96 = v128;
                                v95 = v129;
                              }
                              *(_DWORD *)v93 = *(_DWORD *)(v86 + 4);
                              v100 = v160.top;
                              v101 = 0;
                              v117 = 0;
                              v102 = v127;
                              while ( 1 )
                              {
                                v114 = v100;
                                if ( v100 >= v160.bottom )
                                  break;
                                v103 = *(_DWORD *)(*(_QWORD *)(v86 + 24) + 4LL * v101);
                                v143 = v93 + 4;
                                *(_DWORD *)(v93 + 4) = v103;
                                if ( v103 )
                                {
                                  LODWORD(v109) = v160.left;
                                  v104 = ((__int64 (__fastcall *)(__int64, __int64, struct _RECTL *, struct _SURFOBJ *, struct _SURFOBJ *, struct _RECTL *, LONG, unsigned int))v95)(
                                           v86,
                                           v93,
                                           v96,
                                           v97,
                                           v131,
                                           v109,
                                           v160.right,
                                           v139[0]);
                                  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v140)(v93, v104, v52, v102);
                                  v100 = v114;
                                  if ( v122 )
                                  {
                                    stretch::vInitBuffer(
                                      (stretch *)(v93 + 8),
                                      (struct stretch::_XRUNLEN *)&v162,
                                      (struct _RECTL *)v121,
                                      v114);
                                    v100 = v114;
                                  }
                                  v95 = v129;
                                  v101 = v117;
                                  v96 = v128;
                                }
                                else if ( v122 )
                                {
                                  LODWORD(v109) = v160.left;
                                  ((void (__fastcall *)(__int64, __int64, struct _RECTL *, _QWORD, struct _SURFOBJ *, struct _RECTL *, LONG, _DWORD))v95)(
                                    v86,
                                    v93,
                                    v96,
                                    0,
                                    v131,
                                    v109,
                                    v160.right,
                                    0);
                                  v96 = v128;
                                  v100 = v114;
                                  v101 = v117;
                                  v95 = v129;
                                }
                                v96 = (struct _RECTL *)((char *)v96 + *v157);
                                v128 = v96;
                                *(_DWORD *)v93 += *(_DWORD *)v143;
                                if ( v97 )
                                {
                                  v97 = (struct _SURFOBJ *)((char *)v97 + **(int **)&v164.left);
                                  v123 = v97;
                                }
                                v100 += v25;
                                v101 += v25;
                                v117 = v101;
                              }
                              FreeTmpBuffer(v93);
                              Win32FreePool((void *)v86);
                              v84 = v162.bottom;
                              v82 = v162.right;
                              v83 = v162.top;
                              v81 = v162.left;
                              goto LABEL_198;
                            }
                          }
                        }
                      }
                    }
                  }
                  else if ( v88 < 0x15555553 )
                  {
                    v91 = v162.right - v162.left;
                    goto LABEL_176;
                  }
                  Win32FreePool((void *)v86);
                }
              }
            }
          }
        }
      }
    }
LABEL_219:
    SURFMEM::~SURFMEM((SURFMEM *)v144);
LABEL_220:
    RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v126);
    SURFMEM::~SURFMEM((SURFMEM *)v142);
    goto LABEL_221;
  }
  return 1;
}

```

## disassembly

```asm
0x140263d18  push    rbx
0x140263d1a  push    rsi
0x140263d1b  push    rdi
0x140263d1c  push    r12
0x140263d1e  push    r13
0x140263d20  push    r14
0x140263d22  push    r15
0x140263d24  sub     rsp, 3E0h
0x140263d2b  mov     rax, cs:__security_cookie
0x140263d32  xor     rax, rsp
0x140263d35  mov     [rsp+418h+var_48], rax
0x140263d3d  mov     r11, r9
0x140263d40  mov     [rsp+418h+var_330], r9
0x140263d48  mov     rbx, r8
0x140263d4b  mov     [rsp+418h+var_390], rbx
0x140263d53  mov     r15, rdx
0x140263d56  mov     [rsp+418h+var_318], rdx
0x140263d5e  mov     r10, rcx
0x140263d61  mov     [rsp+418h+var_350], rcx
0x140263d69  mov     rax, [rsp+418h+arg_20]
0x140263d71  mov     [rsp+418h+var_340], rax
0x140263d79  mov     rax, [rsp+418h+arg_48]
0x140263d81  mov     [rsp+418h+var_2C0], rax
0x140263d89  mov     r12, [rsp+418h+arg_38]
0x140263d91  mov     r13, [rsp+418h+arg_40]
0x140263d99  mov     [rsp+418h+var_368], r13
0x140263da1  mov     [rsp+418h+var_2B0], r9
0x140263da9  mov     r8, [rsp+418h+arg_28]
0x140263db1  mov     [rsp+418h+var_358], r8
0x140263db9  mov     r9, [rsp+418h+arg_30]
0x140263dc1  mov     [rsp+418h+var_300], r9
0x140263dc9  mov     eax, [rsp+418h+arg_50]
0x140263dd0  mov     [rsp+418h+var_3A8], eax
0x140263dd4  mov     rcx, [rsp+418h+arg_58]
0x140263ddc  mov     [rsp+418h+var_308], rcx
0x140263de4  dec     eax
0x140263de6  cmp     eax, 3
0x140263de9  ja      loc_1402655DF
0x140263def  xor     edi, edi
0x140263df1  test    r10, r10
0x140263df4  lea     rdx, [r10-18h]
0x140263df8  jnz     short loc_140263DFC
0x140263dfa  mov     edx, edi
0x140263dfc  mov     [rsp+418h+var_320], rdx
0x140263e04  test    r15, r15
0x140263e07  lea     r14, [r15-18h]
0x140263e0b  jnz     short loc_140263E10
0x140263e0d  mov     r14, rdi
0x140263e10  test    rbx, rbx
0x140263e13  jz      short loc_140263E3B
0x140263e15  lea     rax, [rbx-18h]
0x140263e19  mov     [rsp+418h+var_360], rax
0x140263e21  lea     rax, [rbx+40h]
0x140263e25  mov     qword ptr [rsp+418h+var_310], rax
0x140263e2d  lea     rax, [rbx+38h]
0x140263e31  mov     [rsp+418h+var_2E0], rax
0x140263e39  jmp     short loc_140263E5B
0x140263e3b  mov     [rsp+418h+var_360], rdi
0x140263e43  mov     qword ptr [rsp+418h+var_310], 58h ; 'X'
0x140263e4f  mov     [rsp+418h+var_2E0], 50h ; 'P'
0x140263e5b  test    rdx, rdx
0x140263e5e  jz      loc_1402655DF
0x140263e64  test    r14, r14
0x140263e67  jz      loc_1402655DF
0x140263e6d  lea     rax, [rdx+18h]
0x140263e71  mov     [rsp+418h+var_2B8], rax
0x140263e79  mov     ecx, [rax+48h]
0x140263e7c  lea     eax, [rcx-7]
0x140263e7f  cmp     eax, 2
0x140263e82  jbe     loc_1402655DF
0x140263e88  mov     eax, [r14+60h]
0x140263e8c  cmp     eax, 9
0x140263e8f  jz      loc_1402655DF
0x140263e95  cmp     ecx, 0Ah
0x140263e98  jz      loc_1402655DF
0x140263e9e  cmp     eax, 0Ah
0x140263ea1  jz      loc_1402655DF
0x140263ea7  mov     eax, [r13+8]
0x140263eab  cmp     [r13+0], eax
0x140263eaf  jz      loc_1402655D8
0x140263eb5  mov     eax, [r13+0Ch]
0x140263eb9  cmp     [r13+4], eax
0x140263ebd  jz      loc_1402655D8
0x140263ec3  mov     eax, [r12+8]
0x140263ec8  cmp     [r12], eax
0x140263ecc  jz      loc_1402655D8
0x140263ed2  mov     eax, [r12+0Ch]
0x140263ed7  cmp     [r12+4], eax
0x140263edc  jz      loc_1402655D8
0x140263ee2  mov     rax, [rdx+30h]
0x140263ee6  mov     [rsp+418h+var_370], rax
0x140263eee  mov     rbx, [r14+30h]
0x140263ef2  mov     edx, 2
0x140263ef7  lea     rcx, [rsp+418h+var_250]
0x140263eff  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x140263f04  movups  xmm0, xmmword ptr [r13+0]
0x140263f09  movdqu  xmmword ptr [rsp+418h+var_1A0.left], xmm0
0x140263f12  lea     esi, [rdx-1]
0x140263f15  cmp     [r15+4Ch], si
0x140263f1a  jnz     loc_140263FB9
0x140263f20  test    rbx, rbx
0x140263f23  jz      loc_140263FB9
0x140263f29  test    dword ptr [rbx+28h], 20000h
0x140263f30  jz      loc_140263FB9
0x140263f36  lea     r8, [rsp+418h+var_1A0]; struct _RECTL *
0x140263f3e  lea     rdx, [rsp+418h+var_250]; struct SURFMEM *
0x140263f46  mov     rcx, r15; struct _SURFOBJ *
0x140263f49  call    ?MulCopyDeviceToDIB@@YAHPEAU_SURFOBJ@@PEAVSURFMEM@@PEAU_RECTL@@@Z; MulCopyDeviceToDIB(_SURFOBJ *,SURFMEM *,_RECTL *)
0x140263f4e  test    eax, eax
0x140263f50  jz      loc_1402655D1
0x140263f56  mov     rcx, [rsp+418h+var_250]
0x140263f5e  test    rcx, rcx
0x140263f61  jz      loc_140265330
0x140263f67  lea     r13, [rsp+418h+var_1A0]
0x140263f6f  mov     [rsp+418h+var_368], r13
0x140263f77  lea     rax, [rcx+18h]
0x140263f7b  neg     rcx
0x140263f7e  sbb     r15, r15
0x140263f81  and     r15, rax
0x140263f84  mov     [rsp+418h+var_318], r15
0x140263f8c  lea     r14, [r15-18h]
0x140263f90  jnz     short loc_140263F95
0x140263f92  mov     r14, rdi
0x140263f95  mov     rbx, [r14+30h]
0x140263f99  mov     r10, [rsp+418h+var_350]
0x140263fa1  mov     r8, [rsp+418h+var_358]
0x140263fa9  mov     r9, [rsp+418h+var_300]
0x140263fb1  mov     r11, [rsp+418h+var_330]
0x140263fb9  mov     rax, [rsp+418h+var_340]
0x140263fc1  test    rax, rax
0x140263fc4  jz      short loc_140264002
0x140263fc6  mov     eax, [rax+4]
0x140263fc9  test    al, 8
0x140263fcb  jz      short loc_140264002
0x140263fcd  cmp     [r15+4Ch], di
0x140263fd2  jnz     loc_1402655D1
0x140263fd8  cmp     [r10+4Ch], si
0x140263fdd  jnz     loc_1402655D1
0x140263fe3  mov     eax, esi
0x140263fe5  mov     [rsp+418h+var_3A0], eax
0x140263fe9  mov     [rsp+418h+var_328], eax
0x140263ff0  mov     rdx, [rsp+418h+var_390]
0x140263ff8  test    rdx, rdx
0x140263ffb  jz      short loc_140264017
0x140263ffd  jmp     loc_1402655D1
0x140264002  mov     eax, edi
0x140264004  mov     [rsp+418h+var_3A0], eax
0x140264008  mov     [rsp+418h+var_328], eax
0x14026400f  mov     rdx, [rsp+418h+var_390]
0x140264017  mov     ecx, [rsp+418h+var_3A8]
0x14026401b  cmp     ecx, 4
0x14026401e  jnz     short loc_140264089
0x140264020  test    eax, eax
0x140264022  jnz     loc_1402655D1
0x140264028  mov     [rsp+418h+var_3C0], rdi
0x14026402d  mov     dword ptr [rsp+418h+var_3C8], edi
0x140264031  mov     rax, [rsp+418h+var_2C0]
0x140264039  mov     qword ptr [rsp+418h+var_3D0], rax
0x14026403e  mov     qword ptr [rsp+418h+var_3D8], r13
0x140264043  mov     qword ptr [rsp+418h+var_3E0], r12
0x140264048  mov     [rsp+418h+var_3E8], r9
0x14026404d  mov     [rsp+418h+var_3F0], r8
0x140264052  mov     rax, [rsp+418h+var_340]
0x14026405a  mov     [rsp+418h+pvBits], rax
0x14026405f  mov     r9, r11
0x140264062  mov     r8, rdx
0x140264065  mov     rdx, r15
0x140264068  mov     rcx, r10
0x14026406b  call    EngHTBlt
0x140264070  cmp     eax, 0FFFFFFFFh
0x140264073  jz      loc_1402655D1
0x140264079  test    eax, eax
0x14026407b  jz      short loc_1402640B2
0x14026407d  cmp     eax, esi
0x14026407f  jz      loc_140265330
0x140264085  mov     ecx, [rsp+418h+var_3A8]
0x140264089  mov     r8d, [r12+4]
0x14026408e  mov     eax, [r12+0Ch]
0x140264093  cmp     eax, r8d
0x140264096  jge     short loc_1402640BD
0x140264098  mov     [r12+4], eax
0x14026409d  mov     [r12+0Ch], r8d
0x1402640a2  mov     r11d, 2
0x1402640a8  mov     dword ptr [rsp+418h+var_39C], r11d
0x1402640ad  mov     r10d, eax
0x1402640b0  jmp     short loc_1402640CA
0x1402640b2  mov     ecx, 3
0x1402640b7  mov     [rsp+418h+var_3A8], ecx
0x1402640bb  jmp     short loc_140264089
0x1402640bd  mov     r11d, edi
0x1402640c0  mov     dword ptr [rsp+418h+var_39C], edi
0x1402640c4  mov     r10d, r8d
0x1402640c7  mov     r8d, eax
0x1402640ca  mov     edx, [r12]
0x1402640ce  mov     eax, [r12+8]
0x1402640d3  cmp     eax, edx
0x1402640d5  jge     short loc_1402640ED
0x1402640d7  mov     [r12], eax
0x1402640db  mov     [r12+8], edx
0x1402640e0  or      r11d, esi
0x1402640e3  mov     dword ptr [rsp+418h+var_39C], r11d
0x1402640e8  mov     r9d, eax
0x1402640eb  jmp     short loc_1402640F2
0x1402640ed  mov     r9d, edx
0x1402640f0  mov     edx, eax
0x1402640f2  cmp     ecx, 3
0x1402640f5  jnb     short loc_14026412B
0x1402640f7  cmp     [rsp+418h+var_360], rdi
0x1402640ff  jnz     short loc_14026412B
0x140264101  mov     dword ptr [rsp+418h+var_39C+4], esi
0x140264108  mov     ecx, [r13+8]
0x14026410c  sub     ecx, [r13+0]
0x140264110  sub     edx, r9d
0x140264113  cmp     edx, ecx
0x140264115  jl      short loc_140264136
0x140264117  mov     ecx, [r13+0Ch]
0x14026411b  sub     ecx, [r13+4]
0x14026411f  sub     r8d, r10d
0x140264122  cmp     r8d, ecx
0x140264125  mov     ecx, [rsp+418h+var_3A8]
0x140264129  jl      short loc_14026413A
0x14026412b  mov     eax, edi
0x14026412d  mov     dword ptr [rsp+418h+var_39C+4], eax
0x140264134  jmp     short loc_14026413C
0x140264136  mov     ecx, [rsp+418h+var_3A8]
0x14026413a  mov     eax, esi
0x14026413c  test    eax, eax
0x14026413e  jnz     short loc_14026414E
0x140264140  mov     eax, 3
0x140264145  cmp     ecx, eax
0x140264147  cmovb   ecx, eax
0x14026414a  mov     [rsp+418h+var_3A8], ecx
0x14026414e  mov     rdx, [rsp+418h+var_320]
0x140264156  lea     rax, [rdx+0A0h]
0x14026415d  mov     [rsp+418h+var_2A8], rax
0x140264165  mov     ecx, [rax]
0x140264167  bt      ecx, 12h
0x14026416b  jb      loc_1402643A8
0x140264171  mov     rax, [rsp+418h+var_340]
0x140264179  test    rax, rax
0x14026417c  jz      short loc_140264186
0x14026417e  mov     eax, [rax+4]
0x140264181  test    sil, al
0x140264184  jz      short loc_140264191
0x140264186  cmp     [r15+4Ch], di
0x14026418b  jz      loc_1402643A8
0x140264191  cmp     [rdx+64h], di
0x140264195  jz      loc_1402643A8
0x14026419b  test    cl, 2
0x14026419e  jz      loc_1402643A8
0x1402641a4  test    r11d, r11d
0x1402641a7  jnz     loc_1402643A8
0x1402641ad  cmp     [rsp+418h+var_390], rdi
0x1402641b5  jnz     loc_1402643A8
0x1402641bb  mov     ecx, [r13+0]
0x1402641bf  test    ecx, ecx
0x1402641c1  js      loc_1402643A8
0x1402641c7  mov     eax, [r13+4]
0x1402641cb  test    eax, eax
0x1402641cd  js      loc_1402643A8
0x1402641d3  mov     r8d, [r13+8]
0x1402641d7  cmp     r8d, [r15+20h]
0x1402641db  jg      loc_1402643A8
0x1402641e1  mov     edx, [r13+0Ch]
0x1402641e5  cmp     edx, [r15+24h]
0x1402641e9  jg      loc_1402643A8
0x1402641ef  mov     qword ptr [rsp+418h+sizl.cx], rdi
0x1402641f7  xorps   xmm0, xmm0
0x1402641fa  movups  [rsp+418h+var_1D8], xmm0
0x140264202  sub     r8d, ecx
0x140264205  mov     [rsp+418h+var_380], r8d
0x14026420d  mov     [rsp+418h+sizl.cx], r8d
0x140264215  sub     edx, eax
0x140264217  mov     [rsp+418h+var_3A4], edx
0x14026421b  mov     [rsp+418h+sizl.cy], edx
0x140264222  mov     ecx, [r12+8]
0x140264227  sub     ecx, [r12]
0x14026422b  cmp     r8d, ecx
0x14026422e  jg      loc_1402643A8
0x140264234  mov     ecx, [r12+0Ch]
0x140264239  sub     ecx, [r12+4]
0x14026423e  cmp     edx, ecx
0x140264240  jg      loc_1402643A8
0x140264246  mov     [rsp+418h+pvBits], rdi; pvBits
0x14026424b  xor     r9d, r9d; fl
0x14026424e  mov     rax, [rsp+418h+var_350]
0x140264256  mov     r8d, [rax+48h]; iFormat
0x14026425a  xor     edx, edx; lWidth
0x14026425c  mov     rcx, qword ptr [rsp+418h+sizl.cx]; sizl
0x140264264  call    cs:__imp_EngCreateBitmap
0x14026426b  nop     dword ptr [rax+rax+00h]
0x140264270  mov     qword ptr [rsp+418h+sizl.cx], rax
0x140264278  mov     rcx, rax; hsurf
0x14026427b  call    cs:__imp_EngLockSurface
0x140264282  nop     dword ptr [rax+rax+00h]
0x140264287  mov     r15, rax
0x14026428a  test    rax, rax
0x14026428d  jz      loc_1402643A8
0x140264293  mov     [rax+44h], edi
0x140264296  mov     qword ptr [rsp+418h+var_1D8], rdi
  ... truncated ...
```
