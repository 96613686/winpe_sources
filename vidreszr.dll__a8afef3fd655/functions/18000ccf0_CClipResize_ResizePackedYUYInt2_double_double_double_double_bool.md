# CClipResize::ResizePackedYUYInt2(double,double,double,double,bool)

- ea: `0x18000ccf0`
- end: `0x18000e4f1`
- name: `?ResizePackedYUYInt2@CClipResize@@IEAAXNNNN_N@Z`
- size: `6145`
- prototype: `void __fastcall(CClipResize *__hidden this, double, double, double, double, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009e30`

## callees

- `0x18000ccf0`

## pseudocode

```c
void __fastcall CClipResize::ResizePackedYUYInt2(
        CClipResize *this,
        double a2,
        double a3,
        double a4,
        double a5,
        bool a6)
{
  CClipResize *v6; // rbp
  __int64 v7; // rcx
  _BYTE *v10; // rdx
  __int64 v11; // r8
  _BYTE *v12; // rax
  __int64 v13; // rcx
  _BYTE *v14; // rbx
  int v15; // eax
  double v16; // xmm2_8
  double v17; // xmm0_8
  double v18; // xmm1_8
  _DWORD *v19; // rdx
  int v20; // ecx
  __int64 v21; // r9
  int v22; // r12d
  _BYTE *v23; // rcx
  int v24; // edx
  __int64 v25; // r10
  double v26; // xmm1_8
  __int64 v27; // r8
  __int64 v28; // rdx
  unsigned __int8 *v29; // r8
  __int64 v30; // rcx
  int v31; // edi
  unsigned __int8 *v32; // rax
  int v33; // esi
  int v34; // r10d
  int v35; // r14d
  int v36; // r12d
  int v37; // ebp
  int v38; // ebx
  int v39; // r11d
  int v40; // r13d
  int v41; // r9d
  int v42; // ebx
  int v43; // r10d
  __int64 v44; // r8
  __m128i v45; // xmm0
  __int64 v46; // rax
  unsigned __int8 *v47; // rdx
  int *v48; // r8
  bool v49; // cc
  int v50; // edi
  int v51; // ecx
  bool v52; // cc
  __int64 v53; // r8
  unsigned __int8 *v54; // rdx
  int v55; // r11d
  int v56; // r9d
  int v57; // r8d
  int v58; // r11d
  double v59; // xmm1_8
  int v60; // r10d
  int v61; // r11d
  __int64 v62; // r8
  _BYTE *v63; // rax
  int v64; // r10d
  int v65; // ecx
  bool v66; // cc
  int v67; // r8d
  _BYTE *v68; // rax
  int v69; // eax
  int v70; // ecx
  int v71; // eax
  double v72; // xmm12_8
  double v73; // xmm2_8
  double v74; // xmm0_8
  double v75; // xmm1_8
  int v76; // r10d
  int v77; // r12d
  bool v78; // sf
  _BYTE *v79; // r11
  int *v80; // r14
  _BYTE *v81; // rcx
  int v82; // r8d
  __int64 v83; // r9
  int v84; // eax
  unsigned __int8 *v85; // r8
  unsigned __int8 *v86; // rax
  int v87; // esi
  int v88; // edi
  int v89; // r12d
  int v90; // r14d
  int v91; // ebp
  int v92; // r10d
  int v93; // ebx
  int v94; // r13d
  int v95; // r11d
  int v96; // r9d
  int v97; // r11d
  char v98; // cl
  int v99; // r13d
  __int64 v100; // rdx
  int v101; // ebx
  int v102; // esi
  unsigned __int8 *v103; // rax
  int v104; // edi
  int v105; // r10d
  int v106; // r11d
  int v107; // r12d
  int v108; // r14d
  int v109; // ebp
  int v110; // r9d
  int v111; // r11d
  int v112; // r14d
  int v113; // r14d
  int v114; // r11d
  int v115; // edx
  char v116; // al
  __int64 v117; // r9
  __int64 v118; // rbx
  int v119; // esi
  int v120; // r11d
  int v121; // r9d
  __int16 v122; // ax
  __int64 v123; // rax
  int v124; // r9d
  __int64 v125; // rbx
  __int64 v126; // r8
  _BYTE *v127; // r8
  int v128; // r15d
  int *v129; // r14
  _BYTE *v130; // rcx
  int v131; // r8d
  bool v132; // cc
  __int64 v133; // r9
  double v134; // xmm0_8
  int v135; // eax
  int v136; // edi
  __int64 v137; // rbx
  int v138; // r10d
  int v139; // r9d
  int v140; // r11d
  int v141; // r10d
  __int64 v142; // rax
  int v143; // r9d
  int v144; // r10d
  __int64 v145; // rbx
  __int64 v146; // r8
  _BYTE *v147; // rax
  int v148; // edi
  int *v149; // r8
  _BYTE *v150; // rcx
  int v151; // r9d
  bool v152; // cc
  int v153; // ebx
  double v154; // xmm0_8
  __int64 v155; // r9
  int v156; // eax
  int v157; // edx
  int v158; // ebx
  __int64 v159; // rcx
  int v160; // ecx
  int v161; // [rsp+0h] [rbp-118h]
  int v162; // [rsp+0h] [rbp-118h]
  int v163; // [rsp+0h] [rbp-118h]
  int v164; // [rsp+4h] [rbp-114h]
  int v165; // [rsp+4h] [rbp-114h]
  int v166; // [rsp+4h] [rbp-114h]
  int v167; // [rsp+8h] [rbp-110h]
  int v168; // [rsp+8h] [rbp-110h]
  int v169; // [rsp+8h] [rbp-110h]
  int v170; // [rsp+Ch] [rbp-10Ch]
  int v171; // [rsp+Ch] [rbp-10Ch]
  int v172; // [rsp+Ch] [rbp-10Ch]
  int v173; // [rsp+10h] [rbp-108h]
  int v174; // [rsp+10h] [rbp-108h]
  int v175; // [rsp+10h] [rbp-108h]
  int v176; // [rsp+14h] [rbp-104h]
  int v177; // [rsp+14h] [rbp-104h]
  int v178; // [rsp+18h] [rbp-100h]
  int v179; // [rsp+18h] [rbp-100h]
  int v180; // [rsp+18h] [rbp-100h]
  int v181; // [rsp+1Ch] [rbp-FCh]
  int v182; // [rsp+1Ch] [rbp-FCh]
  int v183; // [rsp+20h] [rbp-F8h]
  int v184; // [rsp+20h] [rbp-F8h]
  _BYTE *v185; // [rsp+28h] [rbp-F0h]
  int v186; // [rsp+30h] [rbp-E8h]
  int v187; // [rsp+30h] [rbp-E8h]
  _BYTE *v188; // [rsp+38h] [rbp-E0h]
  int v189; // [rsp+40h] [rbp-D8h]
  _BYTE *v190; // [rsp+48h] [rbp-D0h]
  int v191; // [rsp+48h] [rbp-D0h]
  int v192; // [rsp+50h] [rbp-C8h]
  int v193; // [rsp+50h] [rbp-C8h]
  int v194; // [rsp+54h] [rbp-C4h]
  int v195; // [rsp+54h] [rbp-C4h]
  __int64 v196; // [rsp+58h] [rbp-C0h]
  __int64 v197; // [rsp+60h] [rbp-B8h]
  __int64 v198; // [rsp+68h] [rbp-B0h]
  int v199; // [rsp+68h] [rbp-B0h]
  __int64 v200; // [rsp+70h] [rbp-A8h]
  int *v201; // [rsp+78h] [rbp-A0h]
  int v203; // [rsp+148h] [rbp+30h]
  int v204; // [rsp+148h] [rbp+30h]
  int v205; // [rsp+148h] [rbp+30h]

  v6 = this;
  v7 = *((_QWORD *)this + 19);
  v10 = (_BYTE *)*((_QWORD *)v6 + 22);
  v11 = v7 + 1;
  v188 = v10 + 1;
  if ( a6 )
  {
    v196 = v7 + 1;
    v12 = v10 + 3;
    v13 = v7 + 3;
    v190 = (_BYTE *)*((_QWORD *)v6 + 22);
    v14 = v190;
  }
  else
  {
    v196 = v7;
    v14 = v10 + 1;
    v190 = v10 + 1;
    v13 = v7 + 2;
    v12 = v10 + 2;
    v188 = (_BYTE *)*((_QWORD *)v6 + 22);
    *((_QWORD *)v6 + 19) = v11;
  }
  v185 = v12;
  v15 = 0;
  v197 = v13;
  v173 = 0;
  if ( *((int *)v6 + 35) <= 0 )
    return;
  do
  {
    v16 = a3 - a2;
    if ( *((_DWORD *)v6 + 36) )
      v17 = (a4 - 1.0) * 0.5;
    else
      v17 = 0.0;
    v18 = (double)v15 * a4 + a5 + v17;
    v19 = (_DWORD *)((char *)v6 + 132);
    v20 = (int)v18;
    dword_18001BC58 = (int)v18 << 8;
    v21 = *((_QWORD *)v6 + 19) + 2 * *((_DWORD *)v6 + 32) * (int)v18;
    v198 = v21;
    v22 = (int)(v18 * 256.0 - (double)((int)v18 << 8));
    v192 = v22;
    if ( (int)v18 <= 0 )
    {
      v48 = (int *)((char *)v6 + 132);
      v49 = v20 <= 0;
      if ( v20 < 0 )
        goto LABEL_45;
    }
    else
    {
      if ( v20 < *v19 - 2 )
      {
        v183 = 0;
        v194 = (v22 * v22) >> 8;
        v178 = (v22 * v194) >> 8;
        if ( *((int *)v6 + 34) <= 0 )
          goto LABEL_61;
        v23 = v190;
        while ( 1 )
        {
          v16 = v16 + a2;
          v24 = (int)v16;
          if ( (int)v16 <= 0 )
          {
            if ( !v24 )
              goto LABEL_25;
          }
          else
          {
            v25 = *((int *)v6 + 32);
            if ( v24 < (int)v25 - 2 )
            {
              dword_18001BC58 = v24 << 8;
              v26 = v16 * 256.0 - (double)(v24 << 8);
              v186 = ((int)v26 * (int)v26) >> 8;
              v27 = 2 * v24;
              v28 = v25;
              v29 = (unsigned __int8 *)(v21 + v27);
              v189 = (v186 * (int)v26) >> 8;
              v30 = 2 * v25;
              v31 = v29[2 * v25 - 2];
              v32 = &v29[-2 * v25];
              v33 = v29[2 * v25 + 2];
              v34 = v29[2 * v25 + 4];
              v35 = v32[2];
              v36 = *(v32 - 2);
              v37 = v32[4];
              v38 = v29[4 * v28 - 2];
              v39 = v29[4 * v28 + 4];
              v40 = v29[4];
              v167 = *(v29 - 2);
              v170 = v29[2];
              v176 = v29[v30];
              v181 = v29[4 * v28];
              v164 = *v32;
              v41 = v29[4 * v28 + 2];
              v161 = *v29;
              v203 = v194
                   * (((2 * (v164 + 2 * v176) - v181 - 5 * v161) >> 1 << 8)
                    + (int)v26
                    * ((7 * v167 + 3 * (v33 - v170) + 2 * (v176 + v38 + 2 * (v164 - v36 - v161) - v181) - 5 * v31) >> 1)
                    + v189
                    * ((11 * (v170 - v161)
                      + 5 * (v34 - v31)
                      + 7 * (v167 + v176 - v33 - v40)
                      + 2 * (v38 + 2 * (v37 + v41 + 2 * (v164 - v35) - v181 - v36) - v39)) >> 1)
                    + v186
                    * ((5 * (2 * (v35 + v31 + 2 * v161) - v41 - v34)
                      + 7 * (v40 + v181 - 2 * (v167 + v164))
                      + 2 * (v39 + 2 * (2 * (v33 + v36) - v38 - v37))
                      - 13 * (v176 + v170)) >> 1));
              LODWORD(v28) = (int)v26 * (v161 + v170 + v36 + v181 + 2 * (v31 - v167) - v38 - v33 - v176 - v164)
                           + v189
                           * (v36
                            + v39
                            + 3 * (v161 + v33 - v176 - v170)
                            + 2 * (v40 + v35 + v31 + v181 - v41 - v34 - v164 - v167)
                            - v38
                            - v37)
                           + v186
                           * ((5 * (v41 - v35)
                             + 11 * (v176 - v161)
                             + 7 * (v170 + v164 - v181 - v33)
                             + 2 * (v37 + 2 * (v34 + v38 + 2 * (v167 - v31) - v36 - v40) - v39)) >> 1);
              LODWORD(v30) = (int)v26 * (v161 + v36 - v164 - v167)
                           + v189 * (v161 + v40 + v36 + v176 + 2 * (v35 - v164) - v33 - v37 - v170 - v167)
                           + v186
                           * ((3 * (v33 - v176) + 7 * v164 + 2 * (v170 + v37 + 2 * (v167 - v36 - v161) - v40) - 5 * v35) >> 1);
              v22 = v192;
              v6 = this;
              v42 = ((((v161 << 8)
                     + (int)v26 * ((v170 - v167) >> 1)
                     + v192 * ((v176 - v164) >> 1)
                     + v178 * ((v181 + 3 * (v161 - v176) - v164) >> 1)
                     + v189 * ((v40 + 3 * (v161 - v170) - v167) >> 1)
                     + v186 * ((2 * (v167 + 2 * v170) - 5 * v161 - v40) >> 1)) << 8)
                   + v192 * (int)v30
                   + v178 * (int)v28
                   + v203) >> 16;
              if ( v42 > 255 )
                v42 = 255;
              LOBYTE(v43) = 0;
              if ( v42 >= 0 )
                LOBYTE(v43) = v42;
              goto LABEL_26;
            }
          }
          v44 = *((int *)v6 + 32);
          if ( v24 < (int)v44 - 1 )
          {
LABEL_25:
            dword_18001BC58 = v24 << 8;
            v45 = _mm_cvtsi32_si128(v24 << 8);
            v46 = *((int *)v6 + 32);
            v47 = (unsigned __int8 *)(v21 + 2 * v24);
            *(double *)v45.m128i_i64 = _mm_cvtepi32_pd(v45).m128d_f64[0];
            v43 = (v47[2] * (int)(v16 * 256.0 - *(double *)v45.m128i_i64)
                 + v22 * v47[2 * v46]
                 + *v47 * (256 - (int)(v16 * 256.0 - *(double *)v45.m128i_i64) - v22)
                 + ((v22
                   * (int)(v16 * 256.0 - *(double *)v45.m128i_i64)
                   * (*v47 + v47[2 * v46 + 2] - v47[2 * v46] - v47[2])) >> 8)) >> 8;
LABEL_26:
            v21 = v198;
            goto LABEL_27;
          }
          if ( v24 > 0 && v24 < (int)v44 )
          {
            dword_18001BC58 = v24 << 8;
            v43 = (*(unsigned __int8 *)(v21 + 2 * v24) * (256 - v22)
                 + v22 * *(unsigned __int8 *)(v21 + 2 * v24 + 2 * v44)) >> 8;
LABEL_27:
            v23 = v190;
            goto LABEL_28;
          }
          LOBYTE(v43) = 16;
LABEL_28:
          v14 = v23 + 2;
          *v23 = v43;
          v23 = v14;
          ++v183;
          v190 = v14;
          if ( v183 >= *((_DWORD *)v6 + 34) )
            goto LABEL_60;
        }
      }
      v48 = (int *)((char *)v6 + 132);
    }
    if ( v20 < *v19 - 1 )
    {
      v50 = 0;
      if ( *((int *)v6 + 34) <= 0 )
        goto LABEL_61;
      while ( 1 )
      {
        v16 = v16 + a2;
        v51 = (int)v16;
        v52 = (int)v16 <= 0;
        if ( (int)v16 < 0 )
          goto LABEL_38;
        v53 = *((int *)v6 + 32);
        if ( v51 >= (int)v53 - 1 )
          break;
        dword_18001BC58 = v51 << 8;
        v54 = (unsigned __int8 *)(v21 + 2 * v51);
        v55 = v54[2 * v53 + 2];
        v56 = v54[2];
        v57 = v54[2 * v53];
        v58 = v55 - v57 - v56;
        v59 = v16 * 256.0 - (double)(v51 << 8);
        v60 = v56 * (int)v59;
        v21 = v198;
        v61 = (v60 + v22 * v57 + *v54 * (256 - (int)v59 - v22) + ((v22 * (int)v59 * (*v54 + v58)) >> 8)) >> 8;
LABEL_42:
        *v14 = v61;
        v63 = v14 + 2;
        ++v50;
        v14 += 2;
        if ( v50 >= *((_DWORD *)v6 + 34) )
        {
          v190 = v63;
          goto LABEL_61;
        }
      }
      v52 = v51 <= 0;
LABEL_38:
      if ( v52 || (v62 = *((int *)v6 + 32), v51 >= (int)v62) )
      {
        LOBYTE(v61) = 16;
      }
      else
      {
        dword_18001BC58 = v51 << 8;
        v61 = (*(unsigned __int8 *)(v21 + 2 * v51) * (256 - v22) + v22 * *(unsigned __int8 *)(v21 + 2 * v51 + 2 * v62)) >> 8;
      }
      goto LABEL_42;
    }
    v49 = v20 <= 0;
LABEL_45:
    if ( !v49 && v20 < *v48 )
    {
      v64 = 0;
      if ( *((int *)v6 + 34) <= 0 )
        goto LABEL_61;
      while ( 1 )
      {
        v16 = v16 + a2;
        v65 = (int)v16;
        v66 = (int)v16 <= 0;
        if ( (int)v16 < 0 )
          goto LABEL_52;
        if ( v65 >= *((_DWORD *)v6 + 32) - 1 )
          break;
        dword_18001BC58 = v65 << 8;
        v67 = ((int)(v16 * 256.0 - (double)(v65 << 8)) * *(unsigned __int8 *)(2 * v65 + v21 + 2)
             + *(unsigned __int8 *)(2 * v65 + v21) * (256 - (int)(v16 * 256.0 - (double)(v65 << 8)))) >> 8;
LABEL_56:
        *v14 = v67;
        v68 = v14 + 2;
        ++v64;
        v14 += 2;
        if ( v64 >= *((_DWORD *)v6 + 34) )
        {
          v190 = v68;
          goto LABEL_61;
        }
      }
      v66 = v65 <= 0;
LABEL_52:
      if ( v66 || v65 >= *((_DWORD *)v6 + 32) )
        LOBYTE(v67) = 16;
      else
        LOBYTE(v67) = *(_BYTE *)(2 * v65 + v21);
      goto LABEL_56;
    }
    v69 = 0;
    if ( *((int *)v6 + 34) > 0 )
    {
      do
      {
        *v14 = 16;
        ++v69;
        v14 += 2;
      }
      while ( v69 < *((_DWORD *)v6 + 34) );
LABEL_60:
      v190 = v14;
    }
LABEL_61:
    v70 = *((_DWORD *)v6 + 35);
    v15 = v173 + 1;
    v173 = v15;
  }
  while ( v15 < v70 );
  v71 = 0;
  v195 = 0;
  if ( v70 > 0 )
  {
    v72 = a3 - (a2 + a2);
    while ( 1 )
    {
      v73 = v72;
      if ( *((_DWORD *)v6 + 36) )
        v74 = (a4 - 1.0) * 0.5;
      else
        v74 = 0.0;
      v75 = (double)v71 * a4 + a5 + v74;
      v76 = (int)v75;
      dword_18001BC58 = (int)v75 << 8;
      v77 = (int)(v75 * 256.0 - (double)((int)v75 << 8));
      v191 = v77;
      v78 = (int)v75 < 0;
      if ( (int)v75 > 0 )
      {
        if ( v76 < *((_DWORD *)v6 + 33) - 2 )
        {
          v193 = 0;
          v199 = (v77 * v77) >> 8;
          v187 = (v77 * v199) >> 8;
          if ( *((int *)v6 + 34) > 0 )
          {
            v79 = v188;
            v80 = (int *)((char *)v6 + 128);
            v81 = v185;
            while ( 1 )
            {
              v73 = v73 + a2 + a2;
              v82 = (int)(v73 * 0.5);
              if ( v82 <= 0 )
              {
                if ( v82 < 0 )
                {
                  v80 = (int *)((char *)v6 + 128);
LABEL_86:
                  if ( v82 <= 0 || (v125 = *v80, v82 >= *v80 / 2) )
                  {
                    *v79 = 0x80;
                    LOBYTE(v115) = 0x80;
                  }
                  else
                  {
                    dword_18001BC58 = v82 << 8;
                    v126 = 2 * (v76 * (int)v125 + 2 * v82);
                    *v79 = (unsigned __int16)((256 - v77) * *(unsigned __int8 *)(v126 + v196)
                                            + v77 * *(unsigned __int8 *)(v126 + v196 + 2 * v125)) >> 8;
                    v81 = v185;
                    v115 = ((256 - v77) * *(unsigned __int8 *)(v126 + v197)
                          + v77 * *(unsigned __int8 *)(v126 + v197 + 2LL * *v80)) >> 8;
                  }
                  goto LABEL_90;
                }
              }
              else
              {
                v80 = (int *)((char *)v6 + 128);
                v83 = *((int *)v6 + 32);
                v201 = (int *)((char *)v6 + 128);
                if ( v82 < *((_DWORD *)v6 + 32) / 2 - 2 )
                {
                  dword_18001BC58 = v82 << 8;
                  v177 = (int)(v73 * 128.0 - (double)(v82 << 8)) / 2;
                  v184 = (v177 * v177) >> 8;
                  v182 = (v184 * v177) >> 8;
                  v84 = 2 * (v76 * v83 + 2 * v82);
                  v85 = (unsigned __int8 *)(v84 + v196);
                  v200 = v84;
                  v86 = &v85[-2 * v83];
                  v87 = v85[2 * v83 + 4];
                  v88 = v85[2 * v83 - 4];
                  v89 = *(v86 - 4);
                  v90 = v86[4];
                  v91 = v86[8];
                  v92 = v85[2 * v83 + 8];
                  v93 = v85[4 * v83 - 4];
                  v94 = v85[4 * v83];
                  v95 = v85[4 * v83 + 8];
                  v174 = *(v85 - 4);
                  v171 = v85[4];
                  v179 = v85[8];
                  v165 = v85[2 * v83];
                  v204 = *v86;
                  v96 = v85[4 * v83 + 4];
                  v162 = *v85;
                  v168 = v199
                       * (((2 * (v204 + 2 * v165) - v94 - 5 * v162) >> 1 << 8)
                        + v177
                        * ((7 * v174 + 3 * (v87 - v171) + 2 * (v165 + v93 + 2 * (v204 - v89 - v162) - v94) - 5 * v88) >> 1)
                        + v182
                        * ((11 * (v171 - v162)
                          + 5 * (v92 - v88)
                          + 7 * (v174 + v165 - v87 - v179)
                          + 2 * (v93 + 2 * (v91 + v96 + 2 * (v204 - v90) - v94 - v89) - v95)) >> 1)
                        + v184
                        * ((5 * (2 * (v90 + v88 + 2 * v162) - v96 - v92)
                          + 7 * (v179 + v94 - 2 * (v204 + v174))
                          + 2 * (v95 + 2 * (2 * (v87 + v89) - v93 - v91))
                          - 13 * (v165 + v171)) >> 1));
                  v97 = ((((v162 << 8)
                         + v191 * ((v165 - v204) >> 1)
                         + v177 * ((v171 - v174) >> 1)
                         + v182 * ((v179 + 3 * (v162 - v171) - v174) >> 1)
                         + v187 * ((v94 + 3 * (v162 - v165) - v204) >> 1)
                         + v184 * ((2 * (v174 + 2 * v171) - 5 * v162 - v179) >> 1)) << 8)
                       + v191
                       * (v177 * (v162 + v89 - v204 - v174)
                        + v182 * (v162 + v179 + v89 + v165 + 2 * (v90 - v204) - v87 - v91 - v174 - v171)
                        + v184
                        * ((3 * (v87 - v165) + 7 * v204 + 2 * (v171 + v91 + 2 * (v174 - v89 - v162) - v179) - 5 * v90) >> 1))
                       + v187
                       * (v177 * (v162 + v171 + v89 + v94 + 2 * (v88 - v174) - v93 - v87 - v165 - v204)
                        + v182
                        * (v89
                         + v95
                         + 3 * (v162 + v87 - v165 - v171)
                         + 2 * (v179 + v90 + v88 + v94 - v96 - v92 - v204 - v174)
                         - v93
                         - v91)
                        + v184
                        * ((5 * (v96 - v90)
                          + 11 * (v165 - v162)
                          + 7 * (v171 + v204 - v94 - v87)
                          + 2 * (v91 + 2 * (v92 + v93 + 2 * (v174 - v88) - v89 - v179) - v95)) >> 1))
                       + v168) >> 16;
                  if ( v97 > 255 )
                    v97 = 255;
                  v98 = 0;
                  if ( v97 >= 0 )
                    v98 = v97;
                  *v188 = v98;
                  v99 = *(unsigned __int8 *)(v197 + v200 + 8);
                  v166 = *(unsigned __int8 *)(v197 + v200);
                  v100 = *v201;
                  v101 = *(unsigned __int8 *)(v197 + v200 + 4 * v100 - 4);
                  v102 = *(unsigned __int8 *)(v197 + v200 + 2 * v100 + 4);
                  v103 = (unsigned __int8 *)(v197 + v200 - 2 * v100);
                  v104 = *(unsigned __int8 *)(v197 + v200 + 2 * v100 - 4);
                  v105 = *(unsigned __int8 *)(v197 + v200 + 2 * v100 + 8);
                  v106 = *(unsigned __int8 *)(v197 + v200 + 4 * v100 + 8);
                  v107 = *(v103 - 4);
                  v108 = v103[4];
                  v109 = v103[8];
                  v172 = *(unsigned __int8 *)(v197 + v200 - 4);
                  v175 = *(unsigned __int8 *)(v197 + v200 + 4);
                  v163 = *(unsigned __int8 *)(v197 + v200 + 2 * v100);
                  v180 = *(unsigned __int8 *)(v197 + v200 + 4 * v100);
                  v205 = *v103;
                  v110 = *(unsigned __int8 *)(v197 + v200 + 4 * v100 + 4);
                  v169 = v199
                       * (((2 * (v205 + 2 * v163) - 5 * v166 - v180) >> 1 << 8)
                        + v177
                        * ((7 * v172 + 3 * (v102 - v175) + 2 * (v101 + v163 + 2 * (v205 - v166 - v107) - v180) - 5 * v104) >> 1)
                        + v182
                        * ((11 * (v175 - v166)
                          + 5 * (v105 - v104)
                          + 7 * (v172 + v163 - v99 - v102)
                          + 2 * (v101 + 2 * (v109 + v110 + 2 * (v205 - v108) - v180 - v107) - v106)) >> 1)
                        + v184
                        * ((5 * (2 * (v108 + v104 + 2 * v166) - v110 - v105)
                          + 7 * (v180 + v99 - 2 * (v205 + v172))
                          + 2 * (v106 + 2 * (2 * (v102 + v107) - v101 - v109))
                          - 13 * (v163 + v175)) >> 1));
                  v111 = v187
                       * (v177 * (v107 + v166 + v175 + v180 + 2 * (v104 - v172) - v163 - v101 - v102 - v205)
                        + v182
                        * (v107
                         + v106
                         + 3 * (v166 + v102 - v163 - v175)
                         + 2 * (v108 + v104 + v180 + v99 - v172 - v110 - v105 - v205)
                         - v101
                         - v109)
                        + v184
                        * ((5 * (v110 - v108)
                          + 11 * (v163 - v166)
                          + 7 * (v205 + v175 - v180 - v102)
                          + 2 * (v109 + 2 * (v105 + v101 + 2 * (v172 - v104) - v99 - v107) - v106)) >> 1))
                       + v169;
                  LODWORD(v100) = v184
                                * ((7 * v205
                                  + 3 * (v102 - v163)
                                  + 2 * (v175 + v109 + 2 * (v172 - v166 - v107) - v99)
                                  - 5 * v108) >> 1);
                  v112 = 2 * (v108 - v205) - v172 - v102 - v109;
                  v6 = this;
                  LODWORD(v103) = v177 * (v107 + v166 - v172 - v205);
                  v113 = v107 + v166 + v99 + v163 + v112 - v175;
                  v77 = (int)(v75 * 256.0 - (double)((int)v75 << 8));
                  LODWORD(v100) = v182 * v113 + v100;
                  v80 = (int *)((char *)this + 128);
                  v76 = (int)v75;
                  v81 = v185;
                  v114 = ((((v166 << 8)
                          + v191 * ((v163 - v205) >> 1)
                          + v177 * ((v175 - v172) >> 1)
                          + v187 * ((v180 + 3 * (v166 - v163) - v205) >> 1)
                          + v182 * ((v99 + 3 * (v166 - v175) - v172) >> 1)
                          + v184 * ((2 * (v172 + 2 * v175) - 5 * v166 - v99) >> 1)) << 8)
                        + v191 * ((int)v103 + (int)v100)
                        + v111) >> 16;
                  if ( v114 > 255 )
                    v114 = 255;
                  LOBYTE(v115) = 0;
                  v78 = v114 < 0;
                  v116 = v114;
                  v79 = v188;
                  if ( !v78 )
                    LOBYTE(v115) = v116;
                  goto LABEL_90;
                }
              }
              v117 = *v80;
              if ( v82 >= *v80 / 2 - 1 )
                goto LABEL_86;
              dword_18001BC58 = v82 << 8;
              v118 = 2 * (v76 * (int)v117 + 2 * v82);
              v119 = (int)(v73 * 128.0 - (double)(v82 << 8)) / 2;
              v120 = *(unsigned __int8 *)(v118 + v196 + 2 * v117);
              v121 = *(unsigned __int8 *)(v118 + v196) * (256 - v119 - v77)
                   + *(unsigned __int8 *)(v118 + v196 + 4) * v119
                   + ((v77
                     * v119
                     * (*(unsigned __int8 *)(v118 + v196)
                      + *(unsigned __int8 *)(v118 + v196 + 2 * v117 + 4)
                      - v120
                      - *(unsigned __int8 *)(v118 + v196 + 4))) >> 8);
              v122 = v120 * v77;
              v79 = v188;
              *v188 = (unsigned __int16)(v122 + v121) >> 8;
              v123 = *v80;
              v124 = *(unsigned __int8 *)(v118 + v197 + 2 * v123);
              v81 = v185;
              v76 = (int)v75;
              v115 = (v77 * v124
                    + *(unsigned __int8 *)(v118 + v197) * (256 - v119 - v77)
                    + ((v77
                      * v119
                      * (*(unsigned __int8 *)(v118 + v197)
                       + *(unsigned __int8 *)(v118 + v197 + 2 * v123 + 4)
                       - v124
                       - *(unsigned __int8 *)(v118 + v197 + 4))) >> 8)
                    + v119 * *(unsigned __int8 *)(v118 + v197 + 4)) >> 8;
LABEL_90:
              v127 = v81 + 4;
              *v81 = v115;
              v79 += 4;
              v193 += 2;
              v81 += 4;
              v188 = v79;
              v185 = v81;
              if ( v193 >= *((_DWORD *)v6 + 34) )
              {
                v185 = v127;
                goto LABEL_127;
              }
            }
          }
          goto LABEL_128;
        }
        v78 = v76 < 0;
      }
      if ( !v78 && v76 < *((_DWORD *)v6 + 33) - 1 )
      {
        v128 = 0;
        if ( *((int *)v6 + 34) <= 0 )
          goto LABEL_128;
        v79 = v188;
        v129 = (int *)((char *)v6 + 128);
        v130 = v185;
        while ( 1 )
        {
          v73 = v73 + a2 + a2;
          v131 = (int)(v73 * 0.5);
          v132 = v131 <= 0;
          if ( v131 >= 0 )
          {
            v129 = (int *)((char *)v6 + 128);
            v133 = *((int *)v6 + 32);
            if ( v131 < *((_DWORD *)v6 + 32) / 2 - 1 )
            {
              dword_18001BC58 = v131 << 8;
              v134 = (double)(v131 << 8);
              v135 = (int)(v73 * 128.0 - v134) / 2;
              v136 = 256 - v77 - v135;
              v137 = 2 * (v76 * (int)v133 + 2 * v131);
              v138 = *(unsigned __int8 *)(v137 + v196 + 2 * v133 + 4);
              v139 = *(unsigned __int8 *)(v137 + v196 + 2 * v133);
              v140 = *(unsigned __int8 *)(v137 + v196 + 4);
              v141 = v139 * v77
                   + *(unsigned __int8 *)(v137 + v196) * v136
                   + ((v135 * v77 * (*(unsigned __int8 *)(v137 + v196) + v138 - v139 - v140)) >> 8);
              LOWORD(v135) = v140 * v135;
              v79 = v188;
              *v188 = (unsigned __int16)(v135 + v141) >> 8;
              v142 = *v129;
              v129 = (int *)((char *)v6 + 128);
              v143 = *(unsigned __int8 *)(v137 + v197 + 2 * v142);
              v130 = v185;
              v144 = (v77 * v143
                    + *(unsigned __int8 *)(v137 + v197 + 4) * ((int)(v73 * 128.0 - v134) / 2)
                    + *(unsigned __int8 *)(v137 + v197) * v136
                    + (((int)(v73 * 128.0 - v134)
                      / 2
                      * v77
                      * (*(unsigned __int8 *)(v137 + v197)
                       + *(unsigned __int8 *)(v137 + v197 + 2 * v142 + 4)
                       - v143
                       - *(unsigned __int8 *)(v137 + v197 + 4))) >> 8)) >> 8;
              goto LABEL_106;
            }
            v132 = v131 <= 0;
          }
          if ( v132 )
          {
            v129 = (int *)((char *)v6 + 128);
LABEL_105:
            *v79 = 0x80;
            LOBYTE(v144) = 0x80;
            goto LABEL_106;
          }
          v145 = *v129;
          if ( v131 >= *v129 / 2 )
            goto LABEL_105;
          dword_18001BC58 = v131 << 8;
          v146 = 2 * (v76 * (int)v145 + 2 * v131);
          *v79 = (unsigned __int16)((256 - v77) * *(unsigned __int8 *)(v146 + v196)
                                  + v77 * *(unsigned __int8 *)(v146 + v196 + 2 * v145)) >> 8;
          v130 = v185;
          v144 = ((256 - v77) * *(unsigned __int8 *)(v146 + v197) + v77
                                                                  * *(unsigned __int8 *)(v146 + v197 + 2LL * *v129)) >> 8;
LABEL_106:
          *v130 = v144;
          v147 = v130 + 4;
          v76 = (int)v75;
          v79 += 4;
          v128 += 2;
          v188 = v79;
          v130 = v147;
          v185 = v147;
          if ( v128 >= *((_DWORD *)v6 + 34) )
            goto LABEL_126;
        }
      }
      if ( v76 <= 0 || v76 >= *((_DWORD *)v6 + 33) )
      {
        v160 = 0;
        if ( *((int *)v6 + 34) > 0 )
        {
          v79 = v188;
          v147 = v185;
          do
          {
            *v79 = 0x80;
            v160 += 2;
            *v147 = 0x80;
            v79 += 4;
            v147 += 4;
          }
          while ( v160 < *((_DWORD *)v6 + 34) );
LABEL_126:
          v185 = v147;
LABEL_127:
          v188 = v79;
        }
        goto LABEL_128;
      }
      v148 = 0;
      if ( *((int *)v6 + 34) > 0 )
        break;
LABEL_128:
      v71 = v195 + 1;
      v195 = v71;
      if ( v71 >= *((_DWORD *)v6 + 35) )
        return;
    }
    v79 = v188;
    v149 = (int *)((char *)v6 + 128);
    v150 = v185;
    while ( 2 )
    {
      v73 = v73 + a2 + a2;
      v151 = (int)(v73 * 0.5);
      v152 = v151 <= 0;
      if ( v151 >= 0 )
      {
        v149 = (int *)((char *)v6 + 128);
        v153 = *((_DWORD *)v6 + 32);
        if ( v151 < v153 / 2 - 1 )
        {
          dword_18001BC58 = v151 << 8;
          v154 = (double)(v151 << 8);
          v155 = 2 * (v76 * v153 + 2 * v151);
          v156 = (int)(v73 * 128.0 - v154) / 2;
          *v79 = (unsigned __int16)((256 - v156) * *(unsigned __int8 *)(v155 + v196)
                                  + v156 * *(unsigned __int8 *)(v155 + v196 + 4)) >> 8;
          v150 = v185;
          v149 = (int *)((char *)v6 + 128);
          v157 = ((256 - v156) * *(unsigned __int8 *)(v155 + v197) + v156 * *(unsigned __int8 *)(v155 + v197 + 4)) >> 8;
          goto LABEL_121;
        }
        v152 = v151 <= 0;
      }
      if ( v152 )
      {
        v149 = (int *)((char *)v6 + 128);
      }
      else
      {
        v158 = *v149;
        if ( v151 < *v149 / 2 )
        {
          dword_18001BC58 = v151 << 8;
          v159 = 2 * (v76 * v158 + 2 * v151);
          *v79 = *(_BYTE *)(v196 + v159);
          LOBYTE(v157) = *(_BYTE *)(v197 + v159);
          v150 = v185;
          goto LABEL_121;
        }
      }
      *v79 = 0x80;
      LOBYTE(v157) = 0x80;
LABEL_121:
      v147 = v150 + 4;
      *v150 = v157;
      v79 += 4;
      v185 = v150 + 4;
      v148 += 2;
      v150 += 4;
      if ( v148 >= *((_DWORD *)v6 + 34) )
        goto LABEL_126;
      continue;
    }
  }
}

```

