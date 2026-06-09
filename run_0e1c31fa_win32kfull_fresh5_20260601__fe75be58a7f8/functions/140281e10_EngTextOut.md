# EngTextOut

- ea: `0x140281e10`
- end: `0x140282a59`
- name: `EngTextOut`
- size: `3145`
- prototype: `BOOL __stdcall(SURFOBJ *pso, STROBJ *pstro, FONTOBJ *pfo, CLIPOBJ *pco, RECTL *prclExtra, RECTL *prclOpaque, BRUSHOBJ *pboFore, BRUSHOBJ *pboOpaque, POINTL *pptlOrg, MIX mix)`
- caller_count: `5`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14015ab20`
- `0x1402a1080`
- `0x1402a2a40`
- `0x1403140b0`
- `0x1403213b0`

## callees

- `0x140051ff0`
- `0x140052170`
- `0x14005221c`
- `0x1400954e4`
- `0x1400984c0`
- `0x1400f6d54`
- `0x14012a770`
- `0x14012a914`
- `0x14019b754`
- `0x1401b164c`
- `0x1401c9ac4`
- `0x1401c9bf8`
- `0x140281500`
- `0x140281e10`
- `0x140311264`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342540`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402825ce`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402825ce`
- `win32kbase!EngAllocUserMem` at `0x14028209b`
- `win32kbase!EngAllocUserMem` at `0x14028209b`
- `win32kbase!EngFreeUserMem` at `0x1402821a6`
- `win32kbase!EngFreeUserMem` at `0x140282454`
- `win32kbase!EngFreeUserMem` at `0x1402829e8`
- `win32kbase!EngFreeUserMem` at `0x1402821a6`
- `win32kbase!EngFreeUserMem` at `0x140282454`
- `win32kbase!EngFreeUserMem` at `0x1402829e8`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282198`
- `win32kbase!FreeThreadBufferWithTag` at `0x1402821d7`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282446`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282926`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282a1c`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282198`
- `win32kbase!FreeThreadBufferWithTag` at `0x1402821d7`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282446`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282926`
- `win32kbase!FreeThreadBufferWithTag` at `0x140282a1c`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140282471`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1402829f8`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140282471`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1402829f8`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140282421`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140282421`
- `win32kbase!AllocThreadBufferWithTag` at `0x1402820b6`
- `win32kbase!AllocThreadBufferWithTag` at `0x1402820b6`
- `win32kbase!bIntersect` at `0x14028252e`
- `win32kbase!bIntersect` at `0x14028252e`

## pseudocode

```c
BOOL __stdcall EngTextOut(
        SURFOBJ *pso,
        STROBJ *pstro,
        FONTOBJ *pfo,
        CLIPOBJ *pco,
        RECTL *prclExtra,
        RECTL *prclOpaque,
        BRUSHOBJ *pboFore,
        BRUSHOBJ *pboOpaque,
        POINTL *pptlOrg,
        MIX mix)
{
  int v14; // r14d
  unsigned __int64 v15; // rsi
  struct XDCOBJ *v16; // rax
  unsigned int v17; // r15d
  FLONG flFontType; // eax
  LONG right; // r14d
  LONG left; // edx
  int v22; // edi
  RECTL *p_rclBkGround; // rdx
  LONG *p_right; // rcx
  int v25; // eax
  unsigned int v26; // r14d
  __int64 v27; // rcx
  _DWORD *v28; // rax
  _DWORD *v29; // rbx
  FLONG flAccel; // edx
  LONG top; // edi
  int v32; // ecx
  unsigned __int64 v33; // r8
  int v34; // eax
  unsigned __int64 v35; // rdx
  int v36; // edi
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  LONG v41; // ecx
  LONG v42; // r9d
  LONG v43; // edx
  LONG bottom; // ecx
  LONG v45; // r10d
  LONG v46; // r10d
  LONG v47; // ecx
  LONG v48; // eax
  unsigned int v49; // edi
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  bool v55; // zf
  int v56; // ecx
  LONG v57; // r11d
  __int64 v58; // r13
  LONG v59; // r9d
  LONG v60; // r10d
  RECTL rclBkGround; // xmm0
  int v62; // ecx
  LONG v63; // ecx
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  Gre::Base *v68; // rcx
  struct Gre::Base::SESSION_GLOBALS *v69; // rax
  BOOL (__stdcall *v70)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *); // r10
  __int64 v71; // r9
  unsigned int v72; // edi
  __int64 v73; // rax
  int v74; // edi
  unsigned __int8 *v75; // r9
  unsigned int v76; // eax
  struct _RECTL si128; // xmm6
  struct _GLYPHPOS *pgp; // r13
  __int64 cGlyphs; // rcx
  LONG v80; // eax
  CLIPOBJ *v81; // rdi
  unsigned int v82; // ebx
  int v83; // edi
  struct _FONTOBJ *v84; // rdx
  unsigned __int8 *v85; // rax
  LONG v86; // r9d
  struct _FONTOBJ *v87; // r13
  __int64 v88; // rdi
  struct _GLYPHPOS *v89; // r8
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  __int64 v93; // r9
  unsigned __int8 *v94; // [rsp+28h] [rbp-100h]
  struct _XLATEOBJ *v95; // [rsp+38h] [rbp-F0h]
  ULONG ulCharInc; // [rsp+38h] [rbp-F0h]
  struct SURFACE *v97; // [rsp+40h] [rbp-E8h]
  struct _POINTL *v98; // [rsp+48h] [rbp-E0h]
  struct SURFACE *v99; // [rsp+48h] [rbp-E0h]
  struct _RECTL *v100; // [rsp+50h] [rbp-D8h]
  struct _RECTL *v101; // [rsp+58h] [rbp-D0h]
  int v102; // [rsp+60h] [rbp-C8h]
  unsigned int v103; // [rsp+68h] [rbp-C0h]
  int v104; // [rsp+68h] [rbp-C0h]
  struct _RECTL *v105; // [rsp+80h] [rbp-A8h]
  unsigned int v106; // [rsp+88h] [rbp-A0h]
  struct _BRUSHOBJ *v107; // [rsp+90h] [rbp-98h]
  struct _POINTL *v108; // [rsp+98h] [rbp-90h]
  char v109; // [rsp+A8h] [rbp-80h]
  int v110; // [rsp+ACh] [rbp-7Ch] BYREF
  int v111; // [rsp+B0h] [rbp-78h]
  unsigned int cjMemSize; // [rsp+B4h] [rbp-74h] BYREF
  LONG cjMemSize_4; // [rsp+B8h] [rbp-70h]
  ULONG pc; // [rsp+BCh] [rbp-6Ch] BYREF
  LONG v115; // [rsp+C0h] [rbp-68h]
  int iDComplexity; // [rsp+C4h] [rbp-64h]
  int iSolidColor; // [rsp+C8h] [rbp-60h]
  struct _FONTOBJ *v118; // [rsp+D0h] [rbp-58h]
  unsigned __int8 *v119; // [rsp+D8h] [rbp-50h]
  CLIPOBJ *v120; // [rsp+E0h] [rbp-48h]
  PGLYPHPOS ppgpos; // [rsp+E8h] [rbp-40h] BYREF
  struct SURFACE *v122; // [rsp+F0h] [rbp-38h]
  RECTL *v123; // [rsp+F8h] [rbp-30h]
  _DWORD *v124; // [rsp+100h] [rbp-28h]
  struct _POINTL *v125; // [rsp+108h] [rbp-20h]
  struct _BRUSHOBJ *v126; // [rsp+110h] [rbp-18h]
  struct SURFACE *v127; // [rsp+118h] [rbp-10h]
  struct SURFACE *v128; // [rsp+120h] [rbp-8h] BYREF
  char v129; // [rsp+128h] [rbp+0h]
  int v130; // [rsp+12Ch] [rbp+4h]
  int v131; // [rsp+130h] [rbp+8h]
  struct _RECTL v132; // [rsp+138h] [rbp+10h] BYREF
  SURFOBJ *v133; // [rsp+148h] [rbp+20h]
  struct _RECTL *v134; // [rsp+150h] [rbp+28h]
  unsigned __int64 v135; // [rsp+158h] [rbp+30h]
  __int128 v136; // [rsp+160h] [rbp+38h] BYREF
  __int128 v137; // [rsp+170h] [rbp+48h]
  int v138; // [rsp+188h] [rbp+60h] BYREF
  struct _RECTL v139[20]; // [rsp+18Ch] [rbp+64h] BYREF
  __int128 v140; // [rsp+2D8h] [rbp+1B0h] BYREF
  RECTL v141; // [rsp+2E8h] [rbp+1C0h] BYREF
  unsigned __int64 v142; // [rsp+2F8h] [rbp+1D0h] BYREF
  __int64 v143; // [rsp+300h] [rbp+1D8h]
  CLIPOBJ *v144; // [rsp+308h] [rbp+1E0h]
  BRUSHOBJ *v145; // [rsp+310h] [rbp+1E8h]
  int v146; // [rsp+318h] [rbp+1F0h]
  LONG v147; // [rsp+31Ch] [rbp+1F4h]
  LONG v148; // [rsp+320h] [rbp+1F8h]
  LONG v149; // [rsp+324h] [rbp+1FCh]
  _DWORD v150[14]; // [rsp+328h] [rbp+200h]
  struct _FONTOBJ *v151; // [rsp+360h] [rbp+238h]
  struct _RECTL rclBounds; // [rsp+368h] [rbp+240h] BYREF
  int v153; // [rsp+384h] [rbp+25Ch]

  v123 = prclOpaque;
  v126 = pboFore;
  v134 = prclExtra;
  v133 = pso;
  v125 = pptlOrg;
  v120 = pco;
  v118 = pfo;
  memset_0(&v138, 0, 0x144u);
  v14 = 0;
  ppgpos = 0;
  pc = 0;
  cjMemSize = 0;
  v140 = 0;
  v141 = 0;
  GetTempTextBufferMetrics(pstro, (struct ERECTL *)&v132);
  v15 = (unsigned __int64)&pso[-1].pvScan0 & -(__int64)(pso != 0);
  if ( (pfo->flFontType & 0x10000) != 0 )
  {
    v16 = SURFACE::pdcoAA((SURFACE *)v15);
    if ( v16 )
      v122 = *(struct SURFACE **)(*(_QWORD *)(*(_QWORD *)v16 + 48LL) + 2544LL);
    else
      v122 = (struct SURFACE *)v15;
    v17 = *(_WORD *)(v15 + 100) != 0 ? 0x10 : 0;
    if ( _bittest16((const signed __int16 *)(v15 + 102), 8u) )
      v17 |= 0x80u;
  }
  else
  {
    v17 = 0;
    v122 = 0;
  }
  flFontType = pfo->flFontType;
  if ( (flFontType & 2) != 0 )
    return *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
  if ( pco )
    iDComplexity = pco->iDComplexity;
  else
    iDComplexity = 0;
  if ( (flFontType & 0x10000) != 0 )
  {
    if ( *(_DWORD *)(v15 + 96) == 3 && (!pboOpaque || pboOpaque->iSolidColor == -1) )
      return *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
    v17 |= 8u;
    if ( (flFontType & 0x10000000) != 0 )
    {
      right = pstro->rclBkGround.right;
      if ( right > 2147483643 )
        return *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
      left = pstro->rclBkGround.left;
      if ( (unsigned int)(right - left + 4) >= 0x7FFFFFFF )
        return *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
      v17 |= 0x20u;
      v22 = 8;
      v14 = ((right + 4) & 0xFFFFFFFC) - (left & 0xFFFFFFFC);
    }
    else if ( (flFontType & 0x20000000) != 0 )
    {
      v22 = 0;
    }
    else
    {
      v22 = 4;
      v14 = (((pstro->rclBkGround.right + 8) >> 1) & 0xFFFFFFFC) - ((pstro->rclBkGround.left >> 1) & 0xFFFFFFFC);
    }
    p_rclBkGround = &pstro->rclBkGround;
    p_right = &pstro->rclBkGround.right;
  }
  else
  {
    p_right = &pstro->rclBkGround.right;
    v22 = 1;
    p_rclBkGround = &pstro->rclBkGround;
    v14 = (int)(((pstro->rclBkGround.right + 32) & 0xFFFFFFE0) - (pstro->rclBkGround.left & 0xFFFFFFE0)) >> 3;
  }
  v25 = v132.right - *p_right;
  LODWORD(v119) = ((unsigned int)(v22 * (p_rclBkGround->left - v132.left) + 31) >> 3) & 0x1FFFFFFC;
  v26 = (_DWORD)v119 + (((unsigned int)(v22 * v25 + 31) >> 3) & 0x1FFFFFFC) + v14;
  if ( (int)ULongLongToULong(v26 * (unsigned __int64)(unsigned int)(v132.bottom - v132.top), &cjMemSize) < 0 )
    return *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
  iSolidColor = v126->iSolidColor;
  if ( (unsigned int)((__int64 (*)(void))Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline)() )
  {
    v27 = cjMemSize;
  }
  else
  {
    if ( cjMemSize >= 0x10000 )
    {
      v109 = 0;
      v28 = EngAllocUserMem(cjMemSize, 0x6F746547u);
      goto LABEL_33;
    }
    v27 = cjMemSize;
  }
  v109 = 1;
  v28 = (_DWORD *)AllocThreadBufferWithTag(v27, 1869899079, 32);
