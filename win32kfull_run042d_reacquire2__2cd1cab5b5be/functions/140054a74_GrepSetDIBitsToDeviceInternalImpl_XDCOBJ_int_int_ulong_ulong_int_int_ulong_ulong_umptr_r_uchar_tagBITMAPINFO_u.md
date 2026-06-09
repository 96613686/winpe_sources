# GrepSetDIBitsToDeviceInternalImpl(XDCOBJ &,int,int,ulong,ulong,int,int,ulong,ulong,umptr_r<uchar> &,tagBITMAPINFO *,ulong,uint,int,void *)

- ea: `0x140054a74`
- end: `0x140055f6c`
- name: `?GrepSetDIBitsToDeviceInternalImpl@@YAHAEAVXDCOBJ@@HHKKHHKKAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@KIHPEAX@Z`
- size: `5368`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x140054780`
- `0x1400a55dc`
- `0x140113840`

## callees

- `0x1400512b0`
- `0x140054a74`
- `0x140055f74`
- `0x140056bc8`
- `0x14005d010`
- `0x140067498`
- `0x1400697e4`
- `0x14006bd2c`
- `0x14008cfa0`
- `0x14009a398`
- `0x14018d8f4`
- `0x1401cf360`
- `0x140226ddc`
- `0x14025acac`
- `0x140298e04`
- `0x14032952c`
- `0x140342fa0`
- `0x140343080`
- `0x140343200`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140055320`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140055744`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140055320`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140055744`
- `win32kbase!FreeThreadBufferWithTag` at `0x140055662`
- `win32kbase!FreeThreadBufferWithTag` at `0x140055662`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14005563e`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14005563e`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400552b2`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400552b2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400554ed`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005582d`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400554ed`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005582d`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140055333`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140055333`
- `win32kbase!EngSetLastError` at `0x140054c5e`
- `win32kbase!EngSetLastError` at `0x140055eef`
- `win32kbase!EngSetLastError` at `0x140054c5e`
- `win32kbase!EngSetLastError` at `0x140055eef`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140054db7`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140054db7`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140054f84`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140054f84`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x140055672`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x140055672`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140055082`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140055a0a`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140055082`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140055a0a`
- `win32kbase!?vUpdateTime@XEPALOBJ@@QEAAXXZ` at `0x14005510c`
- `win32kbase!?vUpdateTime@XEPALOBJ@@QEAAXXZ` at `0x14005510c`
- `win32kbase!?bIsPalDefault@XEPALOBJ@@QEBAHXZ` at `0x14005500c`
- `win32kbase!?bIsPalDefault@XEPALOBJ@@QEBAHXZ` at `0x14005500c`

## pseudocode