## disassembly

```asm
0x18000ccf0  mov     [rsp+arg_0], rcx
0x18000ccf5  push    rbx
0x18000ccf6  push    rbp
0x18000ccf7  sub     rsp, 108h
0x18000ccfe  cmp     [rsp+118h+arg_28], 0
0x18000cd06  mov     rbp, rcx
0x18000cd09  mov     rcx, [rcx+98h]
0x18000cd10  movaps  xmm4, xmm1
0x18000cd13  movaps  [rsp+118h+var_58], xmm8
0x18000cd1c  movaps  xmm8, xmm3
0x18000cd20  movaps  [rsp+118h+var_98], xmm12
0x18000cd29  movaps  xmm12, xmm2
0x18000cd2d  mov     rdx, [rbp+0B0h]
0x18000cd34  lea     r8, [rcx+1]
0x18000cd38  lea     rax, [rdx+1]
0x18000cd3c  mov     [rsp+118h+var_E0], rax
0x18000cd41  jz      short loc_18000CD5A
0x18000cd43  mov     [rsp+118h+var_C0], r8
0x18000cd48  lea     rax, [rdx+3]
0x18000cd4c  add     rcx, 3
0x18000cd50  mov     [rsp+118h+var_D0], rdx
0x18000cd55  mov     rbx, rdx
0x18000cd58  jmp     short loc_18000CD7B
0x18000cd5a  mov     [rsp+118h+var_C0], rcx
0x18000cd5f  mov     rbx, rax
0x18000cd62  mov     [rsp+118h+var_D0], rax
0x18000cd67  add     rcx, 2
0x18000cd6b  lea     rax, [rdx+2]
0x18000cd6f  mov     [rsp+118h+var_E0], rdx
0x18000cd74  mov     [rbp+98h], r8
0x18000cd7b  mov     [rsp+118h+var_F0], rax
0x18000cd80  xor     eax, eax
0x18000cd82  mov     [rsp+118h+var_B8], rcx
0x18000cd87  mov     [rsp+118h+var_108], eax
0x18000cd8b  cmp     [rbp+8Ch], eax
0x18000cd91  jle     loc_18000E4D5
0x18000cd97  movsd   xmm5, cs:__real@3fe0000000000000
0x18000cd9f  movsd   xmm3, cs:__real@4070000000000000
0x18000cda7  mov     [rsp+118h+arg_8], rsi
0x18000cdaf  mov     [rsp+118h+arg_10], rdi
0x18000cdb7  mov     [rsp+118h+arg_18], r12
0x18000cdbf  mov     [rsp+118h+var_18], r13
0x18000cdc7  mov     [rsp+118h+var_20], r14
0x18000cdcf  mov     [rsp+118h+var_28], r15
0x18000cdd7  movaps  [rsp+118h+var_38], xmm6
0x18000cddf  movaps  xmm6, xmm12
0x18000cde3  movaps  [rsp+118h+var_68], xmm9
0x18000cdec  subsd   xmm6, xmm4
0x18000cdf0  movaps  [rsp+118h+var_78], xmm10
0x18000cdf9  xorps   xmm9, xmm9
0x18000cdfd  movsd   xmm10, [rsp+118h+arg_20]
0x18000ce07  movaps  [rsp+118h+var_88], xmm11
0x18000ce10  movsd   xmm11, cs:__real@3ff0000000000000
0x18000ce19  nop     dword ptr [rax+00000000h]
0x18000ce20  cmp     dword ptr [rbp+90h], 0
0x18000ce27  movaps  xmm2, xmm6
0x18000ce2a  movd    xmm1, eax
0x18000ce2e  cvtdq2pd xmm1, xmm1
0x18000ce32  mulsd   xmm1, xmm8
0x18000ce37  addsd   xmm1, xmm10
0x18000ce3c  jz      short loc_18000CE4D
0x18000ce3e  movaps  xmm0, xmm8
0x18000ce42  subsd   xmm0, xmm11
0x18000ce47  mulsd   xmm0, xmm5
0x18000ce4b  jmp     short loc_18000CE51
0x18000ce4d  movaps  xmm0, xmm9
0x18000ce51  addsd   xmm1, xmm0
0x18000ce55  lea     rdx, [rbp+84h]
0x18000ce5c  cvttsd2si ecx, xmm1
0x18000ce60  mulsd   xmm1, xmm3
0x18000ce64  mov     eax, ecx
0x18000ce66  shl     eax, 8
0x18000ce69  mov     cs:dword_18001BC58, eax
0x18000ce6f  movd    xmm0, eax
0x18000ce73  mov     eax, ecx
0x18000ce75  imul    eax, [rbp+80h]
0x18000ce7c  cvtdq2pd xmm0, xmm0
0x18000ce80  add     eax, eax
0x18000ce82  movsxd  r9, eax
0x18000ce85  add     r9, [rbp+98h]
0x18000ce8c  mov     [rsp+118h+var_B0], r9
0x18000ce91  subsd   xmm1, xmm0
0x18000ce95  cvttsd2si r12d, xmm1
0x18000ce9a  mov     [rsp+118h+var_C8], r12d
0x18000ce9f  test    ecx, ecx
0x18000cea1  jle     loc_18000D3D7
0x18000cea7  mov     eax, [rdx]
0x18000cea9  sub     eax, 2
0x18000ceac  cmp     ecx, eax
0x18000ceae  jge     loc_18000D3D2
0x18000ceb4  mov     eax, r12d
0x18000ceb7  mov     [rsp+118h+var_F8], 0
0x18000cebf  imul    eax, r12d
0x18000cec3  sar     eax, 8
0x18000cec6  mov     [rsp+118h+var_C4], eax
0x18000ceca  imul    eax, r12d
0x18000cece  sar     eax, 8
0x18000ced1  cmp     dword ptr [rbp+88h], 0
0x18000ced8  mov     [rsp+118h+var_100], eax
0x18000cedc  jle     loc_18000D5F6
0x18000cee2  mov     rcx, [rsp+118h+var_D0]
0x18000cee7  nop     word ptr [rax+rax+00000000h]
0x18000cef0  addsd   xmm2, xmm4
0x18000cef4  cvttsd2si edx, xmm2
0x18000cef8  test    edx, edx
0x18000cefa  jle     loc_18000D2C7
0x18000cf00  movsxd  r10, dword ptr [rbp+80h]
0x18000cf07  lea     eax, [r10-2]
0x18000cf0b  cmp     edx, eax
0x18000cf0d  jge     loc_18000D2C9
0x18000cf13  mov     eax, edx
0x18000cf15  movaps  xmm1, xmm2
0x18000cf18  shl     eax, 8
0x18000cf1b  mov     cs:dword_18001BC58, eax
0x18000cf21  mulsd   xmm1, xmm3
0x18000cf25  movd    xmm0, eax
0x18000cf29  cvtdq2pd xmm0, xmm0
0x18000cf2d  subsd   xmm1, xmm0
0x18000cf31  cvttsd2si ecx, xmm1
0x18000cf35  mov     eax, ecx
0x18000cf37  imul    eax, ecx
0x18000cf3a  sar     eax, 8
0x18000cf3d  imul    ecx, eax
0x18000cf40  mov     [rsp+118h+var_E8], eax
0x18000cf44  lea     eax, [rdx+rdx]
0x18000cf47  movsxd  r8, eax
0x18000cf4a  mov     rdx, r10
0x18000cf4d  add     r8, r9
0x18000cf50  mov     rax, r8
0x18000cf53  sar     ecx, 8
0x18000cf56  mov     [rsp+118h+var_D8], ecx
0x18000cf5a  lea     rcx, [r10+r10]
0x18000cf5e  movzx   edi, byte ptr [rcx+r8-2]
0x18000cf64  sub     rax, rcx
0x18000cf67  movzx   esi, byte ptr [rcx+r8+2]
0x18000cf6d  movzx   r10d, byte ptr [rcx+r8+4]
0x18000cf73  movzx   r15d, byte ptr [r8]
0x18000cf77  movzx   r9d, byte ptr [rax]
0x18000cf7b  movzx   r14d, byte ptr [rax+2]
0x18000cf80  movzx   r12d, byte ptr [rax-2]
0x18000cf85  movzx   ebp, byte ptr [rax+4]
0x18000cf89  movzx   eax, byte ptr [r8-2]
0x18000cf8e  movzx   ebx, byte ptr [r8+rdx*4-2]
0x18000cf94  movzx   r11d, byte ptr [r8+rdx*4+4]
0x18000cf9a  movzx   r13d, byte ptr [r8+4]
0x18000cf9f  mov     [rsp+118h+var_110], eax
0x18000cfa3  movzx   eax, byte ptr [r8+2]
0x18000cfa8  mov     [rsp+118h+var_10C], eax
0x18000cfac  movzx   eax, byte ptr [rcx+r8]
0x18000cfb1  movzx   ecx, byte ptr [r8+rdx*4]
0x18000cfb6  mov     [rsp+118h+var_104], eax
0x18000cfba  mov     [rsp+118h+var_FC], ecx
0x18000cfbe  mov     [rsp+118h+var_114], r9d
0x18000cfc3  movzx   r9d, byte ptr [r8+rdx*4+2]
0x18000cfc9  mov     r8d, esi
0x18000cfcc  sub     r8d, eax
0x18000cfcf  mov     [rsp+118h+var_118], r15d
0x18000cfd3  mov     eax, [rsp+118h+var_114]
0x18000cfd7  lea     r15d, [r15+r15*4]
0x18000cfdb  add     eax, [rsp+118h+var_110]
0x18000cfdf  add     eax, eax
0x18000cfe1  sub     ecx, eax
0x18000cfe3  lea     eax, [rsi+r12]
0x18000cfe7  add     eax, eax
0x18000cfe9  add     ecx, r13d
0x18000cfec  sub     eax, ebx
0x18000cfee  imul    edx, ecx, 7
0x18000cff1  sub     eax, ebp
0x18000cff3  lea     eax, [r11+rax*2]
0x18000cff7  lea     ecx, [rdx+rax*2]
0x18000cffa  mov     eax, [rsp+118h+var_118]
0x18000cffd  lea     eax, [rdi+rax*2]
0x18000d000  add     eax, r14d
0x18000d003  add     eax, eax
0x18000d005  sub     eax, r9d
0x18000d008  sub     eax, r10d
0x18000d00b  lea     eax, [rax+rax*4]
0x18000d00e  add     ecx, eax
0x18000d010  mov     eax, [rsp+118h+var_10C]
0x18000d014  add     eax, [rsp+118h+var_104]
0x18000d018  mov     dword ptr [rsp+118h+arg_28], ecx
0x18000d01f  imul    ecx, eax, 0Dh
0x18000d022  mov     eax, dword ptr [rsp+118h+arg_28]
0x18000d029  sub     eax, ecx
0x18000d02b  mov     ecx, [rsp+118h+var_114]
0x18000d02f  sar     eax, 1
0x18000d031  sub     ecx, r14d
0x18000d034  imul    eax, [rsp+118h+var_E8]
0x18000d039  add     ecx, ecx
0x18000d03b  sub     ecx, [rsp+118h+var_FC]
0x18000d03f  mov     dword ptr [rsp+118h+arg_28], eax
0x18000d046  mov     eax, [rsp+118h+var_104]
0x18000d04a  sub     ecx, r12d
0x18000d04d  sub     eax, esi
0x18000d04f  add     ecx, r9d
0x18000d052  sub     eax, r13d
0x18000d055  add     ecx, ebp
0x18000d057  add     eax, [rsp+118h+var_110]
0x18000d05b  add     ecx, ecx
0x18000d05d  imul    eax, 7
0x18000d060  sub     ecx, r11d
0x18000d063  add     ecx, ebx
0x18000d065  lea     edx, [rax+rcx*2]
0x18000d068  mov     eax, r10d
0x18000d06b  sub     eax, edi
0x18000d06d  lea     eax, [rax+rax*4]
0x18000d070  add     edx, eax
0x18000d072  mov     eax, [rsp+118h+var_10C]
0x18000d076  sub     eax, [rsp+118h+var_118]
0x18000d079  imul    ecx, eax, 0Bh
0x18000d07c  mov     eax, esi
0x18000d07e  sub     eax, [rsp+118h+var_10C]
0x18000d082  add     edx, ecx
0x18000d084  lea     eax, [rax+rax*2]
0x18000d087  mov     ecx, [rsp+118h+var_114]
0x18000d08b  sub     ecx, r12d
0x18000d08e  sar     edx, 1
0x18000d090  sub     ecx, [rsp+118h+var_118]
0x18000d093  imul    edx, [rsp+118h+var_D8]
0x18000d098  add     ecx, ecx
0x18000d09a  add     dword ptr [rsp+118h+arg_28], edx
0x18000d0a1  mov     edx, [rsp+118h+var_FC]
0x18000d0a5  sub     ecx, edx
0x18000d0a7  add     ecx, ebx
0x18000d0a9  add     ecx, [rsp+118h+var_104]
0x18000d0ad  lea     ecx, [rax+rcx*2]
0x18000d0b0  lea     eax, [rdi+rdi*4]
0x18000d0b3  sub     ecx, eax
0x18000d0b5  imul    eax, [rsp+118h+var_110], 7
0x18000d0ba  add     ecx, eax
0x18000d0bc  sar     ecx, 1
0x18000d0be  cvttsd2si eax, xmm1
0x18000d0c2  imul    ecx, eax
0x18000d0c5  mov     eax, [rsp+118h+var_104]
0x18000d0c9  add     dword ptr [rsp+118h+arg_28], ecx
0x18000d0d0  mov     ecx, [rsp+118h+var_114]
0x18000d0d4  lea     eax, [rcx+rax*2]
0x18000d0d7  mov     ecx, dword ptr [rsp+118h+arg_28]
0x18000d0de  add     eax, eax
0x18000d0e0  sub     eax, edx
0x18000d0e2  sub     eax, r15d
0x18000d0e5  sar     eax, 1
0x18000d0e7  shl     eax, 8
0x18000d0ea  add     ecx, eax
0x18000d0ec  mov     eax, [rsp+118h+var_114]
0x18000d0f0  imul    ecx, [rsp+118h+var_C4]
0x18000d0f5  sub     eax, edx
0x18000d0f7  sub     eax, esi
0x18000d0f9  add     eax, [rsp+118h+var_10C]
0x18000d0fd  imul    eax, 7
0x18000d100  mov     dword ptr [rsp+118h+arg_28], ecx
0x18000d107  mov     ecx, [rsp+118h+var_110]
0x18000d10b  sub     ecx, edi
0x18000d10d  add     ecx, ecx
0x18000d10f  sub     ecx, r12d
0x18000d112  sub     ecx, r13d
0x18000d115  add     ecx, ebx
0x18000d117  add     ecx, r10d
0x18000d11a  add     ecx, ecx
0x18000d11c  sub     ecx, r11d
0x18000d11f  add     ecx, ebp
0x18000d121  lea     edx, [rax+rcx*2]
0x18000d124  mov     eax, [rsp+118h+var_104]
0x18000d128  sub     eax, [rsp+118h+var_118]
0x18000d12b  imul    eax, 0Bh
0x18000d12e  add     edx, eax
0x18000d130  mov     eax, r9d
0x18000d133  sub     eax, r14d
0x18000d136  lea     eax, [rax+rax*4]
0x18000d139  add     edx, eax
0x18000d13b  sar     edx, 1
0x18000d13d  imul    edx, [rsp+118h+var_E8]
0x18000d142  mov     ecx, [rsp+118h+var_FC]
0x18000d146  mov     eax, r8d
0x18000d149  sub     eax, [rsp+118h+var_10C]
0x18000d14d  sub     ecx, r9d
0x18000d150  add     eax, [rsp+118h+var_118]
0x18000d153  sub     ecx, r10d
0x18000d156  sub     ecx, [rsp+118h+var_114]
0x18000d15a  sub     ecx, [rsp+118h+var_110]
0x18000d15e  add     ecx, edi
0x18000d160  mov     r10d, [rsp+118h+var_D8]
0x18000d165  sub     edi, [rsp+118h+var_110]
0x18000d169  lea     eax, [rax+rax*2]
0x18000d16c  add     ecx, r14d
0x18000d16f  add     edi, edi
0x18000d171  add     ecx, r13d
0x18000d174  sub     edi, ebx
0x18000d176  sub     edi, esi
0x18000d178  lea     ecx, [rax+rcx*2]
0x18000d17b  sub     ecx, ebx
0x18000d17d  lea     eax, [r14+r14*4]
0x18000d181  mov     ebx, dword ptr [rsp+118h+arg_28]
0x18000d188  sub     ecx, ebp
0x18000d18a  add     ecx, r11d
0x18000d18d  mov     r11d, [rsp+118h+var_104]
0x18000d192  add     ecx, r12d
0x18000d195  sub     edi, r11d
0x18000d198  sub     edi, [rsp+118h+var_114]
0x18000d19c  add     edi, [rsp+118h+var_FC]
  ... truncated ...
```