LABEL_33:
  v124 = v28;
  v29 = v28;
  if ( !v28 )
    return *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
  flAccel = pstro->flAccel;
  top = pstro->rclBkGround.top;
  v111 = -1;
  cjMemSize_4 = top;
  if ( (flAccel & 0xA) == 2 )
  {
    v32 = 0;
    if ( (flAccel & 0x51) == 0x51 )
      v32 = 4;
    v17 |= (pstro->ulCharInc != 0) | ((flAccel & 0x11) != 17 ? 2 : 0) | v32;
  }
  v142 = v15;
  v135 = v15 + 24;
  if ( *(_WORD *)(v15 + 100) )
    v143 = 0;
  else
    v143 = *(_QWORD *)(v15 + 72);
  v33 = (unsigned __int64)v123;
  v34 = 0;
  v35 = (unsigned __int64)v118;
  v144 = v120;
  v145 = pboOpaque;
  v146 = 0;
  v151 = v118;
  if ( v123 )
  {
    if ( !pboOpaque )
    {
      if ( !(unsigned int)Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline(
                            v120,
                            v118,
                            v123,
                            0xFFFFFFFFLL) )
      {
        if ( v109 )
          FreeThreadBufferWithTag(v29);
        else
          EngFreeUserMem(v29);
      }
      v36 = *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
      goto LABEL_48;
    }
    v111 = pboOpaque->iSolidColor;
    if ( v111 == -1 || iSolidColor == -1 )
    {
      EngTextOutBitBlt(
        (struct SURFACE *)v15,
        v118,
        v17,
        (struct _SURFOBJ *)0xFFFFFFFFLL,
        (struct _SURFOBJ *)v94,
        v120,
        v95,
        v123,
        v98,
        (struct _POINTL *)v100,
        pboOpaque,
        v125,
        v103);
    }
    else
    {
      v41 = v123->top;
      if ( top > v41 )
      {
        v147 = v123->left;
        v149 = v123->right;
        v34 = 1;
        v146 = 1;
        v148 = v41;
        v150[0] = top;
      }
      v42 = v123->left;
      v43 = pstro->rclBkGround.left;
      bottom = pstro->rclBkGround.bottom;
      if ( v43 > v123->left )
      {
        *(&v147 + 4 * v34) = v42;
        *(&v148 + 4 * v146) = top;
        v150[4 * v146 - 1] = v43;
        v150[4 * v146] = bottom;
        v34 = ++v146;
      }
      v35 = *(unsigned int *)(v33 + 8);
      v45 = pstro->rclBkGround.right;
      if ( v45 < (int)v35 )
      {
        *(&v147 + 4 * v34) = v45;
        *(&v148 + 4 * v146) = top;
        v150[4 * v146 - 1] = v35;
        v150[4 * v146] = bottom;
        v34 = ++v146;
      }
      v46 = *(_DWORD *)(v33 + 12);
      if ( bottom < v46 )
      {
        *(&v147 + 4 * v34) = v42;
        *(&v148 + 4 * v146) = bottom;
        v150[4 * v146 - 1] = v35;
        v150[4 * v146++] = v46;
      }
    }
  }
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v110 = v17 & 0x10;
  v131 = 2;
  v136 = 0;
  v123 = (RECTL *)EngCopyBits;
  v137 = 0;
  if ( (v17 & 0x10) != 0 )
  {
    v47 = pstro->rclBkGround.top;
    LODWORD(v136) = *(_DWORD *)(v15 + 96);
    v48 = pstro->rclBkGround.right;
    v115 = v47;
    v49 = pstro->rclBkGround.left & ((v17 >> 3) & 4 | 0xFFFFFFF8);
    DWORD1(v136) = v48 - v49;
    v55 = (*(_DWORD *)(v15 + 160) & 0x40000) == 0;
    DWORD2(v136) = pstro->rclBkGround.bottom - v47;
    v50 = 1;
    if ( !v55 )
      v50 = 262145;
    *(_QWORD *)&v137 = 0;
    DWORD2(v137) = v50;
    if ( !SURFMEM::bCreateDIB((SURFMEM *)&v128, (struct _DEVBITMAPINFO *)&v136, 0, 0, 0, 0, 0, 0, 1, 0) )
    {
      if ( !(unsigned int)Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline(
                            v52,
                            v51,
                            v53,
                            v54) )
      {
        v55 = v109 == 0;
        goto LABEL_68;
      }
      goto LABEL_71;
    }
    v56 = 0;
    v57 = 0;
    v127 = v128;
    v58 = *(_QWORD *)(v15 + 48);
    if ( v15 == *(_QWORD *)(v58 + 2544) && (*(_DWORD *)(v58 + 40) & 0x20000) != 0 )
    {
      v56 = *(_DWORD *)(v58 + 2576);
      v57 = *(_DWORD *)(v58 + 2580);
    }
    v35 = (unsigned int)pstro->rclBkGround.left;
    v59 = pstro->rclBkGround.top;
    if ( v56 > (int)v35 )
      v35 = (unsigned int)v56;
    v33 = (unsigned int)pstro->rclBkGround.right;
    v60 = pstro->rclBkGround.bottom;
    rclBkGround = pstro->rclBkGround;
    if ( v57 > v59 )
      v59 = v57;
    *(_QWORD *)&v140 = __PAIR64__(v59, v35);
    v62 = v133->sizlBitmap.cx + v56;
    v141 = rclBkGround;
    if ( v62 < (int)v33 )
      v33 = (unsigned int)v62;
    v63 = v57 + v133->sizlBitmap.cy;
    DWORD2(v140) = v33;
    if ( v63 < v60 )
      v60 = v63;
    HIDWORD(v140) = v60;
    if ( iDComplexity )
    {
      if ( !(unsigned int)bIntersect(&v140, &v120->rclBounds) )
      {
        if ( !(unsigned int)Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline(
                              v65,
                              v64,
                              v66,
                              v67) )
        {
          v55 = v109 == 0;
LABEL_68:
          if ( v55 )
            EngFreeUserMem(v29);
          else
            FreeThreadBufferWithTag(v29);
        }
LABEL_71:
        v36 = *(_DWORD *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v110, 0);
        SURFMEM::~SURFMEM((SURFMEM *)&v128);
LABEL_48:
        FRINGERECT::~FRINGERECT((FRINGERECT *)&v142);
        if ( (unsigned int)Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline(
                             v38,
                             v37,
                             v39,
                             v40) )
          FreeThreadBufferWithTag(v29);
        return v36;
      }
      v60 = HIDWORD(v140);
      v33 = DWORD2(v140);
      v59 = DWORD1(v140);
      v35 = (unsigned int)v140;
    }
    v141.right = DWORD2(v140) - v49;
    v141.left = v35 - v49;
    v141.top = DWORD1(v140) - v115;
    v141.bottom = HIDWORD(v140) - v115;
    if ( v111 == -1 && (int)v35 < (int)v33 && v59 < v60 )
    {
      UMPDReleaseAcquireRFONTSem::UMPDReleaseAcquireRFONTSem(
        (UMPDReleaseAcquireRFONTSem *)&rclBounds,
        (struct SURFACE *)v15,
        v118);
      v69 = Gre::Base::Globals(v68);
      if ( (*(_DWORD *)(v15 + 160) & 0x400) != 0 )
        v70 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *))(v58 + 2832);
      else
        v70 = EngCopyBits;
      ((void (__fastcall *)(unsigned __int64, unsigned __int64, _QWORD, char *, RECTL *, __int128 *))v70)(
        ((unsigned __int64)v128 + 24) & -(__int64)(v128 != 0),
        v135 & -(__int64)(v15 != 0),
        0,
        (char *)v69 + 4664,
        &v141,
        &v140);
      UMPDReleaseAcquireRFONTSem::~UMPDReleaseAcquireRFONTSem((UMPDReleaseAcquireRFONTSem *)&rclBounds);
    }
    top = cjMemSize_4;
  }
  else
  {
    v127 = (struct SURFACE *)v15;
  }
  v71 = (unsigned int)v119;
  v72 = v26 * (top - v132.top);
  *(_QWORD *)&pstro[1].cGlyphs = 0;
  v73 = v72;
  v74 = v111;
  v75 = (unsigned __int8 *)v29 + v73 + v71;
  v119 = v75;
  if ( v111 == -1 )
  {
    v76 = cjMemSize;
  }
  else
  {
    v76 = cjMemSize;
    v35 = (unsigned __int64)cjMemSize >> 2;
    if ( v35 )
    {
      if ( ((unsigned __int8)v29 & 4) == 0 )
      {
        v33 = (unsigned __int64)v29;
LABEL_103:
        memset((void *)v33, 0, 8 * (v35 >> 1));
        v74 = v111;
        v76 = cjMemSize;
        if ( (v35 & 1) != 0 )
          *(_DWORD *)(v33 + 4 * v35 - 4) = 0;
        goto LABEL_106;
      }
      *v29 = 0;
      if ( --v35 )
      {
        v33 = (unsigned __int64)(v29 + 1);
        goto LABEL_103;
      }
    }
  }
