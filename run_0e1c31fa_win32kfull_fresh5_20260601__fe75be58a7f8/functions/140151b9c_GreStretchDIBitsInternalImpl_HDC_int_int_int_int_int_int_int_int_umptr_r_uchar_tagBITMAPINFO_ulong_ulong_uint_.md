# GreStretchDIBitsInternalImpl(HDC__ *,int,int,int,int,int,int,int,int,umptr_r<uchar> &,tagBITMAPINFO *,ulong,ulong,uint,void *)

- ea: `0x140151b9c`
- end: `0x140152f17`
- name: `?GreStretchDIBitsInternalImpl@@YAHPEAUHDC__@@HHHHHHHHAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@KKIPEAX@Z`
- size: `4987`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int, int, int, int, int, __int64, __int64, int, unsigned int, int, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x1401519a0`

## callees

- `0x14005fb0c`
- `0x14006052c`
- `0x140062148`
- `0x140063ee0`
- `0x140064ba0`
- `0x140069888`
- `0x14006ba00`
- `0x14006c84c`
- `0x14006d5e4`
- `0x14006ec10`
- `0x14007a824`
- `0x14007aed0`
- `0x14007eef8`
- `0x14007f010`
- `0x140080590`
- `0x140091e34`
- `0x1400f61f0`
- `0x140137980`
- `0x140151b9c`
- `0x140153ac4`
- `0x140155c24`
- `0x140155e34`
- `0x140155f3c`
- `0x1401562a4`
- `0x1401683b8`
- `0x140183ad8`
- `0x14019b754`
- `0x1401ad764`
- `0x1401b1e94`
- `0x1401f96f8`
- `0x140235334`
- `0x140249ccc`
- `0x1402594cc`
- `0x140303af4`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140151c32`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140151c32`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1401526e4`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140152c8b`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1401526e4`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140152c8b`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14015261e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140152666`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1401526fd`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14015261e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140152666`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1401526fd`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140152d00`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140152d00`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140152ec8`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140152ec8`
- `win32kbase!EngSetLastError` at `0x140151f43`
- `win32kbase!EngSetLastError` at `0x140151f71`
- `win32kbase!EngSetLastError` at `0x140152254`
- `win32kbase!EngSetLastError` at `0x1401522e0`
- `win32kbase!EngSetLastError` at `0x140152303`
- `win32kbase!EngSetLastError` at `0x140152349`
- `win32kbase!EngSetLastError` at `0x14015236a`
- `win32kbase!EngSetLastError` at `0x1401523d4`
- `win32kbase!EngSetLastError` at `0x140151f43`
- `win32kbase!EngSetLastError` at `0x140151f71`
- `win32kbase!EngSetLastError` at `0x140152254`
- `win32kbase!EngSetLastError` at `0x1401522e0`
- `win32kbase!EngSetLastError` at `0x140152303`
- `win32kbase!EngSetLastError` at `0x140152349`
- `win32kbase!EngSetLastError` at `0x14015236a`
- `win32kbase!EngSetLastError` at `0x1401523d4`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140151d0a`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14015242b`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140151d0a`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14015242b`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140151e62`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140152560`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140151e62`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140152560`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x140152ca7`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x140152ca7`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140152525`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140152837`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140152525`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140152837`
- `win32kbase!GrepDeleteDC` at `0x140152e79`
- `win32kbase!GrepDeleteDC` at `0x140152ea6`
- `win32kbase!GrepDeleteDC` at `0x140152e79`
- `win32kbase!GrepDeleteDC` at `0x140152ea6`
- `win32kbase!?bIsPalDefault@XEPALOBJ@@QEBAHXZ` at `0x140152749`
- `win32kbase!?bIsPalDefault@XEPALOBJ@@QEBAHXZ` at `0x140152749`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x140152ce7`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x140152ce7`
- `win32kbase!GreSelectBitmap` at `0x140152de7`
- `win32kbase!GreSelectBitmap` at `0x140152de7`
- `win32kbase!GreDeleteObject` at `0x140152e88`
- `win32kbase!GreDeleteObject` at `0x140152eb5`
- `win32kbase!GreDeleteObject` at `0x140152e88`
- `win32kbase!GreDeleteObject` at `0x140152eb5`

## pseudocode

```c
__int64 __fastcall GreStretchDIBitsInternalImpl(
        Gre::Base *a1,
        LONG a2,
        int a3,
        int a4,
        int a5,
        int a6,
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
  int v18; // eax
  unsigned int v19; // edx
  int v20; // ebx
  unsigned int v21; // edx
  __int64 v22; // r8
  unsigned __int8 v23; // r9
  unsigned int v24; // edx
  __int64 v25; // r11
  int v26; // r13d
  int v27; // edi
  int v28; // ecx
  BOOL v29; // ebx
  int v30; // r15d
  __int64 v31; // rcx
  unsigned int v32; // r14d
  int v33; // ecx
  int v34; // r8d
  __int64 v35; // r10
  unsigned int v36; // r11d
  __int64 v37; // r13
  unsigned int v38; // r12d
  unsigned int v39; // edi
  int v40; // eax
  unsigned int v41; // r9d
  unsigned int v42; // eax
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rcx
  unsigned int v45; // ecx
  DC *v46; // r9
  int v47; // esi
  unsigned int v48; // eax
  unsigned int v49; // edx
  unsigned __int64 v50; // rcx
  unsigned int v51; // r13d
  __int64 v52; // rax
  unsigned int v53; // edx
  __int64 v54; // r10
  unsigned int v55; // edx
  unsigned __int64 v56; // rcx
  unsigned int v57; // eax
  unsigned int v58; // eax
  LONG v59; // r8d
  char v60; // cl
  int v61; // edx
  int v62; // edx
  int v63; // eax
  void *v64; // r8
  bool v65; // zf
  char *XlateObject; // rsi
  struct SURFACE *v67; // r13
  __int64 v68; // rbx
  unsigned int v69; // r8d
  int v70; // edi
  unsigned int v71; // ebx
  __int64 v72; // r8
  __int64 v73; // rdx
  int v74; // edx
  int v75; // r9d
  int v76; // eax
  unsigned int v77; // edi
  int v78; // eax
  char v79; // bl
  int v80; // ecx
  int v81; // r8d
  struct REGION *v82; // rax
  struct ECLIPOBJ *v83; // rdx
  int v84; // r14d
  __int64 v85; // rax
  BOOL (__stdcall *v86)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, COLORADJUSTMENT *, POINTL *, RECTL *, RECTL *, POINTL *, ULONG); // r10
  LONG v87; // ecx
  int v88; // ecx
  char *v89; // r9
  unsigned int v90; // ebx
  int v91; // r15d
  int v92; // ebx
  HDC CompatibleDC; // rax
  int v94; // edi
  HDC v95; // r14
  __int64 CompatibleBitmapWithDIBits; // rdi
  int v97; // ebx
  unsigned int v98; // [rsp+80h] [rbp-80h]
  int v99; // [rsp+84h] [rbp-7Ch]
  unsigned int v100; // [rsp+88h] [rbp-78h]
  char v101; // [rsp+8Ch] [rbp-74h]
  unsigned int v102; // [rsp+90h] [rbp-70h]
  unsigned int v103; // [rsp+94h] [rbp-6Ch]
  POINTL pptlSrc; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v105; // [rsp+A0h] [rbp-60h]
  unsigned int v106; // [rsp+A4h] [rbp-5Ch]
  unsigned int v107; // [rsp+A8h] [rbp-58h]
  unsigned int v108[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v109; // [rsp+C0h] [rbp-40h]
  unsigned int v110; // [rsp+D0h] [rbp-30h]
  unsigned int v111; // [rsp+D4h] [rbp-2Ch]
  unsigned int v112; // [rsp+D8h] [rbp-28h]
  int v113; // [rsp+DCh] [rbp-24h]
  int v114; // [rsp+E0h] [rbp-20h]
  __int64 v115; // [rsp+E8h] [rbp-18h]
  int v116; // [rsp+F0h] [rbp-10h]
  int v117; // [rsp+F8h] [rbp-8h] BYREF
  struct tagRGBQUAD *v118; // [rsp+100h] [rbp+0h]
  __int64 v119; // [rsp+108h] [rbp+8h] BYREF
  int v120; // [rsp+110h] [rbp+10h]
  __int64 v121; // [rsp+118h] [rbp+18h] BYREF
  char v122; // [rsp+120h] [rbp+20h]
  int v123; // [rsp+124h] [rbp+24h]
  int v124; // [rsp+128h] [rbp+28h]
  __int64 v125; // [rsp+130h] [rbp+30h] BYREF
  struct Gre::Base::SESSION_GLOBALS *v126[3]; // [rsp+138h] [rbp+38h] BYREF
  DC *v127[14]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v128; // [rsp+1C0h] [rbp+C0h] BYREF
  char v129; // [rsp+1C8h] [rbp+C8h]
  int v130; // [rsp+1CCh] [rbp+CCh]
  int v131; // [rsp+1D0h] [rbp+D0h]
  _OWORD v132[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 *v133; // [rsp+1F8h] [rbp+F8h]
  _BYTE v134[176]; // [rsp+200h] [rbp+100h] BYREF
  LONG left; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v136; // [rsp+2B4h] [rbp+1B4h]
  int v137; // [rsp+2B8h] [rbp+1B8h]
  int v138; // [rsp+2BCh] [rbp+1BCh]
  __int64 v139; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v140; // [rsp+2C8h] [rbp+1C8h]
  int v141; // [rsp+2CCh] [rbp+1CCh]
  RECTL prclDest; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v143[4]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v144[21]; // [rsp+2E4h] [rbp+1E4h] BYREF
  _BYTE v145[96]; // [rsp+390h] [rbp+290h] BYREF

  pptlSrc = (POINTL)a10;
  v113 = a5;
  v115 = a15;
  v114 = a4;
  v117 = a3;
  prclDest.left = a2;
  v16 = *((_BYTE *)gajRop3 + BYTE2(a13));
  v100 = a12;
  v126[0] = Gre::Base::Globals(a1);
  APIDCOBJ::APIDCOBJ((APIDCOBJ *)v127, (HDC)a1, v126[0]);
  if ( !v127[0] )
  {
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v127);
    return 0;
  }
  if ( (v16 & 0xD4) == 0 )
  {
    v18 = GrepPatBlt((struct XDCOBJ *)v127, prclDest.left, v117, v114, v113, a13);
LABEL_253:
    v98 = v18;
    goto LABEL_254;
  }
  v18 = 0;
  v98 = 0;
  if ( !a11 )
    goto LABEL_253;
  if ( !**(_QWORD **)&pptlSrc )
    goto LABEL_253;
  if ( a12 > 2 )
    goto LABEL_253;
  if ( a14 < 0xC )
    goto LABEL_253;
  v19 = *(_DWORD *)a11;
  v106 = v19;
  if ( a14 < v19 || v19 < 0x28 || *(int *)(a11 + 4) <= 0 || !*(_DWORD *)(a11 + 8) )
    goto LABEL_253;
  v20 = *(unsigned __int8 *)(*((_QWORD *)v127[0] + 122) + 215LL);
  DC::QuickInitXform(v127[0], &v125, 516);
  v21 = *(_DWORD *)(a11 + 16);
  v22 = v125;
  if ( v21 - 4 > 1 )
  {
    v25 = v115;
    v24 = a12;
    goto LABEL_21;
  }
  if ( (unsigned int)XDCOBJ::bSupportsPassthroughImage((XDCOBJ *)v127, v21) )
  {
    if ( BYTE2(a13) == 204 && (v23 & *(_BYTE *)(v22 + 32)) != 0 )
    {
      v24 = a12;
      if ( !a12 )
      {
        v25 = v115;
        if ( !v115 )
        {
LABEL_21:
          v26 = a9;
          v116 = v20;
          if ( v114 == a8 && v113 == a9 && a9 > 0 )
          {
            v27 = a7;
            if ( a8 > 0 && !(a7 | a6) && BYTE2(a13) == 204 && v20 != 4 && (*(_DWORD *)(v22 + 32) & 2) != 0 )
            {
              v28 = -*(_DWORD *)(a11 + 8);
              if ( *(int *)(a11 + 8) > 0 )
                v28 = *(_DWORD *)(a11 + 8);
              if ( a9 >= v28 )
                v26 = v28;
              v18 = GrepSetDIBitsToDeviceInternalImpl(
                      (unsigned int)v127,
                      prclDest.left,
                      v117,
                      v114,
                      v113,
                      a6,
                      a7,
                      a7,
                      v26,
                      *(_QWORD *)&pptlSrc,
                      a11,
                      v24,
                      a14,
                      1,
                      v25);
              goto LABEL_253;
            }
          }
          else
          {
            v27 = a7;
          }
          v29 = 0;
          v30 = 1;
          if ( v24 == 1 )
          {
            DEVLOCKOBJ::DEVLOCKOBJ(v143, 2);
            if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v143, (struct XDCOBJ *)v127, 0) )
            {
              v31 = *((_QWORD *)v127[0] + 62);
              if ( v31 )
                v29 = *(_DWORD *)(v31 + 96) == 1;
            }
            DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v143);
            v22 = v125;
            v24 = a12;
          }
          if ( BYTE2(a13) != 204 || (*(_BYTE *)(v22 + 32) & 1) == 0 || (v32 = 0, v29) )
          {
            v91 = *(_DWORD *)(a11 + 8);
            if ( v91 <= 0 )
              v92 = v27;
            else
              v92 = v91 - v27 - a9;
            OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v134, (struct XDCOBJ *)v127);
            CompatibleDC = GrepCreateCompatibleDC((struct OPTAPIDCOBJ *)v134);
            v94 = *(_DWORD *)(a11 + 16);
            v95 = CompatibleDC;
            ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v145);
            if ( v94 == 1 || v94 == 2 )
            {
              CompatibleBitmapWithDIBits = GrepCreateCompatibleBitmapWithDIBits(
                                             (struct OPTAPIDCOBJ *)v134,
                                             *(_DWORD *)(a11 + 4),
                                             *(_DWORD *)(a11 + 8),
                                             *(_QWORD *)&pptlSrc,
                                             a11,
                                             a12,
                                             a14,
                                             v115);
            }
            else
            {
              GrepCreateDIBitmap((SURFREF *)v132, (OPTAPIDCOBJ *)v134, a11, a12, a14, 0, 0, 0, 0, 0, 0);
              if ( v133 )
                CompatibleBitmapWithDIBits = *v133;
              else
                CompatibleBitmapWithDIBits = 0;
              SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v132);
            }
            if ( v95 && CompatibleBitmapWithDIBits )
            {
              GreSelectBitmap(v95, CompatibleBitmapWithDIBits);
              OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v143, v95);
              v97 = GrepStretchBlt(
                      (struct XDCOBJ *)v127,
                      prclDest.left,
                      v117,
                      v114,
                      v113,
                      (struct OPTAPIDCOBJ *)v143,
                      a6,
                      v92,
                      a8,
                      a9,
                      a13,
                      0xFFFFFFu,
                      1u);
              OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v143);
              GrepDeleteDC(v95, 0x400000);
              GreDeleteObject(CompatibleBitmapWithDIBits);
              if ( v97 )
                v98 = v91;
            }
            else
            {
              GrepDeleteDC(v95, 0x400000);
              GreDeleteObject(CompatibleBitmapWithDIBits);
            }
            ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v145);
            OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v134);
            goto LABEL_254;
          }
          v33 = *(_DWORD *)(a11 + 8);
          v34 = *(_DWORD *)(a11 + 16);
          v35 = *(unsigned int *)(a11 + 4);
          v36 = *(_DWORD *)(a11 + 32);
          v37 = *(unsigned __int16 *)(a11 + 14);
          v38 = 0;
          v109 = 0;
          v118 = (struct tagRGBQUAD *)(a11 + v106);
          v39 = 0;
          *(_OWORD *)v108 = 0;
          v99 = v34;
          v40 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
          v105 = v35;
          v107 = v36;
          if ( v33 < 0 )
            v40 = 1;
          v112 = 0;
          v41 = -v33;
          DWORD2(v109) = v40;
          v111 = 0;
          if ( v33 > 0 )
            v41 = v33;
          v110 = 0;
          v102 = v41;
          if ( v34 == 3 )
          {
            if ( a14 < 0x34 )
            {
              EngSetLastError(0x57u);
              v30 = 0;
LABEL_61:
              v46 = v127[0];
              v47 = 0;
LABEL_133:
              if ( !v30 )
              {
LABEL_235:
                v18 = v98;
                goto LABEL_253;
              }
              LODWORD(v35) = v105;
              v36 = v107;
              v51 = v102;
              goto LABEL_84;
            }
            v42 = 0;
            if ( v24 != 1 )
              v42 = v24;
            v100 = v42;
            if ( (_WORD)v37 == 16 )
            {
              v108[0] = 4;
            }
            else if ( (_DWORD)v37 == 32 )
            {
              v108[0] = 6;
            }
            else
            {
              EngSetLastError(0x57u);
              LODWORD(v35) = v105;
              v30 = 0;
              v41 = v102;
            }
            v43 = v37 * (unsigned int)v35;
            if ( v43 <= 0xFFFFFFFF )
            {
              v44 = (unsigned int)(v43 + 31);
              if ( (unsigned int)v44 >= (unsigned int)v43
                && (int)ULongLongToULong(v41 * ((v44 >> 3) & 0x1FFFFFFC), &v108[3]) >= 0 )
              {
                v39 = 512;
                v38 = 2;
                v112 = *(_DWORD *)(a11 + 40);
                v45 = *(_DWORD *)(a11 + 44);
                v118 = (struct tagRGBQUAD *)(a11 + 40);
                v110 = *(_DWORD *)(a11 + 48);
                v111 = v45;
                goto LABEL_61;
              }
            }
LABEL_110:
            EngSetLastError(0x216u);
            v98 = 0;
            goto LABEL_254;
          }
          if ( !v34 )
          {
            switch ( (_DWORD)v37 )
            {
              case 1:
                v108[0] = 1;
                v32 = 2;
                break;
              case 4:
                v108[0] = 2;
                v32 = 16;
                break;
              case 8:
                v108[0] = 3;
                v32 = 256;
                break;
              default:
                v48 = 0;
                if ( v24 != 1 )
                  v48 = v24;
                v100 = v48;
                if ( (_WORD)v37 == 16 )
                {
                  v108[0] = 4;
                  v38 = 2;
                  v112 = 31744;
                  v111 = 992;
                  v110 = 31;
                }
                else
                {
                  if ( (_WORD)v37 != 24 )
                  {
                    if ( (_DWORD)v37 == 32 )
                    {
                      v108[0] = 6;
                      v38 = 8;
                      v39 = 512;
                      goto LABEL_79;
                    }
LABEL_129:
                    EngSetLastError(0x57u);
                    v18 = 0;
                    goto LABEL_253;
                  }
                  v108[0] = 5;
                  v38 = 8;
                }
                v39 = 512;
                v100 = v48;
LABEL_79:
                v49 = v37 * v35;
                if ( (unsigned __int64)(v37 * v35) > 0xFFFFFFFF )
                  goto LABEL_110;
                v50 = v49 + 31;
                if ( (unsigned int)v50 < v49 || (int)ULongLongToULong(v41 * ((v50 >> 3) & 0x1FFFFFFC), &v108[3]) < 0 )
                  goto LABEL_110;
                v46 = v127[0];
                v51 = v102;
LABEL_83:
                v47 = 0;
LABEL_84:
                v34 = v99;
                goto LABEL_85;
            }
            v38 = 1;
            v39 = 1024;
            goto LABEL_79;
          }
          v46 = v127[0];
          if ( v34 != 10 )
          {
            if ( v34 != 2 )
            {
              if ( v34 != 12 )
              {
                v46 = v127[0];
                if ( v34 == 1 )
                  goto LABEL_123;
                if ( v34 != 11 )
                {
                  if ( v34 == 4 )
                  {
                    v108[0] = 9;
                  }
                  else
                  {
                    if ( v34 != 5 )
                      goto LABEL_129;
                    v108[0] = 10;
                  }
                  v39 = 512;
                  v46 = v127[0];
                  v47 = 0;
                  v51 = v102;
                  v38 = 8;
                  v108[3] = *(_DWORD *)(a11 + 20);
LABEL_85:
                  v52 = v115;
                  if ( !v115 )
                  {
                    v52 = *(_QWORD *)(*((_QWORD *)v46 + 122) + 248LL);
                    v115 = v52;
                  }
                  v105 = *((_DWORD *)v46 + 30);
                  if ( (v105 & 0x10000000) != 0 && (!v52 || (unsigned int)(v34 - 10) > 2) )
                    v105 = v105 & 0xFFFFFFF | 0x20000000;
                  v108[1] = v35;
                  v108[2] = v51;
                  if ( v36 )
                  {
                    v53 = v32;
                    if ( v36 <= v32 )
                      v53 = v36;
                    v107 = v53;
                  }
                  else
                  {
                    v107 = v32;
                  }
                  if ( *(_QWORD *)(*(_QWORD *)&pptlSrc + 8LL) - *(_QWORD *)(*(_QWORD *)&pptlSrc + 16LL) < (unsigned __int64)v108[3] )
                  {
                    EngSetLastError(0x57u);
                    goto LABEL_235;
                  }
                  v139 = *((_QWORD *)v46 + 6);
                  left = prclDest.left;
                  v137 = prclDest.left + v114;
                  v136 = v117;
                  v138 = v117 + v113;
                  DC::QuickInitXform(v46, &v117, 516);
                  if ( !DC::bXform(v127[0], (const struct EXFORMOBJ *)&v117, (struct ERECTL *)&left) )
                  {
                    v18 = 0;
                    goto LABEL_253;
                  }
                  if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&left) )
                  {
                    v18 = a9;
                    goto LABEL_253;
                  }
                  v59 = left;
                  v60 = 0;
                  v61 = v137;
                  v101 = 0;
                  if ( left > v137 )
                  {
                    left = v137;
                    v137 = v59;
                    v60 = 1;
                    if ( (*(_DWORD *)(*((_QWORD *)v127[0] + 122) + 108LL) & 1) == 0 )
                    {
                      left = v61 + 1;
                      v137 = v59 + 1;
                    }
                    v101 = 1;
                  }
                  v62 = v136;
                  if ( v136 > v138 )
                  {
                    v136 = v138 + 1;
                    v101 = v60 ^ 2;
                    v138 = v62 + 1;
                  }
                  v120 = 0;
                  v119 = 0;
                  if ( !v100 )
                    v30 = PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v119, v38, v32, 0, v112, v111, v110, v39, 1) != 0
                        ? v30
                        : 0;
                  DEVLOCKOBJ::DEVLOCKOBJ(v134, 2);
                  if ( !v30 || !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v134, (struct XDCOBJ *)v127, 0) )
                  {
LABEL_234:
                    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v134);
                    PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v119);
                    goto LABEL_235;
                  }
                  XDCOBJ::pSurfaceEff((XDCOBJ *)v127);
                  v63 = *(_DWORD *)(*((_QWORD *)v127[0] + 6) + 40LL) & 0x8000;
                  *(_QWORD *)&v109 = 0;
                  DWORD2(v109) |= 8 * v63;
                  v121 = 0;
                  v122 = 0;
                  v124 = (v47 ^ 1) + 2;
                  v123 = 0;
                  v64 = (void *)(*(_QWORD *)(*(_QWORD *)&pptlSrc + 16LL) + **(_QWORD **)&pptlSrc);
                  if ( v47 )
                  {
                    v128 = 0;
                    v129 = 0;
                    v132[0] = *(_OWORD *)v108;
                    v130 = 0;
                    v132[1] = v109;
                    v131 = 3;
                    if ( SURFMEM::bCreateDIB((SURFMEM *)&v128, (struct _DEVBITMAPINFO *)v132, v64, 0, 0, 0, 0, 0, 1, 0)
                      && (v108[0] = (v108[0] != 7) + 2,
                          SURFMEM::bCreateDIB((SURFMEM *)&v121, (struct _DEVBITMAPINFO *)v108, 0, 0, 0, 0, 0, 0, 1, 0)) )
                    {
                      prclDest.right = v108[1];
                      prclDest.bottom = v108[2];
                      *(_QWORD *)&prclDest.left = 0;
                      pptlSrc = 0;
                      EngCopyBits(
                        (SURFOBJ *)((v121 + 24) & -(__int64)(v121 != 0)),
                        (SURFOBJ *)((v128 + 24) & -(__int64)(v128 != 0)),
                        0,
                        0,
                        &prclDest,
                        &pptlSrc);
                    }
                    else
                    {
                      v30 = 0;
                    }
                    SURFMEM::~SURFMEM((SURFMEM *)&v128);
                    v65 = v30 == 0;
                  }
                  else
                  {
                    v65 = SURFMEM::bCreateDIB((SURFMEM *)&v121, (struct _DEVBITMAPINFO *)v108, v64, 0, 0, 0, 0, 0, 1, 0) == 0;
                  }
                  if ( v65 )
                  {
LABEL_233:
                    SURFMEM::~SURFMEM((SURFMEM *)&v121);
                    goto LABEL_234;
                  }
                  v103 = a14 - v106;
                  XlateObject = 0;
                  v67 = XDCOBJ::pSurfaceEff((XDCOBJ *)v127);
                  pptlSrc = 0;
                  v106 = 0;
                  v68 = *((_QWORD *)v67 + 22);
                  *(_QWORD *)&prclDest.left = *((_QWORD *)v127[0] + 11);
                  if ( !XEPALOBJ::bIsPalDefault((XEPALOBJ *)&prclDest) )
                    *((_QWORD *)v67 + 28) = **(_QWORD **)&prclDest.left;
                  if ( v100 )
                  {
                    if ( v100 == 1 )
                    {
                      v71 = v107;
                      if ( v103 < 2 * (unsigned __int64)v107
                        || !(unsigned int)EXLATEOBJ::bMakeXlate(
                                            &pptlSrc,
                                            v118,
                                            *(_QWORD *)&prclDest.left,
                                            v67,
                                            v107,
                                            v32) )
                      {
                        goto LABEL_232;
                      }
                      XlateObject = (char *)pptlSrc;
                      if ( *((_DWORD *)v126[0] + 788) && (*(_DWORD *)(v139 + 40) & 1) != 0 )
                      {
                        if ( PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v119, v38, v32, 0, v112, v111, v110, v39, 1) )
                        {
                          v72 = *((_QWORD *)v67 + 22);
                          if ( !v72 )
                            v72 = *(_QWORD *)(v139 + 1792);
                          XEPALOBJ::vGetEntriesFrom(&v119, *(_QWORD *)&prclDest.left, v72, v118, v71);
                          v106 = 1;
                        }
                        else
                        {
                          v30 = 0;
                        }
                      }
                      v70 = v99;
                    }
                    else
                    {
                      v70 = v99;
                      if ( v100 != 2 )
                      {
LABEL_188:
                        if ( (*((_DWORD *)v127[0] + 9) & 0xE0) != 0 )
                          XDCOBJ::vAccumulate((XDCOBJ *)v127, (struct ERECTL *)&left);
                        if ( (unsigned int)XDCOBJ::bFullScreen((XDCOBJ *)v127) )
                        {
                          v98 = v102;
                        }
                        else if ( (v134[24] & 1) != 0 )
                        {
                          ERECTL::bOffsetAdd(
                            (ERECTL *)&left,
                            (const struct _POINTL *)(v73 + 8 * (*(_DWORD *)(v73 + 40) & 1LL) + 1016),
                            0);
                          v74 = a6;
                          LODWORD(v139) = a6;
                          if ( v70 == 4 && (BYTE8(v109) & 1) != 0 )
                          {
                            v75 = a7;
                            v76 = a9;
                            v77 = v102;
                          }
                          else
                          {
                            v77 = v102;
                            v76 = a9;
                            v75 = v102 - a7 - a9;
                          }
                          v78 = v75 + v76;
                          v79 = v101;
                          v80 = a6 + a8;
                          HIDWORD(v139) = v75;
                          v81 = v75;
                          v141 = v78;
                          v140 = a6 + a8;
                          if ( a6 > a6 + a8 )
                          {
                            v74 = v80 + 1;
                            v79 = v101 ^ 1;
                            v80 = a6 + 1;
                            LODWORD(v139) = v74;
                            v140 = a6 + 1;
                          }
                          if ( v75 > v78 )
                          {
                            v75 = v78 + 1;
                            v79 ^= 2u;
                            v78 = v81 + 1;
                            HIDWORD(v139) = v75;
                            v141 = v81 + 1;
                          }
                          if ( v80 > 0
                            && v78 > 0
                            && v74 < *(_DWORD *)(v121 + 56)
                            && v75 < *(_DWORD *)(v121 + 60)
                            && !(unsigned int)ERECTL::bEmpty((ERECTL *)&v139) )
                          {
                            v82 = XDCOBJ::prgnEffRao((XDCOBJ *)v127);
                            ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v143, v82, (struct ERECTL *)&left, 0);
                            if ( (unsigned int)ERECTL::bEmpty((ERECTL *)v144) )
                            {
                              v98 = v77;
                            }
                            else
                            {
                              if ( (*((_DWORD *)v127[0] + 9) & 0xE0) != 0 )
                              {
                                v126[0] = (struct Gre::Base::SESSION_GLOBALS *)v144[0];
                                v126[1] = (struct Gre::Base::SESSION_GLOBALS *)v144[1];
                                XDCOBJ::vAccumulateTight((XDCOBJ *)v127, v83, (struct ERECTL *)v126);
                              }
                              if ( v106 )
                              {
                                XEPALOBJ::vRefPalette((XEPALOBJ *)&v119);
                                *(_QWORD *)(v121 + 176) = v119;
                              }
                              v84 = v116;
                              if ( (*((_DWORD *)v67 + 40) & 2) != 0 )
                              {
                                v85 = *((_QWORD *)v67 + 6);
                                v86 = *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, COLORADJUSTMENT *, POINTL *, RECTL *, RECTL *, POINTL *, ULONG))(v85 + 2840);
                                if ( (*(_DWORD *)(v85 + 40) & 0x20000) == 0 )
                                {
                                  if ( v116 == 4 && (*((_BYTE *)v127[0] + 72) & 0x10) == 0 )
                                    v86 = EngStretchBlt;
                                  if ( (int)v139 < 0
                                    || v139 < 0
                                    || v140 > *(_DWORD *)(v121 + 56)
                                    || v141 > *(_DWORD *)(v121 + 60) )
                                  {
                                    v86 = EngStretchBlt;
                                  }
                                }
                              }
                              else
                              {
                                v86 = EngStretchBlt;
                              }
                              if ( (v79 & 1) != 0 )
                              {
                                v87 = left;
                                left = v137;
                                v137 = v87;
                              }
                              if ( (v79 & 2) != 0 )
                              {
                                v88 = v136;
                                v136 = v138;
                                v138 = v88;
                              }
                              ++*((_DWORD *)v67 + 23);
                              v89 = 0;
                              if ( *((__int16 *)v127[0] + 89) >= 0 )
                                v89 = (char *)v127[0] + 176;
                              v90 = 0;
                              if ( ((unsigned int (__fastcall *)(char *, __int64, _QWORD, _BYTE *, char *, char *, char *, LONG *, __int64 *, _QWORD, int))v86)(
                                     (char *)v67 + 24,
                                     (v121 + 24) & -(__int64)(v121 != 0),
                                     0,
                                     v143,
                                     XlateObject,
                                     v89,
                                     (char *)v127[0] + 1192,
                                     &left,
                                     &v139,
                                     0,
                                     v84) )
                              {
                                v90 = v77;
                              }
                              v98 = v90;
                            }
                          }
                        }
                        goto LABEL_232;
                      }
                      if ( *((_DWORD *)v67 + 24) != v108[0] )
                        v30 = 0;
                      XlateObject = (char *)v126[0] + 4664;
                    }
                  }
                  else if ( v107 )
                  {
                    if ( v103 < 4 * v107 )
                      goto LABEL_232;
                    v70 = v99;
                    if ( (unsigned int)(v99 - 10) <= 2 )
                      XEPALOBJ::vCopy_cmykquad((XEPALOBJ *)&v119, (const unsigned int *)&v118->rgbBlue, v69, v107);
                    else
                      XEPALOBJ::vCopy_rgbquad((XEPALOBJ *)&v119, v118, 0, v107);
                    pptlSrc = (POINTL)CreateXlateObject(
                                        v115,
                                        v105,
                                        v119,
                                        v68,
                                        *(_QWORD *)&prclDest.left,
                                        *(_QWORD *)&prclDest.left,
                                        0,
                                        0,
                                        0xFFFFFF,
                                        0);
                    XlateObject = (char *)pptlSrc;
                    if ( !*(_QWORD *)&pptlSrc )
                      v30 = 0;
                  }
                  else
                  {
                    v70 = v99;
                    XlateObject = (char *)CreateXlateObject(
                                            v115,
                                            v105,
                                            v119,
                                            v68,
                                            *(_QWORD *)&prclDest.left,
                                            *(_QWORD *)&prclDest.left,
                                            0,
                                            0,
                                            0xFFFFFF,
                                            0);
                    pptlSrc = (POINTL)XlateObject;
                    if ( !XlateObject )
                    {
                      v30 = 0;
                      XlateObject = 0;
                    }
                  }
                  if ( v30 )
                    goto LABEL_188;
