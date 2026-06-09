# GrepExtTextOutWLocked(XDCOBJ &,int,int,uint,tagRECT const *,ushort const *,int,int const *,ulong,void *,ulong)

- ea: `0x140070514`
- end: `0x1400722ed`
- name: `?GrepExtTextOutWLocked@@YA?AV?$ReturnValueTracer@H@@AEAVXDCOBJ@@HHIPEBUtagRECT@@PEBGHPEBHKPEAXK@Z`
- size: `7641`
- prototype: `__int64 __fastcall(__int64, struct XDCOBJ *, int, unsigned int, int, int *, unsigned __int16 *, int, int *, int, void *, unsigned int)`
- caller_count: `4`
- callee_count: `38`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14006ec30`
- `0x14006f324`
- `0x1401374d0`
- `0x140326088`

## callees

- `0x14004ac68`
- `0x14004af38`
- `0x14004c878`
- `0x14004ca80`
- `0x14004d308`
- `0x14004d7b0`
- `0x1400615f4`
- `0x140063a70`
- `0x140063ee0`
- `0x14006ec10`
- `0x14006f448`
- `0x14006f47c`
- `0x1400704e0`
- `0x140070514`
- `0x140072518`
- `0x140072650`
- `0x14007305c`
- `0x1400954e4`
- `0x140096868`
- `0x1400979a0`
- `0x1400dd838`
- `0x140119280`
- `0x140119ea0`
- `0x14011b4f8`
- `0x14011b568`
- `0x140155c24`
- `0x14017e9c0`
- `0x14019ca60`
- `0x14019cea8`
- `0x14019cf18`
- `0x1401b164c`
- `0x1401c9674`
- `0x1402632cc`
- `0x140299508`
- `0x14030c3f4`
- `0x140326310`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x1400711f9`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x14007172c`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071a99`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071b61`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071b94`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071c21`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x1400711f9`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x14007172c`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071a99`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071b61`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071b94`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x140071c21`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071222`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071747`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071ab7`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071b7f`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071c3f`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071222`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071747`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071ab7`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071b7f`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x140071c3f`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14007085c`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14007085c`
- `win32kbase!EngSetLastError` at `0x140071a35`
- `win32kbase!EngSetLastError` at `0x140071a35`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14007066d`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14007066d`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140071a5c`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140071a74`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140071cbe`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140071a5c`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140071a74`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU_POINTFIX@@_K@Z` at `0x140071cbe`
- `win32kbase!?vUnlock@EPATHOBJ@@QEAAXXZ` at `0x140070e12`
- `win32kbase!?vUnlock@EPATHOBJ@@QEAAXXZ` at `0x140070e12`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x1400710af`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140071106`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x1400710af`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140071106`
- `win32kbase!FreeTmpBuffer` at `0x140070af6`
- `win32kbase!FreeTmpBuffer` at `0x140070af6`
- `win32kbase!Win32FreePool` at `0x140070b15`
- `win32kbase!Win32FreePool` at `0x140070b15`

## pseudocode

```c
__int64 __fastcall GrepExtTextOutWLocked(
        __int64 a1,
        struct XDCOBJ *a2,
        int a3,
        unsigned int a4,
        int a5,
        int *a6,
        unsigned __int16 *a7,
        int a8,
        int *a9,
        int a10,
        void *a11,
        unsigned int a12)
{
  __int64 v13; // rbx
  unsigned int v14; // edi
  int *v15; // r13
  __int64 v16; // rcx
  unsigned int v17; // r15d
  __int64 v18; // rcx
  int v19; // eax
  int v20; // r14d
  __int64 *v21; // rbx
  __int64 v22; // rbx
  int v23; // eax
  int v24; // ebx
  struct XDCOBJ *v25; // rsi
  int v26; // r9d
  int v27; // r10d
  int v28; // edx
  int v29; // r8d
  struct _RECTL *v30; // r13
  struct _RECTL *v31; // rbx
  BOOL v32; // edi
  const struct tagRECT *v33; // rax
  _DWORD *v34; // r11
  int v35; // ebx
  struct REGION *v36; // rax
  int v37; // r9d
  __int64 v38; // r15
  __int64 v39; // rbx
  __int64 v40; // rax
  int v41; // ecx
  struct _BRUSHOBJ *v42; // r11
  __int64 v43; // rdi
  __int64 v44; // r13
  __int64 v45; // r10
  __int64 v46; // rax
  int v47; // r8d
  struct _POINTL *v48; // rbx
  LONG v49; // edx
  struct _SURFOBJ *v50; // r9
  struct _SURFOBJ *v51; // r8
  LONG v52; // r10d
  LONG *v53; // rdi
  BOOL (__stdcall *v54)(SURFOBJ *, STROBJ *, FONTOBJ *, CLIPOBJ *, RECTL *, RECTL *, BRUSHOBJ *, BRUSHOBJ *, POINTL *, MIX); // r10
  int v55; // edx
  struct _GRETHREAD *CurrentThread; // rax
  struct _GRETHREAD *v57; // rax
  _BOOL8 v58; // rdx
  __int64 v60; // rcx
  int v61; // r8d
  int v62; // edi
  int v63; // eax
  int v64; // r8d
  __int64 v65; // rdx
  __int64 v66; // r8
  int v67; // edi
  __int64 v68; // rdx
  int v69; // eax
  int v70; // edi
  int v71; // r11d
  int v72; // ecx
  LONG v73; // ebx
  LONG v74; // eax
  int v75; // eax
  const struct EXFORMOBJR *v76; // rdx
  unsigned int v77; // r9d
  bool v78; // cc
  int v79; // eax
  int v80; // eax
  __int64 v81; // rcx
  int v82; // eax
  int v83; // r8d
  int v84; // r10d
  int v85; // eax
  int v86; // edx
  int v87; // r9d
  _DWORD *v88; // rcx
  int v89; // r11d
  int v90; // edi
  int v91; // r8d
  int v92; // edx
  LONG v93; // edx
  __int64 v94; // rax
  const struct _POINTL *v95; // rdx
  const struct EXFORMOBJR *v96; // rdx
  unsigned int v97; // r9d
  int v98; // eax
  char v99; // al
  LONG v100; // eax
  signed int cEntries; // eax
  int v102; // ecx
  int v103; // edx
  int v104; // eax
  int v105; // edx
  int v106; // eax
  int v107; // edx
  int v108; // eax
  int v109; // edx
  LONG v110; // ecx
  int v111; // eax
  int v112; // r11d
  LONG v113; // edx
  LONG v114; // edx
  struct _BRUSHOBJ *v115; // rax
  int left; // edi
  LONG right; // r9d
  LONG top; // eax
  LONG bottom; // ecx
  const struct EXFORMOBJR *v120; // rdx
  unsigned int v121; // r9d
  _DWORD *v122; // rax
  ERECTL *v123; // rbx
  LONG v124; // edx
  LONG v125; // r8d
  LONG v126; // r9d
  LONG v127; // r10d
  LONG v128; // edx
  struct _SURFOBJ *v129; // r8
  struct _SURFOBJ *v130; // r9
  LONG v131; // r10d
  LONG v132; // ecx
  LONG v133; // eax
  LONG v134; // ecx
  LONG v135; // eax
  int v136; // eax
  ULONG v137; // ecx
  __int64 v138; // rcx
  __int64 v139; // rax
  bool v140; // zf
  LONG v141; // ecx
  LONG v142; // eax
  unsigned __int64 v143; // rcx
  int v144; // r11d
  int v145; // edi
  unsigned __int64 v146; // rcx
  int v147; // r8d
  int v148; // edx
  struct _XLATEOBJ *v149; // [rsp+28h] [rbp-E8h]
  struct _POINTL *v150; // [rsp+38h] [rbp-D8h]
  struct _POINTL *v151; // [rsp+40h] [rbp-D0h]
  unsigned int v152; // [rsp+58h] [rbp-B8h]
  struct _BRUSHOBJ *v153; // [rsp+90h] [rbp-80h] BYREF
  _DWORD *v154; // [rsp+98h] [rbp-78h] BYREF
  struct tagRECT *p_rclBkGround; // [rsp+A0h] [rbp-70h] BYREF
  struct _POINTL *v156; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v157; // [rsp+B0h] [rbp-60h]
  unsigned int v158; // [rsp+B8h] [rbp-58h]
  int v159; // [rsp+BCh] [rbp-54h]
  int v160; // [rsp+C0h] [rbp-50h]
  struct _XLATEOBJ v161; // [rsp+C8h] [rbp-48h] BYREF
  HDEV v162; // [rsp+E0h] [rbp-30h]
  struct XDCOBJ *v163; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v164; // [rsp+F0h] [rbp-20h]
  unsigned __int16 *v165[2]; // [rsp+100h] [rbp-10h] BYREF
  _BYTE v166[4]; // [rsp+110h] [rbp+0h] BYREF
  unsigned int v167; // [rsp+114h] [rbp+4h]
  __int64 v168; // [rsp+118h] [rbp+8h]
  char v169[48]; // [rsp+160h] [rbp+50h] BYREF
  void *v170; // [rsp+190h] [rbp+80h]
  int *v171; // [rsp+198h] [rbp+88h]
  struct _SURFOBJ *v172[2]; // [rsp+1A0h] [rbp+90h] BYREF
  struct _RECTL v173; // [rsp+1B0h] [rbp+A0h] BYREF
  struct _RECTL v174; // [rsp+1C0h] [rbp+B0h] BYREF
  struct _CLIPOBJ v175; // [rsp+1D0h] [rbp+C0h] BYREF
  __int64 v176; // [rsp+208h] [rbp+F8h]
  __int64 v177; // [rsp+220h] [rbp+110h]
  int v178; // [rsp+228h] [rbp+118h]
  int v179; // [rsp+250h] [rbp+140h]
  __int64 v180; // [rsp+260h] [rbp+150h]
  STROBJ pstro; // [rsp+270h] [rbp+160h] BYREF
  __int64 v182; // [rsp+2B0h] [rbp+1A0h]
  int v183; // [rsp+2C0h] [rbp+1B0h]
  int v184; // [rsp+2C4h] [rbp+1B4h]
  int v185; // [rsp+2F0h] [rbp+1E0h]
  _BYTE v186[100]; // [rsp+2F4h] [rbp+1E4h] BYREF
  int v187; // [rsp+358h] [rbp+248h]
  void *v188; // [rsp+378h] [rbp+268h]
  struct _POINTL v189; // [rsp+3B0h] [rbp+2A0h] BYREF
  LONG v190; // [rsp+3B8h] [rbp+2A8h]
  LONG v191; // [rsp+3BCh] [rbp+2ACh]
  LONG v192; // [rsp+3C0h] [rbp+2B0h]
  LONG v193; // [rsp+3C4h] [rbp+2B4h]
  LONG v194; // [rsp+3C8h] [rbp+2B8h]
  int v195; // [rsp+3CCh] [rbp+2BCh]
  struct _POINTFIX v196; // [rsp+3D0h] [rbp+2C0h] BYREF

  v13 = a1;
  v14 = a4;
  v15 = a6;
  v165[0] = a7;
  v170 = a11;
  v164 = a1;
  v16 = *(_QWORD *)a2;
  v158 = a4;
  v160 = a3;
  v171 = a9;
  LODWORD(v153) = (a5 & 0x10) != 0 ? 4 : 2;
  if ( (*(_DWORD *)(v16 + 248) & 1) != 0 && (a5 & 4) != 0 )
    goto LABEL_286;
  if ( (*(_DWORD *)(v16 + 36) & 0x10000) != 0 )
  {
    v137 = 6;
    goto LABEL_287;
  }
  LODWORD(v156) = a5 & 0x2000;
  if ( (a5 & 0x2000) != 0 && !a9 )
  {
LABEL_286:
    v137 = 87;
LABEL_287:
    EngSetLastError(v137);
    v58 = 0;
    goto LABEL_79;
  }
  v17 = a5 & 0xFFFFC36F;
  if ( a6 )
  {
    if ( *a6 == a6[2] || a6[1] == a6[3] )
    {
      a6[2] = a3;
      *a6 = a3;
      a6[3] = a4;
      a6[1] = a4;
      if ( (a5 & 6) == 2 )
      {
        v15 = 0;
        v17 = a5 & 0xFFFFC36D;
      }
    }
  }
  else
  {
    v17 = a5 & 0xFFFFC369;
  }
  v18 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 && (!v17 || v15 && (v17 & 0xFFFFFFF9) == 0) )
  {
    v19 = *(_DWORD *)(v18 + 248) & 1;
    if ( !v19 || (v17 & 4) == 0 )
    {
      LODWORD(v161.pulXlate) = 0;
      v159 = 0;
      *(_OWORD *)v172 = 0;
      v20 = 128;
      if ( v19 )
      {
        v23 = 0;
        v157 = 0;
        HIDWORD(v22) = 0;
      }
      else
      {
        v21 = (__int64 *)(v18 + 1024);
        if ( (*(_DWORD *)(v18 + 40) & 1) == 0 )
          v21 = (__int64 *)(v18 + 1016);
        v22 = *v21;
        v157 = v22;
        v23 = v22;
      }
      *(_DWORD *)&v161.iSrcType = 16 * v23;
      v24 = 16 * HIDWORD(v22);
      DC::QuickInitXform(v18, &v161, 516);
      v25 = 0;
      v163 = 0;
      if ( !v15 )
      {
        v26 = HIDWORD(v172[1]);
        v27 = (int)v172[1];
        v28 = HIDWORD(v172[0]);
        v29 = (int)v172[0];
        goto LABEL_16;
      }
      LODWORD(v162) = v17 & 2;
      v20 = (_DWORD)v162 != 0 ? 136 : 128;
      if ( (*(_DWORD *)(*(_QWORD *)&v161.iUniq + 32LL) & 2) != 0 )
      {
        v89 = v157 + *v15 + ((*(_DWORD *)(*(_QWORD *)&v161.iUniq + 24LL) + 8) >> 4);
        v173.left = v89;
        v90 = v157 + v15[2] + ((*(_DWORD *)(*(_QWORD *)&v161.iUniq + 24LL) + 8) >> 4);
        v173.right = v90;
        v91 = HIDWORD(v157) + v15[1] + ((*(_DWORD *)(*(_QWORD *)&v161.iUniq + 28LL) + 8) >> 4);
        v173.top = v91;
        v92 = *(_DWORD *)(*(_QWORD *)&v161.iUniq + 28LL) + 8;
        LODWORD(v157) = v91;
        v93 = HIDWORD(v157) + v15[3] + (v92 >> 4);
        v161.cEntries = v93;
        v173.bottom = v93;
        goto LABEL_173;
      }
      v103 = *v15;
      if ( (*(_BYTE *)(*(_QWORD *)&v161.iUniq + 32LL) & 1) != 0 )
      {
        v104 = EXFORMOBJ::fxFastX((EXFORMOBJ *)&v161, v103);
        v105 = v15[2];
        v173.left = v157 + ((v104 + 8) >> 4);
        v106 = EXFORMOBJ::fxFastX((EXFORMOBJ *)&v161, v105);
        v107 = v15[1];
        v173.right = v157 + ((v106 + 8) >> 4);
        v108 = EXFORMOBJ::fxFastY((EXFORMOBJ *)&v161, v107);
        v109 = v15[3];
        v173.top = HIDWORD(v157) + ((v108 + 8) >> 4);
        v93 = HIDWORD(v157) + ((int)(EXFORMOBJ::fxFastY((EXFORMOBJ *)&v161, v109) + 8) >> 4);
        v173.bottom = v93;
      }
      else
      {
        v141 = v15[1];
        v189.y = v15[3];
        v142 = v15[2];
        v191 = v141;
        v193 = v141;
        v189.x = v103;
        v190 = v103;
        v192 = v142;
        EXFORMOBJ::bXform((EXFORMOBJ *)&v161, &v189, (struct _POINTFIX *)&v189, 3u);
        v194 = v189.x + v192 - v190;
        v174.left = v194;
        v195 = v189.y + v193 - v191;
        LODWORD(p_rclBkGround) = v195;
        v143 = (v190 > v189.x) ^ (unsigned __int64)(v190 <= v192);
        v144 = *(&v189.x + 2 * v143);
        v145 = *(&v192 + 2 * v143);
        if ( v144 > v145 )
          v144 += 15;
        else
          v145 += 15;
        v89 = v157 + (v144 >> 4);
        v90 = v157 + (v145 >> 4);
        v173.right = v90;
        v173.left = v89;
        v146 = (v191 <= v193) ^ (unsigned __int64)(v191 > v189.y);
        v147 = *(&v189.y + 2 * v146);
        v148 = *(&v193 + 2 * v146);
        if ( v147 > v148 )
          v147 += 15;
        else
          v148 += 15;
        v91 = HIDWORD(v157) + (v147 >> 4);
        v93 = HIDWORD(v157) + (v148 >> 4);
        v173.top = v91;
        v173.bottom = v93;
        v161.cEntries = v93;
        LODWORD(v157) = v91;
        if ( (v17 & 4) == 0 )
        {
          if ( (_DWORD)v162 )
          {
            v189.x += *(_DWORD *)&v161.iSrcType;
            v190 += *(_DWORD *)&v161.iSrcType;
            v20 = 130;
            v192 += *(_DWORD *)&v161.iSrcType;
            v189.y += v24;
            v191 += v24;
            v195 = v24 + (_DWORD)p_rclBkGround;
            v193 += v24;
            v194 = *(_DWORD *)&v161.iSrcType + v174.left;
          }
LABEL_173:
          if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 108LL) & 1) != 0 )
          {
            ++v89;
            ++v90;
            v173.left = v89;
            v173.right = v90;
          }
          if ( v89 > v90 )
          {
            v100 = v89;
            v173.left = v90;
            v89 = v90;
            v173.right = v100;
            v90 = v100;
          }
          if ( v91 <= v93 )
          {
            cEntries = v161.cEntries;
            v102 = v157;
          }
          else
          {
            cEntries = v91;
            v173.top = v93;
            v173.bottom = v91;
            v102 = v93;
          }
          v29 = (int)v172[0];
          v27 = (int)v172[1];
          if ( (v20 & 0xA) != 0 )
          {
            if ( LODWORD(v172[0]) != LODWORD(v172[1]) )
            {
              v28 = HIDWORD(v172[0]);
              v26 = HIDWORD(v172[1]);
              if ( HIDWORD(v172[0]) != HIDWORD(v172[1]) )
              {
                if ( v89 < SLODWORD(v172[0]) )
                  v29 = v89;
                LODWORD(v172[0]) = v29;
                if ( v102 < SHIDWORD(v172[0]) )
                  v28 = v102;
                HIDWORD(v172[0]) = v28;
                if ( v90 > SLODWORD(v172[1]) )
                  v27 = v90;
                v14 = v158;
                LODWORD(v172[1]) = v27;
                if ( cEntries > SHIDWORD(v172[1]) )
                {
                  v26 = cEntries;
                  HIDWORD(v172[1]) = cEntries;
                }
LABEL_16:
                v30 = 0;
                p_rclBkGround = 0;
                *(_QWORD *)&v174.left = 0;
                v154 = 0;
                v187 = 0;
                if ( !a8 )
                {
LABEL_21:
                  v31 = 0;
                  goto LABEL_32;
                }
                if ( (unsigned int)RFONTOBJ::bInit(
                                     (RFONTOBJ *)&v154,
                                     a2,
                                     *(_DWORD *)(*(_QWORD *)a2 + 248LL) & 1,
                                     (unsigned int)v153) )
                  GreAcquireSemaphore<5,RFONT *>(v154);
                if ( !v154 )
                {
                  v26 = HIDWORD(v172[1]);
                  v20 = 0;
                  v27 = (int)v172[1];
                  v28 = HIDWORD(v172[0]);
                  v29 = (int)v172[0];
                  goto LABEL_21;
                }
                v159 = v154[22] & 2;
                LODWORD(v161.pulXlate) = v159 && (v154[181] & 0x8000) == 0;
                v60 = *(_QWORD *)(*(_QWORD *)a2 + 976LL);
                v158 = *(_DWORD *)(*(_QWORD *)a2 + 1752LL) | *(_DWORD *)(v60 + 272) & 0x11F;
                if ( (v158 & 1) != 0 )
                {
                  v63 = *(_DWORD *)(v60 + 152);
                  if ( (v63 & 0x200) == 0 )
                  {
                    v64 = *(_DWORD *)&v161.iSrcType;
                    *(_DWORD *)(v60 + 152) = v63 | 0x100;
                    v65 = *(_QWORD *)a2;
                    v61 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 8LL) + v64;
                    LODWORD(v153) = v61;
                    v62 = *(_DWORD *)(*(_QWORD *)(v65 + 976) + 12LL);
                    goto LABEL_90;
                  }
                  *(_DWORD *)(v60 + 152) = v63 & 0xFFFFFDFF;
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 152LL) |= 0x100u;
                  if ( (*(_DWORD *)(*(_QWORD *)&v161.iUniq + 32LL) & 2) != 0 )
                  {
                    v66 = *(_QWORD *)a2;
                    LODWORD(v153) = *(_DWORD *)(*(_QWORD *)&v161.iUniq + 24LL)
                                  + 16 * *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 216LL);
                    HIDWORD(v153) = *(_DWORD *)(*(_QWORD *)&v161.iUniq + 28LL)
                                  + 16 * *(_DWORD *)(*(_QWORD *)(v66 + 976) + 220LL);
                  }
                  else
                  {
                    v95 = (const struct _POINTL *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 216LL);
                    if ( (*(_BYTE *)(*(_QWORD *)&v161.iUniq + 32LL) & 1) != 0 )
                    {
                      LODWORD(v153) = EXFORMOBJ::fxFastX((EXFORMOBJ *)&v161, v95->x);
                      HIDWORD(v153) = EXFORMOBJ::fxFastY(
                                        (EXFORMOBJ *)&v161,
                                        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 220LL));
                    }
                    else
                    {
                      EXFORMOBJ::bXform((EXFORMOBJ *)&v161, v95, (struct _POINTFIX *)&v153, 1u);
                    }
                  }
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 8LL) = v153;
                }
                else
                {
                  if ( (*(_DWORD *)(*(_QWORD *)&v161.iUniq + 32LL) & 2) != 0 )
                  {
                    v61 = *(_DWORD *)&v161.iSrcType + *(_DWORD *)(*(_QWORD *)&v161.iUniq + 24LL) + 16 * v160;
                    LODWORD(v153) = v61;
                    v62 = *(_DWORD *)(*(_QWORD *)&v161.iUniq + 28LL) + 16 * v14;
LABEL_90:
                    v67 = v24 + v62;
                    goto LABEL_91;
                  }
                  if ( (*(_BYTE *)(*(_QWORD *)&v161.iUniq + 32LL) & 1) != 0 )
                  {
                    v79 = EXFORMOBJ::fxFastX((EXFORMOBJ *)&v161, v160);
                    LODWORD(v153) = *(_DWORD *)&v161.iSrcType + v79;
                    v80 = EXFORMOBJ::fxFastY((EXFORMOBJ *)&v161, v14);
                    v61 = (int)v153;
                    v67 = v24 + v80;
LABEL_91:
                    v68 = *(_QWORD *)a2;
                    HIDWORD(v153) = v67;
                    ESTROBJ::vInit(
                      (ESTROBJ *)&pstro,
                      v165[0],
                      a8,
                      a2,
                      (struct RFONTOBJ *)&v154,
                      (struct EXFORMOBJ *)&v161,
                      v171,
                      (int)v156,
                      *(_DWORD *)(v68 + 1756),
                      *(_DWORD *)(*(_QWORD *)(v68 + 976) + 280LL),
                      *(_DWORD *)(*(_QWORD *)(v68 + 976) + 284LL),
                      *(_DWORD *)(*(_QWORD *)(v68 + 976) + 288LL),
                      v61,
                      v67,
                      v158,
                      0,
                      v170,
                      a12);
                    if ( (v187 & 4) == 0 )
                    {
                      v26 = HIDWORD(v172[1]);
                      v20 = 0;
                      v27 = (int)v172[1];
                      v28 = HIDWORD(v172[0]);
                      v29 = (int)v172[0];
LABEL_30:
                      v31 = (struct _RECTL *)p_rclBkGround;
                      *(_QWORD *)&v174.left = v30;
                      if ( (v158 & 1) != 0 )
                      {
                        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 8LL) += v183;
                        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 12LL) += v184;
                        v26 = HIDWORD(v172[1]);
                        v27 = (int)v172[1];
                        v28 = HIDWORD(v172[0]);
                        v29 = (int)v172[0];
                      }
                      else
                      {
                        *(_QWORD *)&v174.left = v30;
                      }
LABEL_32:
                      v34 = *(_DWORD **)a2;
                      if ( (*(_DWORD *)(*(_QWORD *)a2 + 248LL) & 1) == 0 )
                      {
                        if ( v28 == v26 || v29 == v27 )
                          goto LABEL_70;
                        v35 = v34[9];
                        if ( (v35 & 0xE0) != 0 )
                        {
                          v81 = v34[10] & 1;
                          v82 = v34[2 * v81 + 254];
                          v83 = v29 - v82;
                          v84 = v27 - v82;
                          v85 = v34[2 * v81 + 255];
                          v86 = v28 - v85;
                          v87 = v26 - v85;
                          if ( (v35 & 0x20) != 0 )
                          {
                            if ( v83 < v34[266] )
                              v34[266] = v83;
                            if ( v86 < v34[267] )
                              v34[267] = v86;
                            if ( v84 > v34[268] )
                              v34[268] = v84;
                            if ( v87 > v34[269] )
                              v34[269] = v87;
                          }
                          v88 = *(_DWORD **)a2;
                          if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x80u) != 0 )
                          {
                            if ( v83 < v88[274] )
                              v88[274] = v83;
                            if ( v86 < v88[275] )
                              v88[275] = v86;
                            if ( v84 > v88[276] )
                              v88[276] = v84;
                            if ( v87 > v88[277] )
                              v88[277] = v87;
                          }
                        }
                        v36 = XDCOBJ::prgnEffRao(a2);
                        v176 = 0;
                        v177 = 0;
                        v178 = 0;
                        v179 = 1;
                        v180 = 0;
                        XCLIPOBJ::vSetup((XCLIPOBJ *)&v175, v36, (const struct ERECTL *)v172, v37);
                        LODWORD(v172[0]) = v175.rclBounds.left;
                        *(struct _SURFOBJ **)((char *)v172 + 4) = *(struct _SURFOBJ **)&v175.rclBounds.top;
                        HIDWORD(v172[1]) = v175.rclBounds.bottom;
                        if ( v175.rclBounds.top == v175.rclBounds.bottom || v175.rclBounds.left == v175.rclBounds.right )
                          goto LABEL_70;
                        if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0xE0) != 0 )
                        {
                          *(_OWORD *)v165 = *(_OWORD *)v172;
                          XDCOBJ::vAccumulateTight(
                            a2,
                            (struct ECLIPOBJ *)(unsigned int)v175.rclBounds.top,
                            (struct ERECTL *)v165);
                        }
                        v38 = *(_QWORD *)(*(_QWORD *)a2 + 496LL);
                        if ( !v38 || !(unsigned int)DestSurfaceAccessCheck(*(struct SURFACE **)(*(_QWORD *)a2 + 496LL)) )
                          goto LABEL_70;
                        v39 = *(_QWORD *)(v38 + 176);
                        v162 = *(HDEV *)(v38 + 48);
                        v40 = *(_QWORD *)a2;
                        v41 = *(_DWORD *)(*(_QWORD *)a2 + 72LL);
                        v42 = (struct _BRUSHOBJ *)(*(_QWORD *)a2 + 1608LL);
                        v43 = *(_QWORD *)(*(_QWORD *)a2 + 88LL);
                        v44 = *(_QWORD *)a2 + 1472LL;
                        v153 = v42;
                        v160 = v41;
                        if ( (v41 & 0x10000000) != 0 )
                        {
                          *(_DWORD *)(*(_QWORD *)(v40 + 976) + 152LL) |= 4u;
                          --*(_DWORD *)(v44 + 124);
                        }
                        v45 = *(_QWORD *)a2;
                        v46 = *(_QWORD *)(*(_QWORD *)a2 + 976LL);
                        v47 = *(_DWORD *)(*(_QWORD *)a2 + 316LL) | *(_DWORD *)(v46 + 152);
                        if ( ((*(_BYTE *)(*(_QWORD *)a2 + 316LL) | *(_BYTE *)(v46 + 152)) & 0xC) != 0 )
                        {
                          v94 = *((_QWORD *)a2 + 2);
                          v165[0] = (unsigned __int16 *)v94;
                          if ( (v47 & 4) != 0 )
                          {
                            v149 = (struct _XLATEOBJ *)v38;
                            EBRUSHOBJ::vInitBrush(v44, v45, *(_QWORD *)(v94 + 152), v43, v39);
                            v42 = v153;
                          }
                          if ( ((*(_BYTE *)(*(_QWORD *)a2 + 316LL)
                               | *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 152LL))
                              & 8) != 0 )
                          {
                            v149 = (struct _XLATEOBJ *)v38;
                            EBRUSHOBJ::vInitBrush(v42, *(_QWORD *)a2, *((_QWORD *)v165[0] + 21), v43, v39);
                          }
                          v42 = v153;
                          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 152LL) &= 0xFFFFFFF3;
                          *(_DWORD *)(*(_QWORD *)a2 + 316LL) &= 0xFFFFFFF3;
                        }
                        v48 = (struct _POINTL *)(*(_QWORD *)a2 + 1192LL);
                        if ( (v20 & 0x1A) != 0 )
                        {
                          if ( (v20 & 8) == 0
                            || (left = v173.left, right = v173.right, v173.left == v173.right)
                            || (top = v173.top, bottom = v173.bottom, v173.top == v173.bottom) )
                          {
                            v52 = HIDWORD(v172[1]);
                            v51 = (struct _SURFOBJ *)LODWORD(v172[1]);
                            v50 = (struct _SURFOBJ *)HIDWORD(v172[0]);
                            v49 = (LONG)v172[0];
                          }
                          else
                          {
                            v49 = (LONG)v172[0];
                            v51 = (struct _SURFOBJ *)LODWORD(v172[1]);
                            v52 = HIDWORD(v172[1]);
                            if ( SLODWORD(v172[0]) > v173.left )
                              left = (int)v172[0];
                            v175.rclBounds.left = left;
                            if ( SLODWORD(v172[1]) < v173.right )
                              right = (LONG)v172[1];
                            LODWORD(v156) = right;
                            v175.rclBounds.right = right;
                            v50 = (struct _SURFOBJ *)HIDWORD(v172[0]);
                            if ( SHIDWORD(v172[0]) > v173.top )
                              top = HIDWORD(v172[0]);
                            v175.rclBounds.top = top;
                            if ( SHIDWORD(v172[1]) < v173.bottom )
                              bottom = HIDWORD(v172[1]);
                            v175.rclBounds.bottom = bottom;
                            if ( left < (int)v156 && top < bottom )
                            {
                              ++*(_DWORD *)(v38 + 92);
                              TextOutBitBlt(
                                (struct SURFACE *)v38,
                                (struct RFONTOBJ *)&v154,
                                v51,
                                v50,
                                &v175,
                                v149,
                                &v175.rclBounds,
                                v150,
                                v151,
                                v42,
                                v48,
                                v152);
                              v52 = HIDWORD(v172[1]);
                              v51 = (struct _SURFOBJ *)LODWORD(v172[1]);
                              v50 = (struct _SURFOBJ *)HIDWORD(v172[0]);
                              v49 = (LONG)v172[0];
                            }
                            v175.rclBounds.left = v49;
                            v175.rclBounds.top = (int)v50;
                            v175.rclBounds.right = (int)v51;
                            v175.rclBounds.bottom = v52;
                          }
                          if ( (v20 & 0x12) == 0 )
                          {
LABEL_47:
                            if ( (v20 & 1) == 0 )
                            {
LABEL_69:
                              if ( (v20 & 4) != 0 )
                              {
                                PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v166);
                                if ( !v168
                                  || !(unsigned int)ESTROBJ::bExtraRectsToPath(
                                                      (ESTROBJ *)&pstro,
                                                      (struct EPATHOBJ *)v166)
                                  || !*(_DWORD *)EPATHOBJ_bTextOutSimpleFill(&v156, v166, a2, &v154, v162) )
                                {
                                  v20 = 0;
                                }
                                PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v166);
                              }
                              goto LABEL_70;
                            }
                            v53 = 0;
                            if ( v159 )
                            {
                              v160 = -257;
                              v20 |= (v154[181] & 0x8000) != 0 ? 64 : 32;
                            }
                            if ( p_rclBkGround && (v160 & 0x100) == 0 )
                            {
                              v110 = p_rclBkGround->left;
                              v111 = p_rclBkGround->right;
                              v112 = p_rclBkGround->top;
                              if ( v49 > p_rclBkGround->left )
                                v110 = v49;
                              v175.rclBounds.left = v110;
                              if ( (int)v51 < v111 )
                                v111 = (int)v51;
                              v175.rclBounds.right = v111;
                              v113 = p_rclBkGround->bottom;
                              if ( (int)v50 > v112 )
                                v112 = (int)v50;
                              v175.rclBounds.top = v112;
                              if ( v52 < v113 )
                                v113 = v52;
                              LODWORD(v156) = v113;
                              v175.rclBounds.bottom = v113;
                              v114 = (LONG)v172[0];
                              if ( v110 < v111 && v112 < (int)v156 )
                              {
                                v115 = v153;
                                ++*(_DWORD *)(v38 + 92);
                                TextOutBitBlt(
                                  (struct SURFACE *)v38,
                                  (struct RFONTOBJ *)&v154,
                                  v51,
                                  v50,
                                  &v175,
                                  v149,
                                  &v175.rclBounds,
                                  v150,
                                  v151,
                                  v115,
                                  v48,
                                  v152);
                                v52 = HIDWORD(v172[1]);
                                LODWORD(v51) = v172[1];
                                LODWORD(v50) = HIDWORD(v172[0]);
                                v114 = (LONG)v172[0];
                              }
                              v175.rclBounds.left = v114;
                              v175.rclBounds.top = (int)v50;
                              v175.rclBounds.right = (int)v51;
                              v175.rclBounds.bottom = v52;
                              p_rclBkGround = 0;
                            }
                            if ( *(_QWORD *)&v174.left && *((_DWORD *)v162 + 531) != 4 )
                            {
                              v53 = *(LONG **)&v174.left;
                              *(_QWORD *)&v174.left = 0;
                            }
                            if ( (v20 & 0x20) != 0 )
                            {
                              if ( (v187 & 0x1400) != 0 )
                              {
                                if ( !*(_DWORD *)bProxyDrvTextOut(
                                                   (__int64)&v156,
                                                   a2,
                                                   (SURFACE *)v38,
                                                   (int *)&pstro,
                                                   &v175,
                                                   0,
                                                   0,
                                                   (struct _BRUSHOBJ *)v44,
                                                   v153,
                                                   v48,
                                                   (struct RFONTOBJ *)&v154,
                                                   v162,
                                                   *(_DWORD *)(*(_QWORD *)a2 + 72LL),
                                                   (LONG *)v172) )
                                  v20 = 0;
                              }
                              else
                              {
                                PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v166);
                                if ( !v168
                                  || !(unsigned int)ESTROBJ::bTextToPath((ESTROBJ *)&pstro, (struct EPATHOBJ *)v166)
                                  || !(unsigned int)EPATHOBJ_bTextOutSimpleStroke1(
                                                      (struct EPATHOBJ *)v166,
                                                      a2,
                                                      (struct RFONTOBJ *)&v154,
                                                      v162,
                                                      (struct SURFACE *)v38,
                                                      &v175,
                                                      (struct _BRUSHOBJ *)v44,
                                                      v48,
                                                      (unsigned int)v151) )
                                {
                                  v20 = 0;
                                }
                                PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v166);
                              }
                              goto LABEL_68;
                            }
                            if ( SURFACE::pdcoAA((SURFACE *)v38) )
                              SURFACE::pdcoAA((SURFACE *)v38, 0);
                            v156 = (struct _POINTL *)SURFACE::pfnTextOut((SURFACE *)v38);
                            if ( PDEVOBJ::bSupportsClearTypeAlways((int (*)(struct _SURFOBJ *, struct _STROBJ *, struct _FONTOBJ *, struct _CLIPOBJ *, struct _RECTL *, struct _RECTL *, struct _BRUSHOBJ *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))v156) )
                            {
                              if ( (v154[3] & 0x10010000) != 0 )
                              {
                                SURFACE::pdcoAA((SURFACE *)v38, a2);
                                v54 = (BOOL (__stdcall *)(SURFOBJ *, STROBJ *, FONTOBJ *, CLIPOBJ *, RECTL *, RECTL *, BRUSHOBJ *, BRUSHOBJ *, POINTL *, MIX))v156;
                              }
                            }
                            else
                            {
                              v55 = v154[3];
                              if ( (v55 & 0x10000) != 0
                                && ((*(_DWORD *)(*(_QWORD *)a2 + 72LL) & 0x1000000) == 0 || (v55 & 0x10000000) != 0) )
                              {
                                if ( v54 != EngTextOut )
                                {
                                  *(_QWORD *)(v38 + 152) = a2;
                                  CurrentThread = GreGetCurrentThread();
                                  if ( CurrentThread )
                                    *((_QWORD *)CurrentThread + 36) = a2;
                                }
                                v54 = (BOOL (__stdcall *)(SURFOBJ *, STROBJ *, FONTOBJ *, CLIPOBJ *, RECTL *, RECTL *, BRUSHOBJ *, BRUSHOBJ *, POINTL *, MIX))SpTextOut;
                                v156 = (struct _POINTL *)SpTextOut;
                              }
                            }
                            if ( (v20 & 0x40) != 0 )
                            {
                              if ( (v187 & 0x1400) != 0 )
                              {
                                v122 = (_DWORD *)bProxyDrvTextOut(
                                                   (__int64)&v156,
                                                   a2,
                                                   (SURFACE *)v38,
                                                   (int *)&pstro,
                                                   &v175,
                                                   0,
                                                   0,
                                                   (struct _BRUSHOBJ *)v44,
                                                   v153,
                                                   v48,
                                                   (struct RFONTOBJ *)&v154,
                                                   v162,
                                                   *(_DWORD *)(*(_QWORD *)a2 + 72LL),
                                                   (LONG *)v172);
                                goto LABEL_246;
                              }
                              PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v166);
                              if ( !v168
                                || !(unsigned int)ESTROBJ::bTextToPath((ESTROBJ *)&pstro, (struct EPATHOBJ *)v166)
                                || v167 > 1
                                && (v151 = v48,
                                    v150 = (struct _POINTL *)v44,
                                    v149 = (struct _XLATEOBJ *)v38,
                                    !*(_DWORD *)EPATHOBJ_bTextOutSimpleFill(&v156, v166, a2, &v154, v162)) )
                              {
                                v20 = 0;
                              }
                            }
                            else
                            {
                              ++*(_DWORD *)(v38 + 92);
                              if ( (v20 & 4) == 0 )
                              {
                                if ( (v187 & 0x1400) == 0 )
                                {
                                  v151 = v48;
                                  v150 = (struct _POINTL *)v153;
                                  v149 = (struct _XLATEOBJ *)p_rclBkGround;
                                  v20 = ((unsigned int (__fastcall *)(__int64, STROBJ *, _DWORD *, struct _CLIPOBJ *, _QWORD))v54)(
                                          v38 + 24,
                                          &pstro,
                                          v154,
                                          &v175,
                                          *(_QWORD *)&v174.left) != 0
                                      ? v20
                                      : 0;
                                  goto LABEL_66;
                                }
                                v122 = (_DWORD *)bProxyDrvTextOut(
                                                   (__int64)&v156,
                                                   a2,
                                                   (SURFACE *)v38,
                                                   (int *)&pstro,
                                                   &v175,
                                                   *(__int64 *)&v174.left,
                                                   (struct _RECTL *)p_rclBkGround,
                                                   (struct _BRUSHOBJ *)v44,
                                                   v153,
                                                   v48,
                                                   (struct RFONTOBJ *)&v154,
                                                   v162,
                                                   0,
                                                   (LONG *)v172);
LABEL_246:
                                if ( !*v122 )
                                  v20 = 0;
                                goto LABEL_66;
                              }
                              PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v166);
                              if ( !v168
                                || !(unsigned int)ESTROBJ::bExtraRectsToPath((ESTROBJ *)&pstro, (struct EPATHOBJ *)v166)
                                || ((v187 & 0x1400) != 0
                                  ? (v140 = *(_DWORD *)bProxyDrvTextOut(
                                                         (__int64)&v156,
                                                         a2,
                                                         (SURFACE *)v38,
                                                         (int *)&pstro,
                                                         &v175,
                                                         *(__int64 *)&v174.left,
                                                         (struct _RECTL *)p_rclBkGround,
                                                         (struct _BRUSHOBJ *)v44,
                                                         v153,
                                                         v48,
                                                         (struct RFONTOBJ *)&v154,
                                                         0,
                                                         0,
                                                         (LONG *)v172) == 0)
                                  : (v151 = v48,
                                     v150 = (struct _POINTL *)v153,
                                     v149 = (struct _XLATEOBJ *)p_rclBkGround,
                                     v140 = ((unsigned int (__fastcall *)(__int64, STROBJ *, _DWORD *, struct _CLIPOBJ *, _QWORD))v156)(
                                              v38 + 24,
                                              &pstro,
                                              v154,
                                              &v175,
                                              *(_QWORD *)&v174.left) == 0),
                                    v140
                                 || (v151 = v48,
                                     v150 = (struct _POINTL *)v44,
                                     v149 = (struct _XLATEOBJ *)v38,
                                     !*(_DWORD *)EPATHOBJ_bTextOutSimpleFill(&v156, v166, a2, &v154, v162))) )
                              {
                                v20 = 0;
                              }
                              v20 &= ~4u;
                            }
                            PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v166);