LABEL_106:
  si128 = (struct _RECTL)_mm_load_si128((const __m128i *)&_xmm);
  do
  {
    if ( v74 == -1 )
    {
      v35 = (unsigned __int64)v76 >> 2;
      if ( v35 )
      {
        if ( ((unsigned __int8)v29 & 4) != 0 )
        {
          *v29 = 0;
          if ( !--v35 )
            goto LABEL_115;
          v33 = (unsigned __int64)(v29 + 1);
        }
        else
        {
          v33 = (unsigned __int64)v29;
        }
        memset((void *)v33, 0, 8 * (v35 >> 1));
        v74 = v111;
        if ( (v35 & 1) != 0 )
          *(_DWORD *)(v33 + 4 * v35 - 4) = 0;
      }
    }
LABEL_115:
    pgp = pstro->pgp;
    if ( pgp )
    {
      cGlyphs = pstro->cGlyphs;
      pc = pstro->cGlyphs;
      ppgpos = pgp;
      v115 = 0;
    }
    else
    {
      if ( ((__int64)pstro[4].pwszOrg & 2) != 0 )
        v80 = STROBJ_bEnum(pstro, &pc, &ppgpos);
      else
        v80 = STROBJ_bEnumCheckBounds(pstro, &pc, &ppgpos, &v132);
      v75 = v119;
      cGlyphs = pc;
      pgp = ppgpos;
      v115 = v80;
    }
    cjMemSize_4 = cGlyphs;
    if ( !(_DWORD)cGlyphs )
      goto LABEL_128;
    rclBounds = si128;
    v153 = 0;
    if ( iDComplexity )
    {
      if ( iDComplexity != 1 )
      {
        if ( iDComplexity == 3 )
        {
          v81 = v120;
          XCLIPOBJ::cEnumStart((XCLIPOBJ *)v120, 0, 0, 4u, 0);
          v82 = cjMemSize_4;
          do
          {
            v83 = XCLIPOBJ::bEnum((XCLIPOBJ *)v81, 0x134u, &v138, 0);
            v84 = v118;
            v108 = v125;
            v107 = v126;
            v105 = v134;
            v104 = v111;
            v102 = iSolidColor;
            v99 = v122;
            v97 = v127;
            ulCharInc = pstro->ulCharInc;
            v85 = v119;
            v139[v138].bottom = v86;
            vExpandAndCopyText(
              (struct SURFACE *)v15,
              v84,
              pgp,
              v82,
              v85,
              v26,
              ulCharInc,
              v97,
              v99,
              &pstro->rclBkGround,
              v101,
              v102,
              v104,
              v17,
              v139,
              v105,
              v106,
              v107,
              v108);
            v55 = v83 == 0;
            v81 = v120;
          }
          while ( !v55 );
          v29 = v124;
        }
LABEL_128:
        v87 = v118;
        goto LABEL_129;
      }
      rclBounds = v120->rclBounds;
    }
    v89 = pgp;
    v87 = v118;
    vExpandAndCopyText(
      (struct SURFACE *)v15,
      v118,
      v89,
      cGlyphs,
      v75,
      v26,
      pstro->ulCharInc,
      v127,
      v122,
      &pstro->rclBkGround,
      v101,
      iSolidColor,
      v74,
      v17,
      &rclBounds,
      v134,
      v106,
      v126,
      v125);
LABEL_129:
    v75 = v119;
    v76 = cjMemSize;
    v74 = v111;
  }
  while ( v115 );
  if ( v110 )
  {
    v88 = *(_QWORD *)(v15 + 48);
    UMPDReleaseAcquireRFONTSem::UMPDReleaseAcquireRFONTSem(
      (UMPDReleaseAcquireRFONTSem *)&rclBounds,
      (struct SURFACE *)v15,
      v87);
    if ( (*(_DWORD *)(v15 + 160) & 0x400) != 0 )
      v123 = *(RECTL **)(v88 + 2832);
    ((void (__fastcall *)(unsigned __int64, unsigned __int64, CLIPOBJ *, _QWORD, __int128 *, RECTL *))v123)(
      v135 & -(__int64)(v15 != 0),
      ((unsigned __int64)v128 + 24) & -(__int64)(v128 != 0),
      v120,
      0,
      &v140,
      &v141);
    UMPDReleaseAcquireRFONTSem::~UMPDReleaseAcquireRFONTSem((UMPDReleaseAcquireRFONTSem *)&rclBounds);
  }
  if ( !(unsigned int)Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline(
                        cGlyphs,
                        v35,
                        v33,
                        v75) )
  {
    if ( v109 )
      FreeThreadBufferWithTag(v29);
    else
      EngFreeUserMem(v29);
  }
  SURFMEM::~SURFMEM((SURFMEM *)&v128);
  FRINGERECT::~FRINGERECT((FRINGERECT *)&v142);
  if ( (unsigned int)Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline(
                       v91,
                       v90,
                       v92,
                       v93) )
    FreeThreadBufferWithTag(v29);
  return 1;
}