LABEL_232:
                  EXLATEOBJ::vAltUnlock((EXLATEOBJ *)&pptlSrc);
                  goto LABEL_233;
                }
                if ( v127[0] && (unsigned int)DC::bIsCMYKColor(v127[0]) )
                {
LABEL_123:
                  if ( (_WORD)v37 != 8 )
                  {
                    EngSetLastError(0x57u);
                    v46 = v127[0];
                    v30 = 0;
                  }
                  v57 = *(_DWORD *)(a11 + 20);
                  v39 = 1024;
                  v108[0] = 8;
                  v32 = 256;
                  v38 = 1;
                  v108[3] = v57;
                }
                else
                {
                  EngSetLastError(0x57u);
                  v46 = v127[0];
                  v30 = 0;
                }
                v47 = v38;
                goto LABEL_133;
              }
              if ( !v127[0] || !(unsigned int)DC::bIsCMYKColor(v127[0]) )
                goto LABEL_129;
            }
            if ( (_WORD)v37 != 4 )
            {
              EngSetLastError(0x57u);
              v46 = v127[0];
              v30 = 0;
            }
            v58 = *(_DWORD *)(a11 + 20);
            v108[0] = 7;
            v38 = 1;
            v39 = 1024;
            v108[3] = v58;
            v47 = 1;
            v32 = 16;
            goto LABEL_133;
          }
          if ( !v127[0] || !(unsigned int)DC::bIsCMYKColor(v127[0]) )
            goto LABEL_129;
          switch ( (_DWORD)v37 )
          {
            case 1:
              v108[0] = 1;
              v32 = 2;
              break;
            case 4:
              v108[0] = 2;
              v32 = 16;
              break;
            case 8:
              v108[0] = 3;
              v32 = 256;
              break;
            case 0x20:
              v108[0] = 6;
              v38 = 16;
              v39 = 512;
LABEL_107:
              v55 = v37 * v54;
              if ( (unsigned __int64)(v37 * v54) > 0xFFFFFFFF )
                goto LABEL_110;
              v56 = v55 + 31;
              if ( (unsigned int)v56 < v55 )
                goto LABEL_110;
              v51 = v102;
              if ( (int)ULongLongToULong(v102 * ((v56 >> 3) & 0x1FFFFFFC), &v108[3]) < 0 )
                goto LABEL_110;
              goto LABEL_83;
            default:
              goto LABEL_129;
          }
          v38 = 1;
          v39 = 1024;
          goto LABEL_107;
        }
      }
    }
  }
  v98 = 0;
