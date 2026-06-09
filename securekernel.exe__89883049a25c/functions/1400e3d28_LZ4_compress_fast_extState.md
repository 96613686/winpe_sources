# LZ4_compress_fast_extState

- ea: `0x1400e3d28`
- end: `0x1400e4b93`
- name: `LZ4_compress_fast_extState`
- size: `3691`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400e3c58`

## callees

- `0x1400e3cfc`
- `0x1400e3d28`
- `0x1400e4b9c`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall LZ4_compress_fast_extState(__int64 a1, char *a2, char *a3, int a4, int a5)
{
  __int64 v5; // rsi
  char *v6; // r13
  unsigned int v8; // ebx
  __int64 v9; // rdx
  char *v10; // r15
  char *v11; // rdi
  char *v12; // r10
  char *v13; // rsi
  int v14; // ebp
  int v15; // r13d
  __int64 v16; // r8
  __int16 v17; // r12
  char *v18; // r10
  __int16 v19; // r12
  int v20; // ebp
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // r8d
  char *v24; // rdx
  char *v25; // rsi
  int v26; // ecx
  char *v27; // rdi
  int v28; // eax
  char *v29; // r8
  char *v30; // rdi
  __int64 v31; // rax
  unsigned __int64 v32; // rbp
  _WORD *v33; // rcx
  _QWORD *v34; // r14
  __int16 v35; // ax
  _QWORD *v36; // rdx
  char *v37; // rcx
  unsigned int v40; // ecx
  char v43; // al
  unsigned int n; // ecx
  char *v45; // rdi
  unsigned __int64 v46; // rcx
  __int64 v47; // rdx
  size_t v48; // r15
  unsigned __int64 v49; // rax
  char *v50; // rbp
  __int64 v51; // rcx
  char *v52; // r8
  char *v53; // rdi
  char *v54; // r15
  char *v55; // rsi
  unsigned __int64 v56; // rdx
  int v57; // eax
  int k; // r13d
  char *v59; // r12
  unsigned int v60; // r10d
  unsigned int *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  char *v64; // rsi
  char *v65; // r10
  char *v66; // r8
  char *v67; // rsi
  int v68; // ecx
  _BYTE *v69; // rdi
  int v70; // eax
  _QWORD *v71; // rdx
  _BYTE *v72; // rdi
  __int64 v73; // rax
  unsigned __int64 v74; // r12
  _WORD *v75; // rcx
  _QWORD *v76; // r15
  _QWORD *v77; // rdx
  char *v78; // rcx
  unsigned int v81; // ecx
  char v84; // al
  unsigned int m; // ecx
  char *v86; // rdi
  unsigned __int64 v87; // rcx
  __int64 v88; // rax
  size_t v89; // rbp
  unsigned __int64 v90; // rax
  __int64 v91; // r8
  char *v92; // rbp
  char *v93; // rdi
  char *v94; // r10
  char *v95; // rsi
  char *v96; // r8
  int v97; // r15d
  int v98; // r13d
  __int64 v99; // rdx
  char *v100; // r10
  __int16 v101; // r12
  int v102; // r15d
  __int64 v103; // rcx
  __int64 v104; // rax
  unsigned int v105; // edx
  char *v106; // rsi
  __int64 v107; // rcx
  char *v108; // r15
  char *v109; // rdi
  int v110; // eax
  char *v111; // rdx
  char *v112; // rdi
  __int64 v113; // rax
  unsigned __int64 v114; // r12
  _WORD *v115; // rcx
  _QWORD *v116; // rdx
  __int16 v117; // ax
  _QWORD *v118; // rsi
  char *v119; // rcx
  unsigned int v122; // r8d
  char v125; // al
  unsigned int i; // r8d
  __int64 v127; // rax
  char *v128; // rdi
  unsigned __int64 v129; // rcx
  __int64 v130; // rsi
  size_t v131; // rbp
  unsigned __int64 v132; // rax
  _DWORD *v133; // rcx
  int v134; // edi
  int v135; // ebp
  __int64 v136; // rcx
  char *v137; // rbp
  char *v138; // r8
  char *v139; // rsi
  unsigned __int64 v140; // rdx
  int v141; // eax
  int j; // r13d
  char *v143; // r12
  unsigned int v144; // r10d
  unsigned int *v145; // rax
  __int64 v146; // rdx
  __int64 v147; // rcx
  char *v148; // rsi
  char *v149; // r10
  char *v150; // r8
  __int64 v151; // rcx
  char *v152; // r12
  _BYTE *v153; // rdi
  int v154; // eax
  _QWORD *v155; // rdx
  _BYTE *v156; // rdi
  __int64 v157; // rax
  unsigned __int64 v158; // r15
  unsigned __int64 v159; // r13
  _WORD *v160; // rcx
  _QWORD *v161; // rsi
  _QWORD *v162; // rdx
  _QWORD *v163; // rcx
  unsigned int v166; // r10d
  char *v169; // rsi
  char v170; // al
  unsigned int v171; // r10d
  __int64 v172; // rax
  char *v173; // rdi
  unsigned __int64 v174; // rcx
  __int64 v175; // rax
  char *v176; // rcx
  unsigned int *inited; // [rsp+20h] [rbp-78h]
  char *v179; // [rsp+28h] [rbp-70h]
  char *v180; // [rsp+28h] [rbp-70h]
  char *v181; // [rsp+28h] [rbp-70h]
  char *v182; // [rsp+28h] [rbp-70h]
  char *v183; // [rsp+30h] [rbp-68h]
  char *v184; // [rsp+30h] [rbp-68h]
  char *v185; // [rsp+30h] [rbp-68h]
  char *v186; // [rsp+38h] [rbp-60h]
  int v187; // [rsp+B0h] [rbp+18h]

  v187 = (int)a3;
  v5 = a4;
  v6 = a3;
  inited = (unsigned int *)LZ4_initStream();
  if ( a5 < (int)LZ4_compressBound((unsigned int)v5) )
  {
    if ( (int)v5 < 65547 )
    {
      v8 = 0;
      if ( (unsigned int)v5 > 0x7E000000 )
        return v8;
      if ( !(_DWORD)v5 )
      {
        if ( a5 <= 0 )
          return v8;
        goto LABEL_5;
      }
      v91 = inited[4100];
      inited[4102] += v5;
      v92 = &a2[v5];
      v184 = &v6[a5];
      v93 = v6;
      inited[4101] = 3;
      inited[4100] = v91 + v5;
      if ( (int)v5 >= 13 )
      {
        v94 = a2 + 1;
        v186 = a2;
        v95 = &a2[-v91];
        v181 = &a2[-v91];
        *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)a2) >> 19)) = v91;
LABEL_123:
        v96 = v94;
        v97 = 1;
        v98 = 64;
        v99 = (unsigned int)(-1640531535 * *(_DWORD *)v94) >> 19;
        while ( 1 )
        {
          v100 = v96;
          v101 = (_WORD)v96 - (_WORD)v95;
          v96 += v97;
          if ( v96 > v92 - 11 )
          {
LABEL_171:
            LODWORD(v6) = v187;
            goto LABEL_172;
          }
          v102 = v98;
          v103 = (unsigned int)v99;
          ++v98;
          v97 = v102 >> 6;
          v104 = *((unsigned __int16 *)inited + v99);
          v105 = -1640531535 * *(_DWORD *)v96;
          v106 = &v95[v104];
          *((_WORD *)inited + v103) = v101;
          v99 = v105 >> 19;
          if ( *(_DWORD *)v106 == *(_DWORD *)v100 )
            break;
          v95 = v181;
        }
        if ( v106 > v186 )
        {
          do
          {
            if ( *(v100 - 1) != *(v106 - 1) )
              break;
            --v100;
            --v106;
          }
          while ( v100 > a2 && v106 > v186 );
        }
        v107 = (unsigned int)((_DWORD)v100 - (_DWORD)a2);
        v108 = v93;
        v109 = v93 + 1;
        if ( &v109[v107 + 8 + (unsigned int)v107 / 0xFF] <= v184 )
        {
          if ( (unsigned int)v107 < 0xF )
          {
            *v108 = 16 * ((_BYTE)v100 - (_BYTE)a2);
          }
          else
          {
            v110 = v107 - 15;
            *v108 = -16;
            while ( v110 >= 255 )
            {
              *v109++ = -1;
              v110 -= 255;
            }
            *v109++ = v110;
          }
          v111 = v109;
          v112 = &v109[v107];
          do
          {
            v113 = *(_QWORD *)a2;
            a2 += 8;
            *(_QWORD *)v111 = v113;
            v111 += 8;
          }
          while ( v111 < v112 );
          v114 = (unsigned __int64)(v92 - 12);
          while ( 1 )
          {
            v115 = v112;
            v116 = v106 + 4;
            v117 = (_WORD)v100 - (_WORD)v106;
            v93 = v112 + 2;
            v118 = v100 + 4;
            *v115 = v117;
            v119 = v100 + 4;
            if ( (unsigned __int64)(v100 + 4) >= v114 )
            {
              while ( (unsigned __int64)v119 < v114 )
              {
                if ( *v116 != *(_QWORD *)v119 )
                {
                  __asm { tzcnt   r8, r8 }
                  v122 = (_DWORD)v119 + ((unsigned int)_R8 >> 3) - (_DWORD)v118;
                  goto LABEL_160;
                }
                v119 += 8;
LABEL_148:
                ++v116;
              }
              if ( v119 < v92 - 8 && *(_DWORD *)v116 == *(_DWORD *)v119 )
              {
                v119 += 4;
                v116 = (_QWORD *)((char *)v116 + 4);
              }
              if ( v119 < v92 - 6 && *(_WORD *)v116 == *(_WORD *)v119 )
              {
                v119 += 2;
                v116 = (_QWORD *)((char *)v116 + 2);
              }
              if ( v119 < v92 - 5 && *(_BYTE *)v116 == *v119 )
                LODWORD(v119) = (_DWORD)v119 + 1;
              v122 = (_DWORD)v119 - (_DWORD)v118;
            }
            else
            {
              if ( *v116 == *v118 )
              {
                v119 = v100 + 12;
                goto LABEL_148;
              }
              __asm { tzcnt   r8, rcx }
              v122 = (unsigned int)_R8 >> 3;
            }
LABEL_160:
            v100 += v122 + 4;
            if ( &v93[(v122 + 240) / 0xFF + 6] > v184 )
              break;
            v125 = *v108;
            if ( v122 < 0xF )
            {
              *v108 = v125 + v122;
            }
            else
            {
              *v108 = v125 + 15;
              for ( i = v122 - 15; ; i -= 1020 )
              {
                *(_DWORD *)v93 = -1;
                if ( i < 0x3FC )
                  break;
                v93 += 4;
              }
              v127 = i / 0xFF;
              v128 = &v93[v127];
              *v128 = i + v127;
              v93 = v128 + 1;
            }
            a2 = v100;
            if ( v100 >= v92 - 11 )
              goto LABEL_171;
            *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)(v100 - 2)) >> 19)) = (_WORD)v100 - (_WORD)v181 - 2;
            v129 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)v100) >> 19;
            v130 = *((unsigned __int16 *)inited + v129);
            *((_WORD *)inited + v129) = (_WORD)v100 - (_WORD)v181;
            v106 = &v181[v130];
            if ( *(_DWORD *)v106 != *(_DWORD *)v100 )
            {
              v95 = v181;
              v94 = v100 + 1;
              goto LABEL_123;
            }
            v108 = v93;
            v112 = v93 + 1;
            *v108 = 0;
          }
        }
        return v8;
      }
LABEL_172:
      v131 = v92 - a2;
      if ( &v93[v131 + 1 + (v131 + 240) / 0xFF] > v184 )
        return v8;
      if ( v131 < 0xF )
      {
        LOBYTE(v132) = 16 * v131;
      }
      else
      {
        *v93 = -16;
        v132 = v131 - 15;
        ++v93;
        while ( v132 >= 0xFF )
        {
          *v93++ = -1;
          v132 -= 255LL;
        }
      }
      v133 = v93;
      *v93 = v132;
      v134 = (_DWORD)v93 + 1;
      memmove((char *)v133 + 1, a2, v131);
      v135 = v131 - (_DWORD)v6;
      return (unsigned int)(v134 + v135);
    }
    if ( (unsigned int)v5 <= 0x7E000000 )
    {
      inited[4102] += v5;
      v136 = inited[4100];
      v137 = &a2[v5];
      v185 = &v6[a5];
      v138 = a2 + 1;
      inited[4101] = 2;
      v53 = v6;
      v54 = a2;
      inited[4100] = v136 + v5;
      v139 = &a2[-v136];
      v182 = &a2[-v136];
      inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)a2) >> 52] = v136;
      v140 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)(a2 + 1)) >> 52;
      v8 = 0;
LABEL_183:
      v141 = 1;
      for ( j = 64; ; ++j )
      {
        v143 = v138;
        v144 = (_DWORD)v138 - (_DWORD)v139;
        v138 += v141;
        if ( v138 > v137 - 11 )
          break;
        v145 = &inited[v140];
        v146 = *(_QWORD *)v138;
        v147 = *v145;
        *v145 = v144;
        v148 = &v139[v147];
        if ( (int)v147 + 0xFFFF >= v144 && *(_DWORD *)v148 == *(_DWORD *)v143 )
        {
          v149 = v148;
          v150 = v143;
          if ( v148 > a2 && *(v143 - 1) == *(v148 - 1) )
          {
            do
            {
              --v150;
              --v149;
            }
            while ( v150 > v54 && v149 > a2 && *(v150 - 1) == *(v149 - 1) );
          }
          v151 = (unsigned int)((_DWORD)v150 - (_DWORD)v54);
          v152 = v53;
          v153 = v53 + 1;
          if ( &v153[v151 + 8 + (unsigned int)v151 / 0xFF] <= v185 )
          {
            if ( (unsigned int)v151 < 0xF )
            {
              *v152 = 16 * ((_BYTE)v150 - (_BYTE)v54);
            }
            else
            {
              v154 = v151 - 15;
              *v152 = -16;
              while ( v154 >= 255 )
              {
                *v153++ = -1;
                v154 -= 255;
              }
              *v153++ = v154;
            }
            v155 = v153;
            v156 = &v153[v151];
            do
            {
              v157 = *(_QWORD *)v54;
              v54 += 8;
              *v155++ = v157;
            }
            while ( v155 < (_QWORD *)v156 );
            v158 = (unsigned __int64)(v137 - 5);
            v159 = (unsigned __int64)(v137 - 12);
            while ( 1 )
            {
              v160 = v156;
              v161 = v150 + 4;
              v162 = v149 + 4;
              v53 = v156 + 2;
              *v160 = (_WORD)v150 - (_WORD)v149;
              v163 = v150 + 4;
              if ( (unsigned __int64)(v150 + 4) >= v159 )
              {
                while ( (unsigned __int64)v163 < v159 )
                {
                  if ( *v162 != *v163 )
                  {
                    __asm { tzcnt   r10, r10 }
                    v166 = (_DWORD)v163 + ((unsigned int)_R10 >> 3) - (_DWORD)v161;
                    goto LABEL_221;
                  }
                  ++v163;
LABEL_209:
                  ++v162;
                }
                if ( (unsigned __int64)v163 < v158 - 3 && *(_DWORD *)v162 == *(_DWORD *)v163 )
                {
                  v163 = (_QWORD *)((char *)v163 + 4);
                  v162 = (_QWORD *)((char *)v162 + 4);
                }
                if ( (unsigned __int64)v163 < v158 - 1 && *(_WORD *)v162 == *(_WORD *)v163 )
                {
                  v163 = (_QWORD *)((char *)v163 + 2);
                  v162 = (_QWORD *)((char *)v162 + 2);
                }
                if ( (unsigned __int64)v163 < v158 && *(_BYTE *)v162 == *(_BYTE *)v163 )
                  LODWORD(v163) = (_DWORD)v163 + 1;
                v166 = (_DWORD)v163 - (_DWORD)v161;
              }
              else
              {
                if ( *v162 == *v161 )
                {
                  v163 = v150 + 12;
                  goto LABEL_209;
                }
                __asm { tzcnt   r10, rcx }
                v166 = (unsigned int)_R10 >> 3;
              }
LABEL_221:
              v169 = v185;
              v150 += v166 + 4;
              if ( &v53[(v166 + 240) / 0xFF + 6] > v185 )
                break;
              v170 = *v152;
              if ( v166 < 0xF )
              {
                *v152 = v170 + v166;
              }
              else
              {
                v171 = v166 - 15;
                *v152 = v170 + 15;
                while ( 1 )
                {
                  *(_DWORD *)v53 = -1;
                  if ( v171 < 0x3FC )
                    break;
                  v53 += 4;
                  v171 -= 1020;
                }
                v172 = v171 / 0xFF;
                v173 = &v53[v172];
                *v173 = v171 + v172;
                v53 = v173 + 1;
              }
              v54 = v150;
              if ( v150 >= v137 - 11 )
                goto LABEL_234;
              v139 = v182;
              inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)(v150 - 2)) >> 52] = (_DWORD)v150 - (_DWORD)v182 - 2;
              v174 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)v150) >> 52;
              v175 = inited[v174];
              inited[v174] = (_DWORD)v150 - (_DWORD)v182;
              v149 = &v182[v175];
              if ( (int)v175 + 0xFFFF < (unsigned int)((_DWORD)v150 - (_DWORD)v182)
                || *(_DWORD *)v149 != *(_DWORD *)v150 )
              {
                v138 = v150 + 1;
                v140 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)v138) >> 52;
                goto LABEL_183;
              }
              v152 = v53;
              v158 = (unsigned __int64)(v137 - 5);
              v156 = v53 + 1;
              *v152 = 0;
            }
          }
          return v8;
        }
        v139 = v182;
        v141 = j >> 6;
        v140 = (0xCF1BBCDCBB000000uLL * v146) >> 52;
      }
      v169 = v185;
LABEL_234:
      v89 = v137 - v54;
      if ( &v53[(v89 + 240) / 0xFF + 1 + v89] > v169 )
        return v8;
      if ( v89 < 0xF )
        goto LABEL_240;
      *v53 = -16;
      v90 = v89 - 15;
      ++v53;
      while ( v90 >= 0xFF )
      {
        *v53++ = -1;
        v90 -= 255LL;
      }
      goto LABEL_241;
    }
    return 0;
  }
  if ( (int)v5 >= 65547 )
  {
    if ( (unsigned int)v5 <= 0x7E000000 )
    {
      inited[4102] += v5;
      v50 = &a2[v5];
      v51 = inited[4100];
      v52 = a2 + 1;
      inited[4101] = 2;
      v53 = v6;
      v54 = a2;
      inited[4100] = v51 + v5;
      v55 = &a2[-v51];
      v180 = &a2[-v51];
      inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)a2) >> 52] = v51;
      v56 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)(a2 + 1)) >> 52;
LABEL_63:
      v57 = 1;
      for ( k = 64; ; ++k )
      {
        v59 = v52;
        v60 = (_DWORD)v52 - (_DWORD)v55;
        v52 += v57;
        if ( v52 > v50 - 11 )
          break;
        v61 = &inited[v56];
        v62 = *(_QWORD *)v52;
        v63 = *v61;
        *v61 = v60;
        v64 = &v55[v63];
        if ( (int)v63 + 0xFFFF >= v60 && *(_DWORD *)v64 == *(_DWORD *)v59 )
        {
          v65 = v64;
          v66 = v59;
          if ( v64 > a2 && *(v59 - 1) == *(v64 - 1) )
          {
            do
            {
              --v66;
              --v65;
            }
            while ( v66 > v54 && v65 > a2 && *(v66 - 1) == *(v65 - 1) );
          }
          v67 = v53;
          v68 = (_DWORD)v66 - (_DWORD)v54;
          v69 = v53 + 1;
          if ( (unsigned int)((_DWORD)v66 - (_DWORD)v54) < 0xF )
          {
            *v67 = 16 * v68;
          }
          else
          {
            v70 = v68 - 15;
            *v67 = -16;
            while ( v70 >= 255 )
            {
              *v69++ = -1;
              v70 -= 255;
            }
            *v69++ = v70;
          }
          v71 = v69;
          v72 = &v69[v68];
          do
          {
            v73 = *(_QWORD *)v54;
            v54 += 8;
            *v71++ = v73;
          }
          while ( v71 < (_QWORD *)v72 );
          v74 = (unsigned __int64)(v50 - 12);
          while ( 1 )
          {
            v75 = v72;
            v76 = v66 + 4;
            v77 = v65 + 4;
            v53 = v72 + 2;
            *v75 = (_WORD)v66 - (_WORD)v65;
            v78 = v66 + 4;
            if ( (unsigned __int64)(v66 + 4) >= v74 )
            {
              while ( (unsigned __int64)v78 < v74 )
              {
                if ( *v77 != *(_QWORD *)v78 )
                {
                  __asm { tzcnt   rax, r10 }
                  v81 = ((unsigned int)_RAX >> 3) - (_DWORD)v76 + (_DWORD)v78;
                  goto LABEL_100;
                }
                v78 += 8;
LABEL_88:
                ++v77;
              }
              if ( v78 < v50 - 8 && *(_DWORD *)v77 == *(_DWORD *)v78 )
              {
                v78 += 4;
                v77 = (_QWORD *)((char *)v77 + 4);
              }
              if ( v78 < v50 - 6 && *(_WORD *)v77 == *(_WORD *)v78 )
              {
                v78 += 2;
                v77 = (_QWORD *)((char *)v77 + 2);
              }
              if ( v78 < v50 - 5 && *(_BYTE *)v77 == *v78 )
                LODWORD(v78) = (_DWORD)v78 + 1;
              v81 = (_DWORD)v78 - (_DWORD)v76;
            }
            else
            {
              if ( *v77 == *v76 )
              {
                v78 = v66 + 12;
                goto LABEL_88;
              }
              __asm { tzcnt   rcx, rcx }
              v81 = (unsigned int)_RCX >> 3;
            }
LABEL_100:
            v66 += v81 + 4;
            v84 = *v67;
            if ( v81 < 0xF )
            {
              *v67 = v84 + v81;
            }
            else
            {
              *v67 = v84 + 15;
              for ( m = v81 - 15; ; m -= 1020 )
              {
                *(_DWORD *)v53 = -1;
                if ( m < 0x3FC )
                  break;
                v53 += 4;
              }
              v86 = &v53[m / 0xFF];
              *v86 = m / 0xFF + m;
              v53 = v86 + 1;
            }
            v54 = v66;
            if ( v66 >= v50 - 11 )
              goto LABEL_111;
            inited[(0xCF1BBCDCBB000000uLL * *(_QWORD *)(v66 - 2)) >> 52] = (_DWORD)v66 - (_DWORD)v180 - 2;
            v87 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)v66) >> 52;
            v88 = inited[v87];
            v65 = &v180[v88];
            inited[v87] = (_DWORD)v66 - (_DWORD)v180;
            v55 = v180;
            if ( (int)v88 + 0xFFFF < (unsigned int)((_DWORD)v66 - (_DWORD)v180) || *(_DWORD *)v65 != *(_DWORD *)v66 )
            {
              v52 = v66 + 1;
              v56 = (0xCF1BBCDCBB000000uLL * *(_QWORD *)v52) >> 52;
              goto LABEL_63;
            }
            v67 = v53;
            v72 = v53 + 1;
            *v67 = 0;
          }
        }
        v55 = v180;
        v57 = k >> 6;
        v56 = (0xCF1BBCDCBB000000uLL * v62) >> 52;
      }
LABEL_111:
      v89 = v50 - v54;
      if ( v89 < 0xF )
      {
LABEL_240:
        LOBYTE(v90) = 16 * v89;
      }
      else
      {
        *v53 = -16;
        v90 = v89 - 15;
        ++v53;
        while ( v90 >= 0xFF )
        {
          *v53++ = -1;
          v90 -= 255LL;
        }
      }
LABEL_241:
      v176 = v53;
      *v53 = v90;
      v134 = (_DWORD)v53 + 1;
      memmove(v176 + 1, v54, v89);
      v135 = v89 - v187;
      return (unsigned int)(v134 + v135);
    }
    return 0;
  }
  v8 = 0;
  if ( (unsigned int)v5 <= 0x7E000000 )
  {
    if ( !(_DWORD)v5 )
    {
LABEL_5:
      *v6 = 0;
      return 1;
    }
    v9 = inited[4100];
    v10 = &a2[v5];
    inited[4102] += v5;
    v11 = v6;
    inited[4101] = 3;
    inited[4100] = v9 + v5;
    if ( (int)v5 >= 13 )
    {
      v12 = a2 + 1;
      v179 = a2;
      v183 = &a2[-v9];
      *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)a2) >> 19)) = v9;
LABEL_8:
      v13 = v12;
      v14 = 1;
      v15 = 64;
      v16 = (unsigned int)(-1640531535 * *(_DWORD *)v12) >> 19;
      while ( 1 )
      {
        v17 = (__int16)v13;
        v18 = v13;
        v13 += v14;
        v19 = v17 - (_WORD)v183;
        if ( v13 > v10 - 11 )
          break;
        v20 = v15;
        v21 = (unsigned int)v16;
        ++v15;
        v14 = v20 >> 6;
        v22 = *((unsigned __int16 *)inited + v16);
        v23 = -1640531535 * *(_DWORD *)v13;
        v24 = &v183[v22];
        *((_WORD *)inited + v21) = v19;
        v16 = v23 >> 19;
        if ( *(_DWORD *)&v183[v22] == *(_DWORD *)v18 )
        {
          if ( v24 > v179 )
          {
            do
            {
              if ( *(v18 - 1) != *(v24 - 1) )
                break;
              --v18;
              --v24;
            }
            while ( v24 > v179 && v18 > a2 );
          }
          v25 = v11;
          v26 = (_DWORD)v18 - (_DWORD)a2;
          v27 = v11 + 1;
          if ( (unsigned int)((_DWORD)v18 - (_DWORD)a2) < 0xF )
          {
            *v25 = 16 * v26;
          }
          else
          {
            v28 = v26 - 15;
            *v25 = -16;
            while ( v28 >= 255 )
            {
              *v27++ = -1;
              v28 -= 255;
            }
            *v27++ = v28;
          }
          v29 = v27;
          v30 = &v27[v26];
          do
          {
            v31 = *(_QWORD *)a2;
            a2 += 8;
            *(_QWORD *)v29 = v31;
            v29 += 8;
          }
          while ( v29 < v30 );
          v32 = (unsigned __int64)(v10 - 12);
          while ( 1 )
          {
            v33 = v30;
            v34 = v18 + 4;
            v11 = v30 + 2;
            v35 = (_WORD)v18 - (_WORD)v24;
            v36 = v24 + 4;
            *v33 = v35;
            v37 = v18 + 4;
            if ( (unsigned __int64)(v18 + 4) >= v32 )
            {
              while ( (unsigned __int64)v37 < v32 )
              {
                if ( *v36 != *(_QWORD *)v37 )
                {
                  __asm { tzcnt   rax, r8 }
                  v40 = ((unsigned int)_RAX >> 3) - (_DWORD)v34 + (_DWORD)v37;
                  goto LABEL_43;
                }
                v37 += 8;
LABEL_31:
                ++v36;
              }
              if ( v37 < v10 - 8 && *(_DWORD *)v36 == *(_DWORD *)v37 )
              {
                v37 += 4;
                v36 = (_QWORD *)((char *)v36 + 4);
              }
              if ( v37 < v10 - 6 && *(_WORD *)v36 == *(_WORD *)v37 )
              {
                v37 += 2;
                v36 = (_QWORD *)((char *)v36 + 2);
              }
              if ( v37 < v10 - 5 && *(_BYTE *)v36 == *v37 )
                LODWORD(v37) = (_DWORD)v37 + 1;
              v40 = (_DWORD)v37 - (_DWORD)v34;
            }
            else
            {
              if ( *v34 == *v36 )
              {
                v37 = v18 + 12;
                goto LABEL_31;
              }
              __asm { tzcnt   rcx, rcx }
              v40 = (unsigned int)_RCX >> 3;
            }
LABEL_43:
            v18 += v40 + 4;
            v43 = *v25;
            if ( v40 < 0xF )
            {
              *v25 = v43 + v40;
            }
            else
            {
              *v25 = v43 + 15;
              for ( n = v40 - 15; ; n -= 1020 )
              {
                *(_DWORD *)v11 = -1;
                if ( n < 0x3FC )
                  break;
                v11 += 4;
              }
              v45 = &v11[n / 0xFF];
              *v45 = n / 0xFF + n;
              v11 = v45 + 1;
            }
            a2 = v18;
            if ( v18 >= v10 - 11 )
              goto LABEL_53;
            *((_WORD *)inited + ((unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)(v18 - 2)) >> 19)) = (_WORD)v18 - (_WORD)v183 - 2;
            v46 = (unsigned __int64)(unsigned int)(-1640531535 * *(_DWORD *)v18) >> 19;
            v47 = *((unsigned __int16 *)inited + v46);
            *((_WORD *)inited + v46) = (_WORD)v18 - (_WORD)v183;
            v24 = &v183[v47];
            if ( *(_DWORD *)v24 != *(_DWORD *)v18 )
            {
              v12 = v18 + 1;
              goto LABEL_8;
            }
            v25 = v11;
            v30 = v11 + 1;
            *v25 = 0;
          }
        }
      }
LABEL_53:
      LODWORD(v6) = v187;
    }
    v48 = v10 - a2;
    if ( v48 < 0xF )
    {
      LOBYTE(v49) = 16 * v48;
    }
    else
    {
      *v11 = -16;
      v49 = v48 - 15;
      ++v11;
      while ( v49 >= 0xFF )
      {
        *v11++ = -1;
        v49 -= 255LL;
      }
    }
    *v11 = v49;
    memmove(v11 + 1, a2, v48);
    return (unsigned int)((_DWORD)v11 + 1 + v48 - (_DWORD)v6);
  }
  return v8;
}

```

