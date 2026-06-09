# EngStretchBltOld(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int *)

- ea: `0x14026723c`
- end: `0x140268b29`
- name: `?EngStretchBltOld@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAH@Z`
- size: `6381`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x140077380`

## callees

- `0x140075244`
- `0x140077348`
- `0x140079b44`
- `0x140079b84`
- `0x140079bb0`
- `0x14007a258`
- `0x14007a918`
- `0x14008cfa0`
- `0x1400fc340`
- `0x140107e00`
- `0x1401478f0`
- `0x140158f00`
- `0x140161b5c`
- `0x140163094`
- `0x14018be60`
- `0x1401acf04`
- `0x1401b3a90`
- `0x14026723c`
- `0x140298e04`
- `0x14032a720`
- `0x14032a910`
- `0x14032a980`
- `0x14032aa00`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140267c39`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402685e1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402686eb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140267c39`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402685e1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402686eb`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268827`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268848`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14026885c`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268ac8`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268ae9`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268827`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268848`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14026885c`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268ac8`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140268ae9`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140267b4c`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140267e15`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140267b4c`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140267e15`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140267bc6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402688e1`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14026891a`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140267bc6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402688e1`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14026891a`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140267bed`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140267bed`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14026893d`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14026893d`
- `win32kbase!EngLockSurface` at `0x14026779f`
- `win32kbase!EngLockSurface` at `0x14026779f`
- `win32kbase!EngUnlockSurface` at `0x1402678a7`
- `win32kbase!EngUnlockSurface` at `0x1402678a7`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140267c23`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140267cfa`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140267feb`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140267c23`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140267cfa`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x140267feb`
- `win32kbase!EngCreateBitmap` at `0x140267788`
- `win32kbase!EngCreateBitmap` at `0x140267788`
- `win32kbase!EngDeleteSurface` at `0x1402678bb`
- `win32kbase!EngDeleteSurface` at `0x1402678bb`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x14026898c`
- `win32kbase!?bIntersect@@YAHPEBU_RECTL@@0PEAU1@@Z` at `0x14026898c`
- `win32kbase!AllocFreeTmpBuffer` at `0x14026840d`
- `win32kbase!AllocFreeTmpBuffer` at `0x14026840d`
- `win32kbase!FreeTmpBuffer` at `0x1402687dd`
- `win32kbase!FreeTmpBuffer` at `0x1402687dd`
- `win32kbase!Win32FreePool` at `0x1402687ec`
- `win32kbase!Win32FreePool` at `0x140268ab4`
- `win32kbase!Win32FreePool` at `0x1402687ec`
- `win32kbase!Win32FreePool` at `0x140268ab4`

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
  SIZEL v50; // r15
  LONG v51; // r15d
  int v52; // r11d
  SIZEL v53; // r15
  int v54; // eax
  _DWORD *v55; // r12
  Gre::Base *v56; // rcx
  struct _SURFOBJ *v57; // r15
  struct Gre::Base::SESSION_GLOBALS *v58; // r9
  BOOL (__stdcall *v59)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  unsigned __int64 v60; // rbx
  int v61; // eax
  BOOL (__stdcall *v62)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // rax
  unsigned __int64 v63; // r9
  stretch *v64; // r8
  int v65; // eax
  int v66; // ecx
  __int64 v67; // rcx
  unsigned int v68; // ecx
  LONG v69; // r10d
  LONG v70; // r11d
  int v71; // edx
  int v72; // r9d
  int v73; // ecx
  int v74; // r8d
  int v75; // ecx
  XCLIPOBJ *v76; // rsi
  int v77; // ebx
  struct _RECTL *v78; // rcx
  LONG v79; // eax
  LONG v80; // ecx
  LONG v81; // edx
  LONG v82; // r8d
  unsigned int v83; // ecx
  __int64 v84; // r13
  __int64 v85; // r9
  unsigned int v86; // r8d
  int v87; // edx
  struct _RECTL *v88; // r12
  unsigned int v89; // eax
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // r8
  __int64 v93; // rbx
  __int64 v94; // rdx
  _DWORD *v95; // r9
  PVOID *v96; // r11
  struct _RECTL *v97; // r8
  struct _SURFOBJ *v98; // r14
  unsigned int v99; // r11d
  unsigned int v100; // r11d
  LONG v101; // r9d
  int v102; // r10d
  unsigned __int64 v103; // r12
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
  PVOID *v129; // [rsp+B8h] [rbp-360h]
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
    v129 = &a3[-1].pvScan0;
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
    v148 = (_DWORD *)(*(_QWORD *)&v137 + 144LL);
    v38 = *(_DWORD *)(*(_QWORD *)&v137 + 144LL);
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
                      if ( (*((_DWORD *)v16 + 36) & 0x400) != 0 )
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
      v51 = a8->right;
      v161.right = v51 + 1;
      v161.bottom = v25 + HIDWORD(*(_QWORD *)&a8->right);
      *(_QWORD *)&v164.left = 0;
      v164.right = *(_DWORD *)(*(_QWORD *)&v137 + 56LL);
      v164.bottom = *(_DWORD *)(*(_QWORD *)&v137 + 60LL);
      ERECTL::operator*=(&v161, &v164);
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
        v165.m128i_i32[0] = v52 - v161.left;
        v165.m128i_i32[1] -= v161.top;
        v165.m128i_i32[2] = v51 - v161.left;
        v165.m128i_i32[3] -= v161.top;
        v149[3] = 0;
        v152 = 0;
        v149[1] = v25 + v161.right - v161.left;
        v149[2] = v25 + v161.bottom - v161.top;
        v150 = 0;
        v53 = v137;
        if ( v118 )
          v54 = *((_DWORD *)v16 + 24);
        else
          v54 = *(_DWORD *)(*(_QWORD *)&v137 + 96LL);
        v149[0] = v54;
        v55 = v148;
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
        v130 = *(struct tagCOLORADJUSTMENT **)(*(_QWORD *)&v53 + 48LL);
        v57 = v146;
        if ( v130 )
          PDEVOBJ::vSync((PDEVOBJ *)&v130, v146, 0, 0);
        if ( v129 )
        {
          v58 = Gre::Base::Globals(v56);
          if ( (*v55 & 0x400) != 0 )
            v59 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v127 + 2832);
          else
            v59 = EngCopyBits;
          v109 = (struct _RECTL *)&v124;
          pvBits = &v161;
          ((void (__fastcall *)(__int64, struct _SURFOBJ *, _QWORD, char *))v59)(
            (v142[0] + 24LL) & -(__int64)(v142[0] != 0),
            v57,
            0,
            (char *)v58 + 4664);
        }
        v50 = (SIZEL)v142[0];
        v13 = (struct _RECTL *)&v165;
        v127 = (unsigned __int64)v171;
      }
      else
      {
        v50 = v137;
        v127 = (unsigned __int64)v135;
      }
      sizl = v50;
    }
    else
    {
      v50 = v137;
      sizl = v137;
      v127 = (unsigned __int64)v135;
    }
    v130 = (struct tagCOLORADJUSTMENT *)*((_QWORD *)v16 + 6);
    if ( v130 )
      PDEVOBJ::vSync((PDEVOBJ *)&v130, v138, 0, 0);
    ERECTL::operator*=(&v160, v14);
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
        v61 = *((_DWORD *)v16 + 24);
      else
        v61 = *(_DWORD *)(*(_QWORD *)&v50 + 96LL);
      v153[0] = v61;
      v155 = *((_DWORD *)v16 + 36) & 0x40000;
      SURFMEM::bCreateDIB((SURFMEM *)v144, (struct _DEVBITMAPINFO *)v153, 0, 0, 0, 0, 0, 0, v25, 0);
      if ( !v144[0] )
        goto LABEL_219;
      *(_QWORD *)&v163.left = 0;
      v163.right = v160.right - v160.left;
      v163.bottom = v160.bottom - v160.top;
      if ( (*((_DWORD *)v16 + 36) & 0x400) != 0 )
        v62 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v19 + 2832);
      else
        v62 = EngCopyBits;
      v63 = 0;
      if ( !v118 )
        v63 = v133;
      v109 = &v160;
      pvBits = &v163;
      ((void (__fastcall *)(unsigned __int64, char *, _QWORD, unsigned __int64))v62)(
        ((unsigned __int64)v144[0] + 24) & -(__int64)(v144[0] != 0),
        (char *)v16 + 24,
        0,
        v63);
      v163.left = v14->left - v160.left;
      v163.top = v14->top - v160.top;
      v163.right = v14->right - v160.left;
      v163.bottom = v14->bottom - v160.top;
      v64 = v144[0];
      v16 = v144[0];
      v14 = &v163;
      v128 = &v163;
      v60 = 0;
      v131 = 0;
      v160.right -= v160.left;
      v65 = v160.bottom - v160.top;
      v160.bottom -= v160.top;
      *(_QWORD *)&v160.left = 0;
      if ( (v119 & 2) != 0 )
      {
        v66 = *((_DWORD *)v144[0] + 22);
        if ( v66 <= 0 )
          v67 = *((_QWORD *)v144[0] + 9);
        else
          v67 = *((_QWORD *)v144[0] + 9) + v66 * (v65 - 1);
        *((_QWORD *)v144[0] + 10) = v67;
        *((_DWORD *)v144[0] + 22) = -*((_DWORD *)v144[0] + 22);
        v64 = v144[0];
      }
      if ( ((unsigned __int8)v119 & (unsigned __int8)v25) != 0 )
      {
        v68 = *((_DWORD *)v64 + 24);
        if ( v68 - 1 > 5 )
          goto LABEL_219;
        ((void (__fastcall *)(stretch *))funcs_14005AB36[v68 - 1])(v64);
      }
    }
    else
    {
      v60 = 0;
      if ( !v118 )
        v60 = v133;
      v131 = (struct _SURFOBJ *)v60;
    }
    v130 = *(struct tagCOLORADJUSTMENT **)(*(_QWORD *)&v50 + 48LL);
    if ( v130 )
      PDEVOBJ::vSync(
        (PDEVOBJ *)&v130,
        (struct _SURFOBJ *)((*(_QWORD *)&v50 + 24LL) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)&v50 >> 64)),
        0,
        0);
    v69 = v14->left;
    v70 = v14->right;
    v71 = v70 - v14->left;
    if ( v71 < 128000000 )
    {
      v120 = v14->top;
      v125 = v14->bottom;
      v72 = v125 - v120;
      if ( v125 - v120 < 128000000 )
      {
        v73 = v13->right - v13->left;
        if ( v73 < 128000000 )
        {
          v74 = v13->bottom - v13->top;
          if ( v74 < 128000000 && v73 > -128000000 && v74 > -128000000 )
          {
            if ( v113 == 3 && !v123 && (!v60 || ((unsigned __int8)*(_DWORD *)(v60 + 4) & (unsigned __int8)v25) != 0) )
            {
              v75 = *((_DWORD *)v16 + 24);
              if ( *(_DWORD *)(*(_QWORD *)&v50 + 96LL) == v75 && ((v75 - 3) & 0xFFFFFFFC) == 0 && v75 != 5 )
              {
                if ( v127 && *(_BYTE *)(v127 + 20) == 3 )
                {
                  v164 = 0;
                  *(_QWORD *)&v160.right = 0;
                  *(_QWORD *)&v160.left = 0;
                  v168 = 0;
                  v169 = 0;
                  v76 = v135;
                  XCLIPOBJ::cEnumStart(v135, 0, 0, 4u, 0);
                  do
                  {
                    v77 = XCLIPOBJ::bEnum(v76, 0x14u, &v168, 0);
                    if ( v168.left )
                    {
                      LODWORD(v111) = *(_DWORD *)(*(_QWORD *)&v50 + 96LL);
                      LODWORD(v110) = *((_DWORD *)v16 + 22);
                      stretch::StretchDIBDirect(
                        *(stretch **)(*(_QWORD *)&v50 + 80LL),
                        (void *)*(unsigned int *)(*(_QWORD *)&v50 + 88LL),
                        *(_DWORD *)(*(_QWORD *)&v50 + 56LL),
                        *(_DWORD *)(*(_QWORD *)&v50 + 60LL),
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
                  while ( v77 );
                  v25 = 1;
                }
                else
                {
                  v78 = v13;
                  if ( v127 && *(_BYTE *)(v127 + 20) == (_BYTE)v25 )
                    v78 = (struct _RECTL *)(v127 + 4);
                  LODWORD(v111) = *(_DWORD *)(*(_QWORD *)&v50 + 96LL);
                  LODWORD(v110) = *((_DWORD *)v16 + 22);
                  stretch::StretchDIBDirect(
                    *(stretch **)(*(_QWORD *)&v50 + 80LL),
                    (void *)*(unsigned int *)(*(_QWORD *)&v50 + 88LL),
                    *(_DWORD *)(*(_QWORD *)&v50 + 56LL),
                    *(_DWORD *)(*(_QWORD *)&v50 + 60LL),
                    (unsigned int)v13,
                    *((struct _RECTL **)v16 + 10),
                    v110,
                    *((_DWORD *)v16 + 14),
                    *((_DWORD *)v16 + 15),
                    (unsigned int)v14,
                    &v160,
                    v78,
                    v111,
                    v112);
                }
                v79 = v160.left;
                v162 = v160;
                v80 = v160.right;
                v81 = v160.top;
                v82 = v160.bottom;
LABEL_198:
                if ( v50 == v137 )
                {
LABEL_199:
                  SURFMEM::~SURFMEM((SURFMEM *)v144);
                  goto LABEL_200;
                }
                v162.left = v124 + v79;
                v162.top = HIDWORD(v124) + v81;
                v162.right = v124 + v80;
                v162.bottom = HIDWORD(v124) + v82;
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
            if ( v70 >= v69 && v125 >= v120 )
            {
              v83 = v72 + v71;
              if ( v72 + v71 >= (unsigned int)v71 && v83 < 0x3FFFFFF5 )
              {
                v84 = PALLOCNOZ(4 * v83 + 40, 1752462151);
                v130 = (struct tagCOLORADJUSTMENT *)v84;
                if ( v84 )
                {
                  *(_DWORD *)v140 = v25;
                  stretch::vInitStrDDA((stretch *)v84, (struct stretch::_STRDDA *)&v160, v128, v13, pvBits);
                  v162 = *(struct _RECTL *)v84;
                  if ( v60 )
                  {
                    if ( ((unsigned __int8)v25 & *(_BYTE *)(v60 + 4)) != 0 )
                      v60 = 0;
                    v131 = (struct _SURFOBJ *)v60;
                  }
                  if ( v127 )
                    v127 &= -(__int64)(*(_BYTE *)(v127 + 20) != 0);
                  v85 = *(unsigned int *)(*(_QWORD *)&v50 + 96LL);
                  if ( v122 )
                    *(_DWORD *)(v84 + 20) = (v113 != v25) - v25;
                  v86 = v162.right - v162.left;
                  v87 = v13->right - v13->left;
                  v88 = v128;
                  if ( v128->right - v128->left <= v87 )
                  {
                    if ( v86 + 3 >= v86 )
                    {
                      v89 = (v86 + 3) >> 1;
                      if ( v89 < 0x15555553 )
                      {
LABEL_176:
                        if ( v86 <= 0x5F5E100 )
                        {
                          v90 = 12 * (v89 + 2);
                          if ( (unsigned int)v90 <= 0x2710000 )
                          {
                            v140 = (void (**)(struct stretch::_STRRUN *, struct stretch::_XRUNLEN *, struct SURFACE *, struct _CLIPOBJ *))(&stretch::apfnWrite)[v85];
                            v91 = v113 - 1;
                            v92 = v91 + 3LL * *((unsigned int *)v16 + 24);
                            v129 = (PVOID *)*(&stretch::apfnRead + v92);
                            v93 = AllocFreeTmpBuffer(v90, v91, v92);
                            v138 = (struct _SURFOBJ *)v93;
                            if ( v93 )
                            {
                              v94 = v122;
                              v125 = v122;
                              v95 = *(_DWORD **)v139;
                              *(_QWORD *)&v164.left = *(_QWORD *)v139;
                              v96 = v129;
                              v141 = (struct _POINTL *)v129;
                              v157 = (int *)((char *)v16 + 88);
                              v97 = (struct _RECTL *)(*((_QWORD *)v16 + 10) + *((_DWORD *)v16 + 22) * v160.top);
                              v128 = v97;
                              *(_QWORD *)v139 = 0;
                              if ( v123 )
                              {
                                v139[0] = v160.left + *(_DWORD *)v145 - v88->left;
                                v98 = (struct _SURFOBJ *)(*(_QWORD *)v143
                                                        + *v95 * (v160.top + *((_DWORD *)v145 + 1) - v88->top));
                              }
                              else
                              {
                                v98 = 0;
                              }
                              v123 = v98;
                              v121 = 0;
                              if ( v122 )
                              {
                                v99 = -1;
                                if ( v113 != v25 )
                                  v99 = 0;
                                stretch::vInitBuffer(
                                  (stretch *)(v93 + 8),
                                  (struct stretch::_XRUNLEN *)&v162,
                                  (struct _RECTL *)v99,
                                  (unsigned int)v95);
                                v121 = v100;
                                v97 = v128;
                                v96 = v129;
                              }
                              *(_DWORD *)v93 = *(_DWORD *)(v84 + 4);
                              v101 = v160.top;
                              v102 = 0;
                              v117 = 0;
                              v103 = v127;
                              while ( 1 )
                              {
                                v114 = v101;
                                if ( v101 >= v160.bottom )
                                  break;
                                v94 = *(unsigned int *)(*(_QWORD *)(v84 + 24) + 4LL * v102);
                                v143 = v93 + 4;
                                *(_DWORD *)(v93 + 4) = v94;
                                if ( (_DWORD)v94 )
                                {
                                  LODWORD(v109) = v160.left;
                                  v104 = ((__int64 (__fastcall *)(__int64, __int64, struct _RECTL *, struct _SURFOBJ *, struct _SURFOBJ *, struct _RECTL *, LONG, unsigned int))v96)(
                                           v84,
                                           v93,
                                           v97,
                                           v98,
                                           v131,
                                           v109,
                                           v160.right,
                                           v139[0]);
                                  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v140)(v93, v104, v50, v103);
                                  v101 = v114;
                                  v94 = v122;
                                  if ( v122 )
                                  {
                                    stretch::vInitBuffer(
                                      (stretch *)(v93 + 8),
                                      (struct stretch::_XRUNLEN *)&v162,
                                      (struct _RECTL *)v121,
                                      v114);
                                    v101 = v114;
                                  }
                                  v96 = v129;
                                  v102 = v117;
                                  v97 = v128;
                                }
                                else if ( v122 )
                                {
                                  LODWORD(v109) = v160.left;
                                  ((void (__fastcall *)(__int64, __int64, struct _RECTL *, _QWORD, struct _SURFOBJ *, struct _RECTL *, LONG, _DWORD))v96)(
                                    v84,
                                    v93,
                                    v97,
                                    0,
                                    v131,
                                    v109,
                                    v160.right,
                                    0);
                                  v97 = v128;
                                  v101 = v114;
                                  v102 = v117;
                                  v96 = v129;
                                }
                                v97 = (struct _RECTL *)((char *)v97 + *v157);
                                v128 = v97;
                                *(_DWORD *)v93 += *(_DWORD *)v143;
                                if ( v98 )
                                {
                                  v98 = (struct _SURFOBJ *)((char *)v98 + **(int **)&v164.left);
                                  v123 = v98;
                                }
                                v101 += v25;
                                v102 += v25;
                                v117 = v102;
                              }
                              FreeTmpBuffer(v93, v94, v97);
                              Win32FreePool((void *)v84);
                              v82 = v162.bottom;
                              v80 = v162.right;
                              v81 = v162.top;
                              v79 = v162.left;
                              goto LABEL_198;
                            }
                          }
                        }
                      }
                    }
                  }
                  else if ( v86 < 0x15555553 )
                  {
                    v89 = v162.right - v162.left;
                    goto LABEL_176;
                  }
                  Win32FreePool((void *)v84);
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
0x14026723c  push    rbx
0x14026723e  push    rsi
0x14026723f  push    rdi
0x140267240  push    r12
0x140267242  push    r13
0x140267244  push    r14
0x140267246  push    r15
0x140267248  sub     rsp, 3E0h
0x14026724f  mov     rax, cs:__security_cookie
0x140267256  xor     rax, rsp
0x140267259  mov     [rsp+418h+var_48], rax
0x140267261  mov     r11, r9
0x140267264  mov     [rsp+418h+var_330], r9
0x14026726c  mov     rbx, r8
0x14026726f  mov     [rsp+418h+var_390], rbx
0x140267277  mov     r15, rdx
0x14026727a  mov     [rsp+418h+var_318], rdx
0x140267282  mov     r10, rcx
0x140267285  mov     [rsp+418h+var_350], rcx
0x14026728d  mov     rax, [rsp+418h+arg_20]
0x140267295  mov     [rsp+418h+var_340], rax
0x14026729d  mov     rax, [rsp+418h+arg_48]
0x1402672a5  mov     [rsp+418h+var_2C0], rax
0x1402672ad  mov     r12, [rsp+418h+arg_38]
0x1402672b5  mov     r13, [rsp+418h+arg_40]
0x1402672bd  mov     [rsp+418h+var_368], r13
0x1402672c5  mov     [rsp+418h+var_2B0], r9
0x1402672cd  mov     r8, [rsp+418h+arg_28]
0x1402672d5  mov     [rsp+418h+var_358], r8
0x1402672dd  mov     r9, [rsp+418h+arg_30]
0x1402672e5  mov     [rsp+418h+var_300], r9
0x1402672ed  mov     eax, [rsp+418h+arg_50]
0x1402672f4  mov     [rsp+418h+var_3A8], eax
0x1402672f8  mov     rcx, [rsp+418h+arg_58]
0x140267300  mov     [rsp+418h+var_308], rcx
0x140267308  dec     eax
0x14026730a  cmp     eax, 3
0x14026730d  ja      loc_140268B03
0x140267313  xor     edi, edi
0x140267315  test    r10, r10
0x140267318  lea     rdx, [r10-18h]
0x14026731c  jnz     short loc_140267320
0x14026731e  mov     edx, edi
0x140267320  mov     [rsp+418h+var_320], rdx
0x140267328  test    r15, r15
0x14026732b  lea     r14, [r15-18h]
0x14026732f  jnz     short loc_140267334
0x140267331  mov     r14, rdi
0x140267334  test    rbx, rbx
0x140267337  jz      short loc_14026735F
0x140267339  lea     rax, [rbx-18h]
0x14026733d  mov     [rsp+418h+var_360], rax
0x140267345  lea     rax, [rbx+40h]
0x140267349  mov     qword ptr [rsp+418h+var_310], rax
0x140267351  lea     rax, [rbx+38h]
0x140267355  mov     [rsp+418h+var_2E0], rax
0x14026735d  jmp     short loc_14026737F
0x14026735f  mov     [rsp+418h+var_360], rdi
0x140267367  mov     qword ptr [rsp+418h+var_310], 58h ; 'X'
0x140267373  mov     [rsp+418h+var_2E0], 50h ; 'P'
0x14026737f  test    rdx, rdx
0x140267382  jz      loc_140268B03
0x140267388  test    r14, r14
0x14026738b  jz      loc_140268B03
0x140267391  lea     rax, [rdx+18h]
0x140267395  mov     [rsp+418h+var_2B8], rax
0x14026739d  mov     ecx, [rax+48h]
0x1402673a0  lea     eax, [rcx-7]
0x1402673a3  cmp     eax, 2
0x1402673a6  jbe     loc_140268B03
0x1402673ac  mov     eax, [r14+60h]
0x1402673b0  cmp     eax, 9
0x1402673b3  jz      loc_140268B03
0x1402673b9  cmp     ecx, 0Ah
0x1402673bc  jz      loc_140268B03
0x1402673c2  cmp     eax, 0Ah
0x1402673c5  jz      loc_140268B03
0x1402673cb  mov     eax, [r13+8]
0x1402673cf  cmp     [r13+0], eax
0x1402673d3  jz      loc_140268AFC
0x1402673d9  mov     eax, [r13+0Ch]
0x1402673dd  cmp     [r13+4], eax
0x1402673e1  jz      loc_140268AFC
0x1402673e7  mov     eax, [r12+8]
0x1402673ec  cmp     [r12], eax
0x1402673f0  jz      loc_140268AFC
0x1402673f6  mov     eax, [r12+0Ch]
0x1402673fb  cmp     [r12+4], eax
0x140267400  jz      loc_140268AFC
0x140267406  mov     rax, [rdx+30h]
0x14026740a  mov     [rsp+418h+var_370], rax
0x140267412  mov     rbx, [r14+30h]
0x140267416  mov     edx, 2
0x14026741b  lea     rcx, [rsp+418h+var_250]
0x140267423  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x140267428  movups  xmm0, xmmword ptr [r13+0]
0x14026742d  movdqu  xmmword ptr [rsp+418h+var_1A0.left], xmm0
0x140267436  lea     esi, [rdx-1]
0x140267439  cmp     [r15+4Ch], si
0x14026743e  jnz     loc_1402674DD
0x140267444  test    rbx, rbx
0x140267447  jz      loc_1402674DD
0x14026744d  test    dword ptr [rbx+28h], 20000h
0x140267454  jz      loc_1402674DD
0x14026745a  lea     r8, [rsp+418h+var_1A0]; struct _RECTL *
0x140267462  lea     rdx, [rsp+418h+var_250]; struct SURFMEM *
0x14026746a  mov     rcx, r15; struct _SURFOBJ *
0x14026746d  call    ?MulCopyDeviceToDIB@@YAHPEAU_SURFOBJ@@PEAVSURFMEM@@PEAU_RECTL@@@Z; MulCopyDeviceToDIB(_SURFOBJ *,SURFMEM *,_RECTL *)
0x140267472  test    eax, eax
0x140267474  jz      loc_140268AF5
0x14026747a  mov     rcx, [rsp+418h+var_250]
0x140267482  test    rcx, rcx
0x140267485  jz      loc_140268854
0x14026748b  lea     r13, [rsp+418h+var_1A0]
0x140267493  mov     [rsp+418h+var_368], r13
0x14026749b  lea     rax, [rcx+18h]
0x14026749f  neg     rcx
0x1402674a2  sbb     r15, r15
0x1402674a5  and     r15, rax
0x1402674a8  mov     [rsp+418h+var_318], r15
0x1402674b0  lea     r14, [r15-18h]
0x1402674b4  jnz     short loc_1402674B9
0x1402674b6  mov     r14, rdi
0x1402674b9  mov     rbx, [r14+30h]
0x1402674bd  mov     r10, [rsp+418h+var_350]
0x1402674c5  mov     r8, [rsp+418h+var_358]
0x1402674cd  mov     r9, [rsp+418h+var_300]
0x1402674d5  mov     r11, [rsp+418h+var_330]
0x1402674dd  mov     rax, [rsp+418h+var_340]
0x1402674e5  test    rax, rax
0x1402674e8  jz      short loc_140267526
0x1402674ea  mov     eax, [rax+4]
0x1402674ed  test    al, 8
0x1402674ef  jz      short loc_140267526
0x1402674f1  cmp     [r15+4Ch], di
0x1402674f6  jnz     loc_140268AF5
0x1402674fc  cmp     [r10+4Ch], si
0x140267501  jnz     loc_140268AF5
0x140267507  mov     eax, esi
0x140267509  mov     [rsp+418h+var_3A0], eax
0x14026750d  mov     [rsp+418h+var_328], eax
0x140267514  mov     rdx, [rsp+418h+var_390]
0x14026751c  test    rdx, rdx
0x14026751f  jz      short loc_14026753B
0x140267521  jmp     loc_140268AF5
0x140267526  mov     eax, edi
0x140267528  mov     [rsp+418h+var_3A0], eax
0x14026752c  mov     [rsp+418h+var_328], eax
0x140267533  mov     rdx, [rsp+418h+var_390]
0x14026753b  mov     ecx, [rsp+418h+var_3A8]
0x14026753f  cmp     ecx, 4
0x140267542  jnz     short loc_1402675AD
0x140267544  test    eax, eax
0x140267546  jnz     loc_140268AF5
0x14026754c  mov     [rsp+418h+var_3C0], rdi
0x140267551  mov     dword ptr [rsp+418h+var_3C8], edi
0x140267555  mov     rax, [rsp+418h+var_2C0]
0x14026755d  mov     qword ptr [rsp+418h+var_3D0], rax
0x140267562  mov     qword ptr [rsp+418h+var_3D8], r13
0x140267567  mov     qword ptr [rsp+418h+var_3E0], r12
0x14026756c  mov     [rsp+418h+var_3E8], r9
0x140267571  mov     [rsp+418h+var_3F0], r8
0x140267576  mov     rax, [rsp+418h+var_340]
0x14026757e  mov     [rsp+418h+pvBits], rax
0x140267583  mov     r9, r11
0x140267586  mov     r8, rdx
0x140267589  mov     rdx, r15
0x14026758c  mov     rcx, r10
0x14026758f  call    EngHTBlt
0x140267594  cmp     eax, 0FFFFFFFFh
0x140267597  jz      loc_140268AF5
0x14026759d  test    eax, eax
0x14026759f  jz      short loc_1402675D6
0x1402675a1  cmp     eax, esi
0x1402675a3  jz      loc_140268854
0x1402675a9  mov     ecx, [rsp+418h+var_3A8]
0x1402675ad  mov     r8d, [r12+4]
0x1402675b2  mov     eax, [r12+0Ch]
0x1402675b7  cmp     eax, r8d
0x1402675ba  jge     short loc_1402675E1
0x1402675bc  mov     [r12+4], eax
0x1402675c1  mov     [r12+0Ch], r8d
0x1402675c6  mov     r11d, 2
0x1402675cc  mov     dword ptr [rsp+418h+var_39C], r11d
0x1402675d1  mov     r10d, eax
0x1402675d4  jmp     short loc_1402675EE
0x1402675d6  mov     ecx, 3
0x1402675db  mov     [rsp+418h+var_3A8], ecx
0x1402675df  jmp     short loc_1402675AD
0x1402675e1  mov     r11d, edi
0x1402675e4  mov     dword ptr [rsp+418h+var_39C], edi
0x1402675e8  mov     r10d, r8d
0x1402675eb  mov     r8d, eax
0x1402675ee  mov     edx, [r12]
0x1402675f2  mov     eax, [r12+8]
0x1402675f7  cmp     eax, edx
0x1402675f9  jge     short loc_140267611
0x1402675fb  mov     [r12], eax
0x1402675ff  mov     [r12+8], edx
0x140267604  or      r11d, esi
0x140267607  mov     dword ptr [rsp+418h+var_39C], r11d
0x14026760c  mov     r9d, eax
0x14026760f  jmp     short loc_140267616
0x140267611  mov     r9d, edx
0x140267614  mov     edx, eax
0x140267616  cmp     ecx, 3
0x140267619  jnb     short loc_14026764F
0x14026761b  cmp     [rsp+418h+var_360], rdi
0x140267623  jnz     short loc_14026764F
0x140267625  mov     dword ptr [rsp+418h+var_39C+4], esi
0x14026762c  mov     ecx, [r13+8]
0x140267630  sub     ecx, [r13+0]
0x140267634  sub     edx, r9d
0x140267637  cmp     edx, ecx
0x140267639  jl      short loc_14026765A
0x14026763b  mov     ecx, [r13+0Ch]
0x14026763f  sub     ecx, [r13+4]
0x140267643  sub     r8d, r10d
0x140267646  cmp     r8d, ecx
0x140267649  mov     ecx, [rsp+418h+var_3A8]
0x14026764d  jl      short loc_14026765E
0x14026764f  mov     eax, edi
0x140267651  mov     dword ptr [rsp+418h+var_39C+4], eax
0x140267658  jmp     short loc_140267660
0x14026765a  mov     ecx, [rsp+418h+var_3A8]
0x14026765e  mov     eax, esi
0x140267660  test    eax, eax
0x140267662  jnz     short loc_140267672
0x140267664  mov     eax, 3
0x140267669  cmp     ecx, eax
0x14026766b  cmovb   ecx, eax
0x14026766e  mov     [rsp+418h+var_3A8], ecx
0x140267672  mov     rdx, [rsp+418h+var_320]
0x14026767a  lea     rax, [rdx+90h]
0x140267681  mov     [rsp+418h+var_2A8], rax
0x140267689  mov     ecx, [rax]
0x14026768b  bt      ecx, 12h
0x14026768f  jb      loc_1402678CC
0x140267695  mov     rax, [rsp+418h+var_340]
0x14026769d  test    rax, rax
0x1402676a0  jz      short loc_1402676AA
0x1402676a2  mov     eax, [rax+4]
0x1402676a5  test    sil, al
0x1402676a8  jz      short loc_1402676B5
0x1402676aa  cmp     [r15+4Ch], di
0x1402676af  jz      loc_1402678CC
0x1402676b5  cmp     [rdx+64h], di
0x1402676b9  jz      loc_1402678CC
0x1402676bf  test    cl, 2
0x1402676c2  jz      loc_1402678CC
0x1402676c8  test    r11d, r11d
0x1402676cb  jnz     loc_1402678CC
0x1402676d1  cmp     [rsp+418h+var_390], rdi
0x1402676d9  jnz     loc_1402678CC
0x1402676df  mov     ecx, [r13+0]
0x1402676e3  test    ecx, ecx
0x1402676e5  js      loc_1402678CC
0x1402676eb  mov     eax, [r13+4]
0x1402676ef  test    eax, eax
0x1402676f1  js      loc_1402678CC
0x1402676f7  mov     r8d, [r13+8]
0x1402676fb  cmp     r8d, [r15+20h]
0x1402676ff  jg      loc_1402678CC
0x140267705  mov     edx, [r13+0Ch]
0x140267709  cmp     edx, [r15+24h]
0x14026770d  jg      loc_1402678CC
0x140267713  mov     qword ptr [rsp+418h+sizl.cx], rdi
0x14026771b  xorps   xmm0, xmm0
0x14026771e  movups  [rsp+418h+var_1D8], xmm0
0x140267726  sub     r8d, ecx
0x140267729  mov     [rsp+418h+var_380], r8d
0x140267731  mov     [rsp+418h+sizl.cx], r8d
0x140267739  sub     edx, eax
0x14026773b  mov     [rsp+418h+var_3A4], edx
0x14026773f  mov     [rsp+418h+sizl.cy], edx
0x140267746  mov     ecx, [r12+8]
0x14026774b  sub     ecx, [r12]
0x14026774f  cmp     r8d, ecx
0x140267752  jg      loc_1402678CC
0x140267758  mov     ecx, [r12+0Ch]
0x14026775d  sub     ecx, [r12+4]
0x140267762  cmp     edx, ecx
0x140267764  jg      loc_1402678CC
0x14026776a  mov     [rsp+418h+pvBits], rdi; pvBits
0x14026776f  xor     r9d, r9d; fl
0x140267772  mov     rax, [rsp+418h+var_350]
0x14026777a  mov     r8d, [rax+48h]; iFormat
0x14026777e  xor     edx, edx; lWidth
0x140267780  mov     rcx, qword ptr [rsp+418h+sizl.cx]; sizl
0x140267788  call    cs:__imp_EngCreateBitmap
0x14026778f  nop     dword ptr [rax+rax+00h]
0x140267794  mov     qword ptr [rsp+418h+sizl.cx], rax
0x14026779c  mov     rcx, rax; hsurf
0x14026779f  call    cs:__imp_EngLockSurface
0x1402677a6  nop     dword ptr [rax+rax+00h]
0x1402677ab  mov     r15, rax
0x1402677ae  test    rax, rax
0x1402677b1  jz      loc_1402678CC
0x1402677b7  mov     [rax+44h], edi
0x1402677ba  mov     qword ptr [rsp+418h+var_1D8], rdi
  ... truncated ...
```