LABEL_254:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v127);
  return v98;
}

```

## disassembly

```asm
0x140151b9c  push    rbp
0x140151b9e  push    rbx
0x140151b9f  push    rsi
0x140151ba0  push    rdi
0x140151ba1  push    r12
0x140151ba3  push    r13
0x140151ba5  push    r14
0x140151ba7  push    r15
0x140151ba9  lea     rbp, [rsp-308h]
0x140151bb1  sub     rsp, 408h
0x140151bb8  mov     rax, cs:__security_cookie
0x140151bbf  xor     rax, rsp
0x140151bc2  mov     [rbp+340h+var_50], rax
0x140151bc9  mov     rax, [rbp+340h+arg_48]
0x140151bd0  lea     rdi, gajRop3
0x140151bd7  mov     r12d, [rbp+340h+arg_60]
0x140151bde  mov     rbx, rcx
0x140151be1  mov     r13d, [rbp+340h+arg_58]
0x140151be8  mov     r15d, [rbp+340h+arg_68]
0x140151bef  mov     rsi, [rbp+340h+arg_50]
0x140151bf6  mov     qword ptr [rbp+340h+var_3A8.x], rax
0x140151bfa  mov     eax, [rbp+340h+arg_20]
0x140151c00  mov     [rbp+340h+var_364], eax
0x140151c03  mov     rax, [rbp+340h+arg_70]
0x140151c0a  mov     [rbp+340h+var_358], rax
0x140151c0e  mov     eax, r12d
0x140151c11  shr     eax, 10h
0x140151c14  movzx   r14d, al
0x140151c18  mov     [rbp+340h+var_360], r9d
0x140151c1c  mov     [rbp+340h+var_348], r8d
0x140151c20  mov     [rbp+340h+var_170.left], edx
0x140151c26  mov     dil, [r14+rdi]
0x140151c2a  mov     [rbp+340h+var_3B8], r13d
0x140151c2e  mov     [rbp+340h+var_3AC], r15d
0x140151c32  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140151c39  nop     dword ptr [rax+rax+00h]
0x140151c3e  mov     rdx, rbx; HDC
0x140151c41  lea     rcx, [rbp+340h+var_2F0]; this
0x140151c45  mov     r8, rax; struct Gre::Base::SESSION_GLOBALS *
0x140151c48  mov     [rbp+340h+var_308], rax
0x140151c4c  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *,Gre::Base::SESSION_GLOBALS &)
0x140151c51  mov     rcx, [rbp+340h+var_2F0]
0x140151c55  test    rcx, rcx
0x140151c58  jnz     short loc_140151C6A
0x140151c5a  lea     rcx, [rbp+340h+var_2F0]; this
0x140151c5e  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140151c63  xor     eax, eax
0x140151c65  jmp     loc_140152EF3
0x140151c6a  test    dil, 0D4h
0x140151c6e  jnz     short loc_140151C98
0x140151c70  mov     eax, [rbp+340h+var_364]
0x140151c73  lea     rcx, [rbp+340h+var_2F0]; struct XDCOBJ *
0x140151c77  mov     r9d, [rbp+340h+var_360]; int
0x140151c7b  mov     r8d, [rbp+340h+var_348]; int
0x140151c7f  mov     edx, [rbp+340h+var_170.left]; int
0x140151c85  mov     dword ptr [rsp+440h+pptlSrc], r12d; unsigned int
0x140151c8a  mov     dword ptr [rsp+440h+prclDest], eax; int
0x140151c8e  call    ?GrepPatBlt@@YAHAEAVXDCOBJ@@HHHHK@Z; GrepPatBlt(XDCOBJ &,int,int,int,int,ulong)
0x140151c93  jmp     loc_140152EE4
0x140151c98  xor     edi, edi
0x140151c9a  mov     eax, edi
0x140151c9c  mov     [rbp+340h+var_3C0], eax
0x140151c9f  test    rsi, rsi
0x140151ca2  jz      loc_140152EE4
0x140151ca8  mov     rdx, qword ptr [rbp+340h+var_3A8.x]
0x140151cac  cmp     [rdx], rdi
0x140151caf  jz      loc_140152EE4
0x140151cb5  cmp     r13d, 2
0x140151cb9  ja      loc_140152EE4
0x140151cbf  cmp     r15d, 0Ch
0x140151cc3  jb      loc_140152EE4
0x140151cc9  mov     edx, [rsi]
0x140151ccb  mov     [rbp+340h+var_39C], edx
0x140151cce  cmp     r15d, edx
0x140151cd1  jb      loc_140152EE4
0x140151cd7  cmp     edx, 28h ; '('
0x140151cda  jb      loc_140152EE4
0x140151ce0  cmp     [rsi+4], edi
0x140151ce3  jle     loc_140152EE4
0x140151ce9  cmp     [rsi+8], edi
0x140151cec  jz      loc_140152EE4
0x140151cf2  mov     rax, [rcx+3D0h]
0x140151cf9  lea     rdx, [rbp+340h+var_310]
0x140151cfd  mov     r8d, 204h
0x140151d03  movzx   ebx, byte ptr [rax+0D7h]
0x140151d0a  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140151d11  nop     dword ptr [rax+rax+00h]
0x140151d16  mov     edx, [rsi+10h]; unsigned int
0x140151d19  lea     r9d, [rdi+1]
0x140151d1d  mov     r8, [rbp+340h+var_310]
0x140151d21  lea     eax, [rdx-4]
0x140151d24  cmp     eax, r9d
0x140151d27  ja      short loc_140151D5E
0x140151d29  lea     rcx, [rbp+340h+var_2F0]; this
0x140151d2d  call    ?bSupportsPassthroughImage@XDCOBJ@@QEAAHK@Z; XDCOBJ::bSupportsPassthroughImage(ulong)
0x140151d32  test    eax, eax
0x140151d34  jz      short loc_140151D56
0x140151d36  cmp     r14d, 0CCh
0x140151d3d  jnz     short loc_140151D56
0x140151d3f  test    [r8+20h], r9b
0x140151d43  jz      short loc_140151D56
0x140151d45  mov     edx, r13d
0x140151d48  test    r13d, r13d
0x140151d4b  jnz     short loc_140151D56
0x140151d4d  mov     r11, [rbp+340h+var_358]
0x140151d51  test    r11, r11
0x140151d54  jz      short loc_140151D65
0x140151d56  mov     [rbp+340h+var_3C0], edi
0x140151d59  jmp     loc_140152EE7
0x140151d5e  mov     r11, [rbp+340h+var_358]
0x140151d62  mov     edx, r13d
0x140151d65  mov     r10d, [rbp+340h+var_360]
0x140151d69  mov     ecx, ebx
0x140151d6b  mov     eax, [rbp+340h+arg_38]
0x140151d71  mov     r13d, [rbp+340h+arg_40]
0x140151d78  mov     [rbp+340h+var_350], ebx
0x140151d7b  cmp     r10d, eax
0x140151d7e  jnz     loc_140151E34
0x140151d84  mov     r9d, [rbp+340h+var_364]
0x140151d88  cmp     r9d, r13d
0x140151d8b  jnz     loc_140151E34
0x140151d91  test    r13d, r13d
0x140151d94  jle     loc_140151E34
0x140151d9a  mov     edi, [rbp+340h+arg_30]
0x140151da0  test    eax, eax
0x140151da2  jle     loc_140151E3A
0x140151da8  mov     ebx, [rbp+340h+arg_28]
0x140151dae  mov     eax, ebx
0x140151db0  or      eax, edi
0x140151db2  jnz     loc_140151E3A
0x140151db8  cmp     r14d, 0CCh
0x140151dbf  jnz     short loc_140151E3A
0x140151dc1  cmp     ecx, 4
0x140151dc4  jz      short loc_140151E3A
0x140151dc6  mov     eax, [r8+20h]
0x140151dca  test    al, 2
0x140151dcc  jz      short loc_140151E3A
0x140151dce  mov     eax, [rsi+8]
0x140151dd1  mov     ecx, eax
0x140151dd3  mov     r8d, [rbp+340h+var_348]
0x140151dd7  neg     ecx
0x140151dd9  mov     [rsp+440h+var_3D0], r11
0x140151dde  mov     [rsp+440h+var_3D8], 1
0x140151de6  cmovs   ecx, eax
0x140151de9  mov     rax, qword ptr [rbp+340h+var_3A8.x]
0x140151ded  cmp     r13d, ecx
0x140151df0  mov     [rsp+440h+var_3E0], r15d
0x140151df5  mov     [rsp+440h+var_3E8], edx
0x140151df9  cmovge  r13d, ecx
0x140151dfd  mov     edx, [rbp+340h+var_170.left]
0x140151e03  lea     rcx, [rbp+340h+var_2F0]
0x140151e07  mov     qword ptr [rsp+440h+var_3F0], rsi
0x140151e0c  mov     [rsp+440h+var_3F8], rax
0x140151e11  mov     dword ptr [rsp+440h+var_400], r13d
0x140151e16  mov     dword ptr [rsp+440h+var_408], edi
0x140151e1a  mov     [rsp+440h+var_410], edi
0x140151e1e  mov     dword ptr [rsp+440h+pptlSrc], ebx
0x140151e22  mov     dword ptr [rsp+440h+prclDest], r9d
0x140151e27  mov     r9d, r10d
0x140151e2a  call    ?GrepSetDIBitsToDeviceInternalImpl@@YAHAEAVXDCOBJ@@HHKKHHKKAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@KIHPEAX@Z; GrepSetDIBitsToDeviceInternalImpl(XDCOBJ &,int,int,ulong,ulong,int,int,ulong,ulong,umptr_r<uchar> &,tagBITMAPINFO *,ulong,uint,int,void *)
0x140151e2f  jmp     loc_140152EE4
0x140151e34  mov     edi, [rbp+340h+arg_30]
0x140151e3a  xor     ebx, ebx
0x140151e3c  lea     r15d, [rbx+1]
0x140151e40  cmp     edx, r15d
0x140151e43  jnz     short loc_140151E9D
0x140151e45  lea     edx, [rbx+2]
0x140151e48  lea     rcx, [rbp+340h+var_160]
0x140151e4f  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x140151e54  xor     r8d, r8d
0x140151e57  lea     rdx, [rbp+340h+var_2F0]
0x140151e5b  lea     rcx, [rbp+340h+var_160]
0x140151e62  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140151e69  nop     dword ptr [rax+rax+00h]
0x140151e6e  test    eax, eax
0x140151e70  jz      short loc_140151E8A
0x140151e72  mov     rax, [rbp+340h+var_2F0]
0x140151e76  mov     rcx, [rax+1F0h]
0x140151e7d  test    rcx, rcx
0x140151e80  jz      short loc_140151E8A
0x140151e82  cmp     [rcx+60h], r15d
0x140151e86  cmovz   ebx, r15d
0x140151e8a  lea     rcx, [rbp+340h+var_160]; this
0x140151e91  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x140151e96  mov     r8, [rbp+340h+var_310]
0x140151e9a  mov     edx, [rbp+340h+var_3B8]
0x140151e9d  cmp     r14d, 0CCh
0x140151ea4  jnz     loc_140152CBB
0x140151eaa  test    [r8+20h], r15b
0x140151eae  jz      loc_140152CBB
0x140151eb4  xor     r14d, r14d
0x140151eb7  test    ebx, ebx
0x140151eb9  jnz     loc_140152CBB
0x140151ebf  mov     ecx, [rsi+8]
0x140151ec2  lea     ebx, [r14+57h]
0x140151ec6  mov     r8d, [rsi+10h]
0x140151eca  xorps   xmm0, xmm0
0x140151ecd  mov     eax, [rbp+340h+var_39C]
0x140151ed0  mov     r9d, ecx
0x140151ed3  mov     r10d, [rsi+4]
0x140151ed7  add     rax, rsi
0x140151eda  mov     r11d, [rsi+20h]
0x140151ede  test    ecx, ecx
0x140151ee0  movzx   r13d, word ptr [rsi+0Eh]
0x140151ee5  mov     r12d, r14d
0x140151ee8  movups  [rbp+340h+var_380], xmm0
0x140151eec  mov     [rbp+340h+var_340], rax
0x140151ef0  mov     edi, r14d
0x140151ef3  movups  xmmword ptr [rbp+340h+var_390], xmm0
0x140151ef7  mov     [rbp+340h+var_3BC], r8d
0x140151efb  psrldq  xmm0, 8
0x140151f00  movd    eax, xmm0
0x140151f04  mov     [rbp+340h+var_3A0], r10d
0x140151f08  mov     [rbp+340h+var_398], r11d
0x140151f0c  cmovs   eax, r15d
0x140151f10  mov     [rbp+340h+var_368], r14d
0x140151f14  neg     r9d
0x140151f17  mov     dword ptr [rbp+340h+var_380+8], eax
0x140151f1a  mov     [rbp+340h+var_36C], r14d
0x140151f1e  cmovs   r9d, ecx
0x140151f22  mov     [rbp+340h+var_370], r14d
0x140151f26  mov     [rbp+340h+var_3B0], r9d
0x140151f2a  lea     ecx, [rbx-47h]
0x140151f2d  mov     [rbp+340h+var_3B4], r14d
0x140151f31  cmp     r8d, 3
0x140151f35  jnz     loc_14015200C
0x140151f3b  cmp     [rbp+340h+var_3AC], 34h ; '4'
0x140151f3f  jnb     short loc_140151F57
0x140151f41  mov     ecx, ebx; iError
0x140151f43  call    cs:__imp_EngSetLastError
0x140151f4a  nop     dword ptr [rax+rax+00h]
0x140151f4f  mov     r15d, r14d
0x140151f52  jmp     loc_140152000
0x140151f57  cmp     edx, r15d
0x140151f5a  mov     eax, r14d
0x140151f5d  cmovnz  eax, edx
0x140151f60  mov     [rbp+340h+var_3B8], eax
0x140151f63  cmp     r13w, cx
0x140151f67  jz      short loc_140151F93
0x140151f69  cmp     r13d, 20h ; ' '
0x140151f6d  jz      short loc_140151F8A
0x140151f6f  mov     ecx, ebx; iError
0x140151f71  call    cs:__imp_EngSetLastError
0x140151f78  nop     dword ptr [rax+rax+00h]
0x140151f7d  mov     r10d, [rbp+340h+var_3A0]
0x140151f81  mov     r15d, r14d
0x140151f84  mov     r9d, [rbp+340h+var_3B0]
0x140151f88  jmp     short loc_140151F9A
0x140151f8a  mov     [rbp+340h+var_390], 6
0x140151f91  jmp     short loc_140151F9A
0x140151f93  mov     [rbp+340h+var_390], 4
0x140151f9a  mov     edx, r10d
0x140151f9d  mov     eax, 0FFFFFFFFh
0x140151fa2  imul    rdx, r13
0x140151fa6  cmp     rdx, rax
0x140151fa9  ja      loc_14015224F
0x140151faf  lea     ecx, [rdx+1Fh]
0x140151fb2  cmp     ecx, edx
0x140151fb4  jb      loc_14015224F
0x140151fba  shr     rcx, 3
0x140151fbe  lea     rdx, [rbp+340h+var_390+0Ch]; unsigned int *
0x140151fc2  mov     eax, r9d
0x140151fc5  and     ecx, 1FFFFFFCh
0x140151fcb  imul    rcx, rax; unsigned __int64
0x140151fcf  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140151fd4  test    eax, eax
0x140151fd6  js      loc_14015224F
0x140151fdc  lea     rax, [rsi+28h]
0x140151fe0  mov     edi, 200h
0x140151fe5  mov     ecx, [rax]
0x140151fe7  mov     r12d, 2
0x140151fed  mov     [rbp+340h+var_368], ecx
0x140151ff0  mov     ecx, [rax+4]
0x140151ff3  mov     [rbp+340h+var_340], rax
0x140151ff7  mov     eax, [rax+8]
0x140151ffa  mov     [rbp+340h+var_370], eax
0x140151ffd  mov     [rbp+340h+var_36C], ecx
0x140152000  mov     r9, [rbp+340h+var_2F0]
0x140152004  mov     esi, r14d
0x140152007  jmp     loc_14015239D
0x14015200c  test    r8d, r8d
0x14015200f  jnz     loc_140152189
0x140152015  mov     eax, r13d
0x140152018  sub     eax, r15d
0x14015201b  jz      loc_1401520C0
0x140152021  sub     eax, 3
0x140152024  jz      loc_1401520B4
0x14015202a  lea     ecx, [r8+4]
0x14015202e  cmp     eax, ecx
0x140152030  jz      short loc_1401520A5
0x140152032  cmp     edx, r15d
0x140152035  mov     eax, r14d
0x140152038  cmovnz  eax, edx
0x14015203b  mov     edx, eax
0x14015203d  mov     [rbp+340h+var_3B8], eax
0x140152040  lea     eax, [rcx+0Ch]
0x140152043  cmp     r13w, ax
0x140152047  jz      short loc_140152085
0x140152049  lea     ecx, [rax+8]
0x14015204c  cmp     r13w, cx
  ... truncated ...
```