## disassembly

```asm
0x1400e3d28  mov     [rsp+arg_10], r8
0x1400e3d2d  push    rbx
0x1400e3d2e  push    rbp
0x1400e3d2f  push    rsi
0x1400e3d30  push    rdi
0x1400e3d31  push    r12
0x1400e3d33  push    r13
0x1400e3d35  push    r14
0x1400e3d37  push    r15
0x1400e3d39  sub     rsp, 58h
0x1400e3d3d  movsxd  rsi, r9d
0x1400e3d40  mov     r13, r8
0x1400e3d43  mov     r14, rdx
0x1400e3d46  call    LZ4_initStream
0x1400e3d4b  mov     ecx, esi
0x1400e3d4d  mov     [rsp+98h+var_78], rax
0x1400e3d52  mov     r12, rax
0x1400e3d55  call    LZ4_compressBound
0x1400e3d5a  movsxd  rdx, [rsp+98h+arg_20]
0x1400e3d62  cmp     edx, eax
0x1400e3d64  jl      loc_1400E43DD
0x1400e3d6a  cmp     esi, 1000Bh
0x1400e3d70  jge     loc_1400E40A4
0x1400e3d76  xor     ebx, ebx
0x1400e3d78  cmp     esi, 7E000000h
0x1400e3d7e  ja      loc_1400E4B7F
0x1400e3d84  test    esi, esi
0x1400e3d86  jnz     short loc_1400E3D96
0x1400e3d88  mov     [r13+0], bl
0x1400e3d8c  mov     ebx, 1
0x1400e3d91  jmp     loc_1400E4B7F
0x1400e3d96  mov     edx, [r12+4010h]
0x1400e3d9e  lea     r15, [r14+rsi]
0x1400e3da2  add     [r12+4018h], esi
0x1400e3daa  mov     rdi, r13
0x1400e3dad  mov     dword ptr [r12+4014h], 3
0x1400e3db9  mov     r9d, 1
0x1400e3dbf  mov     r11d, 0FFh
0x1400e3dc5  lea     eax, [rdx+rsi]
0x1400e3dc8  mov     [r12+4010h], eax
0x1400e3dd0  cmp     esi, 0Dh
0x1400e3dd3  jl      loc_1400E4057
0x1400e3dd9  imul    ecx, [r14], 9E3779B1h
0x1400e3de0  lea     r10, [r14+1]
0x1400e3de4  mov     rax, [rsp+98h+var_78]
0x1400e3de9  mov     r12, r14
0x1400e3dec  sub     r12, rdx
0x1400e3def  mov     [rsp+98h+var_70], r14
0x1400e3df4  mov     [rsp+98h+var_68], r12
0x1400e3df9  shr     rcx, 13h
0x1400e3dfd  mov     [rax+rcx*2], dx
0x1400e3e01  imul    r8d, [r10], 9E3779B1h
0x1400e3e08  mov     rsi, r10
0x1400e3e0b  mov     ebp, r9d
0x1400e3e0e  mov     r13d, 40h ; '@'
0x1400e3e14  shr     r8d, 13h
0x1400e3e18  mov     rdx, [rsp+98h+var_68]
0x1400e3e1d  mov     r12d, esi
0x1400e3e20  movsxd  rax, ebp
0x1400e3e23  mov     r10, rsi
0x1400e3e26  add     rsi, rax
0x1400e3e29  sub     r12d, edx
0x1400e3e2c  lea     rax, [r15-0Bh]
0x1400e3e30  cmp     rsi, rax
0x1400e3e33  ja      loc_1400E404F
0x1400e3e39  mov     rax, [rsp+98h+var_78]
0x1400e3e3e  mov     ebp, r13d
0x1400e3e41  mov     ecx, r8d
0x1400e3e44  add     r13d, r9d
0x1400e3e47  sar     ebp, 6
0x1400e3e4a  movzx   eax, word ptr [rax+r8*2]
0x1400e3e4f  imul    r8d, [rsi], 9E3779B1h
0x1400e3e56  add     rdx, rax
0x1400e3e59  mov     rax, [rsp+98h+var_78]
0x1400e3e5e  mov     [rax+rcx*2], r12w
0x1400e3e63  mov     eax, [r10]
0x1400e3e66  shr     r8d, 13h
0x1400e3e6a  cmp     [rdx], eax
0x1400e3e6c  jnz     short loc_1400E3E18
0x1400e3e6e  mov     r8, [rsp+98h+var_70]
0x1400e3e73  cmp     rdx, r8
0x1400e3e76  jbe     short loc_1400E3E9D
0x1400e3e78  jmp     short loc_1400E3E94
0x1400e3e7a  sub     r10, r9
0x1400e3e7d  sub     rdx, r9
0x1400e3e80  cmp     rdx, r8
0x1400e3e83  mov     ecx, ebx
0x1400e3e85  mov     eax, ebx
0x1400e3e87  setnbe  cl
0x1400e3e8a  cmp     r10, r14
0x1400e3e8d  setnbe  al
0x1400e3e90  test    eax, ecx
0x1400e3e92  jz      short loc_1400E3E9D
0x1400e3e94  mov     al, [rdx-1]
0x1400e3e97  cmp     [r10-1], al
0x1400e3e9b  jz      short loc_1400E3E7A
0x1400e3e9d  mov     ecx, r10d
0x1400e3ea0  mov     rsi, rdi
0x1400e3ea3  sub     ecx, r14d
0x1400e3ea6  add     rdi, r9
0x1400e3ea9  cmp     ecx, 0Fh
0x1400e3eac  jb      short loc_1400E3ECB
0x1400e3eae  lea     eax, [rcx-0Fh]
0x1400e3eb1  mov     byte ptr [rsi], 0F0h
0x1400e3eb4  jmp     short loc_1400E3EBF
0x1400e3eb6  mov     [rdi], r11b
0x1400e3eb9  add     rdi, r9
0x1400e3ebc  sub     eax, r11d
0x1400e3ebf  cmp     eax, r11d
0x1400e3ec2  jge     short loc_1400E3EB6
0x1400e3ec4  mov     [rdi], al
0x1400e3ec6  add     rdi, r9
0x1400e3ec9  jmp     short loc_1400E3ED2
0x1400e3ecb  mov     al, cl
0x1400e3ecd  shl     al, 4
0x1400e3ed0  mov     [rsi], al
0x1400e3ed2  mov     eax, ecx
0x1400e3ed4  mov     r8, rdi
0x1400e3ed7  add     rdi, rax
0x1400e3eda  mov     rax, [r14]
0x1400e3edd  lea     r14, [r14+8]
0x1400e3ee1  mov     [r8], rax
0x1400e3ee4  add     r8, 8
0x1400e3ee8  cmp     r8, rdi
0x1400e3eeb  jb      short loc_1400E3EDA
0x1400e3eed  mov     r12, [rsp+98h+var_68]
0x1400e3ef2  lea     rbp, [r15-0Ch]
0x1400e3ef6  mov     r13d, 2
0x1400e3efc  mov     rcx, rdi
0x1400e3eff  lea     r14, [r10+4]
0x1400e3f03  movzx   eax, r10w
0x1400e3f07  add     rdi, r13
0x1400e3f0a  sub     ax, dx
0x1400e3f0d  add     rdx, 4
0x1400e3f11  mov     [rcx], ax
0x1400e3f14  mov     rcx, r14
0x1400e3f17  cmp     r14, rbp
0x1400e3f1a  jnb     short loc_1400E3F34
0x1400e3f1c  mov     rcx, [rdx]
0x1400e3f1f  xor     rcx, [r14]
0x1400e3f22  jnz     short loc_1400E3F2A
0x1400e3f24  lea     rcx, [r10+0Ch]
0x1400e3f28  jmp     short loc_1400E3F45
0x1400e3f2a  tzcnt   rcx, rcx
0x1400e3f2f  shr     ecx, 3
0x1400e3f32  jmp     short loc_1400E3F9D
0x1400e3f34  cmp     rcx, rbp
0x1400e3f37  jnb     short loc_1400E3F5A
0x1400e3f39  mov     r8, [rcx]
0x1400e3f3c  xor     r8, [rdx]
0x1400e3f3f  jnz     short loc_1400E3F4B
0x1400e3f41  add     rcx, 8
0x1400e3f45  add     rdx, 8
0x1400e3f49  jmp     short loc_1400E3F34
0x1400e3f4b  tzcnt   rax, r8
0x1400e3f50  shr     eax, 3
0x1400e3f53  sub     eax, r14d
0x1400e3f56  add     ecx, eax
0x1400e3f58  jmp     short loc_1400E3F9D
0x1400e3f5a  lea     r8, [r15-5]
0x1400e3f5e  lea     rax, [r8-3]
0x1400e3f62  cmp     rcx, rax
0x1400e3f65  jnb     short loc_1400E3F75
0x1400e3f67  mov     eax, [rcx]
0x1400e3f69  cmp     [rdx], eax
0x1400e3f6b  jnz     short loc_1400E3F75
0x1400e3f6d  add     rcx, 4
0x1400e3f71  add     rdx, 4
0x1400e3f75  lea     rax, [r8-1]
0x1400e3f79  cmp     rcx, rax
0x1400e3f7c  jnb     short loc_1400E3F8C
0x1400e3f7e  movzx   eax, word ptr [rcx]
0x1400e3f81  cmp     [rdx], ax
0x1400e3f84  jnz     short loc_1400E3F8C
0x1400e3f86  add     rcx, r13
0x1400e3f89  add     rdx, r13
0x1400e3f8c  cmp     rcx, r8
0x1400e3f8f  jnb     short loc_1400E3F9A
0x1400e3f91  mov     al, [rcx]
0x1400e3f93  cmp     [rdx], al
0x1400e3f95  jnz     short loc_1400E3F9A
0x1400e3f97  add     rcx, r9
0x1400e3f9a  sub     ecx, r14d
0x1400e3f9d  mov     eax, ecx
0x1400e3f9f  add     r10, 4
0x1400e3fa3  add     r10, rax
0x1400e3fa6  mov     al, [rsi]
0x1400e3fa8  cmp     ecx, 0Fh
0x1400e3fab  jb      short loc_1400E3FE7
0x1400e3fad  add     al, 0Fh
0x1400e3faf  mov     [rsi], al
0x1400e3fb1  add     ecx, 0FFFFFFF1h
0x1400e3fb4  mov     eax, 3FCh
0x1400e3fb9  jmp     short loc_1400E3FC5
0x1400e3fbb  add     rdi, 4
0x1400e3fbf  add     ecx, 0FFFFFC04h
0x1400e3fc5  mov     dword ptr [rdi], 0FFFFFFFFh
0x1400e3fcb  cmp     ecx, eax
0x1400e3fcd  jnb     short loc_1400E3FBB
0x1400e3fcf  mov     eax, 80808081h
0x1400e3fd4  mul     ecx
0x1400e3fd6  shr     edx, 7
0x1400e3fd9  add     cl, dl
0x1400e3fdb  mov     eax, edx
0x1400e3fdd  add     rdi, rax
0x1400e3fe0  mov     [rdi], cl
0x1400e3fe2  add     rdi, r9
0x1400e3fe5  jmp     short loc_1400E3FEB
0x1400e3fe7  add     cl, al
0x1400e3fe9  mov     [rsi], cl
0x1400e3feb  lea     rax, [r15-0Bh]
0x1400e3fef  mov     r14, r10
0x1400e3ff2  cmp     r10, rax
0x1400e3ff5  jnb     short loc_1400E404F
0x1400e3ff7  imul    ecx, [r10-2], 9E3779B1h
0x1400e3fff  movzx   r8d, r10w
0x1400e4003  mov     rsi, [rsp+98h+var_78]
0x1400e4008  sub     r8w, r12w
0x1400e400c  movzx   edx, r8w
0x1400e4010  sub     dx, r13w
0x1400e4014  shr     rcx, 13h
0x1400e4018  mov     [rsi+rcx*2], dx
0x1400e401c  imul    ecx, [r10], 9E3779B1h
0x1400e4023  shr     rcx, 13h
0x1400e4027  movzx   edx, word ptr [rsi+rcx*2]
0x1400e402b  mov     [rsi+rcx*2], r8w
0x1400e4030  add     rdx, r12
0x1400e4033  mov     eax, [r10]
0x1400e4036  cmp     [rdx], eax
0x1400e4038  jnz     short loc_1400E4047
0x1400e403a  mov     rsi, rdi
0x1400e403d  add     rdi, r9
0x1400e4040  mov     [rsi], bl
0x1400e4042  jmp     loc_1400E3EFC
0x1400e4047  add     r10, r9
0x1400e404a  jmp     loc_1400E3E01
0x1400e404f  mov     r13, [rsp+98h+arg_10]
0x1400e4057  sub     r15, r14
0x1400e405a  mov     rbx, r15
0x1400e405d  cmp     r15, 0Fh
0x1400e4061  jb      short loc_1400E407F
0x1400e4063  mov     byte ptr [rdi], 0F0h
0x1400e4066  lea     rax, [r15-0Fh]
0x1400e406a  add     rdi, r9
0x1400e406d  jmp     short loc_1400E4078
0x1400e406f  mov     [rdi], r11b
0x1400e4072  add     rdi, r9
0x1400e4075  sub     rax, r11
0x1400e4078  cmp     rax, r11
0x1400e407b  jnb     short loc_1400E406F
0x1400e407d  jmp     short loc_1400E4084
0x1400e407f  mov     al, bl
0x1400e4081  shl     al, 4
0x1400e4084  mov     rcx, rdi
0x1400e4087  mov     [rdi], al
0x1400e4089  add     rdi, r9
0x1400e408c  mov     r8, rbx; Size
0x1400e408f  inc     rcx; void *
0x1400e4092  mov     rdx, r14; Src
0x1400e4095  call    memmove
0x1400e409a  sub     ebx, r13d
0x1400e409d  add     ebx, edi
0x1400e409f  jmp     loc_1400E4B7F
0x1400e40a4  cmp     esi, 7E000000h
0x1400e40aa  ja      loc_1400E47A5
0x1400e40b0  add     [r12+4018h], esi
0x1400e40b8  lea     rbp, [r14+rsi]
0x1400e40bc  mov     ecx, [r12+4010h]
0x1400e40c4  lea     r8, [r14+1]
0x1400e40c8  mov     dword ptr [r12+4014h], 2
0x1400e40d4  mov     r9, 0CF1BBCDCBB000000h
0x1400e40de  mov     rdi, r13
0x1400e40e1  mov     r15, r14
0x1400e40e4  mov     r11d, 0FFh
0x1400e40ea  lea     eax, [rcx+rsi]
0x1400e40ed  mov     rsi, r14
0x1400e40f0  mov     [r12+4010h], eax
0x1400e40f8  sub     rsi, rcx
0x1400e40fb  mov     rax, [r14]
0x1400e40fe  imul    rax, r9
0x1400e4102  mov     [rsp+98h+var_70], rsi
0x1400e4107  shr     rax, 34h
0x1400e410b  mov     [r12+rax*4], ecx
0x1400e410f  mov     rdx, [r8]
0x1400e4112  imul    rdx, r9
0x1400e4116  shr     rdx, 34h
0x1400e411a  xor     ebx, ebx
0x1400e411c  lea     r9d, [rbx+1]
0x1400e4120  mov     eax, r9d
0x1400e4123  mov     r13d, 40h ; '@'
0x1400e4129  cdqe
0x1400e412b  mov     r10d, r8d
0x1400e412e  mov     r12, r8
0x1400e4131  sub     r10d, esi
0x1400e4134  add     r8, rax
0x1400e4137  lea     rax, [rbp-0Bh]
0x1400e413b  cmp     r8, rax
0x1400e413e  ja      loc_1400E43B1
0x1400e4144  mov     rax, [rsp+98h+var_78]
0x1400e4149  lea     rax, [rax+rdx*4]
  ... truncated ...
```
