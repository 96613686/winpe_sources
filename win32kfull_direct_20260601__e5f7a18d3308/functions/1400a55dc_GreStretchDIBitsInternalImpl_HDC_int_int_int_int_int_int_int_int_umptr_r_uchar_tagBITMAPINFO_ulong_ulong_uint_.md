# GreStretchDIBitsInternalImpl(HDC__ *,int,int,int,int,int,int,int,int,umptr_r<uchar> &,tagBITMAPINFO *,ulong,ulong,uint,void *)

- ea: `0x1400a55dc`
- end: `0x1400a6cad`
- name: `?GreStretchDIBitsInternalImpl@@YAHPEAUHDC__@@HHHHHHHHAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@KKIPEAX@Z`
- size: `5841`
- prototype: `__int64 __fastcall(Gre::Base *, int, int, int, int, LONG, int, int, int, __int64, __int64, unsigned int, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a53e0`

## callees

- `0x140050c78`
- `0x1400512b0`
- `0x140054a74`
- `0x140056bc8`
- `0x14005b820`
- `0x14005b938`
- `0x14005d010`
- `0x140060b1c`
- `0x140067498`
- `0x140068674`
- `0x1400697e4`
- `0x140069870`
- `0x1400698b4`
- `0x14006bd2c`
- `0x14006d0d0`
- `0x1400746e0`
- `0x14008aa50`
- `0x14008cfa0`
- `0x14009a40c`
- `0x14009b5c8`
- `0x1400a4e80`
- `0x1400a51d0`
- `0x1400a55dc`
- `0x1400a7100`
- `0x1400a8f68`
- `0x1401156c8`
- `0x140154d18`
- `0x14018d8f4`
- `0x14019d704`
- `0x1401a17bc`
- `0x1401aac80`
- `0x1401cf360`
- `0x140226ddc`
- `0x140235784`
- `0x140264b80`
- `0x140298e04`
- `0x140342fa0`
- `0x140343080`
- `0x140343200`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a566f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a5ee5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a5ff8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a566f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a5ee5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a5ff8`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400a5ba6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400a5fdd`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400a5ba6`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400a5fdd`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a5f57`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a5fbf`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a6a87`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a5f57`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a5fbf`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a6a87`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400a5a80`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400a5a80`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400a6316`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400a6316`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400a646f`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400a646f`
- `win32kbase!EngSetLastError` at `0x1400a5ccf`
- `win32kbase!EngSetLastError` at `0x1400a5cf5`
- `win32kbase!EngSetLastError` at `0x1400a64a3`
- `win32kbase!EngSetLastError` at `0x1400a659b`
- `win32kbase!EngSetLastError` at `0x1400a6701`
- `win32kbase!EngSetLastError` at `0x1400a685d`
- `win32kbase!EngSetLastError` at `0x1400a69c1`
- `win32kbase!EngSetLastError` at `0x1400a6a1d`
- `win32kbase!EngSetLastError` at `0x1400a5ccf`
- `win32kbase!EngSetLastError` at `0x1400a5cf5`
- `win32kbase!EngSetLastError` at `0x1400a64a3`
- `win32kbase!EngSetLastError` at `0x1400a659b`
- `win32kbase!EngSetLastError` at `0x1400a6701`
- `win32kbase!EngSetLastError` at `0x1400a685d`
- `win32kbase!EngSetLastError` at `0x1400a69c1`
- `win32kbase!EngSetLastError` at `0x1400a6a1d`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x1400a5777`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x1400a5dc5`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x1400a5777`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x1400a5dc5`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1400a5ed1`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1400a67f7`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1400a5ed1`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1400a67f7`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x1400a5bc2`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x1400a5bc2`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x1400a5e9b`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x1400a6b95`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x1400a5e9b`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x1400a6b95`
- `win32kbase!GrepDeleteDC` at `0x1400a6445`
- `win32kbase!GrepDeleteDC` at `0x1400a6533`
- `win32kbase!GrepDeleteDC` at `0x1400a6445`
- `win32kbase!GrepDeleteDC` at `0x1400a6533`
- `win32kbase!?vUpdateTime@XEPALOBJ@@QEAAXXZ` at `0x1400a619a`
- `win32kbase!?vUpdateTime@XEPALOBJ@@QEAAXXZ` at `0x1400a619a`
- `win32kbase!?bIsPalDefault@XEPALOBJ@@QEBAHXZ` at `0x1400a6041`
- `win32kbase!?bIsPalDefault@XEPALOBJ@@QEBAHXZ` at `0x1400a6041`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x1400a62fd`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x1400a62fd`
- `win32kbase!GreSelectBitmap` at `0x1400a63bb`
- `win32kbase!GreSelectBitmap` at `0x1400a63bb`
- `win32kbase!GreDeleteObject` at `0x1400a6454`
- `win32kbase!GreDeleteObject` at `0x1400a6542`
- `win32kbase!GreDeleteObject` at `0x1400a6454`
- `win32kbase!GreDeleteObject` at `0x1400a6542`

## pseudocode