```c
__int64 __fastcall GrepSetDIBitsToDeviceInternalImpl(
        struct XDCOBJ *a1,
        LONG a2,
        LONG a3,
        unsigned int a4,
        unsigned int a5,
        LONG a6,
        int a7,
        int a8,
        unsigned int a9,
        _QWORD *a10,
        unsigned int *a11,
        unsigned int a12,
        unsigned int a13,
        int a14,
        __int64 a15)
{
  LONG left; // r11d
  __int64 v17; // rdi
  __int64 v18; // rax
  int v19; // r10d
  unsigned int v20; // esi
  __int64 v21; // rax
  __int64 v22; // r12
  int v23; // ecx
  unsigned int v24; // r8d
  __int64 v25; // r9
  unsigned int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // r15d
  unsigned int v29; // ecx
  unsigned __int64 v30; // rdx
  int v31; // r9d
  unsigned __int64 v32; // rdx
  ULONG v33; // ecx
  unsigned int v35; // r12d
  int v36; // ecx
  struct XDCOBJ *v37; // r14
  unsigned int v38; // esi
  __int64 v39; // rax
  _DWORD *v40; // rdx
  int v41; // ecx
  unsigned int v42; // r8d
  int v43; // eax
  LONG top; // edx
  LONG v45; // ecx
  _DWORD *v46; // rax
  int v47; // ecx
  _DWORD *v48; // rcx
  __int64 v49; // rcx
  unsigned __int64 v50; // rbx
  __int64 v51; // rax
  unsigned int v52; // r14d
  __int64 v53; // rdi
  int IsPalDefault; // eax
  _QWORD *v55; // r8
  __int64 v56; // rbx
  int v57; // esi
  unsigned int v58; // edx
  _BYTE *v59; // rcx
  _BYTE *v60; // rdx
  char v61; // al
  __int64 XlateObject; // rax
  int v63; // r12d
  unsigned int v64; // r10d
  unsigned int v65; // eax
  unsigned int v66; // ecx
  unsigned __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r9
  struct Gre::Base::SESSION_GLOBALS *v71; // rax
  __int64 v72; // rax
  int bottom; // r11d
  int right; // r14d
  int v75; // edi
  LONG v76; // r15d
  LONG v77; // r9d
  int v78; // edx
  LONG v79; // ecx
  struct _SURFOBJ *v80; // r13
  LONG v81; // r10d
  __int64 v82; // r12
  LONG v83; // esi
  LONG v84; // r12d
  LONG v85; // edx
  LONG v86; // r8d
  LONG v87; // eax
  __int64 v88; // r9
  __int64 v89; // rdx
  __int64 v90; // rax
  __int64 v91; // r8
  __int64 v92; // rcx
  int v93; // r10d
  LONG v94; // r15d
  LONG v95; // r14d
  XDCOBJ *v96; // r14
  struct REGION *v97; // rax
  int v98; // edi
  __int64 v99; // rax
  unsigned __int64 v100; // rsi
  __int64 v101; // rcx
  int v102; // ecx
  int v103; // ecx
  int v104; // eax
  Gre::Base *v105; // rcx
  int v106; // eax
  int v107; // r9d
  XDCOBJ *v108; // r14
  struct REGION *v109; // rax
  struct ECLIPOBJ *v110; // rdx
  __int64 v111; // rax
  __int64 v112; // rcx
  __int16 v113; // r8
  unsigned __int64 v114; // r14
  int Xlate; // eax
  __int64 v116; // r8
  float v117; // xmm2_4
  __m128i v118; // xmm0
  __m128i v119; // xmm1
  __m128i v120; // xmm3
  int v121; // r8d
  __m128i v122; // xmm4
  unsigned int v123; // edx
  float v124; // xmm0_4
  __int64 v125; // rax
  __int64 v126; // rax
  int v127; // r8d
  unsigned int v128; // edx
  __int64 v129; // rax
  __int64 v130; // rax
  int v131; // esi
  unsigned int v132; // r8d
  __int64 v133; // rax
  __int64 v134; // rax
  int v135; // esi
  unsigned int v136; // ecx
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // r8
  int v140; // eax
  struct _CLIPOBJ *v141; // [rsp+20h] [rbp-E0h]
  int v142; // [rsp+60h] [rbp-A0h]
  int v143; // [rsp+64h] [rbp-9Ch]
  unsigned int v144; // [rsp+68h] [rbp-98h]
  unsigned int v145; // [rsp+6Ch] [rbp-94h]
  int v146; // [rsp+70h] [rbp-90h]
  LONG v147; // [rsp+70h] [rbp-90h]
  unsigned __int64 v149; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v150; // [rsp+80h] [rbp-80h]
  unsigned int v151; // [rsp+84h] [rbp-7Ch]
  unsigned int v152; // [rsp+88h] [rbp-78h]
  unsigned int v153; // [rsp+8Ch] [rbp-74h]
  __int64 v154; // [rsp+90h] [rbp-70h]
  __int64 v155; // [rsp+98h] [rbp-68h] BYREF
  __int64 v156; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v157; // [rsp+A8h] [rbp-58h]
  __int64 v158; // [rsp+B0h] [rbp-50h]
  __int64 v159; // [rsp+B8h] [rbp-48h]
  int v160; // [rsp+C0h] [rbp-40h]
  LONG v161; // [rsp+C4h] [rbp-3Ch]
  struct XDCOBJ *v162; // [rsp+C8h] [rbp-38h]
  __int64 v163; // [rsp+D0h] [rbp-30h] BYREF
  int v164; // [rsp+D8h] [rbp-28h]
  LONG v165; // [rsp+E0h] [rbp-20h] BYREF
  LONG v166; // [rsp+E4h] [rbp-1Ch]
  unsigned int v167; // [rsp+E8h] [rbp-18h]
  LONG v168; // [rsp+ECh] [rbp-14h]
  void *Src; // [rsp+F0h] [rbp-10h]
  _QWORD *v170; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v171; // [rsp+100h] [rbp+0h]
  __m128i v172; // [rsp+108h] [rbp+8h] BYREF
  __m128i v173; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v174[3]; // [rsp+128h] [rbp+28h] BYREF
  HDC v175[3]; // [rsp+140h] [rbp+40h] BYREF
  char v176; // [rsp+158h] [rbp+58h]
  struct _RECTL v177; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _RECTL v178; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v179[4]; // [rsp+200h] [rbp+100h] BYREF
  __m128i v180; // [rsp+204h] [rbp+104h] BYREF
  __int64 v181; // [rsp+238h] [rbp+138h]
  __int64 v182; // [rsp+250h] [rbp+150h]
  int v183; // [rsp+258h] [rbp+158h]
  int v184; // [rsp+280h] [rbp+180h]
  __int64 v185; // [rsp+290h] [rbp+190h]
  unsigned int v186; // [rsp+350h] [rbp+250h]

  v162 = a1;
  left = a2;
  v17 = *(_QWORD *)a1;
  v161 = a6;
  v171 = a15;
  v18 = *(_QWORD *)(v17 + 976);
  v167 = a4;
  v172.m128i_i64[0] = (__int64)a10;
  if ( (*(_DWORD *)(v18 + 108) & 1) != 0 )
    left = a4 + a2 - 1;
  v19 = 0;
  if ( !a11 )
    goto LABEL_29;
  if ( !*a10 )
    goto LABEL_29;
  v20 = a12;
  if ( a12 > 2 )
    goto LABEL_29;
  if ( a13 < 0x28 )
    goto LABEL_29;
  v21 = *a11;
  v143 = v21;
  if ( (unsigned int)v21 < 0x28 )
    goto LABEL_29;
  v22 = a11[1];
  v168 = v22;
  if ( (int)v22 <= 0 )
    goto LABEL_29;
  v23 = a11[2];
  if ( !v23 )
    goto LABEL_29;
  v24 = a11[4];
  v153 = v24;
  v156 = 0;
  v157 = 0;
  v159 = 0;
  v158 = 0;
  if ( v23 < 0 )
  {
    LODWORD(v159) = 1;
    if ( v24 > 0xC )
      goto LABEL_29;
    v107 = 7225;
    if ( !_bittest(&v107, v24) )
      goto LABEL_29;
    v23 = -v23;
  }
  v25 = *((unsigned __int16 *)a11 + 7);
  v146 = v23;
  v160 = 0;
  if ( v24 != 3 )
  {
    v152 = 0;
    Src = (char *)a11 + v21;
    v151 = 0;
    v150 = 0;
    if ( !v24 )
    {
      if ( (_DWORD)v25 != 1 )
      {
        if ( (_DWORD)v25 != 4 )
        {
          if ( (_DWORD)v25 != 8 )
          {
            v145 = 0;
            v26 = 0;
            v27 = 0;
            if ( a12 != 1 )
              v26 = a12;
            a12 = v26;
            v144 = 512;
            v20 = v26;
            if ( (_WORD)v25 == 16 )
            {
              LODWORD(v156) = 4;
              v28 = 2;
              v152 = 31744;
              v151 = 992;
              v150 = 31;
            }
            else
            {
              if ( (_WORD)v25 != 24 )
              {
                if ( (_DWORD)v25 == 32 )
                {
                  LODWORD(v156) = 6;
                  v28 = 8;
LABEL_22:
                  v29 = v22 * v25;
                  if ( (unsigned __int64)(v22 * v25) > 0xFFFFFFFF )
                    goto LABEL_26;
                  v30 = v29 + 31;
                  if ( (unsigned int)v30 < v29 )
                    goto LABEL_26;
                  v31 = a9;
                  v142 = a9;
                  v32 = a9 * ((v30 >> 3) & 0x1FFFFFFC);
                  if ( v32 > 0xFFFFFFFF )
                  {
                    HIDWORD(v157) = -1;
LABEL_26:
                    v33 = 534;
LABEL_27:
                    EngSetLastError(v33);
                    return 0;
                  }
                  goto LABEL_40;
                }
LABEL_29:
                v33 = 87;
                goto LABEL_27;
              }
              LODWORD(v156) = 5;
              v28 = 8;
            }
            a12 = v26;
            goto LABEL_22;
          }
LABEL_237:
          LODWORD(v156) = 3;
          v27 = 256;
          goto LABEL_107;
        }
        goto LABEL_238;
      }
      goto LABEL_106;
    }
    if ( v24 == 10 )
    {
      if ( !(unsigned int)DC::bIsCMYKColor((DC *)v17) )
        goto LABEL_29;
      if ( (_DWORD)v25 != 1 )
      {
        if ( (_DWORD)v25 != 4 )
        {
          if ( (_DWORD)v25 != 8 )
          {
            if ( (_DWORD)v25 != 32 )
              goto LABEL_29;
            v27 = v64;
            LODWORD(v156) = 6;
            v28 = 16;
            v144 = 512;
LABEL_108:
            v145 = v27;
            goto LABEL_22;
          }
          goto LABEL_237;
        }
LABEL_238:
        LODWORD(v156) = 2;
        v27 = 16;
        goto LABEL_107;
      }
LABEL_106:
      LODWORD(v156) = 1;
      v27 = 2;
LABEL_107:
      v28 = 1;
      v144 = 1024;
      goto LABEL_108;
    }
    if ( v24 != 2 )
    {
      if ( v24 != 12 )
      {
        if ( v24 != 1 )
        {
          if ( v24 != 11 )
          {
            if ( v24 == 4 )
            {
              LODWORD(v156) = 9;
            }
            else
            {
              if ( v24 != 5 )
                goto LABEL_29;
              LODWORD(v156) = 10;
            }
            v31 = a9;
            v27 = 0;
            v145 = 0;
            v28 = 8;
            a8 = 0;
            v144 = 512;
            v142 = a9;
LABEL_39:
            LODWORD(v32) = a11[5];
            goto LABEL_40;
          }
          if ( !(unsigned int)DC::bIsCMYKColor((DC *)v17) )
            goto LABEL_29;
          v23 = v146;
        }
        if ( (_WORD)v25 != 8 )
          goto LABEL_29;
        v27 = 256;
        LODWORD(v156) = 8;
        v145 = 256;
LABEL_38:
        v160 = 1;
        v31 = v23;
        v142 = v23;
        v28 = 1;
        a8 = v19;
        v144 = 1024;
        goto LABEL_39;
      }
      if ( !v17 || !(unsigned int)DC::bIsCMYKColor((DC *)v17) )
        goto LABEL_29;
      v23 = v146;
    }
    if ( (_WORD)v25 != 4 )
      goto LABEL_29;
    LODWORD(v156) = 7;
    v27 = 16;
    v145 = 16;
    goto LABEL_38;
  }
  if ( a13 < 0x34 )
    goto LABEL_29;
  v65 = 0;
  if ( a12 != 1 )
    v65 = a12;
  a12 = v65;
  v20 = v65;
  if ( (_WORD)v25 == 16 )
  {
    LODWORD(v156) = 4;
  }
  else
  {
    if ( (_DWORD)v25 != 32 )
      goto LABEL_29;
    LODWORD(v156) = 6;
  }
  v66 = v22 * v25;
  if ( (unsigned __int64)(v22 * v25) > 0xFFFFFFFF )
    goto LABEL_26;
  v67 = v66 + 31;
  if ( (unsigned int)v67 < v66 )
    goto LABEL_26;
  v31 = a9;
  v142 = a9;
  v32 = a9 * ((v67 >> 3) & 0x1FFFFFFC);
  if ( v32 > 0xFFFFFFFF )
  {
    HIDWORD(v157) = -1;
    goto LABEL_26;
  }
  v144 = 512;
  v27 = 0;
  v152 = a11[10];
  v151 = a11[11];
  v28 = 2;
  v150 = a11[12];
  Src = a11 + 10;
  v145 = 0;
LABEL_40:
  v35 = a11[8];
  HIDWORD(v157) = v32;
  if ( v35 )
  {
    if ( v35 > v27 )
      v35 = v27;
  }
  else
  {
    v35 = v27;
  }
  if ( *(_QWORD *)(v172.m128i_i64[0] + 8) - *(_QWORD *)(v172.m128i_i64[0] + 16) < (unsigned __int64)(unsigned int)v32 )
    goto LABEL_29;
  v36 = v146;
  HIDWORD(v156) = v168;
  if ( v153 - 4 > 1 )
    v36 = v31;
  LODWORD(v157) = v36;
  if ( (*(_DWORD *)(v17 + 36) & 0x10000) != 0 )
    goto LABEL_29;
  *(_QWORD *)&v177.left = *((_QWORD *)v162 + 2);
  v173.m128i_i64[0] = *(_QWORD *)(v17 + 48);
  v166 = a3;
  v37 = v162;
  v165 = left;
  if ( v153 - 4 <= 1 && (!(unsigned int)XDCOBJ::bSupportsPassthroughImage(v162, v153) || v20 || v171) )
  {
    v38 = 0;
    v142 = 0;
  }
  else
  {
    v38 = v142;
  }
  if ( a14 )
  {
    DC::QuickInitXform(v17, &v155, 516);
    v39 = v155;
    if ( (*(_BYTE *)(v155 + 32) & 0x43) != 0x43 )
    {
      bCvtPts1(v155, &v165, 1);
      v39 = v155;
    }
    if ( v38 && a11[4] - 4 <= 1 )
    {
      v38 &= -((*(_BYTE *)(v39 + 32) & 1) != 0);
      v142 = v38;
    }
    left = v165;
  }
  v40 = *(_DWORD **)v37;
  v41 = v167;
  v42 = a5;
  v149 = __PAIR64__(a5, v167);
  v43 = v40[130];
  if ( (v43 & 1) != 0 && (v43 & 2) == 0 )
  {
    v155 = *(_QWORD *)(v40 + 131);
    EPOINTL::vScale((EPOINTL *)&v149, (const struct POINTFL *)&v155);
    left = v165;
    v42 = HIDWORD(v149);
    v41 = v149;
  }
  top = v166;
  v45 = left + v41;
  v178.left = left;
  v178.top = v166;
  v178.right = v45;
  v178.bottom = v166 + v42;
  if ( left > v45 )
  {
    v178.right = left;
    left = v45;
    v178.left = v45;
  }
  if ( v166 > (int)(v166 + v42) )
  {
    v178.bottom = v166;
    top = v166 + v42;
    v178.top = v166 + v42;
  }
  if ( top == v178.bottom || left == v178.right || !v38 )
    return v38;
  v46 = *(_DWORD **)v37;
  v47 = *(_DWORD *)(*(_QWORD *)v37 + 36LL);
  if ( (v47 & 0xE0) != 0 )
  {
    if ( (v47 & 0x20) != 0 )
    {
      if ( left < v46[266] )
      {
        v46[266] = left;
        top = v178.top;
        left = v178.left;
      }
      if ( top < v46[267] )
      {
        v46[267] = top;
        top = v178.top;
        left = v178.left;
      }
      if ( v178.right > v46[268] )
      {
        v46[268] = v178.right;
        top = v178.top;
        left = v178.left;
      }
      if ( v178.bottom > v46[269] )
      {
        v46[269] = v178.bottom;
        top = v178.top;
        left = v178.left;
      }
    }
    v48 = *(_DWORD **)v37;
    if ( (*(_DWORD *)(*(_QWORD *)v37 + 36LL) & 0x80u) != 0 )
    {
      if ( left < v48[274] )
      {
        v48[274] = left;
        top = v178.top;
      }
      if ( top < v48[275] )
        v48[275] = top;
      if ( v178.right > v48[276] )
        v48[276] = v178.right;
      if ( v178.bottom > v48[277] )
        v48[277] = v178.bottom;
    }
  }
  DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v175);
  if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v175, v37, 0) )
  {
    v49 = *(_QWORD *)v37;
    v50 = *(_QWORD *)(*(_QWORD *)v37 + 496LL);
    v149 = v50;
    if ( v50 )
    {
      v186 = a13 - v143;
      v51 = v171;
      if ( !v171 )
      {
        v51 = *(_QWORD *)(*(_QWORD *)(v49 + 976) + 248LL);
        v171 = v51;
      }
      v52 = *(_DWORD *)(v49 + 120);
      if ( (v52 & 0x10000000) != 0 && (!v51 || v153 - 10 > 2) )
        v52 = v52 & 0xFFFFFFF | 0x20000000;
      v53 = *(_QWORD *)(v50 + 160);
      v164 = 0;
      v163 = 0;
      v170 = *(_QWORD **)(v49 + 88);
      IsPalDefault = XEPALOBJ::bIsPalDefault((XEPALOBJ *)&v170);
      v55 = v170;
      if ( !IsPalDefault )
        *(_QWORD *)(v50 + 208) = *v170;
      v56 = 0;
      v57 = 1;
      v154 = 0;
      v155 = 0;
      if ( a12 )
      {
        if ( a12 == 1 )
        {
          if ( v186 >= 2 * (unsigned __int64)v35 )
          {
            v114 = v149;
            Xlate = EXLATEOBJ::bMakeXlate(&v155, Src, v55, v149, v35, v145);
            v56 = v155;
            if ( !Xlate )
              goto LABEL_100;
            v154 = v155;
            if ( *(_DWORD *)(*(_QWORD *)&v177.left + 3152LL)
              && (*(_DWORD *)(v173.m128i_i64[0] + 40) & 1) != 0
              && PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v163, v28, v145, 0, v152, v151, v150, v144, 1) )
            {
              v116 = *(_QWORD *)(v114 + 160);
              if ( !v116 )
                v116 = *(_QWORD *)(v173.m128i_i64[0] + 1792);
              XEPALOBJ::vGetEntriesFrom(&v163, v170, v116, Src, v35);
              v63 = 1;
LABEL_122:
              SURFMEM::SURFMEM(v174, 3);
              SURFMEM::bCreateDIB(
                (SURFMEM *)v174,
                (struct _DEVBITMAPINFO *)&v156,
                (void *)(*(_QWORD *)(v172.m128i_i64[0] + 16) + *(_QWORD *)v172.m128i_i64[0]),
                0,
                0,
                0,
                0,
                0,
                1,
                0);
              if ( v57 && v174[0] )
              {
                *(_DWORD *)(v174[0] + 92LL) = 0;
                if ( (v176 & 1) != 0 )
                {
                  v68 = *(_QWORD *)v162;
                  v69 = *(_DWORD *)(*(_QWORD *)v162 + 40LL) & 1LL;
                  v70 = *(int *)(*(_QWORD *)v162 + 8 * v69 + 1016);
                  if ( (unsigned __int64)(v70 + v178.left + 0x80000000LL) <= 0xFFFFFFFF
                    && (unsigned __int64)(v70 + v178.right + 0x80000000LL) <= 0xFFFFFFFF )
                  {
                    v139 = *(int *)(v68 + 8 * v69 + 1020);
                    if ( (unsigned __int64)(v139 + v178.top + 0x80000000LL) <= 0xFFFFFFFF
                      && (unsigned __int64)(v139 + v178.bottom + 0x80000000LL) <= 0xFFFFFFFF )
                    {
                      v76 = v70 + v178.left;
                      v178.left += v70;
                      right = *(_DWORD *)(v68 + 8 * v69 + 1016) + v178.right;
                      v178.right = right;
                      v75 = *(_DWORD *)(v68 + 8 * v69 + 1020) + v178.top;
                      v178.top = v75;
                      bottom = *(_DWORD *)(v68 + 8 * v69 + 1020) + v178.bottom;
                      v178.bottom = bottom;
                      if ( v63 )
                      {
                        v72 = v163;
                        if ( v163 )
                        {
                          v71 = Gre::Base::Globals((Gre::Base *)v69);
                          INC_SHARE_REF_CNT(v71, v163);
                          v72 = v163;
                        }
                        *(_QWORD *)(v174[0] + 160LL) = v72;
                        bottom = v178.bottom;
                        right = v178.right;
                        v75 = v178.top;
                        v76 = v178.left;
                      }
                      v77 = v161;
                      v78 = v146;
                      v79 = v146 - a5 - a7;
                      v80 = (struct _SURFOBJ *)(v149 + 24);
                      v81 = v161 + v167;
                      v177.left = v161;
                      v82 = *(_QWORD *)(v149 + 48);
                      v83 = v146 - a7;
                      v177.bottom = v146 - a7;
                      v172.m128i_i64[0] = v82;
                      v177.top = v79;
                      v177.right = v161 + v167;
                      if ( v160 )
                      {
                        v108 = v162;
                        v109 = XDCOBJ::prgnEffRao(v162);
                        v181 = 0;
                        v184 = 1;
                        v182 = 0;
                        v183 = 0;
                        v185 = 0;
                        XCLIPOBJ::vSetup((XCLIPOBJ *)v179, v109, (const struct ERECTL *)&v178, 0);
                        if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)&v180) )
                        {
                          if ( (*(_DWORD *)(*(_QWORD *)v108 + 36LL) & 0xE0) != 0 )
                          {
                            v172 = v180;
                            XDCOBJ::vAccumulateTight(v108, v110, &v172);
                          }
                          v111 = v174[0];
                          v112 = v174[0] + 24LL;
                          ++*(_DWORD *)(v149 + 92);
                          if ( bClipSrcDstRectsAndValidate(
                                 v80,
                                 (struct _SURFOBJ *)(v112 & -(__int64)(v111 != 0)),
                                 v108,
                                 0,
                                 v141,
                                 &v178,
                                 &v177) )
                          {
                            if ( (unsigned int)DC::bDpiScaleTransform(*(DC **)v108) )
                            {
                              if ( (v113 & 2) != 0 )
                                (*(void (__fastcall **)(struct _SURFOBJ *, __int64, _QWORD, _BYTE *, __int64, _QWORD, _QWORD, struct _RECTL *, struct _RECTL *, _QWORD, int))(v82 + 2840))(
                                  v80,
                                  (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                  0,
                                  v179,
                                  v154,
                                  0,
                                  0,
                                  &v178,
                                  &v177,
                                  0,
                                  3);
                              else
                                ((void (__fastcall *)(struct _SURFOBJ *, __int64, _QWORD, _BYTE *, __int64, _QWORD, _QWORD, struct _RECTL *, struct _RECTL *, _QWORD, int))EngStretchBlt)(
                                  v80,
                                  (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                  0,
                                  v179,
                                  v154,
                                  0,
                                  0,
                                  &v178,
                                  &v177,
                                  0,
                                  3);
                            }
                            else
                            {
                              v172.m128i_i64[0] = *(_QWORD *)&v177.left;
                              if ( (v113 & 0x400) != 0 )
                                (*(void (__fastcall **)(struct _SURFOBJ *, __int64, _BYTE *, __int64, struct _RECTL *, __m128i *))(v82 + 2832))(
                                  v80,
                                  (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                  v179,
                                  v154,
                                  &v178,
                                  &v172);
                              else
                                ((void (__fastcall *)(struct _SURFOBJ *, __int64, _BYTE *, __int64, struct _RECTL *, __m128i *))EngCopyBits)(
                                  v80,
                                  (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                  v179,
                                  v154,
                                  &v178,
                                  &v172);
                            }
                          }
                        }
                      }
                      else
                      {
                        v147 = v146 - a8;
                        v84 = v78 - a8 - v142;
                        v85 = v79;
                        v86 = v161 + v167;
                        if ( v161 < 0 )
                          v77 = 0;
                        v87 = v83;
                        v177.left = v77;
                        if ( v84 > v79 )
                          v85 = v84;
                        v177.top = v85;
                        if ( v168 < v81 )
                          v86 = v168;
                        v177.right = v86;
                        if ( v147 < v83 )
                          v87 = v147;
                        v177.bottom = v87;
                        if ( v86 >= v77 )
                        {
                          if ( v87 < v85 )
                            v85 = v87;
                          v177.top = v85;
                          if ( v85 != v87 && v77 != v86 )
                          {
                            LODWORD(v88) = v77 - v161;
                            LODWORD(v89) = v85 - v79;
                            LODWORD(v90) = v87 - v83;
                            LODWORD(v91) = v86 - v81;
                            v92 = *(_QWORD *)v162;
                            v93 = *(_DWORD *)(*(_QWORD *)v162 + 520LL);
                            if ( (v93 & 1) != 0 && (v93 & 2) == 0 )
                            {
                              v117 = *(float *)(v92 + 524);
                              v118 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v88);
                              v119 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v89);
                              *(float *)v118.m128i_i32 = *(float *)v118.m128i_i32 * v117;
                              v120 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v91);
                              v121 = _mm_cvtsi128_si32(v118);
                              v122 = (__m128i)COERCE_UNSIGNED_INT((float)(int)v90);
                              v123 = (unsigned __int8)(v121 >> 23);
                              if ( v123 > 0x9E )
                                goto LABEL_232;
                              v124 = *(float *)(v92 + 528);
                              *(float *)v119.m128i_i32 = *(float *)v119.m128i_i32 * v124;
                              v125 = v121 & 0x7FFFFF | 0x800000LL;
                              if ( v123 < 0x76 )
                                v126 = v125 >> (118 - (unsigned __int8)v123);
                              else
                                v126 = v125 << ((unsigned __int8)v123 - 118);
                              v88 = (v126 + 0x80000000LL) >> 32;
                              if ( v121 < 0 )
                                LODWORD(v88) = -(int)v88;
                              v127 = _mm_cvtsi128_si32(v119);
                              v128 = (unsigned __int8)(v127 >> 23);
                              if ( v128 > 0x9E )
                                goto LABEL_232;
                              *(float *)v120.m128i_i32 = *(float *)v120.m128i_i32 * v117;
                              v129 = v127 & 0x7FFFFF | 0x800000LL;
                              if ( v128 < 0x76 )
                                v130 = v129 >> (118 - (unsigned __int8)v128);
                              else
                                v130 = v129 << ((unsigned __int8)v128 - 118);
                              v89 = (v130 + 0x80000000LL) >> 32;
                              if ( v127 < 0 )
                                LODWORD(v89) = -(int)v89;
                              v131 = _mm_cvtsi128_si32(v120);
                              v132 = (unsigned __int8)(v131 >> 23);
                              if ( v132 > 0x9E )
                                goto LABEL_232;
                              *(float *)v122.m128i_i32 = *(float *)v122.m128i_i32 * v124;
                              v133 = v131 & 0x7FFFFF | 0x800000LL;
                              if ( v132 < 0x76 )
                                v134 = v133 >> (118 - (unsigned __int8)v132);
                              else
                                v134 = v133 << ((unsigned __int8)v132 - 118);
                              v91 = (v134 + 0x80000000LL) >> 32;
                              if ( v131 < 0 )
                                LODWORD(v91) = -(int)v91;
                              v135 = _mm_cvtsi128_si32(v122);
                              v136 = (unsigned __int8)(v135 >> 23);
                              if ( v136 > 0x9E )
                              {
LABEL_232:
                                LODWORD(v90) = 0;
                                LODWORD(v91) = 0;
                                LODWORD(v89) = 0;
                                LODWORD(v88) = 0;
                              }
                              else
                              {
                                v137 = v135 & 0x7FFFFF | 0x800000LL;
                                if ( v136 < 0x76 )
                                  v138 = v137 >> (118 - (unsigned __int8)v136);
                                else
                                  v138 = v137 << ((unsigned __int8)v136 - 118);
                                v90 = (v138 + 0x80000000LL) >> 32;
                                if ( v135 < 0 )
                                  LODWORD(v90) = -(int)v90;
                              }
                            }
                            v94 = v88 + v76;
                            v95 = v91 + right;
                            v178.left = v94;
                            v178.right = v95;
                            v178.top = v89 + v75;
                            v178.bottom = v90 + bottom;
                            if ( (_DWORD)v89 + v75 != (_DWORD)v90 + bottom && v94 != v95 )
                            {
                              v96 = v162;
                              v97 = XDCOBJ::prgnEffRao(v162);
                              v98 = 1;
                              v181 = 0;
                              v184 = 1;
                              v182 = 0;
                              v183 = 0;
                              v185 = 0;
                              XCLIPOBJ::vSetup((XCLIPOBJ *)v179, v97, (const struct ERECTL *)&v178, 0);
                              if ( v180.m128i_i32[0] != v180.m128i_i32[2] && v180.m128i_i32[1] != v180.m128i_i32[3] )
                              {
                                if ( (*(_DWORD *)(*(_QWORD *)v96 + 36LL) & 0xE0) != 0 )
                                {
                                  v173 = v180;
                                  XDCOBJ::vAccumulateTight(v96, (struct ECLIPOBJ *)v180.m128i_u32[1], &v173);
                                }
                                if ( v153 - 4 <= 1 )
                                {
                                  v177.bottom += v84 - v177.top;
                                  v177.top = v84;
                                }
                                else
                                {
                                  v177.bottom -= v84;
                                  v177.top -= v84;
                                }
                                v99 = v174[0];
                                v100 = v149;
                                v101 = v174[0] + 24LL;
                                ++*(_DWORD *)(v149 + 92);
                                if ( bClipSrcDstRectsAndValidate(
                                       v80,
                                       (struct _SURFOBJ *)(v101 & -(__int64)(v99 != 0)),
                                       v96,
                                       0,
                                       v141,
                                       &v178,
                                       &v177) )
                                {
                                  v102 = *(_DWORD *)(*(_QWORD *)v96 + 520LL);
                                  if ( (v102 & 1) == 0 || (v102 & 2) != 0 )
                                    v98 = 0;
                                  v103 = *(_DWORD *)(v100 + 144);
                                  if ( v98 )
                                  {
                                    v104 = (v103 & 2) != 0
                                         ? (*(__int64 (__fastcall **)(struct _SURFOBJ *, __int64, _QWORD, _BYTE *, __int64, _QWORD, _QWORD, struct _RECTL *, struct _RECTL *, _QWORD, int))(v172.m128i_i64[0] + 2840))(
                                             v80,
                                             (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                             0,
                                             v179,
                                             v154,
                                             0,
                                             0,
                                             &v178,
                                             &v177,
                                             0,
                                             3)
                                         : ((__int64 (__fastcall *)(struct _SURFOBJ *, __int64, _QWORD, _BYTE *, __int64, _QWORD, _QWORD, struct _RECTL *, struct _RECTL *, _QWORD, int))EngStretchBlt)(
                                             v80,
                                             (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                             0,
                                             v179,
                                             v154,
                                             0,
                                             0,
                                             &v178,
                                             &v177,
                                             0,
                                             3);
                                  }
                                  else
                                  {
                                    v173.m128i_i64[0] = *(_QWORD *)&v177.left;
                                    v104 = (v103 & 0x400) != 0
                                         ? (*(__int64 (__fastcall **)(struct _SURFOBJ *, __int64, _BYTE *, __int64, struct _RECTL *, __m128i *))(v172.m128i_i64[0] + 2832))(
                                             v80,
                                             (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                             v179,
                                             v154,
                                             &v178,
                                             &v173)
                                         : ((__int64 (__fastcall *)(struct _SURFOBJ *, __int64, _BYTE *, __int64, struct _RECTL *, __m128i *))EngCopyBits)(
                                             v80,
                                             (v174[0] + 24LL) & -(__int64)(v174[0] != 0),
                                             v179,
                                             v154,
                                             &v178,
                                             &v173);
                                  }
                                  if ( !v104 )
                                    goto LABEL_159;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                v38 = v142;
LABEL_160:
                SURFMEM::~SURFMEM((SURFMEM *)v174);
                if ( v56 )
                {
                  v106 = *(_DWORD *)(v56 + 36);
                  if ( v106 >= 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)Gre::Base::Globals(v105) + 8 * *(int *)(v56 + 36)
                                                                                              + 1100);
                  }
                  else if ( v106 == -1 )
                  {
                    FreeThreadBufferWithTag(v56);
                  }
                }
                PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v163);
                goto LABEL_165;
              }
LABEL_159:
              v38 = 0;
              goto LABEL_160;
            }
            goto LABEL_177;
          }
        }
        else
        {
          v140 = *(_DWORD *)(v149 + 96);
          if ( v140 == (_DWORD)v156 || v140 == 2 && (_DWORD)v156 == 7 || v140 == 3 && (_DWORD)v156 == 8 )
          {
            v154 = *(_QWORD *)&v177.left + 4664LL;
            goto LABEL_121;
          }
        }
      }
      else
      {
        if ( !PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v163, v28, v145, 0, v152, v151, v150, v144, 1) )
        {
LABEL_268:
          v57 = 0;
LABEL_121:
          v63 = 0;
          goto LABEL_122;
        }
        if ( !v35 )
        {
LABEL_99:
          XlateObject = CreateXlateObject(v171, v52, v163, v53, v170, v170, 0, 0, 0xFFFFFF, 0);
          v56 = XlateObject;
          if ( !XlateObject )
          {
LABEL_100:
            v57 = 0;
            v63 = 0;
            goto LABEL_122;
          }
          v154 = XlateObject;
LABEL_177:
          v63 = 0;
          goto LABEL_122;
        }
        if ( v186 >= 4 * v35 )
        {
          if ( v153 - 10 <= 2 )
          {
            if ( v35 > *(_DWORD *)(v163 + 28) )
              v35 = *(_DWORD *)(v163 + 28);
            memmove(*(void **)(v163 + 112), Src, 4LL * v35);
          }
          else
          {
            v58 = *(_DWORD *)(v163 + 28);
            v59 = *(_BYTE **)(v163 + 112);
            if ( v35 <= v58 || (v35 = *(_DWORD *)(v163 + 28), v58) )
            {
              v60 = Src;
              do
              {
                v59[3] = 0;
                v59[2] = *v60;
                *v59 = v60[2];
                v61 = v60[1];
                v60 += 4;
                v59[1] = v61;
                v59 += 4;
                --v35;
              }
              while ( v35 );
            }
          }
          XEPALOBJ::vUpdateTime((XEPALOBJ *)&v163);
          goto LABEL_99;
        }
      }
      EngSetLastError(0x57u);
      goto LABEL_268;
    }
  }
LABEL_165:
  DEVLOCKOBJ::~DEVLOCKOBJ(v175);
  return v38;
}

```