LABEL_66:
                            *(_QWORD *)(v38 + 152) = 0;
                            v57 = GreGetCurrentThread();
                            if ( v57 )
                              *((_QWORD *)v57 + 36) = 0;
LABEL_68:
                            if ( v53 )
                            {
                              v124 = v175.rclBounds.left;
                              v125 = v175.rclBounds.top;
                              v126 = v175.rclBounds.right;
                              v127 = v175.rclBounds.bottom;
                              ++*(_DWORD *)(v38 + 92);
                              LODWORD(v156) = v124;
                              LODWORD(v153) = v125;
                              LODWORD(p_rclBkGround) = v126;
                              v174.left = v127;
                              while ( !(unsigned int)ERECTL::bEmpty((ERECTL *)v53) )
                              {
                                v132 = *v53;
                                v133 = v53[2];
                                if ( v128 > *v53 )
                                  v132 = v128;
                                v175.rclBounds.left = v132;
                                if ( (int)v130 < v133 )
                                  v133 = (int)v130;
                                v175.rclBounds.right = v133;
                                if ( v132 < v133 )
                                {
                                  v134 = v53[1];
                                  v135 = v53[3];
                                  if ( (int)v129 > v134 )
                                    v134 = (int)v129;
                                  v175.rclBounds.top = v134;
                                  if ( v131 < v135 )
                                    v135 = v131;
                                  v175.rclBounds.bottom = v135;
                                  if ( v134 < v135 )
                                    TextOutBitBlt(
                                      (struct SURFACE *)v38,
                                      (struct RFONTOBJ *)&v154,
                                      v129,
                                      v130,
                                      &v175,
                                      v149,
                                      &v175.rclBounds,
                                      v150,
                                      v151,
                                      (struct _BRUSHOBJ *)v44,
                                      v48,
                                      v152);
                                }
                                v53 += 4;
                              }
                              v175.rclBounds.left = v128;
                              v175.rclBounds.top = (int)v129;
                              v175.rclBounds.right = (int)v130;
                              v175.rclBounds.bottom = v131;
                            }
                            goto LABEL_69;
                          }
                          PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v166);
                          if ( v168 )
                          {
                            if ( ((v20 & 2) == 0 || EPATHOBJ::bAddPolygon((EPATHOBJ *)v166, v120, &v189, v121))
                              && ((v20 & 0x10) == 0
                               || EPATHOBJ::bAddPolygon((EPATHOBJ *)v166, v120, (const struct _POINTL *)&v196, v121)) )
                            {
                              v151 = v48;
                              v150 = (struct _POINTL *)v153;
                              v149 = (struct _XLATEOBJ *)v38;
                              v20 = *(_DWORD *)EPATHOBJ_bTextOutSimpleFill(&v156, v166, a2, &v154, v162) != 0 ? v20 : 0;
                            }
                            else
                            {
                              v20 = 0;
                            }
                          }
                          PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v166);
                        }
                        v49 = (LONG)v172[0];
                        v50 = (struct _SURFOBJ *)HIDWORD(v172[0]);
                        v51 = (struct _SURFOBJ *)LODWORD(v172[1]);
                        v52 = HIDWORD(v172[1]);
                        goto LABEL_47;
                      }
                      v75 = 0;
                      if ( (v17 & 4) == 0 )
                        v75 = v20;
                      v20 = v75;
                      XEPATHOBJ::XEPATHOBJ((XEPATHOBJ *)v166, a2);
                      if ( !v168 )
                      {
LABEL_112:
                        EPATHOBJ::vUnlock((EPATHOBJ *)v166);
                        CAutoTGO::vUnguard((CAutoTGO *)v169);
LABEL_70:
                        if ( (v187 & 0x801) != 0 )
                        {
                          if ( (v187 & 1) != 0 )
                            FreeTmpBuffer(v182);
                          if ( (v187 & 0x800) != 0 )
                            Win32FreePool(v188);
                        }
                        RFONTOBJ::~RFONTOBJ((RFONTOBJ *)&v154);
                        if ( v25 )
                          TXTCLEANUP::vMopUp((TXTCLEANUP *)&v163);
                        v13 = v164;
                        goto LABEL_78;
                      }
                      if ( ((v20 & 8) == 0 || (unsigned int)bAddRectToPath((struct EPATHOBJ *)v166, &v173))
                        && ((v20 & 2) == 0 || EPATHOBJ::bAddPolygon((EPATHOBJ *)v166, v76, &v189, v77))
                        && ((v20 & 0x10) == 0
                         || EPATHOBJ::bAddPolygon((EPATHOBJ *)v166, v76, (const struct _POINTL *)&v196, v77)) )
                      {
                        if ( (v20 & 1) == 0 || v31 && !(unsigned int)bAddRectToPath((struct EPATHOBJ *)v166, v31) )
                          goto LABEL_279;
                        if ( (v187 & 0x1400) != 0 )
                          v136 = ESTROBJ::bLinkedTextToPath(&pstro, (struct EPATHOBJ *)v166);
                        else
                          v136 = ESTROBJ::bTextToPathWorkhorse(&pstro, (struct EPATHOBJ *)v166);
                        if ( v136 )
                        {
                          if ( v30 )
                          {
                            while ( !(unsigned int)ERECTL::bEmpty((ERECTL *)v30) )
                            {
                              if ( !(unsigned int)bAddRectToPath((struct EPATHOBJ *)v166, v30) )
                                goto LABEL_281;
                              ++v30;
                            }
                          }
LABEL_279:
                          if ( (v20 & 4) == 0
                            || (unsigned int)ESTROBJ::bExtraRectsToPath((ESTROBJ *)&pstro, (struct EPATHOBJ *)v166) )
                          {
                            goto LABEL_112;
                          }
                        }
                      }