```c
__int64 __fastcall GreStretchDIBitsInternalImpl(
        Gre::Base *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        LONG a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        __int64 a15)
{
  char v16; // di
  int v17; // eax
  unsigned int v18; // edx
  int v19; // ebx
  int v20; // eax
  DC *v21; // r9
  __int64 v22; // r8
  unsigned int v23; // edx
  unsigned int v24; // r13d
  int v25; // edi
  BOOL v26; // ebx
  unsigned int v27; // r14d
  int v28; // r11d
  __int64 v29; // r10
  unsigned int v30; // r8d
  int v31; // r12d
  int v32; // ecx
  __int64 v33; // r13
  int v34; // eax
  int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // edi
  unsigned int v38; // r15d
  unsigned int v39; // eax
  unsigned int v40; // r8d
  unsigned __int64 v41; // rdx
  unsigned int v42; // r13d
  unsigned __int64 v43; // rdx
  int v44; // esi
  __int64 v46; // rdx
  __int64 v47; // rcx
  int v48; // eax
  LONG v49; // edx
  unsigned int v50; // edi
  int v51; // eax
  int v52; // r9d
  int v53; // eax
  char v54; // bl
  int v55; // ecx
  int v56; // r8d
  struct REGION *v57; // rax
  struct ECLIPOBJ *v58; // rdx
  int v59; // r15d
  BOOL (__stdcall *v60)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, COLORADJUSTMENT *, POINTL *, RECTL *, RECTL *, POINTL *, ULONG); // r10
  char *v61; // r9
  int v62; // ebx
  unsigned int v63; // ebx
  int v64; // ecx
  int v65; // eax
  __int64 v66; // rax
  unsigned int v67; // r13d
  DC *v68; // r11
  DC *v69; // rbx
  int v70; // r8d
  int v71; // edx
  int v72; // r10d
  char v73; // cl
  Gre::Base *v74; // rcx
  int v75; // eax
  bool v76; // zf
  Gre::Base *v77; // rcx
  int v78; // edx
  int v79; // esi
  void *v80; // r8
  struct Gre::Base::SESSION_GLOBALS *v81; // rax
  __int64 v82; // r14
  __int64 XlateObject; // rsi
  __int64 v84; // rbx
  int v85; // edi
  DC *v86; // rdx
  __int64 v87; // rax
  int v88; // r15d
  int v89; // ebx
  HDC CompatibleDC; // rax
  int v91; // edi
  HDC v92; // r14
  __int64 CompatibleBitmapWithDIBits; // rdi
  int v94; // ebx
  int v95; // edi
  unsigned int v96; // edx
  unsigned __int64 v97; // rcx
  unsigned __int64 v98; // rdx
  unsigned __int64 v99; // rcx
  unsigned int v100; // ecx
  unsigned int v101; // eax
  __int64 v102; // rcx
  __int64 v103; // r10
  int v104; // eax
  unsigned int v105; // eax
  __int64 v106; // rbx
  __int64 v107; // r8
  int v108; // ecx
  int v109; // ecx
  unsigned int v110; // [rsp+80h] [rbp-80h]
  int v111; // [rsp+84h] [rbp-7Ch]
  int v112; // [rsp+88h] [rbp-78h]
  int v113; // [rsp+8Ch] [rbp-74h]
  char v114; // [rsp+90h] [rbp-70h]
  unsigned int v115; // [rsp+94h] [rbp-6Ch]
  unsigned int v116; // [rsp+98h] [rbp-68h]
  unsigned int v117; // [rsp+9Ch] [rbp-64h]
  unsigned int v118; // [rsp+9Ch] [rbp-64h]
  POINTL pptlSrc; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v120; // [rsp+A8h] [rbp-58h]
  unsigned int v121[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v122; // [rsp+C0h] [rbp-40h]
  unsigned int v123; // [rsp+D0h] [rbp-30h]
  unsigned int v124; // [rsp+D4h] [rbp-2Ch]
  unsigned int v125; // [rsp+D8h] [rbp-28h]
  int v126; // [rsp+DCh] [rbp-24h]
  int v127; // [rsp+E0h] [rbp-20h]
  int v128; // [rsp+E4h] [rbp-1Ch]
  int v129; // [rsp+E8h] [rbp-18h]
  __int64 v130; // [rsp+F0h] [rbp-10h]
  __int64 v131; // [rsp+F8h] [rbp-8h] BYREF
  int v132; // [rsp+100h] [rbp+0h]
  int v133[2]; // [rsp+108h] [rbp+8h] BYREF
  void *Src; // [rsp+110h] [rbp+10h]
  DC *v135; // [rsp+120h] [rbp+20h] BYREF
  int v136; // [rsp+128h] [rbp+28h]
  struct Gre::Base::SESSION_GLOBALS *v137; // [rsp+130h] [rbp+30h]
  __int64 v138; // [rsp+138h] [rbp+38h]
  char v139[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v140[48]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v141; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v142[2]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v143[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v144[3]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v145[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 *v146; // [rsp+1F8h] [rbp+F8h]
  _QWORD v147[3]; // [rsp+200h] [rbp+100h] BYREF
  char v148; // [rsp+218h] [rbp+118h]
  char v149[32]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v150; // [rsp+260h] [rbp+160h]
  __int16 v151; // [rsp+268h] [rbp+168h]
  int v152; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v153; // [rsp+2A4h] [rbp+1A4h]
  int v154; // [rsp+2A8h] [rbp+1A8h]
  int v155; // [rsp+2ACh] [rbp+1ACh]
  __int64 v156; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v157; // [rsp+2B8h] [rbp+1B8h]
  int v158; // [rsp+2BCh] [rbp+1BCh]
  RECTL prclDest; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v160[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _DWORD v161[35]; // [rsp+2D4h] [rbp+1D4h] BYREF
  __int64 v162; // [rsp+360h] [rbp+260h]
  _BYTE v163[96]; // [rsp+370h] [rbp+270h] BYREF

  pptlSrc = (POINTL)a10;
  v130 = a15;
  v128 = a2;
  v126 = a4;
  v16 = *((_BYTE *)gajRop3 + BYTE2(a13));
  v127 = a3;
  v112 = a12;
  v133[0] = a5;
  v142[0] = Gre::Base::Globals(a1);
  v137 = (struct Gre::Base::SESSION_GLOBALS *)v142[0];
  v138 = 0;
  v135 = 0;
  v136 = 0;
  UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v139);
  DCOBJ::vLock((DCOBJ *)&v135, (HDC)a1);
  UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v140);
  v140[32] = 1;
  if ( !v135 )
    goto LABEL_45;
  if ( *((_WORD *)v135 + 6) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( *((_WORD *)v135 + 6) != 1 )
    DCOBJ::vUnlock((DCOBJ *)&v135);
  if ( !v135 )
  {
LABEL_45:
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v135);
    return 0;
  }
  if ( (v16 & 0xD4) == 0 )
  {
    v17 = GrepPatBlt((struct XDCOBJ *)&v135, v128, v127, v126, a5, a13);
    goto LABEL_80;
  }
  v17 = 0;
  v111 = 0;
  if ( !a11 )
    goto LABEL_80;
  if ( !**(_QWORD **)&pptlSrc )
    goto LABEL_80;
  if ( a12 > 2 )
    goto LABEL_80;
  if ( a14 < 0xC )
    goto LABEL_80;
  v18 = *(_DWORD *)a11;
  v120 = v18;
  if ( a14 < v18 || v18 < 0x28 || *(int *)(a11 + 4) <= 0 || !*(_DWORD *)(a11 + 8) )
    goto LABEL_80;
  v19 = *(unsigned __int8 *)(*((_QWORD *)v135 + 122) + 215LL);
  DC::QuickInitXform(v135, &v141, 516);
  v20 = *(_DWORD *)(a11 + 16);
  v21 = v135;
  v22 = v141;
  if ( v20 == 4 )
  {
    if ( (*((_DWORD *)v135 + 19) & 1) == 0 || (v65 = 1, *((_DWORD *)v135 + 8) == 1) )
      v65 = 0;
  }
  else
  {
    if ( v20 != 5 )
    {
      v23 = a12;
      goto LABEL_19;
    }
    v65 = XDCOBJ::bSupportsPNG((XDCOBJ *)&v135);
  }
  if ( !v65 || BYTE2(a13) != 204 || (*(_BYTE *)(v22 + 32) & 1) == 0 || (v23 = a12) != 0 || v130 )
  {
    v63 = 0;
    goto LABEL_81;
  }
LABEL_19:
  v24 = a9;
  v129 = v19;
  if ( v126 == a8 && v133[0] == a9 && a9 > 0 )
  {
    v25 = a7;
    if ( a8 > 0 && !(a7 | a6) && BYTE2(a13) == 204 && v19 != 4 && (*(_DWORD *)(v22 + 32) & 2) != 0 )
    {
      v64 = -*(_DWORD *)(a11 + 8);
      if ( *(int *)(a11 + 8) > 0 )
        v64 = *(_DWORD *)(a11 + 8);
      if ( a9 >= v64 )
        v24 = v64;
      v17 = GrepSetDIBitsToDeviceInternalImpl(
              (struct XDCOBJ *)&v135,
              v128,
              v127,
              v126,
              v133[0],
              a6,
              a7,
              a7,
              v24,
              *(_QWORD **)&pptlSrc,
              (unsigned int *)a11,
              v23,
              a14,
              1,
              v130);
      goto LABEL_80;
    }
  }
  else
  {
    v25 = a7;
  }
  v26 = 0;
  if ( v23 == 1 )
  {
    DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v160);
    if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v160, (struct XDCOBJ *)&v135, 0) )
    {
      v102 = *((_QWORD *)v135 + 62);
      if ( v102 )
        v26 = *(_DWORD *)(v102 + 96) == 1;
    }
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v160);
    v21 = v135;
    v22 = v141;
    v23 = a12;
  }
  if ( BYTE2(a13) != 204 || (v27 = 0, (*(_BYTE *)(v22 + 32) & 1) == 0) || v26 )
  {
    v88 = *(_DWORD *)(a11 + 8);
    if ( v88 <= 0 )
      v89 = v25;
    else
      v89 = v88 - v25 - a9;
    DCOBJ::DCOBJ((DCOBJ *)v147, v137);
    UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>(v149);
    if ( v135 )
      v150 = *(_QWORD *)v135;
    else
      v150 = 0;
    v147[0] = v135;
    v151 = 256;
    CompatibleDC = GrepCreateCompatibleDC((struct OPTAPIDCOBJ *)v147);
    v91 = *(_DWORD *)(a11 + 16);
    v92 = CompatibleDC;
    ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v163);
    if ( v91 == 1 || v91 == 2 )
    {
      CompatibleBitmapWithDIBits = GrepCreateCompatibleBitmapWithDIBits(
                                     (OPTAPIDCOBJ *)v147,
                                     *(_DWORD *)(a11 + 4),
                                     *(_DWORD *)(a11 + 8),
                                     *(_QWORD *)&pptlSrc,
                                     a11,
                                     a12,
                                     a14,
                                     v130);
    }
    else
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD))GrepCreateDIBitmap)(
        v145,
        v147,
        4,
        pptlSrc,
        a11,
        a12,
        a14,
        0,
        0,
        0,
        0,
        0,
        0);
      if ( v146 )
        CompatibleBitmapWithDIBits = *v146;
      else
        CompatibleBitmapWithDIBits = 0;
      SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v145);
    }
    if ( v92 && CompatibleBitmapWithDIBits )
    {
      GreSelectBitmap(v92, CompatibleBitmapWithDIBits);
      OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v160, v92);
      v94 = GrepStretchBlt(
              (struct XDCOBJ *)&v135,
              v128,
              v127,
              v126,
              v133[0],
              (struct OPTAPIDCOBJ *)v160,
              a6,
              v89,
              a8,
              a9,
              a13,
              0xFFFFFFu,
              1u);
      OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v160);
      GrepDeleteDC(v92, 0x400000);
      GreDeleteObject(CompatibleBitmapWithDIBits);
      if ( v94 )
        v111 = v88;
    }
    else
    {
      GrepDeleteDC(v92, 0x400000);
      GreDeleteObject(CompatibleBitmapWithDIBits);
    }
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v163);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v147);
    v63 = v111;
    goto LABEL_81;
  }
  v28 = *(_DWORD *)(a11 + 16);
  v29 = *(unsigned int *)(a11 + 4);
  v30 = *(_DWORD *)(a11 + 32);
  v31 = 1;
  v32 = *(_DWORD *)(a11 + 8);
  v33 = *(unsigned __int16 *)(a11 + 14);
  Src = (void *)(a11 + v120);
  v122 = 0;
  v113 = v28;
  *(_OWORD *)v121 = 0;
  prclDest.left = v29;
  v34 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
  v117 = v30;
  if ( v32 < 0 )
    v34 = 1;
  DWORD2(v122) = v34;
  v35 = -v32;
  if ( v32 > 0 )
    v35 = v32;
  v115 = v35;
  v36 = 0;
  v110 = 0;
  v37 = 0;
  v125 = 0;
  v124 = 0;
  v123 = 0;
  if ( v28 == 3 )
  {
    if ( a14 >= 0x34 )
    {
      if ( v23 != 1 )
        v36 = v23;
      v112 = v36;
      if ( (_WORD)v33 == 16 )
      {
        v121[0] = 4;
      }
      else if ( (_DWORD)v33 == 32 )
      {
        v121[0] = 6;
      }
      else
      {
        EngSetLastError(0x57u);
        v31 = 0;
        LODWORD(v29) = prclDest.left;
      }
      v98 = (unsigned int)v29 * v33;
      if ( v98 > 0xFFFFFFFF )
        goto LABEL_186;
      v99 = (unsigned int)(v98 + 31);
      if ( (unsigned int)v99 < (unsigned int)v98
        || (int)ULongLongToULong(v115 * ((v99 >> 3) & 0x1FFFFFFC), &v121[3]) < 0 )
      {
        goto LABEL_186;
      }
      v27 = 2;
      v37 = 512;
      v125 = *(_DWORD *)(a11 + 40);
      v100 = *(_DWORD *)(a11 + 44);
      Src = (void *)(a11 + 40);
      v123 = *(_DWORD *)(a11 + 48);
      v124 = v100;
      v110 = 2;
    }
    else
    {
      EngSetLastError(0x57u);
      v21 = v135;
      v31 = 0;
    }
    v38 = 0;
    v44 = 0;
LABEL_104:
    if ( !v31 )
      goto LABEL_79;
    LODWORD(v29) = prclDest.left;
    v28 = v113;
    v42 = v115;
    goto LABEL_106;
  }
  v38 = 0;
  switch ( v28 )
  {
    case 0:
      if ( (_DWORD)v33 == 1 )
      {
        v121[0] = 1;
        v110 = 1;
        v38 = 2;
      }
      else
      {
        if ( (_DWORD)v33 == 4 )
        {
          v121[0] = 2;
          v38 = 16;
        }
        else
        {
          if ( (_DWORD)v33 != 8 )
          {
            v39 = 0;
            if ( v23 != 1 )
              v39 = v23;
            v112 = v39;
            if ( (_WORD)v33 == 16 )
            {
              v121[0] = 4;
              v95 = 2;
              v125 = 31744;
              v124 = 992;
              v123 = 31;
            }
            else
            {
              if ( (_WORD)v33 != 24 )
              {
                if ( (_DWORD)v33 == 32 )
                {
                  v121[0] = 6;
                  v110 = 8;
                  v37 = 512;
LABEL_40:
                  v40 = v29 * v33;
                  if ( (unsigned __int64)(v29 * v33) <= 0xFFFFFFFF )
                  {
                    v41 = v40 + 31;
                    if ( (unsigned int)v41 >= v40 )
                    {
                      v42 = v115;
                      v43 = v115 * ((v41 >> 3) & 0x1FFFFFFC);
                      if ( v43 <= 0xFFFFFFFF )
                      {
                        v121[3] = v43;
LABEL_44:
                        v27 = v110;
                        v44 = 0;
LABEL_106:
                        v30 = v117;
                        goto LABEL_107;
                      }
                      v121[3] = -1;
                    }
                  }
LABEL_186:
                  EngSetLastError(0x216u);
                  v63 = 0;
                  goto LABEL_81;
                }
LABEL_201:
                EngSetLastError(0x57u);
                v17 = 0;
                goto LABEL_80;
              }
              v121[0] = 5;
              v95 = 8;
            }
            v110 = v95;
            v37 = 512;
            v112 = v39;
            goto LABEL_40;
          }
          v121[0] = 3;
          v38 = 256;
        }
        v110 = 1;
      }
      v37 = 1024;
      goto LABEL_40;
    case 10:
      if ( !v21 || !(unsigned int)DC::bIsCMYKColor(v21) )
        goto LABEL_201;
      if ( (_DWORD)v33 != 1 )
      {
        switch ( (_DWORD)v33 )
        {
          case 4:
            v121[0] = 2;
            v38 = 16;
            break;
          case 8:
            v121[0] = 3;
            v38 = 256;
            break;
          case 0x20:
            v121[0] = 6;
            v104 = 16;
            v37 = 512;
            goto LABEL_255;
          default:
            goto LABEL_201;
        }
        v110 = 1;
        v37 = 1024;
LABEL_213:
        v96 = v103 * v33;
        if ( (unsigned __int64)(v103 * v33) <= 0xFFFFFFFF )
        {
          v97 = v96 + 31;
          if ( (unsigned int)v97 >= v96 )
          {
            v42 = v115;
            if ( (int)ULongLongToULong(v115 * ((v97 >> 3) & 0x1FFFFFFC), &v121[3]) >= 0 )
              goto LABEL_44;
          }
        }
        goto LABEL_186;
      }
      v104 = 1;
      v37 = 1024;
      v121[0] = 1;
      v38 = 2;
LABEL_255:
      v110 = v104;
      goto LABEL_213;
    case 2:
LABEL_223:
      if ( (_WORD)v33 != 4 )
      {
        EngSetLastError(0x57u);
        v21 = v135;
        v31 = 0;
      }
      v101 = *(_DWORD *)(a11 + 20);
      v121[0] = 7;
      v27 = 1;
      v110 = 1;
      v37 = 1024;
      v121[3] = v101;
      v44 = 1;
      v38 = 16;
      goto LABEL_104;
    case 12:
      if ( !v21 || !(unsigned int)DC::bIsCMYKColor(v21) )
        goto LABEL_201;
      goto LABEL_223;
    case 1:
      goto LABEL_266;
    case 11:
      if ( !v21 || !(unsigned int)DC::bIsCMYKColor(v21) )
      {
        EngSetLastError(0x57u);
        v21 = v135;
        v31 = 0;
LABEL_103:
        v44 = v27;
        goto LABEL_104;
      }
LABEL_266:
      if ( (_WORD)v33 != 8 )
      {
        EngSetLastError(0x57u);
        v21 = v135;
        v31 = 0;
      }
      v105 = *(_DWORD *)(a11 + 20);
      v27 = 1;
      v121[0] = 8;
      v38 = 256;
      v110 = 1;
      v37 = 1024;
      v121[3] = v105;
      goto LABEL_103;
    case 4:
      v121[0] = 9;
      break;
    case 5:
      v121[0] = 10;
      break;
    default:
      goto LABEL_201;
  }
  v27 = 8;
  v42 = v115;
  v37 = 512;
  v110 = 8;
  v44 = 0;
  v121[3] = *(_DWORD *)(a11 + 20);
LABEL_107:
  v66 = v130;
  if ( !v130 )
  {
    v66 = *(_QWORD *)(*((_QWORD *)v21 + 122) + 248LL);
    v130 = v66;
  }
  v118 = *((_DWORD *)v21 + 30);
  if ( (v118 & 0x10000000) != 0 && (!v66 || (unsigned int)(v28 - 10) > 2) )
    v118 = v118 & 0xFFFFFFF | 0x20000000;
  v121[2] = v42;
  v67 = v38;
  v121[1] = v29;
  if ( v30 && v30 <= v38 )
    v67 = v30;
  if ( *(_QWORD *)(*(_QWORD *)&pptlSrc + 8LL) - *(_QWORD *)(*(_QWORD *)&pptlSrc + 16LL) < (unsigned __int64)v121[3] )
  {
    EngSetLastError(0x57u);
    goto LABEL_79;
  }
  v156 = *((_QWORD *)v21 + 6);
  v152 = v128;
  v154 = v128 + v126;
  v153 = v127;
  v155 = v127 + v133[0];
  DC::QuickInitXform(v21, v133, 516);
  v68 = v135;
  v69 = v135;
  if ( (*(_BYTE *)(*(_QWORD *)v133 + 32LL) & 0x43) != 0x43 )
  {
    if ( !(unsigned int)bCvtPts1(*(_QWORD *)v133, &v152, 2) )
      goto LABEL_79;
    v68 = v135;
  }
  v70 = v152;
  v71 = v154;
  if ( (*(_DWORD *)(*((_QWORD *)v69 + 122) + 108LL) & 1) != 0 )
  {
    v70 = v152 + 1;
    v71 = v154 + 1;
    ++v152;
    ++v154;
  }
  if ( v70 == v71 || (v72 = v153, v153 == v155) )
  {
    v17 = a9;
    goto LABEL_80;
  }
  v114 = 0;
  v73 = 0;
  if ( v70 > v71 )
  {
    v152 = v71;
    v154 = v70;
    if ( (*(_DWORD *)(*((_QWORD *)v68 + 122) + 108LL) & 1) == 0 )
    {
      v152 = v71 + 1;
      v154 = v70 + 1;
    }
    v73 = 1;
    v114 = 1;
  }
  if ( v153 > v155 )
  {
    v153 = v155 + 1;
    v155 = v72 + 1;
    v114 = v73 ^ 2;
  }
  v132 = 0;
  v131 = 0;
  if ( !v112 )
    v31 = PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v131, v27, v38, 0, v125, v124, v123, v37, 1) != 0 ? v31 : 0;
  DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v147);
  if ( !v31 || !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v147, (struct XDCOBJ *)&v135, 0) )
    goto LABEL_78;
  Gre::Base::Globals(v74);
  v75 = *(_DWORD *)(*((_QWORD *)v135 + 6) + 40LL) & 0x8000;
  *(_QWORD *)&v122 = 0;
  DWORD2(v122) |= 8 * v75;
  SURFMEM::SURFMEM(v143, 3);
  if ( v44 )
  {
    SURFMEM::SURFMEM(v144, 2);
    v79 = v78 - 1;
    v145[0] = *(_OWORD *)v121;
    v145[1] = v122;
    if ( SURFMEM::bCreateDIB((SURFMEM *)v144, (struct _DEVBITMAPINFO *)v145, v80, 0, 0, 0, 0, 0, v78 - 1, 0)
      && (v121[0] = (v121[0] != 7) + 2,
          SURFMEM::bCreateDIB((SURFMEM *)v143, (struct _DEVBITMAPINFO *)v121, 0, 0, 0, 0, 0, 0, v79, 0)) )
    {
      prclDest.right = v121[1];
      prclDest.bottom = v121[2];
      *(_QWORD *)&prclDest.left = 0;
      pptlSrc = 0;
      EngCopyBits(
        (SURFOBJ *)((v143[0] + 24LL) & -(__int64)(v143[0] != 0)),
        (SURFOBJ *)((v144[0] + 24LL) & -(__int64)(v144[0] != 0)),
        0,
        0,
        &prclDest,
        &pptlSrc);
    }
    else
    {
      v31 = 0;
    }
    SURFMEM::~SURFMEM((SURFMEM *)v144);
    v76 = v31 == 0;
  }
  else
  {
    v76 = SURFMEM::bCreateDIB(
            (SURFMEM *)v143,
            (struct _DEVBITMAPINFO *)v121,
            (void *)(**(_QWORD **)&pptlSrc + *(_QWORD *)(*(_QWORD *)&pptlSrc + 16LL)),
            0,
            0,
            0,
            0,
            0,
            1,
            0) == 0;
  }
  if ( !v76 )
  {
    v116 = a14 - v120;
    v81 = Gre::Base::Globals(v77);
    v82 = *((_QWORD *)v135 + 62);
    if ( v82 )
    {
      if ( v138 )
        v82 = v138;
    }
    else
    {
      v82 = *((_QWORD *)v81 + 547);
    }
    XlateObject = 0;
    v84 = *(_QWORD *)(v82 + 160);
    *(_QWORD *)&prclDest.left = *((_QWORD *)v135 + 11);
    pptlSrc = 0;
    v120 = 0;
    if ( !XEPALOBJ::bIsPalDefault((XEPALOBJ *)&prclDest) )
      *(_QWORD *)(v82 + 208) = **(_QWORD **)&prclDest.left;
    if ( v112 )
    {
      if ( v112 == 1 )
      {
        if ( v116 < 2 * (unsigned __int64)v67
          || !(unsigned int)EXLATEOBJ::bMakeXlate(&pptlSrc, Src, *(_QWORD *)&prclDest.left, v82, v67, v38) )
        {
          goto LABEL_76;
        }
        XlateObject = (__int64)pptlSrc;
        if ( *(_DWORD *)(v142[0] + 3152LL) )
        {
          v106 = v156;
          if ( (*(_DWORD *)(v156 + 40) & 1) != 0 )
          {
            if ( PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v131, v110, v38, 0, v125, v124, v123, v37, 1) )
            {
              v107 = *(_QWORD *)(v82 + 160);
              if ( !v107 )
                v107 = *(_QWORD *)(v106 + 1792);
              XEPALOBJ::vGetEntriesFrom(&v131, *(_QWORD *)&prclDest.left, v107, Src, v67);
              v120 = 1;
            }
            else
            {
              v31 = 0;
            }
          }
        }
        v85 = v113;
      }
      else
      {
        v85 = v113;
        if ( v112 != 2 )
          goto LABEL_141;
        if ( *(_DWORD *)(v82 + 96) != v121[0] )
          v31 = 0;
        XlateObject = v142[0] + 4664LL;
      }
    }
    else if ( v67 )
    {
      if ( v116 < 4 * v67 )
        goto LABEL_76;
      v85 = v113;
      if ( (unsigned int)(v113 - 10) > 2 )
      {
        XEPALOBJ::vCopy_rgbquad((XEPALOBJ *)&v131, (struct tagRGBQUAD *)Src, 0, v67);
      }
      else
      {
        if ( v67 > *(_DWORD *)(v131 + 28) )
          v67 = *(_DWORD *)(v131 + 28);
        memmove(*(void **)(v131 + 112), Src, 4LL * v67);
        XEPALOBJ::vUpdateTime((XEPALOBJ *)&v131);
      }
      pptlSrc = (POINTL)CreateXlateObject(
                          v130,
                          v118,
                          v131,
                          v84,
                          *(_QWORD *)&prclDest.left,
                          *(_QWORD *)&prclDest.left,
                          0,
                          0,
                          0xFFFFFF,
                          0);
      XlateObject = (__int64)pptlSrc;
      if ( !*(_QWORD *)&pptlSrc )
        v31 = 0;
    }
    else
    {
      v85 = v113;
      XlateObject = CreateXlateObject(
                      v130,
                      v118,
                      v131,
                      v84,
                      *(_QWORD *)&prclDest.left,
                      *(_QWORD *)&prclDest.left,
                      0,
                      0,
                      0xFFFFFF,
                      0);
      pptlSrc = (POINTL)XlateObject;
      if ( !XlateObject )
      {
        v31 = 0;
        XlateObject = 0;
      }
    }
    if ( v31 )
    {
LABEL_141:
      v86 = v135;
      if ( (*((_DWORD *)v135 + 9) & 0xE0) != 0 )
      {
        XDCOBJ::vAccumulate((XDCOBJ *)&v135, (struct ERECTL *)&v152);
        v86 = v135;
      }
      if ( !*((_QWORD *)v86 + 62) || (unsigned int)DC::bInFullScreen(v86) )
      {
        v111 = v115;
      }
      else if ( (v148 & 1) != 0 )
      {
        v47 = *(_DWORD *)(v46 + 40) & 1LL;
        v152 += *(_DWORD *)(v46 + 8 * v47 + 1016);
        v154 += *(_DWORD *)(v46 + 8 * v47 + 1016);
        v153 += *(_DWORD *)(v46 + 8 * v47 + 1020);
        v48 = *(_DWORD *)(v46 + 8 * v47 + 1020);
        v49 = a6;
        v155 += v48;
        LODWORD(v156) = a6;
        if ( v85 == 4 && (BYTE8(v122) & 1) != 0 )
        {
          v52 = a7;
          v51 = a9;
          v50 = v115;
        }
        else
        {
          v50 = v115;
          v51 = a9;
          v52 = v115 - a7 - a9;
        }
        v53 = v52 + v51;
        v54 = v114;
        v55 = a6 + a8;
        HIDWORD(v156) = v52;
        v56 = v52;
        v158 = v53;
        v157 = a6 + a8;
        if ( a6 > a6 + a8 )
        {
          v49 = v55 + 1;
          v54 = v114 ^ 1;
          v55 = a6 + 1;
          LODWORD(v156) = v49;
          v157 = a6 + 1;
        }
        if ( v52 > v53 )
        {
          v52 = v53 + 1;
          v54 ^= 2u;
          v53 = v56 + 1;
          HIDWORD(v156) = v52;
          v158 = v56 + 1;
        }
        if ( v55 > 0
          && v53 > 0
          && v52 != v53
          && v49 != v55
          && v49 < *(_DWORD *)(v143[0] + 56LL)
          && v52 < *(_DWORD *)(v143[0] + 60LL) )
        {
          v57 = XDCOBJ::prgnEffRao((XDCOBJ *)&v135);
          *(_QWORD *)&v161[13] = 0;
          *(_QWORD *)&v161[19] = 0;
          v161[21] = 0;
          v161[31] = 1;
          v162 = 0;
          XCLIPOBJ::vSetup((XCLIPOBJ *)v160, v57, (const struct ERECTL *)&v152, 0);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)v161) )
          {
            v111 = v50;
          }
          else
          {
            if ( (*((_DWORD *)v135 + 9) & 0xE0) != 0 )
            {
              v142[0] = *(_QWORD *)v161;
              v142[1] = *(_QWORD *)&v161[2];
              XDCOBJ::vAccumulateTight((XDCOBJ *)&v135, v58, (struct ERECTL *)v142);
            }
            if ( v120 )
            {
              XEPALOBJ::vRefPalette((XEPALOBJ *)&v131);
              *(_QWORD *)(v143[0] + 160LL) = v131;
            }
            v59 = v129;
            if ( (*(_DWORD *)(v82 + 144) & 2) != 0 )
            {
              v87 = *(_QWORD *)(v82 + 48);
              v60 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, COLORADJUSTMENT *, POINTL *, RECTL *, RECTL *, POINTL *, ULONG))(v87 + 2840);
              if ( (*(_DWORD *)(v87 + 40) & 0x20000) == 0 )
              {
                if ( v129 == 4 && (*((_BYTE *)v135 + 72) & 0x10) == 0 )
                  v60 = EngStretchBlt;
                if ( v156 < 0
                  || (int)v156 < 0
                  || v157 > *(_DWORD *)(v143[0] + 56LL)
                  || v158 > *(_DWORD *)(v143[0] + 60LL) )
                {
                  v60 = EngStretchBlt;
                }
              }
            }
            else
            {
              v60 = EngStretchBlt;
            }
            if ( (v54 & 1) != 0 )
            {
              v108 = v152;
              v152 = v154;
              v154 = v108;
            }
            if ( (v54 & 2) != 0 )
            {
              v109 = v153;
              v153 = v155;
              v155 = v109;
            }
            ++*(_DWORD *)(v82 + 92);
            v61 = 0;
            if ( *((__int16 *)v135 + 89) >= 0 )
              v61 = (char *)v135 + 176;
            v62 = 0;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, _QWORD, _BYTE *, __int64, char *, char *, int *, __int64 *, _QWORD, int))v60)(
                   v82 + 24,
                   (v143[0] + 24LL) & -(__int64)(v143[0] != 0),
                   0,
                   v160,
                   XlateObject,
                   v61,
                   (char *)v135 + 1192,
                   &v152,
                   &v156,
                   0,
                   v59) )
            {
              v62 = v50;
            }
            v111 = v62;
          }
        }
      }
    }
LABEL_76:
    EXLATEOBJ::vAltUnlock((EXLATEOBJ *)&pptlSrc);
  }
  SURFMEM::~SURFMEM((SURFMEM *)v143);
LABEL_78:
  DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v147);
  PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v131);
LABEL_79:
  v17 = v111;
LABEL_80:
  v63 = v17;
LABEL_81:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v135);
  return v63;
}

```