## disassembly

```asm
0x140054a74  mov     [rsp-8+arg_10], rbx
0x140054a79  push    rbp
0x140054a7a  push    rsi
0x140054a7b  push    rdi
0x140054a7c  push    r12
0x140054a7e  push    r13
0x140054a80  push    r14
0x140054a82  push    r15
0x140054a84  lea     rbp, [rsp-1B0h]
0x140054a8c  sub     rsp, 2B0h
0x140054a93  mov     rax, cs:__security_cookie
0x140054a9a  xor     rax, rsp
0x140054a9d  mov     [rbp+1E0h+var_40], rax
0x140054aa4  mov     rbx, [rbp+1E0h+arg_50]
0x140054aab  mov     rax, rcx
0x140054aae  mov     [rbp+1E0h+var_218], rcx
0x140054ab2  mov     r11d, edx
0x140054ab5  mov     ecx, [rbp+1E0h+arg_28]
0x140054abb  mov     r13d, 1
0x140054ac1  mov     rdx, [rbp+1E0h+arg_48]
0x140054ac8  mov     r14d, r8d
0x140054acb  mov     rdi, [rax]
0x140054ace  mov     [rbp+1E0h+var_21C], ecx
0x140054ad1  mov     rcx, [rbp+1E0h+arg_70]
0x140054ad8  mov     [rbp+1E0h+var_1E0], rcx
0x140054adc  mov     rax, [rdi+3D0h]
0x140054ae3  mov     [rbp+1E0h+var_1F8], r9d
0x140054ae7  mov     [rbp+1E0h+var_1D8], rdx
0x140054aeb  mov     ecx, [rax+6Ch]
0x140054aee  test    r13b, cl
0x140054af1  jnz     loc_140055D46
0x140054af7  xor     r10d, r10d
0x140054afa  test    rbx, rbx
0x140054afd  jz      loc_140054C7B
0x140054b03  cmp     [rdx], r10
0x140054b06  jz      loc_140054C7B
0x140054b0c  mov     esi, [rbp+1E0h+arg_58]
0x140054b12  cmp     esi, 2
0x140054b15  ja      loc_140054C7B
0x140054b1b  mov     edx, [rbp+1E0h+arg_60]
0x140054b21  cmp     edx, 28h ; '('
0x140054b24  jb      loc_140054C7B
0x140054b2a  mov     eax, [rbx]
0x140054b2c  mov     [rsp+2E0h+var_27C], eax
0x140054b30  cmp     eax, 28h ; '('
0x140054b33  jb      loc_140054C7B
0x140054b39  mov     r12d, [rbx+4]
0x140054b3d  mov     [rbp+1E0h+var_1F4], r12d
0x140054b41  test    r12d, r12d
0x140054b44  jle     loc_140054C7B
0x140054b4a  mov     ecx, [rbx+8]
0x140054b4d  test    ecx, ecx
0x140054b4f  jz      loc_140054C7B
0x140054b55  mov     r8d, [rbx+10h]
0x140054b59  mov     [rbp+1E0h+var_254], r8d
0x140054b5d  mov     [rbp+1E0h+var_240], r10
0x140054b61  mov     [rbp+1E0h+var_238], r10
0x140054b65  mov     [rbp+1E0h+var_228], r10
0x140054b69  mov     [rbp+1E0h+var_230], r10
0x140054b6d  js      loc_140055765
0x140054b73  movzx   r9d, word ptr [rbx+0Eh]
0x140054b78  mov     r15d, 4
0x140054b7e  mov     [rsp+2E0h+var_270], ecx
0x140054b82  mov     [rbp+1E0h+var_220], r10d
0x140054b86  cmp     r8d, 3
0x140054b8a  jz      loc_1400551C2
0x140054b90  add     rax, rbx
0x140054b93  mov     [rbp+1E0h+var_258], r10d
0x140054b97  mov     [rbp+1E0h+Src], rax
0x140054b9b  mov     [rbp+1E0h+var_25C], r10d
0x140054b9f  mov     [rbp+1E0h+var_260], r10d
0x140054ba3  test    r8d, r8d
0x140054ba6  jnz     loc_140054CC1
0x140054bac  mov     eax, r9d
0x140054baf  sub     eax, r13d
0x140054bb2  jz      loc_1400551A3
0x140054bb8  sub     eax, 3
0x140054bbb  jz      loc_140055D63
0x140054bc1  cmp     eax, r15d
0x140054bc4  jz      loc_140055D51
0x140054bca  cmp     esi, r13d
0x140054bcd  mov     [rsp+2E0h+var_274], r10d
0x140054bd2  mov     eax, r10d
0x140054bd5  mov     r8d, r10d
0x140054bd8  cmovnz  eax, esi
0x140054bdb  mov     r15d, 10h
0x140054be1  mov     [rbp+1E0h+arg_58], eax
0x140054be7  mov     r10d, 200h
0x140054bed  mov     [rsp+2E0h+var_278], r10d
0x140054bf2  mov     esi, eax
0x140054bf4  cmp     r9w, r15w
0x140054bf8  jz      loc_14005593D
0x140054bfe  lea     ecx, [r15+8]
0x140054c02  cmp     r9w, cx
0x140054c06  jz      loc_1400556A9
0x140054c0c  cmp     r9d, 20h ; ' '
0x140054c10  jnz     short loc_140054C7B
0x140054c12  mov     dword ptr [rbp+1E0h+var_240], 6
0x140054c19  lea     r15d, [rcx-10h]
0x140054c1d  mov     rcx, r9
0x140054c20  mov     r10d, 0FFFFFFFFh
0x140054c26  imul    rcx, r12
0x140054c2a  cmp     rcx, r10
0x140054c2d  ja      short loc_140054C59
0x140054c2f  lea     edx, [rcx+1Fh]
0x140054c32  cmp     edx, ecx
0x140054c34  jb      short loc_140054C59
0x140054c36  mov     r9d, [rbp+1E0h+arg_40]
0x140054c3d  shr     rdx, 3
0x140054c41  and     edx, 1FFFFFFCh
0x140054c47  mov     [rsp+2E0h+var_280], r9d
0x140054c4c  imul    rdx, r9
0x140054c50  cmp     rdx, r10
0x140054c53  jbe     short loc_140054CB5
0x140054c55  mov     dword ptr [rbp+1E0h+var_238+4], r10d
0x140054c59  mov     ecx, 216h; iError
0x140054c5e  call    cs:__imp_EngSetLastError
0x140054c65  nop     dword ptr [rax+rax+00h]
0x140054c6a  xor     eax, eax
0x140054c6c  jmp     loc_140055F42
0x140054c72  test    rdi, rdi
0x140054c75  jnz     loc_140055E19
0x140054c7b  mov     ecx, 57h ; 'W'
0x140054c80  jmp     short loc_140054C5E
0x140054c82  lea     rax, [rbx+28h]
0x140054c86  mov     [rsp+2E0h+var_278], 200h
0x140054c8e  mov     r10d, [rax]
0x140054c91  xor     r8d, r8d
0x140054c94  mov     [rbp+1E0h+var_258], r10d
0x140054c98  mov     r10d, [rax+4]
0x140054c9c  mov     [rbp+1E0h+var_25C], r10d
0x140054ca0  mov     r10d, [rax+8]
0x140054ca4  lea     r15d, [r8+2]
0x140054ca8  mov     [rbp+1E0h+var_260], r10d
0x140054cac  mov     [rbp+1E0h+Src], rax
0x140054cb0  mov     [rsp+2E0h+var_274], r8d
0x140054cb5  mov     eax, [rbp+1E0h+arg_38]
0x140054cbb  mov     [rsp+2E0h+var_26C], eax
0x140054cbf  jmp     short loc_140054D1B
0x140054cc1  cmp     r8d, 0Ah
0x140054cc5  jz      loc_140055187
0x140054ccb  cmp     r8d, 2
0x140054ccf  jz      loc_140055AE1
0x140054cd5  cmp     r8d, 0Ch
0x140054cd9  jz      short loc_140054C72
0x140054cdb  cmp     r8d, r13d
0x140054cde  jnz     loc_140055DAA
0x140054ce4  mov     eax, 8
0x140054ce9  cmp     r9w, ax
0x140054ced  jnz     short loc_140054C7B
0x140054cef  mov     r8d, 100h
0x140054cf5  mov     dword ptr [rbp+1E0h+var_240], eax
0x140054cf8  mov     [rsp+2E0h+var_274], r8d
0x140054cfd  mov     [rbp+1E0h+var_220], r13d
0x140054d01  mov     r9d, ecx
0x140054d04  mov     [rsp+2E0h+var_280], ecx
0x140054d08  mov     r15d, r13d
0x140054d0b  mov     [rsp+2E0h+var_26C], r10d
0x140054d10  mov     [rsp+2E0h+var_278], 400h
0x140054d18  mov     edx, [rbx+14h]
0x140054d1b  mov     r12d, [rbx+20h]
0x140054d1f  mov     dword ptr [rbp+1E0h+var_238+4], edx
0x140054d22  test    r12d, r12d
0x140054d25  jnz     loc_140055163
0x140054d2b  mov     r12d, r8d
0x140054d2e  mov     rcx, [rbp+1E0h+var_1D8]
0x140054d32  mov     rax, [rcx+10h]
0x140054d36  mov     rcx, [rcx+8]
0x140054d3a  sub     rcx, rax
0x140054d3d  mov     eax, edx
0x140054d3f  cmp     rcx, rax
0x140054d42  jb      loc_140054C7B
0x140054d48  mov     eax, [rbp+1E0h+var_1F4]
0x140054d4b  mov     edx, [rbp+1E0h+var_254]; unsigned int
0x140054d4e  mov     ecx, [rsp+2E0h+var_270]
0x140054d52  mov     dword ptr [rbp+1E0h+var_240+4], eax
0x140054d55  lea     eax, [rdx-4]
0x140054d58  cmp     eax, r13d
0x140054d5b  cmova   ecx, r9d
0x140054d5f  mov     dword ptr [rbp+1E0h+var_238], ecx
0x140054d62  test    dword ptr [rdi+24h], 10000h
0x140054d69  jnz     loc_140054C7B
0x140054d6f  mov     rcx, [rbp+1E0h+var_218]; this
0x140054d73  mov     rax, [rcx+10h]
0x140054d77  mov     qword ptr [rbp+1E0h+var_100.left], rax
0x140054d7e  mov     rax, [rdi+30h]
0x140054d82  mov     [rbp+1E0h+var_1C8], rax
0x140054d86  lea     eax, [rdx-4]
0x140054d89  mov     [rbp+1E0h+var_1FC], r14d
0x140054d8d  mov     r14, rcx
0x140054d90  mov     [rbp+1E0h+var_200], r11d
0x140054d94  cmp     eax, r13d
0x140054d97  jbe     loc_140055E32
0x140054d9d  mov     esi, [rsp+2E0h+var_280]
0x140054da1  cmp     [rbp+1E0h+arg_68], 0
0x140054da8  jz      short loc_140054DED
0x140054daa  mov     r8d, 204h
0x140054db0  lea     rdx, [rbp+1E0h+var_248]
0x140054db4  mov     rcx, rdi
0x140054db7  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140054dbe  nop     dword ptr [rax+rax+00h]
0x140054dc3  mov     rax, [rbp+1E0h+var_248]
0x140054dc7  mov     ecx, [rax+20h]
0x140054dca  and     ecx, 43h
0x140054dcd  cmp     cl, 43h ; 'C'
0x140054dd0  jnz     loc_14005516F
0x140054dd6  test    esi, esi
0x140054dd8  jz      short loc_140054DE9
0x140054dda  mov     ecx, [rbx+10h]
0x140054ddd  sub     ecx, 4
0x140054de0  cmp     ecx, r13d
0x140054de3  jbe     loc_140055E55
0x140054de9  mov     r11d, [rbp+1E0h+var_200]
0x140054ded  mov     rdx, [r14]
0x140054df0  mov     ecx, [rbp+1E0h+var_1F8]
0x140054df3  mov     r8d, [rbp+1E0h+arg_20]
0x140054dfa  mov     dword ptr [rsp+2E0h+var_268], ecx
0x140054dfe  mov     eax, [rdx+208h]
0x140054e04  mov     dword ptr [rsp+2E0h+var_268+4], r8d
0x140054e09  test    r13b, al
0x140054e0c  jnz     loc_140055E6C
0x140054e12  mov     edx, [rbp+1E0h+var_1FC]
0x140054e15  add     ecx, r11d
0x140054e18  mov     [rbp+1E0h+var_F0.left], r11d
0x140054e1f  mov     [rbp+1E0h+var_F0.top], edx
0x140054e25  mov     [rbp+1E0h+var_F0.right], ecx
0x140054e2b  lea     eax, [rdx+r8]
0x140054e2f  mov     [rbp+1E0h+var_F0.bottom], eax
0x140054e35  cmp     r11d, ecx
0x140054e38  jle     short loc_140054E4A
0x140054e3a  mov     [rbp+1E0h+var_F0.right], r11d
0x140054e41  mov     r11d, ecx
0x140054e44  mov     [rbp+1E0h+var_F0.left], ecx
0x140054e4a  cmp     edx, eax
0x140054e4c  jle     short loc_140054E5C
0x140054e4e  mov     [rbp+1E0h+var_F0.bottom], edx
0x140054e54  mov     edx, eax
0x140054e56  mov     [rbp+1E0h+var_F0.top], eax
0x140054e5c  cmp     edx, [rbp+1E0h+var_F0.bottom]
0x140054e62  jz      loc_140055687
0x140054e68  cmp     r11d, [rbp+1E0h+var_F0.right]
0x140054e6f  jz      loc_140055687
0x140054e75  test    esi, esi
0x140054e77  jz      loc_140055687
0x140054e7d  mov     rax, [r14]
0x140054e80  mov     ecx, [rax+24h]
0x140054e83  test    cl, 0E0h
0x140054e86  jz      loc_140054F71
0x140054e8c  test    cl, 20h
0x140054e8f  jz      loc_140054F15
0x140054e95  cmp     r11d, [rax+428h]
0x140054e9c  jge     short loc_140054EB2
0x140054e9e  mov     [rax+428h], r11d
0x140054ea5  mov     edx, [rbp+1E0h+var_F0.top]
0x140054eab  mov     r11d, [rbp+1E0h+var_F0.left]
0x140054eb2  cmp     edx, [rax+42Ch]
0x140054eb8  jge     short loc_140054ECD
0x140054eba  mov     [rax+42Ch], edx
0x140054ec0  mov     edx, [rbp+1E0h+var_F0.top]
0x140054ec6  mov     r11d, [rbp+1E0h+var_F0.left]
0x140054ecd  mov     r8d, [rbp+1E0h+var_F0.right]
0x140054ed4  cmp     r8d, [rax+430h]
0x140054edb  jle     short loc_140054EF1
0x140054edd  mov     [rax+430h], r8d
0x140054ee4  mov     edx, [rbp+1E0h+var_F0.top]
0x140054eea  mov     r11d, [rbp+1E0h+var_F0.left]
0x140054ef1  mov     r8d, [rbp+1E0h+var_F0.bottom]
0x140054ef8  cmp     r8d, [rax+434h]
0x140054eff  jle     short loc_140054F15
0x140054f01  mov     [rax+434h], r8d
0x140054f08  mov     edx, [rbp+1E0h+var_F0.top]
0x140054f0e  mov     r11d, [rbp+1E0h+var_F0.left]
0x140054f15  mov     rcx, [r14]
0x140054f18  mov     eax, [rcx+24h]
0x140054f1b  test    al, al
0x140054f1d  jns     short loc_140054F71
0x140054f1f  cmp     r11d, [rcx+448h]
0x140054f26  jge     short loc_140054F35
0x140054f28  mov     [rcx+448h], r11d
0x140054f2f  mov     edx, [rbp+1E0h+var_F0.top]
0x140054f35  cmp     edx, [rcx+44Ch]
0x140054f3b  jge     short loc_140054F43
0x140054f3d  mov     [rcx+44Ch], edx
0x140054f43  mov     r8d, [rbp+1E0h+var_F0.right]
0x140054f4a  cmp     r8d, [rcx+450h]
0x140054f51  jle     short loc_140054F5A
0x140054f53  mov     [rcx+450h], r8d
0x140054f5a  mov     r8d, [rbp+1E0h+var_F0.bottom]
0x140054f61  cmp     r8d, [rcx+454h]
0x140054f68  jle     short loc_140054F71
0x140054f6a  mov     [rcx+454h], r8d
0x140054f71  lea     rcx, [rbp+1E0h+var_1A0]; this
0x140054f75  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x140054f7a  xor     r8d, r8d
0x140054f7d  lea     rcx, [rbp+1E0h+var_1A0]
0x140054f81  mov     rdx, r14
0x140054f84  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140054f8b  nop     dword ptr [rax+rax+00h]
0x140054f90  test    eax, eax
0x140054f92  jz      loc_14005567E
  ... truncated ...
```