LABEL_281:
                      v20 = 0;
                      goto LABEL_112;
                    }
                    v69 = ESTROBJ::bOpaqueArea((ESTROBJ *)&pstro, &v196, &pstro.rclBkGround);
                    v70 = v69;
                    v71 = pstro.rclBkGround.right;
                    v72 = pstro.rclBkGround.left;
                    if ( (v154[3] & 0x10000000) != 0 )
                    {
                      v72 = pstro.rclBkGround.left - 1;
                      v71 = pstro.rclBkGround.right + 1;
                      --pstro.rclBkGround.left;
                      ++pstro.rclBkGround.right;
                    }
                    if ( (v187 & 0x1400) != 0 )
                    {
                      ESTROBJ::vEudcOpaqueArea((ESTROBJ *)&pstro, &v196, v69);
                      v71 = pstro.rclBkGround.right;
                      v72 = pstro.rclBkGround.left;
                    }
                    v29 = (int)v172[0];
                    v27 = (int)v172[1];
                    if ( LODWORD(v172[0]) == LODWORD(v172[1])
                      || (v28 = HIDWORD(v172[0]), v26 = HIDWORD(v172[1]), HIDWORD(v172[0]) == HIDWORD(v172[1])) )
                    {
                      v73 = pstro.rclBkGround.top;
                      v29 = v72;
                      v74 = pstro.rclBkGround.bottom;
                      v28 = pstro.rclBkGround.top;
                      v27 = v71;
                      v172[0] = (struct _SURFOBJ *)__PAIR64__(pstro.rclBkGround.top, v72);
                      LODWORD(v172[1]) = v71;
                    }
                    else
                    {
                      v73 = pstro.rclBkGround.top;
                      v74 = pstro.rclBkGround.bottom;
                      if ( v72 < SLODWORD(v172[0]) )
                        v29 = v72;
                      LODWORD(v172[0]) = v29;
                      if ( pstro.rclBkGround.top < SHIDWORD(v172[0]) )
                        v28 = pstro.rclBkGround.top;
                      HIDWORD(v172[0]) = v28;
                      if ( v71 > SLODWORD(v172[1]) )
                        v27 = v71;
                      LODWORD(v172[1]) = v27;
                      if ( pstro.rclBkGround.bottom <= SHIDWORD(v172[1]) )
                      {
LABEL_106:
                        if ( a10 == 2 )
                        {
                          if ( v70 )
                            v20 |= 0x10u;
                          else
                            p_rclBkGround = (struct tagRECT *)&pstro.rclBkGround;
                        }
                        v32 = v72 >= v71 || v73 >= v74;
                        if ( (v20 & 8) == 0
                          || v173.bottom < v74
                          || v173.left > v72
                          || v173.top > v73
                          || v173.right < v71
                          || v32 )
                        {
                          v33 = p_rclBkGround;
                          if ( !p_rclBkGround )
                          {
                            if ( v32 )
                              goto LABEL_28;
                            goto LABEL_27;
                          }
                        }
                        else
                        {
                          v33 = (const struct tagRECT *)&v173;
                          v20 &= ~8u;
                          p_rclBkGround = (struct tagRECT *)&v173;
                        }
                        if ( (unsigned int)IsRectEmptyInl(v33) )
                        {
LABEL_28:
                          if ( (v158 & 0xA0) != 0 )
                          {
                            if ( v185 )
                            {
                              v30 = (struct _RECTL *)v186;
                              v123 = (ERECTL *)v186;
                              if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)v186) )
                              {
                                do
                                {
                                  ERECTL::operator+=(v172, v123);
                                  v123 = (ERECTL *)((char *)v123 + 16);
                                }
                                while ( !(unsigned int)ERECTL::bEmpty(v123) );
                                v26 = HIDWORD(v172[1]);
                                v27 = (int)v172[1];
                                v28 = HIDWORD(v172[0]);
                                v29 = (int)v172[0];
                              }
                            }
                            else
                            {
                              v20 |= 4u;
                            }
                          }
                          if ( (v17 & 4) == 0 )
                            goto LABEL_30;
                          v78 = v173.left <= v29;
                          if ( v173.left <= v29 )
                          {
                            if ( v173.bottom >= v26 && v173.top <= v28 && v173.right >= v27 )
                            {
                              LOBYTE(v17) = -5;
                              goto LABEL_30;
                            }
                            v78 = v173.left <= v29;
                          }
                          if ( !v78 )
                            v29 = v173.left;
                          LODWORD(v172[0]) = v29;
                          if ( v173.top > v28 )
                            v28 = v173.top;
                          HIDWORD(v172[0]) = v28;
                          if ( v173.right < v27 )
                            v27 = v173.right;
                          LODWORD(v172[1]) = v27;
                          if ( v173.bottom < v26 )
                            v26 = v173.bottom;
                          HIDWORD(v172[1]) = v26;
                          if ( v27 < v29 )
                          {
                            v29 = v27;
                            LODWORD(v172[0]) = v27;
                          }
                          else if ( v26 < v28 )
                          {
                            v28 = v26;
                            HIDWORD(v172[0]) = v26;
                          }
                          goto LABEL_30;
                        }