```

## disassembly

```asm
0x140281e10  mov     rax, rsp
0x140281e13  push    rbp
0x140281e14  push    rbx
0x140281e15  push    rsi
0x140281e16  push    rdi
0x140281e17  push    r12
0x140281e19  push    r13
0x140281e1b  push    r14
0x140281e1d  push    r15
0x140281e1f  lea     rbp, [rax-2F8h]
0x140281e26  sub     rsp, 3D8h
0x140281e2d  movaps  xmmword ptr [rax-58h], xmm6
0x140281e31  mov     rax, cs:__security_cookie
0x140281e38  xor     rax, rsp
0x140281e3b  mov     [rbp+2F0h+var_60], rax
0x140281e42  mov     rax, [rbp+2F0h+prclOpaque]
0x140281e49  mov     rbx, r8
0x140281e4c  mov     r13, [rbp+2F0h+pboOpaque]
0x140281e53  mov     r12, rdx
0x140281e56  mov     [rbp+2F0h+var_320], rax
0x140281e5a  mov     rsi, rcx
0x140281e5d  mov     rax, [rbp+2F0h+pboFore]
0x140281e64  xor     edx, edx; Val
0x140281e66  mov     [rbp+2F0h+var_308], rax
0x140281e6a  mov     r8d, 144h; Size
0x140281e70  mov     rax, [rbp+2F0h+prclExtra]
0x140281e77  mov     rdi, r9
0x140281e7a  mov     [rbp+2F0h+var_2C8], rax
0x140281e7e  mov     rax, [rbp+2F0h+pptlOrg]
0x140281e85  mov     [rbp+2F0h+var_2D0], rcx
0x140281e89  lea     rcx, [rbp+2F0h+var_290]; void *
0x140281e8d  mov     [rbp+2F0h+var_310], rax
0x140281e91  mov     [rbp+2F0h+var_338], r9
0x140281e95  mov     [rbp+2F0h+var_348], rbx
0x140281e99  call    memset_0
0x140281e9e  xor     r14d, r14d
0x140281ea1  lea     rdx, [rbp+2F0h+var_2E0]; struct ERECTL *
0x140281ea5  xorps   xmm0, xmm0
0x140281ea8  mov     [rbp+2F0h+ppgpos], r14
0x140281eac  xorps   xmm1, xmm1
0x140281eaf  mov     [rbp+2F0h+pc], r14d
0x140281eb3  mov     rcx, r12; struct _STROBJ *
0x140281eb6  mov     dword ptr [rbp+2F0h+cjMemSize], r14d
0x140281eba  movups  [rbp+2F0h+var_140], xmm0
0x140281ec1  movups  [rbp+2F0h+var_130], xmm1
0x140281ec8  call    ?GetTempTextBufferMetrics@@YAXPEAU_STROBJ@@PEAVERECTL@@@Z; GetTempTextBufferMetrics(_STROBJ *,ERECTL *)
0x140281ecd  mov     rax, rsi
0x140281ed0  lea     rcx, [rsi-18h]
0x140281ed4  neg     rax
0x140281ed7  sbb     rsi, rsi
0x140281eda  and     rsi, rcx
0x140281edd  test    dword ptr [rbx+0Ch], 10000h
0x140281ee4  jz      short loc_140281F28
0x140281ee6  mov     rcx, rsi; this
0x140281ee9  call    ?pdcoAA@SURFACE@@QEAAPEAVXDCOBJ@@XZ; SURFACE::pdcoAA(void)
0x140281eee  test    rax, rax
0x140281ef1  jz      short loc_140281F07
0x140281ef3  mov     rax, [rax]
0x140281ef6  mov     rcx, [rax+30h]
0x140281efa  mov     rcx, [rcx+9F0h]
0x140281f01  mov     [rbp+2F0h+var_328], rcx
0x140281f05  jmp     short loc_140281F0B
0x140281f07  mov     [rbp+2F0h+var_328], rsi
0x140281f0b  movzx   eax, word ptr [rsi+64h]
0x140281f0f  neg     ax
0x140281f12  sbb     r15d, r15d
0x140281f15  and     r15d, 10h
0x140281f19  bt      word ptr [rsi+66h], 8
0x140281f1f  jnb     short loc_140281F2F
0x140281f21  bts     r15d, 7
0x140281f26  jmp     short loc_140281F2F
0x140281f28  mov     r15d, r14d
0x140281f2b  mov     [rbp+2F0h+var_328], r14
0x140281f2f  mov     eax, [rbx+0Ch]
0x140281f32  test    al, 2
0x140281f34  jz      short loc_140281F48
0x140281f36  xor     edx, edx
0x140281f38  lea     rcx, [rbp+2F0h+var_36C]
0x140281f3c  call    ??0?$ReturnValueTracer@K@@QEAA@K@Z; ReturnValueTracer<ulong>::ReturnValueTracer<ulong>(ulong)
0x140281f41  mov     eax, [rax]
0x140281f43  jmp     loc_140282A2D
0x140281f48  test    rdi, rdi
0x140281f4b  jz      short loc_140281F56
0x140281f4d  movzx   ecx, byte ptr [rdi+14h]
0x140281f51  mov     [rbp+2F0h+var_354], ecx
0x140281f54  jmp     short loc_140281F5A
0x140281f56  mov     [rbp+2F0h+var_354], r14d
0x140281f5a  mov     ecx, 4
0x140281f5f  bt      eax, 10h
0x140281f63  jnb     loc_140281FF9
0x140281f69  cmp     dword ptr [rsi+60h], 3
0x140281f6d  jnz     short loc_140281F7B
0x140281f6f  test    r13, r13
0x140281f72  jz      short loc_140281F36
0x140281f74  cmp     dword ptr [r13+0], 0FFFFFFFFh
0x140281f79  jz      short loc_140281F36
0x140281f7b  or      r15d, 8
0x140281f7f  bt      eax, 1Ch
0x140281f83  jnb     short loc_140281FC1
0x140281f85  mov     r14d, [r12+14h]
0x140281f8a  cmp     r14d, 7FFFFFFBh
0x140281f91  jg      short loc_140281F36
0x140281f93  mov     edx, [r12+0Ch]
0x140281f98  mov     eax, r14d
0x140281f9b  sub     eax, edx
0x140281f9d  add     eax, ecx
0x140281f9f  cmp     eax, 7FFFFFFFh
0x140281fa4  jnb     short loc_140281F36
0x140281fa6  add     r14d, ecx
0x140281fa9  or      r15d, 20h
0x140281fad  mov     ecx, 0FFFFFFFCh
0x140281fb2  mov     edi, 8
0x140281fb7  and     r14d, ecx
0x140281fba  and     edx, ecx
0x140281fbc  sub     r14d, edx
0x140281fbf  jmp     short loc_140281FED
0x140281fc1  bt      eax, 1Dh
0x140281fc5  jb      short loc_140281FEB
0x140281fc7  mov     r14d, [r12+14h]
0x140281fcc  mov     edi, ecx
0x140281fce  mov     eax, [r12+0Ch]
0x140281fd3  add     r14d, 8
0x140281fd7  sar     r14d, 1
0x140281fda  mov     ecx, 0FFFFFFFCh
0x140281fdf  sar     eax, 1
0x140281fe1  and     r14d, ecx
0x140281fe4  and     eax, ecx
0x140281fe6  sub     r14d, eax
0x140281fe9  jmp     short loc_140281FED
0x140281feb  xor     edi, edi
0x140281fed  lea     rdx, [r12+0Ch]
0x140281ff2  lea     rcx, [r12+14h]
0x140281ff7  jmp     short loc_14028201F
0x140281ff9  lea     rcx, [r12+14h]
0x140281ffe  mov     edi, 1
0x140282003  mov     r14d, [rcx]
0x140282006  lea     rdx, [r12+0Ch]
0x14028200b  mov     eax, [rdx]
0x14028200d  add     r14d, 20h ; ' '
0x140282011  and     r14d, 0FFFFFFE0h
0x140282015  and     eax, 0FFFFFFE0h
0x140282018  sub     r14d, eax
0x14028201b  sar     r14d, 3
0x14028201f  mov     edx, [rdx]
0x140282021  mov     r8d, 1FFFFFFCh
0x140282027  sub     edx, [rbp+2F0h+var_2E0.left]
0x14028202a  mov     eax, [rbp+2F0h+var_2E0.right]
0x14028202d  sub     eax, [rcx]
0x14028202f  mov     ecx, [rbp+2F0h+var_2E0.bottom]
0x140282032  sub     ecx, [rbp+2F0h+var_2E0.top]
0x140282035  imul    eax, edi
0x140282038  imul    edx, edi
0x14028203b  add     eax, 1Fh
0x14028203e  shr     eax, 3
0x140282041  add     edx, 1Fh
0x140282044  and     eax, r8d
0x140282047  shr     edx, 3
0x14028204a  and     edx, r8d
0x14028204d  add     eax, edx
0x14028204f  mov     dword ptr [rbp+2F0h+var_340], edx
0x140282052  add     r14d, eax
0x140282055  lea     rdx, [rbp+2F0h+cjMemSize]; unsigned int *
0x140282059  mov     eax, r14d
0x14028205c  imul    rcx, rax; unsigned __int64
0x140282060  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140282065  xor     edi, edi
0x140282067  test    eax, eax
0x140282069  js      loc_140281F36
0x14028206f  mov     rax, [rbp+2F0h+var_308]
0x140282073  mov     eax, [rax]
0x140282075  mov     [rbp+2F0h+var_350], eax
0x140282078  call    Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline
0x14028207d  mov     edx, 6F746547h; ulTag
0x140282082  test    eax, eax
0x140282084  jnz     short loc_1402820A9
0x140282086  mov     eax, dword ptr [rbp+2F0h+cjMemSize]
0x140282089  cmp     eax, 10000h
0x14028208e  jnb     short loc_140282094
0x140282090  mov     ecx, eax
0x140282092  jmp     short loc_1402820AC
0x140282094  mov     rcx, rax; cjMemSize
0x140282097  mov     [rbp+2F0h+var_370], dil
0x14028209b  call    cs:__imp_EngAllocUserMem
0x1402820a2  nop     dword ptr [rax+rax+00h]
0x1402820a7  jmp     short loc_1402820C2
0x1402820a9  mov     ecx, dword ptr [rbp+2F0h+cjMemSize]
0x1402820ac  mov     r8d, 20h ; ' '
0x1402820b2  mov     [rbp+2F0h+var_370], 1
0x1402820b6  call    cs:__imp_AllocThreadBufferWithTag
0x1402820bd  nop     dword ptr [rax+rax+00h]
0x1402820c2  xor     r10d, r10d
0x1402820c5  mov     [rbp+2F0h+var_318], rax
0x1402820c9  mov     rbx, rax
0x1402820cc  test    rax, rax
0x1402820cf  jz      loc_140281F36
0x1402820d5  mov     edx, [r12+4]
0x1402820da  or      r9d, 0FFFFFFFFh; struct _SURFOBJ *
0x1402820de  mov     edi, [r12+10h]
0x1402820e3  mov     eax, edx
0x1402820e5  and     al, 0Ah
0x1402820e7  mov     [rbp+2F0h+var_368], r9d
0x1402820eb  mov     dword ptr [rbp+2F0h+cjMemSize+4], edi
0x1402820ee  cmp     al, 2
0x1402820f0  jnz     short loc_140282122
0x1402820f2  mov     eax, edx
0x1402820f4  mov     ecx, r10d
0x1402820f7  and     eax, 51h
0x1402820fa  cmp     al, 51h ; 'Q'
0x1402820fc  lea     eax, [r10+4]
0x140282100  cmovz   ecx, eax
0x140282103  and     edx, 11h
0x140282106  sub     dl, 11h
0x140282109  neg     dl
0x14028210b  sbb     eax, eax
0x14028210d  and     eax, 2
0x140282110  or      ecx, eax
0x140282112  mov     eax, r10d
0x140282115  cmp     [r12+8], r10d
0x14028211a  setnz   al
0x14028211d  or      ecx, eax
0x14028211f  or      r15d, ecx
0x140282122  lea     rax, [rsi+18h]
0x140282126  mov     [rbp+2F0h+var_120], rsi
0x14028212d  mov     [rbp+2F0h+var_2C0], rax
0x140282131  cmp     [rax+4Ch], r10w
0x140282136  jnz     short loc_140282145
0x140282138  mov     rax, [rsi+48h]
0x14028213c  mov     [rbp+2F0h+var_118], rax
0x140282143  jmp     short loc_14028214C
0x140282145  mov     [rbp+2F0h+var_118], r10
0x14028214c  mov     r8, [rbp+2F0h+var_320]
0x140282150  mov     eax, r10d
0x140282153  mov     rcx, [rbp+2F0h+var_338]
0x140282157  mov     rdx, [rbp+2F0h+var_348]; struct _FONTOBJ *
0x14028215b  mov     [rbp+2F0h+var_110], rcx
0x140282162  mov     [rbp+2F0h+var_108], r13
0x140282169  mov     [rbp+2F0h+var_100], eax
0x14028216f  mov     [rbp+2F0h+var_B8], rdx
0x140282176  test    r8, r8
0x140282179  jz      loc_14028236B
0x14028217f  test    r13, r13
0x140282182  jnz     short loc_1402821EA
0x140282184  call    Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline
0x140282189  xor     esi, esi
0x14028218b  test    eax, eax
0x14028218d  jnz     short loc_1402821B2
0x14028218f  mov     rcx, rbx; pv
0x140282192  cmp     [rbp+2F0h+var_370], sil
0x140282196  jz      short loc_1402821A6
0x140282198  call    cs:__imp_FreeThreadBufferWithTag
0x14028219f  nop     dword ptr [rax+rax+00h]
0x1402821a4  jmp     short loc_1402821B2
0x1402821a6  call    cs:__imp_EngFreeUserMem
0x1402821ad  nop     dword ptr [rax+rax+00h]
0x1402821b2  xor     edx, edx
0x1402821b4  lea     rcx, [rbp+2F0h+var_36C]
0x1402821b8  call    ??0?$ReturnValueTracer@K@@QEAA@K@Z; ReturnValueTracer<ulong>::ReturnValueTracer<ulong>(ulong)
0x1402821bd  mov     edi, [rax]
0x1402821bf  lea     rcx, [rbp+2F0h+var_120]; this
0x1402821c6  call    ??1FRINGERECT@@QEAA@XZ; FRINGERECT::~FRINGERECT(void)
0x1402821cb  call    Feature_Servicing_Kernel1BPPTextBufferMapping__private_IsEnabledDeviceUsageNoInline
0x1402821d0  test    eax, eax
0x1402821d2  jz      short loc_1402821E3
0x1402821d4  mov     rcx, rbx
0x1402821d7  call    cs:__imp_FreeThreadBufferWithTag
0x1402821de  nop     dword ptr [rax+rax+00h]
0x1402821e3  mov     eax, edi
0x1402821e5  jmp     loc_140282A2D
0x1402821ea  mov     r11d, [r13+0]
0x1402821ee  mov     [rbp+2F0h+var_368], r11d
0x1402821f2  cmp     r11d, r9d
0x1402821f5  jz      loc_140282345
0x1402821fb  cmp     [rbp+2F0h+var_350], r9d
0x1402821ff  jz      loc_140282345
0x140282205  mov     ecx, [r8+4]
0x140282209  cmp     edi, ecx
0x14028220b  jle     short loc_140282237
0x14028220d  mov     eax, [r8]
0x140282210  mov     [rbp+2F0h+var_FC], eax
0x140282216  mov     eax, [r8+8]
0x14028221a  mov     [rbp+2F0h+var_F4], eax
0x140282220  mov     eax, 1
0x140282225  mov     [rbp+2F0h+var_100], eax
0x14028222b  mov     [rbp+2F0h+var_F8], ecx
0x140282231  mov     [rbp+2F0h+var_F0], edi
0x140282237  mov     r9d, [r8]
0x14028223a  mov     edx, [r12+0Ch]
0x14028223f  mov     ecx, [r12+18h]
0x140282244  cmp     edx, r9d
0x140282247  jle     short loc_140282297
0x140282249  cdqe
0x14028224b  add     rax, rax
0x14028224e  mov     [rbp+rax*8+2F0h+var_FC], r9d
0x140282256  movsxd  rax, [rbp+2F0h+var_100]
0x14028225d  add     rax, rax
0x140282260  mov     [rbp+rax*8+2F0h+var_F8], edi
0x140282267  movsxd  rax, [rbp+2F0h+var_100]
0x14028226e  add     rax, rax
0x140282271  mov     [rbp+rax*8+2F0h+var_F4], edx
0x140282278  movsxd  rax, [rbp+2F0h+var_100]
  ... truncated ...
```