## disassembly

```asm
0x1400a55dc  push    rbp
0x1400a55de  push    rbx
0x1400a55df  push    rsi
0x1400a55e0  push    rdi
0x1400a55e1  push    r12
0x1400a55e3  push    r13
0x1400a55e5  push    r14
0x1400a55e7  push    r15
0x1400a55e9  lea     rbp, [rsp-2E8h]
0x1400a55f1  sub     rsp, 3E8h
0x1400a55f8  mov     rax, cs:__security_cookie
0x1400a55ff  xor     rax, rsp
0x1400a5602  mov     [rbp+320h+var_50], rax
0x1400a5609  mov     rax, [rbp+320h+arg_48]
0x1400a5610  lea     rdi, gajRop3
0x1400a5617  mov     r12d, [rbp+320h+arg_60]
0x1400a561e  mov     rbx, rcx
0x1400a5621  mov     r15d, [rbp+320h+arg_58]
0x1400a5628  mov     r13d, [rbp+320h+arg_20]
0x1400a562f  mov     rsi, [rbp+320h+arg_50]
0x1400a5636  mov     qword ptr [rbp+320h+var_380.x], rax
0x1400a563a  mov     rax, [rbp+320h+arg_70]
0x1400a5641  mov     [rbp+320h+var_330], rax
0x1400a5645  mov     eax, r12d
0x1400a5648  shr     eax, 10h
0x1400a564b  movzx   r14d, al
0x1400a564f  mov     [rbp+320h+var_33C], edx
0x1400a5652  mov     edx, [rbp+320h+arg_68]
0x1400a5658  mov     [rbp+320h+var_344], r9d
0x1400a565c  mov     dil, [r14+rdi]
0x1400a5660  mov     [rbp+320h+var_340], r8d
0x1400a5664  mov     [rbp+320h+var_398], r15d
0x1400a5668  mov     [rbp+320h+var_318], r13d
0x1400a566c  mov     [rbp+320h+var_388], edx
0x1400a566f  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a5676  nop     dword ptr [rax+rax+00h]
0x1400a567b  mov     [rbp+320h+var_288], rax
0x1400a5682  lea     rcx, [rbp+320h+var_2E0]
0x1400a5686  mov     [rbp+320h+var_2F0], rax
0x1400a568a  xor     eax, eax
0x1400a568c  mov     [rbp+320h+var_2E8], rax
0x1400a5690  mov     [rbp+320h+var_300], rax
0x1400a5694  mov     [rbp+320h+var_2F8], eax
0x1400a5697  call    ??0?$UnexpectedThreadTerminationHandler@VDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(void)
0x1400a569c  mov     rdx, rbx; HDC
0x1400a569f  lea     rcx, [rbp+320h+var_300]; this
0x1400a56a3  call    ?vLock@DCOBJ@@QEAAXPEAUHDC__@@@Z; DCOBJ::vLock(HDC__ *)
0x1400a56a8  lea     rcx, [rbp+320h+var_2C0]
0x1400a56ac  call    ??0?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(void)
0x1400a56b1  mov     rax, [rbp+320h+var_300]
0x1400a56b5  mov     ebx, 1
0x1400a56ba  mov     [rbp+320h+var_2A0], bl
0x1400a56c0  test    rax, rax
0x1400a56c3  jz      loc_1400A5933
0x1400a56c9  movzx   eax, word ptr [rax+0Ch]
0x1400a56cd  cmp     ax, bx
0x1400a56d0  jnz     loc_1400A677E
0x1400a56d6  mov     rax, [rbp+320h+var_300]
0x1400a56da  movzx   ecx, word ptr [rax+0Ch]
0x1400a56de  cmp     cx, bx
0x1400a56e1  jnz     loc_1400A6788
0x1400a56e7  mov     rcx, [rbp+320h+var_300]
0x1400a56eb  test    rcx, rcx
0x1400a56ee  jz      loc_1400A5933
0x1400a56f4  test    dil, 0D4h
0x1400a56f8  jz      loc_1400A6796
0x1400a56fe  xor     edi, edi
0x1400a5700  mov     eax, edi
0x1400a5702  mov     [rbp+320h+var_39C], eax
0x1400a5705  test    rsi, rsi
0x1400a5708  jz      loc_1400A5BD1
0x1400a570e  mov     rdx, qword ptr [rbp+320h+var_380.x]
0x1400a5712  cmp     [rdx], rdi
0x1400a5715  jz      loc_1400A5BD1
0x1400a571b  cmp     r15d, 2
0x1400a571f  ja      loc_1400A5BD1
0x1400a5725  mov     r15d, [rbp+320h+var_388]
0x1400a5729  cmp     r15d, 0Ch
0x1400a572d  jb      loc_1400A5BD1
0x1400a5733  mov     edx, [rsi]
0x1400a5735  mov     [rbp+320h+var_378], edx
0x1400a5738  cmp     r15d, edx
0x1400a573b  jb      loc_1400A5BD1
0x1400a5741  cmp     edx, 28h ; '('
0x1400a5744  jb      loc_1400A5BD1
0x1400a574a  cmp     [rsi+4], edi
0x1400a574d  jle     loc_1400A5BD1
0x1400a5753  cmp     [rsi+8], edi
0x1400a5756  jz      loc_1400A5BD1
0x1400a575c  mov     rax, [rcx+3D0h]
0x1400a5763  lea     rdx, [rbp+320h+var_290]
0x1400a576a  mov     r8d, 204h
0x1400a5770  movzx   ebx, byte ptr [rax+0D7h]
0x1400a5777  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x1400a577e  nop     dword ptr [rax+rax+00h]
0x1400a5783  mov     eax, [rsi+10h]
0x1400a5786  mov     r9, [rbp+320h+var_300]
0x1400a578a  mov     r8, [rbp+320h+var_290]
0x1400a5791  cmp     eax, 4
0x1400a5794  jz      loc_1400A5CA1
0x1400a579a  cmp     eax, 5
0x1400a579d  jz      loc_1400A67B9
0x1400a57a3  mov     edx, [rbp+320h+var_398]
0x1400a57a6  mov     r11d, [rbp+320h+var_344]
0x1400a57aa  mov     ecx, ebx
0x1400a57ac  mov     eax, [rbp+320h+arg_38]
0x1400a57b2  mov     r13d, [rbp+320h+arg_40]
0x1400a57b9  mov     [rbp+320h+var_338], ebx
0x1400a57bc  cmp     r11d, eax
0x1400a57bf  jz      loc_1400A5BE4
0x1400a57c5  mov     edi, [rbp+320h+arg_30]
0x1400a57cb  xor     ebx, ebx
0x1400a57cd  lea     ecx, [rbx+1]
0x1400a57d0  cmp     edx, ecx
0x1400a57d2  jz      loc_1400A67DD
0x1400a57d8  cmp     r14d, 0CCh
0x1400a57df  jnz     loc_1400A629B
0x1400a57e5  xor     r14d, r14d
0x1400a57e8  test    [r8+20h], cl
0x1400a57ec  jz      loc_1400A629E
0x1400a57f2  test    ebx, ebx
0x1400a57f4  jnz     loc_1400A629E
0x1400a57fa  mov     r11d, [rsi+10h]
0x1400a57fe  lea     ebx, [r14+1]
0x1400a5802  mov     eax, [rbp+320h+var_378]
0x1400a5805  xorps   xmm0, xmm0
0x1400a5808  mov     r10d, [rsi+4]
0x1400a580c  add     rax, rsi
0x1400a580f  mov     r8d, [rsi+20h]
0x1400a5813  mov     r12d, ecx
0x1400a5816  mov     ecx, [rsi+8]
0x1400a5819  test    ecx, ecx
0x1400a581b  movzx   r13d, word ptr [rsi+0Eh]
0x1400a5820  mov     [rbp+320h+Src], rax
0x1400a5824  movups  [rbp+320h+var_360], xmm0
0x1400a5828  mov     [rbp+320h+var_394], r11d
0x1400a582c  movups  xmmword ptr [rbp+320h+var_370], xmm0
0x1400a5830  mov     [rbp+320h+var_160.left], r10d
0x1400a5837  psrldq  xmm0, 8
0x1400a583c  movd    eax, xmm0
0x1400a5840  mov     [rbp+320h+var_384], r8d
0x1400a5844  cmovs   eax, ebx
0x1400a5847  mov     dword ptr [rbp+320h+var_360+8], eax
0x1400a584a  mov     eax, ecx
0x1400a584c  neg     eax
0x1400a584e  cmovs   eax, ecx
0x1400a5851  mov     [rbp+320h+var_38C], eax
0x1400a5854  xor     eax, eax
0x1400a5856  mov     [rbp+320h+var_3A0], eax
0x1400a5859  mov     edi, eax
0x1400a585b  mov     [rbp+320h+var_348], eax
0x1400a585e  mov     [rbp+320h+var_34C], eax
0x1400a5861  mov     [rbp+320h+var_350], eax
0x1400a5864  lea     ebx, [rax+57h]
0x1400a5867  mov     [rbp+320h+var_390], eax
0x1400a586a  lea     ecx, [rax+10h]
0x1400a586d  cmp     r11d, 3
0x1400a5871  jz      loc_1400A5CC3
0x1400a5877  xor     r15d, r15d
0x1400a587a  test    r11d, r11d
0x1400a587d  jnz     loc_1400A6586
0x1400a5883  mov     eax, r13d
0x1400a5886  sub     eax, 1
0x1400a5889  jz      loc_1400A6202
0x1400a588f  sub     eax, 3
0x1400a5892  jz      loc_1400A65AE
0x1400a5898  lea     ecx, [rbx-53h]
0x1400a589b  cmp     eax, ecx
0x1400a589d  jz      loc_1400A656C
0x1400a58a3  cmp     edx, 1
0x1400a58a6  mov     eax, r15d
0x1400a58a9  cmovnz  eax, edx
0x1400a58ac  mov     edx, eax
0x1400a58ae  mov     [rbp+320h+var_398], eax
0x1400a58b1  lea     eax, [rbx-47h]
0x1400a58b4  cmp     r13w, ax
0x1400a58b8  jz      loc_1400A6894
0x1400a58be  lea     ecx, [rbx-3Fh]
0x1400a58c1  cmp     r13w, cx
0x1400a58c5  jz      loc_1400A64B6
0x1400a58cb  cmp     r13d, 20h ; ' '
0x1400a58cf  jnz     loc_1400A6599
0x1400a58d5  lea     edi, [rbx-4Fh]
0x1400a58d8  mov     [rbp+320h+var_370], 6
0x1400a58df  mov     [rbp+320h+var_3A0], edi
0x1400a58e2  mov     edi, 200h
0x1400a58e7  mov     r8, r13
0x1400a58ea  mov     ecx, 0FFFFFFFFh
0x1400a58ef  imul    r8, r10
0x1400a58f3  cmp     r8, rcx
0x1400a58f6  ja      loc_1400A649E
0x1400a58fc  lea     edx, [r8+1Fh]
0x1400a5900  cmp     edx, r8d
0x1400a5903  jb      loc_1400A649E
0x1400a5909  mov     r13d, [rbp+320h+var_38C]
0x1400a590d  shr     rdx, 3
0x1400a5911  and     edx, 1FFFFFFCh
0x1400a5917  imul    rdx, r13
0x1400a591b  cmp     rdx, rcx
0x1400a591e  ja      loc_1400A649B
0x1400a5924  mov     [rbp+320h+var_370+0Ch], edx
0x1400a5927  mov     r14d, [rbp+320h+var_3A0]
0x1400a592b  mov     esi, [rbp+320h+var_390]
0x1400a592e  jmp     loc_1400A5D23
0x1400a5933  lea     rcx, [rbp+320h+var_300]; this
0x1400a5937  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1400a593c  xor     eax, eax
0x1400a593e  jmp     loc_1400A6C8A
0x1400a5943  mov     rcx, rdx; this
0x1400a5946  call    ?bInFullScreen@DC@@QEBAHXZ; DC::bInFullScreen(void)
0x1400a594b  test    eax, eax
0x1400a594d  jnz     loc_1400A60EF
0x1400a5953  lea     r12d, [rax+1]
0x1400a5957  test    [rbp+320h+var_208], r12b
0x1400a595e  jz      loc_1400A5B96
0x1400a5964  mov     ecx, [rdx+28h]
0x1400a5967  mov     r10d, [rbp+320h+arg_28]
0x1400a596e  and     rcx, r12
0x1400a5971  mov     eax, [rdx+rcx*8+3F8h]
0x1400a5978  add     [rbp+320h+var_180], eax
0x1400a597e  mov     eax, [rdx+rcx*8+3F8h]
0x1400a5985  add     [rbp+320h+var_178], eax
0x1400a598b  mov     eax, [rdx+rcx*8+3FCh]
0x1400a5992  add     [rbp+320h+var_17C], eax
0x1400a5998  mov     eax, [rdx+rcx*8+3FCh]
0x1400a599f  mov     edx, r10d
0x1400a59a2  add     [rbp+320h+var_174], eax
0x1400a59a8  mov     dword ptr [rbp+320h+var_170], edx
0x1400a59ae  cmp     edi, 4
0x1400a59b1  jz      loc_1400A6BF6
0x1400a59b7  mov     edi, [rbp+320h+var_38C]
0x1400a59ba  mov     r9d, edi
0x1400a59bd  sub     r9d, [rbp+320h+arg_30]
0x1400a59c4  mov     eax, [rbp+320h+arg_40]
0x1400a59ca  sub     r9d, eax
0x1400a59cd  mov     ecx, [rbp+320h+arg_38]
0x1400a59d3  add     eax, r9d
0x1400a59d6  mov     ebx, [rbp+320h+var_390]
0x1400a59d9  add     ecx, r10d
0x1400a59dc  mov     dword ptr [rbp+320h+var_170+4], r9d
0x1400a59e3  mov     r8d, r9d
0x1400a59e6  mov     [rbp+320h+var_164], eax
0x1400a59ec  mov     [rbp+320h+var_168], ecx
0x1400a59f2  cmp     r10d, ecx
0x1400a59f5  jg      loc_1400A6C15
0x1400a59fb  cmp     r8d, eax
0x1400a59fe  jg      loc_1400A6137
0x1400a5a04  test    ecx, ecx
0x1400a5a06  jle     loc_1400A5B96
0x1400a5a0c  test    eax, eax
0x1400a5a0e  jle     loc_1400A5B96
0x1400a5a14  mov     r8, [rbp+320h+var_278]
0x1400a5a1b  cmp     r9d, eax
0x1400a5a1e  jz      loc_1400A5B96
0x1400a5a24  cmp     edx, ecx
0x1400a5a26  jz      loc_1400A5B96
0x1400a5a2c  cmp     edx, [r8+38h]
0x1400a5a30  jge     loc_1400A5B96
0x1400a5a36  cmp     r9d, [r8+3Ch]
0x1400a5a3a  jge     loc_1400A5B96
0x1400a5a40  lea     rcx, [rbp+320h+var_300]; this
0x1400a5a44  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x1400a5a49  lea     r8, [rbp+320h+var_180]
0x1400a5a50  mov     [rbp+320h+var_118], r13
0x1400a5a57  mov     rdx, rax
0x1400a5a5a  mov     [rbp+320h+var_100], r13
0x1400a5a61  lea     rcx, [rbp+320h+var_150]
0x1400a5a68  mov     [rbp+320h+var_F8], r13d
0x1400a5a6f  xor     r9d, r9d
0x1400a5a72  mov     [rbp+320h+var_D0], r12d
0x1400a5a79  mov     [rbp+320h+var_C0], r13
0x1400a5a80  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x1400a5a87  nop     dword ptr [rax+rax+00h]
0x1400a5a8c  lea     rcx, [rbp+320h+var_14C]; this
0x1400a5a93  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x1400a5a98  test    eax, eax
0x1400a5a9a  jnz     loc_1400A621B
0x1400a5aa0  mov     rax, [rbp+320h+var_300]
0x1400a5aa4  mov     ecx, [rax+24h]
0x1400a5aa7  test    cl, 0E0h
0x1400a5aaa  jz      short loc_1400A5AD8
0x1400a5aac  mov     rax, [rbp+320h+var_14C]
0x1400a5ab3  lea     r8, [rbp+320h+var_288]; struct ERECTL *
0x1400a5aba  mov     [rbp+320h+var_288], rax
0x1400a5ac1  lea     rcx, [rbp+320h+var_300]; this
0x1400a5ac5  mov     rax, [rbp+320h+var_144]
0x1400a5acc  mov     [rbp+320h+var_280], rax
0x1400a5ad3  call    ?vAccumulateTight@XDCOBJ@@QEAAXPEAVECLIPOBJ@@AEAVERECTL@@@Z; XDCOBJ::vAccumulateTight(ECLIPOBJ *,ERECTL &)
0x1400a5ad8  cmp     [rbp+320h+var_378], r13d
0x1400a5adc  jnz     loc_1400A6C30
0x1400a5ae2  mov     eax, [r14+90h]
0x1400a5ae9  mov     r15d, [rbp+320h+var_338]
0x1400a5aed  test    al, 2
0x1400a5aef  jnz     loc_1400A6223
0x1400a5af5  lea     r10, EngStretchBlt
0x1400a5afc  test    r12b, bl
0x1400a5aff  jnz     loc_1400A6C50
0x1400a5b05  test    bl, 2
0x1400a5b08  jnz     loc_1400A6C6D
0x1400a5b0e  add     [r14+5Ch], r12d
  ... truncated ...
```