LABEL_27:
                        v20 |= 1u;
                        goto LABEL_28;
                      }
                    }
                    HIDWORD(v172[1]) = v74;
                    v26 = v74;
                    goto LABEL_106;
                  }
                  v153 = (struct _BRUSHOBJ *)__PAIR64__(v14, v160);
                  EXFORMOBJ::bXform((EXFORMOBJ *)&v161, (const struct _POINTL *)&v153, (struct _POINTFIX *)&v153, 1u);
                }
                v61 = *(_DWORD *)&v161.iSrcType + (_DWORD)v153;
                v62 = HIDWORD(v153);
                LODWORD(v153) = *(_DWORD *)&v161.iSrcType + (_DWORD)v153;
                goto LABEL_90;
              }
            }
            *(struct _RECTL *)v172 = v173;
            v26 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v173, 12));
            v28 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v173, 4));
            v27 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v173, 8));
            v29 = _mm_cvtsi128_si32((__m128i)v173);
          }
          else
          {
            v26 = HIDWORD(v172[1]);
            v28 = HIDWORD(v172[0]);
          }
          v14 = v158;
          goto LABEL_16;
        }
        PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v166);
        if ( v168 )
        {
          if ( EPATHOBJ::bAddPolygon((EPATHOBJ *)v166, v96, &v189, v97) )
          {
            v138 = *(_QWORD *)a2;
            v174 = 0;
            v174.top = 16 * (*(_DWORD *)(v138 + 1004) - HIDWORD(v157));
            v174.bottom = 16 * (*(_DWORD *)(v138 + 1012) - HIDWORD(v157));
            RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&p_rclBkGround, (struct EPATHOBJ *)v166, 1u, &v174);
            if ( p_rclBkGround )
            {
              v139 = *(_QWORD *)a2;
              v25 = a2;
              v163 = a2;
              *(_QWORD *)(v139 + 1128) = p_rclBkGround;
              if ( (unsigned int)DC::bTightenRao(*(DC **)a2) )
                LOBYTE(v17) = v17 & 0xFB;
            }
          }
        }
        if ( (v17 & 4) != 0 )
          v20 = 0;
        PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v166);
        v93 = v173.bottom;
        v98 = 0;
        if ( (v17 & 4) == 0 )
          v98 = a8;
        a8 = v98;
        v99 = 0;
        if ( (v17 & 4) == 0 )
          v99 = v17;
        LOBYTE(v17) = v99;
      }
      v91 = v173.top;
      v90 = v173.right;
      v89 = v173.left;
      LODWORD(v157) = v173.top;
      v161.cEntries = v93;
      goto LABEL_173;
    }
  }
  v20 = 0;
LABEL_78:
  v58 = v20 != 0;
LABEL_79:
  ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(v13, v58);
  return v13;
}

```

## disassembly

```asm
0x140070514  push    rbp
0x140070516  push    rbx
0x140070517  push    rsi
0x140070518  push    rdi
0x140070519  push    r12
0x14007051b  push    r13
0x14007051d  push    r14
0x14007051f  push    r15
0x140070521  lea     rbp, [rsp-2F8h]
0x140070529  sub     rsp, 408h
0x140070530  mov     rax, cs:__security_cookie
0x140070537  xor     rax, rsp
0x14007053a  mov     [rbp+330h+var_50], rax
0x140070541  mov     rax, [rbp+330h+arg_30]
0x140070548  mov     r12, rdx
0x14007054b  mov     r15d, [rbp+330h+arg_20]
0x140070552  mov     rbx, rcx
0x140070555  mov     rdx, [rbp+330h+arg_40]
0x14007055c  mov     edi, r9d
0x14007055f  mov     r13, [rbp+330h+arg_28]
0x140070566  mov     [rbp+330h+var_340], rax
0x14007056a  mov     rax, [rbp+330h+arg_50]
0x140070571  mov     [rbp+330h+var_2B0], rax
0x140070578  mov     eax, r15d
0x14007057b  and     al, 10h
0x14007057d  mov     [rbp+330h+var_350], rcx
0x140070581  mov     rcx, [r12]
0x140070585  neg     al
0x140070587  mov     [rbp+330h+var_388], r9d
0x14007058b  sbb     eax, eax
0x14007058d  mov     [rbp+330h+var_380], r8d
0x140070591  and     eax, 2
0x140070594  mov     [rbp+330h+var_2A8], rdx
0x14007059b  add     eax, 2
0x14007059e  mov     dword ptr [rbp+330h+var_3B0], eax
0x1400705a1  mov     eax, [rcx+0F8h]
0x1400705a7  test    al, 1
0x1400705a9  jnz     loc_140071C50
0x1400705af  test    dword ptr [rcx+24h], 10000h
0x1400705b6  jnz     loc_140071C5F
0x1400705bc  mov     eax, r15d
0x1400705bf  and     eax, 2000h
0x1400705c4  mov     dword ptr [rbp+330h+var_398], eax
0x1400705c7  jnz     loc_140071A27
0x1400705cd  and     r15d, 0FFFFC36Fh
0x1400705d4  mov     edx, 0FFFFFFF9h
0x1400705d9  test    r13, r13
0x1400705dc  jnz     loc_140070EB1
0x1400705e2  and     r15d, edx
0x1400705e5  mov     rcx, [r12]
0x1400705e9  test    rcx, rcx
0x1400705ec  jz      loc_140070F29
0x1400705f2  test    r15d, r15d
0x1400705f5  jnz     loc_140070F1B
0x1400705fb  mov     eax, [rcx+0F8h]
0x140070601  and     eax, 1
0x140070604  jz      short loc_140070610
0x140070606  test    r15b, 4
0x14007060a  jnz     loc_140070F29
0x140070610  xor     r11d, r11d
0x140070613  mov     dword ptr [rbp+330h+var_378.pulXlate], 0
0x14007061a  mov     [rbp+330h+var_384], r11d
0x14007061e  xorps   xmm0, xmm0
0x140070621  movdqa  xmmword ptr [rbp+330h+var_2A0], xmm0
0x140070629  mov     r14d, 80h
0x14007062f  test    eax, eax
0x140070631  jnz     loc_140071C69
0x140070637  mov     eax, [rcx+28h]
0x14007063a  lea     rbx, [rcx+400h]
0x140070641  test    al, 1
0x140070643  jnz     short loc_14007064C
0x140070645  lea     rbx, [rcx+3F8h]
0x14007064c  mov     rbx, [rbx]
0x14007064f  mov     [rbp+330h+var_390], rbx
0x140070653  mov     eax, dword ptr [rbp+330h+var_390]
0x140070656  shl     eax, 4
0x140070659  lea     rdx, [rbp+330h+var_378]
0x14007065d  shr     rbx, 20h
0x140070661  mov     r8d, 204h
0x140070667  mov     dword ptr [rbp+330h+var_378.iSrcType], eax
0x14007066a  shl     ebx, 4
0x14007066d  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140070674  nop     dword ptr [rax+rax+00h]
0x140070679  xor     esi, esi
0x14007067b  mov     [rbp+330h+var_358], rsi
0x14007067f  test    r13, r13
0x140070682  jnz     loc_140070FEE
0x140070688  mov     r9d, dword ptr [rbp+330h+var_2A0+0Ch]
0x14007068f  mov     r10d, dword ptr [rbp+330h+var_2A0+8]
0x140070696  mov     edx, dword ptr [rbp+330h+var_2A0+4]
0x14007069c  mov     r8d, dword ptr [rbp+330h+var_2A0]
0x1400706a3  xor     r13d, r13d
0x1400706a6  mov     [rbp+330h+var_3A0], 0
0x1400706ae  mov     qword ptr [rbp+330h+var_280.left], r13
0x1400706b5  mov     [rbp+330h+var_3A8], r13
0x1400706b9  mov     [rbp+330h+var_E8], r13d
0x1400706c0  cmp     [rbp+330h+arg_38], r13d
0x1400706c7  jz      short loc_140070720
0x1400706c9  mov     rax, [r12]
0x1400706cd  lea     rcx, [rbp+330h+var_3A8]; this
0x1400706d1  mov     r9d, dword ptr [rbp+330h+var_3B0]; unsigned int
0x1400706d5  mov     rdx, r12; struct XDCOBJ *
0x1400706d8  mov     r8d, [rax+0F8h]
0x1400706df  and     r8d, 1; int
0x1400706e3  call    ?bInit@RFONTOBJ@@QEAAHAEAVXDCOBJ@@HK@Z; RFONTOBJ::bInit(XDCOBJ &,int,ulong)
0x1400706e8  test    eax, eax
0x1400706ea  jz      short loc_1400706F5
0x1400706ec  mov     rcx, [rbp+330h+var_3A8]
0x1400706f0  call    ??$GreAcquireSemaphore@$04PEAVRFONT@@@@YAXPEAVRFONT@@@Z; GreAcquireSemaphore<5,RFONT *>(RFONT *)
0x1400706f5  mov     rax, [rbp+330h+var_3A8]
0x1400706f9  test    rax, rax
0x1400706fc  jnz     loc_140070B50
0x140070702  mov     r9d, dword ptr [rbp+330h+var_2A0+0Ch]
0x140070709  xor     r14d, r14d
0x14007070c  mov     r10d, dword ptr [rbp+330h+var_2A0+8]
0x140070713  mov     edx, dword ptr [rbp+330h+var_2A0+4]
0x140070719  mov     r8d, dword ptr [rbp+330h+var_2A0]
0x140070720  mov     edi, r13d
0x140070723  mov     rbx, r13
0x140070726  jmp     loc_1400707C7
0x14007072b  cmp     ebx, eax
0x14007072d  jge     loc_140070DDD
0x140070733  xor     edi, edi
0x140070735  test    r14b, 8
0x140070739  jnz     loc_1400715CA
0x14007073f  mov     rax, [rbp+330h+var_3A0]
0x140070743  test    rax, rax
0x140070746  jnz     loc_140071612
0x14007074c  test    edi, edi
0x14007074e  jnz     short loc_140070754
0x140070750  or      r14d, 1
0x140070754  test    byte ptr [rbp+330h+var_388], 0A0h
0x140070758  jnz     loc_140071803
0x14007075e  test    r15b, 4
0x140070762  jnz     loc_140070E2C
0x140070768  test    byte ptr [rbp+330h+var_388], 1
0x14007076c  mov     rbx, [rbp+330h+var_3A0]
0x140070770  mov     edi, [rbp+330h+var_384]
0x140070773  mov     [rbp+330h+var_3A0], rbx
0x140070777  mov     qword ptr [rbp+330h+var_280.left], r13
0x14007077e  jz      loc_1400711DC
0x140070784  mov     rax, [r12]
0x140070788  mov     rcx, [rax+3D0h]
0x14007078f  mov     eax, [rbp+330h+var_180]
0x140070795  add     [rcx+8], eax
0x140070798  mov     rax, [r12]
0x14007079c  mov     rcx, [rax+3D0h]
0x1400707a3  mov     eax, [rbp+330h+var_17C]
0x1400707a9  add     [rcx+0Ch], eax
0x1400707ac  mov     r9d, dword ptr [rbp+330h+var_2A0+0Ch]
0x1400707b3  mov     r10d, dword ptr [rbp+330h+var_2A0+8]
0x1400707ba  mov     edx, dword ptr [rbp+330h+var_2A0+4]
0x1400707c0  mov     r8d, dword ptr [rbp+330h+var_2A0]
0x1400707c7  mov     r11, [r12]
0x1400707cb  mov     eax, [r11+0F8h]
0x1400707d2  test    al, 1
0x1400707d4  jnz     loc_140070DE7
0x1400707da  cmp     edx, r9d
0x1400707dd  jz      loc_140070ADA
0x1400707e3  cmp     r8d, r10d
0x1400707e6  jz      loc_140070ADA
0x1400707ec  mov     ebx, [r11+24h]
0x1400707f0  test    bl, 0E0h
0x1400707f3  jnz     loc_140070F31
0x1400707f9  test    edi, edi
0x1400707fb  jnz     loc_1400711D1
0x140070801  test    r15b, 4
0x140070805  jnz     loc_1400711D1
0x14007080b  xor     r9d, r9d
0x14007080e  mov     rcx, r12; this
0x140070811  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x140070816  lea     r8, [rbp+330h+var_2A0]
0x14007081d  mov     [rbp+330h+var_238], 0
0x140070828  mov     rdx, rax
0x14007082b  mov     [rbp+330h+var_220], 0
0x140070836  lea     rcx, [rbp+330h+var_270]
0x14007083d  mov     [rbp+330h+var_218], 0
0x140070847  mov     [rbp+330h+var_1F0], 1
0x140070851  mov     [rbp+330h+var_1E0], 0
0x14007085c  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x140070863  nop     dword ptr [rax+rax+00h]
0x140070868  mov     edx, [rbp+330h+var_270.rclBounds.top]; struct ECLIPOBJ *
0x14007086e  mov     r8d, [rbp+330h+var_270.rclBounds.bottom]
0x140070875  mov     ecx, [rbp+330h+var_270.rclBounds.left]
0x14007087b  mov     eax, [rbp+330h+var_270.rclBounds.right]
0x140070881  mov     dword ptr [rbp+330h+var_2A0], ecx
0x140070887  mov     dword ptr [rbp+330h+var_2A0+4], edx
0x14007088d  mov     dword ptr [rbp+330h+var_2A0+8], eax
0x140070893  mov     dword ptr [rbp+330h+var_2A0+0Ch], r8d
0x14007089a  cmp     edx, r8d
0x14007089d  jz      loc_140070ADA
0x1400708a3  cmp     ecx, eax
0x1400708a5  jz      loc_140070ADA
0x1400708ab  mov     rax, [r12]
0x1400708af  mov     ecx, [rax+24h]
0x1400708b2  test    cl, 0E0h
0x1400708b5  jnz     loc_14007113B
0x1400708bb  mov     rax, [r12]
0x1400708bf  mov     r15, [rax+1F0h]
0x1400708c6  test    r15, r15
0x1400708c9  jz      loc_140070ADA
0x1400708cf  mov     rcx, r15; struct SURFACE *
0x1400708d2  call    ?DestSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; DestSurfaceAccessCheck(SURFACE *)
0x1400708d7  test    eax, eax
0x1400708d9  jz      loc_140070ADA
0x1400708df  mov     rax, [r15+30h]
0x1400708e3  xor     edx, edx
0x1400708e5  mov     rbx, [r15+0B0h]
0x1400708ec  mov     [rbp+330h+var_360], rax
0x1400708f0  mov     rax, [r12]
0x1400708f4  mov     ecx, [rax+48h]
0x1400708f7  lea     r11, [rax+648h]
0x1400708fe  mov     rdi, [rax+58h]
0x140070902  lea     r13, [rax+5C0h]
0x140070909  mov     [rbp+330h+var_3B0], r11
0x14007090d  mov     [rbp+330h+var_380], ecx
0x140070910  bt      ecx, 1Ch
0x140070914  jb      loc_140071F10
0x14007091a  mov     r10, [r12]
0x14007091e  mov     rax, [r10+3D0h]
0x140070925  mov     r8d, [rax+98h]
0x14007092c  or      r8d, [r10+13Ch]
0x140070933  test    r8b, 0Ch
0x140070937  jnz     loc_140071082
0x14007093d  mov     rbx, [r12]
0x140070941  add     rbx, 4A8h
0x140070948  test    r14b, 1Ah
0x14007094c  jnz     loc_140071627
0x140070952  mov     edx, dword ptr [rbp+330h+var_2A0]
0x140070958  mov     r9d, dword ptr [rbp+330h+var_2A0+4]; struct _SURFOBJ *
0x14007095f  mov     r8d, dword ptr [rbp+330h+var_2A0+8]; struct _SURFOBJ *
0x140070966  mov     r10d, dword ptr [rbp+330h+var_2A0+0Ch]
0x14007096d  test    r14b, 1
0x140070971  jz      loc_140070AD0
0x140070977  xor     edi, edi
0x140070979  cmp     [rbp+330h+var_384], edi
0x14007097c  jnz     loc_140071FB3
0x140070982  mov     r11, [rbp+330h+var_3A0]
0x140070986  test    r11, r11
0x140070989  jnz     loc_140071465
0x14007098f  mov     rax, qword ptr [rbp+330h+var_280.left]
0x140070996  mov     rcx, [rbp+330h+var_360]
0x14007099a  test    rax, rax
0x14007099d  jnz     loc_140071A00
0x1400709a3  test    r14b, 20h
0x1400709a7  jnz     loc_140071B4D
0x1400709ad  mov     rcx, r15; this
0x1400709b0  call    ?pdcoAA@SURFACE@@QEAAPEAVXDCOBJ@@XZ; SURFACE::pdcoAA(void)
0x1400709b5  test    rax, rax
0x1400709b8  jnz     loc_1400720AD
0x1400709be  mov     rcx, r15; this
0x1400709c1  call    ?pfnTextOut@SURFACE@@QEAAP6AHPEAU_SURFOBJ@@PEAU_STROBJ@@PEAU_FONTOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@4PEAU_BRUSHOBJ@@5PEAU_POINTL@@K@ZXZ; SURFACE::pfnTextOut(void)
0x1400709c6  mov     rcx, rax; int (*)(struct _SURFOBJ *, struct _STROBJ *, struct _FONTOBJ *, struct _CLIPOBJ *, struct _RECTL *, struct _RECTL *, struct _BRUSHOBJ *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x1400709c9  mov     [rbp+330h+var_398], rax
0x1400709cd  mov     r10, rax
0x1400709d0  call    ?bSupportsClearTypeAlways@PDEVOBJ@@SA_NP6AHPEAU_SURFOBJ@@PEAU_STROBJ@@PEAU_FONTOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@4PEAU_BRUSHOBJ@@5PEAU_POINTL@@K@Z@Z; PDEVOBJ::bSupportsClearTypeAlways(int (*)(_SURFOBJ *,_STROBJ *,_FONTOBJ *,_CLIPOBJ *,_RECTL *,_RECTL *,_BRUSHOBJ *,_BRUSHOBJ *,_POINTL *,ulong))
0x1400709d5  test    al, al
0x1400709d7  jnz     loc_14007153F
0x1400709dd  mov     rax, [rbp+330h+var_3A8]
0x1400709e1  mov     edx, [rax+0Ch]
0x1400709e4  bt      edx, 10h
0x1400709e8  jnb     short loc_140070A2A
0x1400709ea  mov     rax, [r12]
0x1400709ee  test    dword ptr [rax+48h], 1000000h
0x1400709f5  jnz     loc_1400720BC
0x1400709fb  lea     rax, EngTextOut
0x140070a02  cmp     r10, rax
0x140070a05  jz      short loc_140070A1F
0x140070a07  mov     [r15+98h], r12
0x140070a0e  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140070a13  test    rax, rax
0x140070a16  jz      short loc_140070A1F
0x140070a18  mov     [rax+120h], r12
0x140070a1f  lea     r10, ?SpTextOut@@YAHPEAU_SURFOBJ@@PEAU_STROBJ@@PEAU_FONTOBJ@@PEAU_CLIPOBJ@@PEAU_RECTL@@4PEAU_BRUSHOBJ@@5PEAU_POINTL@@K@Z; SpTextOut(_SURFOBJ *,_STROBJ *,_FONTOBJ *,_CLIPOBJ *,_RECTL *,_RECTL *,_BRUSHOBJ *,_BRUSHOBJ *,_POINTL *,ulong)
0x140070a26  mov     [rbp+330h+var_398], r10
0x140070a2a  test    r14b, 40h
0x140070a2e  jnz     loc_140071A85
0x140070a34  inc     dword ptr [r15+5Ch]
0x140070a38  test    r14b, 4
0x140070a3c  jnz     loc_140071B90
0x140070a42  test    [rbp+330h+var_E8], 1400h
0x140070a4c  mov     rdx, [rbp+330h+var_3A0]
0x140070a50  jnz     loc_140071758
0x140070a56  mov     rax, [rbp+330h+var_3B0]
0x140070a5a  lea     r9, [rbp+330h+var_270]
0x140070a61  mov     r8, [rbp+330h+var_3A8]
0x140070a65  lea     rcx, [r15+18h]
0x140070a69  mov     dword ptr [rsp+440h+var_3F8], 0D0Dh
0x140070a71  mov     [rsp+440h+var_400], rbx; struct _POINTL *
0x140070a76  mov     [rsp+440h+var_408], rax; struct _POINTL *
0x140070a7b  mov     rax, qword ptr [rbp+330h+var_280.left]
0x140070a82  mov     [rsp+440h+var_410], r13
0x140070a87  mov     [rsp+440h+var_418], rdx; struct _XLATEOBJ *
0x140070a8c  lea     rdx, [rbp+330h+pstro]
0x140070a93  mov     [rsp+440h+var_420], rax
0x140070a98  mov     rax, r10
0x140070a9b  call    _guard_dispatch_icall
0x140070aa0  neg     eax
0x140070aa2  sbb     ecx, ecx
0x140070aa4  and     r14d, ecx
  ... truncated ...
```
