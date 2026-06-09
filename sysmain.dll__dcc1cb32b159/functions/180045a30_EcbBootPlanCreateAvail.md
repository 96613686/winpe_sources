# EcbBootPlanCreateAvail

- ea: `0x180045a30`
- end: `0x18004641c`
- name: `EcbBootPlanCreateAvail`
- size: `2540`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c230`

## callees

- `0x180021e0c`
- `0x180045a30`
- `0x180046424`
- `0x1800b645a`
- `0x1800b6472`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!_wfopen` at `0x18004622c`
- `msvcrt!_wfopen` at `0x18004622c`
- `msvcrt!qsort` at `0x180046011`
- `msvcrt!qsort` at `0x1800460b1`
- `msvcrt!qsort` at `0x180046011`
- `msvcrt!qsort` at `0x1800460b1`
- `msvcrt!fclose` at `0x180046411`
- `msvcrt!fclose` at `0x180046411`
- `msvcrt!fprintf` at `0x180046358`
- `msvcrt!fprintf` at `0x1800463c1`
- `msvcrt!fprintf` at `0x1800463e4`
- `msvcrt!fprintf` at `0x180046403`
- `msvcrt!fprintf` at `0x180046358`
- `msvcrt!fprintf` at `0x1800463c1`
- `msvcrt!fprintf` at `0x1800463e4`
- `msvcrt!fprintf` at `0x180046403`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045d0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045d0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f4a`

## pseudocode

```c
__int64 EcbBootPlanCreateAvail()
{
  FILE *v0; // r14
  _DWORD *v1; // rdx
  char *v2; // rsi
  int v3; // r8d
  unsigned int v4; // ebx
  unsigned int v5; // r12d
  __int64 v6; // r13
  __int64 v7; // r9
  int v8; // edi
  int v9; // r10d
  int v10; // r12d
  int v11; // ebx
  int v12; // r11d
  int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rax
  char *v16; // r9
  unsigned int v17; // r11d
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r8
  int v21; // r9d
  unsigned int v22; // r10d
  unsigned int v23; // ecx
  unsigned int v24; // r15d
  int v25; // ecx
  __int64 v26; // r11
  __int64 v27; // rdi
  __int64 v28; // rdi
  double v29; // xmm1_8
  double v30; // xmm1_8
  __int64 v31; // rbx
  double v32; // xmm6_8
  int v33; // edi
  double v34; // xmm0_8
  int v35; // ebx
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  _QWORD *v39; // rax
  double v40; // xmm0_8
  __int64 v41; // rax
  double i; // xmm0_8
  double v43; // xmm6_8
  unsigned int v44; // r15d
  unsigned int v45; // r11d
  __int64 *v46; // r8
  __int64 v47; // r15
  int v48; // r9d
  __int64 v49; // rcx
  unsigned int k; // edx
  unsigned int v51; // eax
  unsigned int v52; // r10d
  int v53; // edi
  __int64 v54; // rdi
  SIZE_T v55; // r15
  void *v56; // rax
  void *v57; // rbx
  SIZE_T v58; // rdi
  void *v59; // rax
  void *v60; // rbx
  int v61; // edx
  int v62; // ebx
  __int64 **v63; // r8
  int v64; // r11d
  unsigned int v65; // r10d
  __int64 **v66; // r9
  int v67; // r12d
  unsigned int v68; // edi
  __int64 v69; // rcx
  void *v70; // rcx
  unsigned int v71; // edi
  unsigned int v72; // ebx
  int m; // r12d
  unsigned int v74; // r13d
  int v75; // eax
  int v76; // r15d
  __int64 v77; // r8
  int v78; // edx
  int v79; // r9d
  __int64 v80; // rcx
  unsigned int v81; // r15d
  unsigned int v82; // ebx
  __int64 v84; // rcx
  unsigned int v85; // ebx
  __int64 v86; // rcx
  unsigned int v87; // ecx
  __int64 *v88; // rdx
  unsigned int v89; // eax
  unsigned int v90; // ecx
  unsigned int v91; // r10d
  int v92; // r8d
  int v93; // eax
  int v94; // r15d
  int j; // r11d
  unsigned int v96; // ecx
  unsigned int v97; // edx
  int v98; // r11d
  unsigned int v99; // r12d
  int v100; // eax
  int v101; // [rsp+38h] [rbp-D0h]
  unsigned int v102; // [rsp+3Ch] [rbp-CCh]
  unsigned int v103; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v104; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v105; // [rsp+50h] [rbp-B8h]
  int v106; // [rsp+54h] [rbp-B4h]
  __int128 v107; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v108; // [rsp+68h] [rbp-A0h]
  __int64 v109; // [rsp+70h] [rbp-98h]
  char *v110; // [rsp+78h] [rbp-90h]
  _DWORD Base[6]; // [rsp+80h] [rbp-88h] BYREF
  wchar_t pszDest[264]; // [rsp+98h] [rbp-70h] BYREF

  v0 = 0;
  v1 = EcbGlobals;
  v107 = 0;
  v104 = 0;
  v2 = (char *)EcbGlobals + 8792;
  if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x2000000) != 0 )
  {
    if ( StringCchPrintfW(pszDest, 0x104u, L"%ws\\ecboot.avail", (char *)EcbGlobals + 48) < 0 )
      return 1101;
    v0 = _wfopen(pszDest, L"w");
    if ( !v0 )
      return 1101;
    v1 = EcbGlobals;
  }
  v3 = 0;
  v4 = 0;
  v101 = 0;
  v5 = 0;
  v103 = 0;
  v6 = 64;
  while ( v5 < 6 )
  {
    if ( v5 )
    {
      v86 = v5 - 1;
      v14 = 58160 * v86 + 68272;
      v15 = 58160 * v86 + 68264;
    }
    else
    {
      v14 = 10112;
      v15 = 10104;
    }
    v16 = (char *)v1 + v14;
    v110 = v16;
    if ( *(_DWORD *)((char *)v1 + v15) )
    {
      v17 = 0;
      v102 = 0;
      v18 = 0;
      v108 = 0;
      while ( 1 )
      {
        v106 = v18;
        if ( (unsigned int)v18 >= *((_DWORD *)v16 + 14343) )
        {
          v101 = ++v3;
          break;
        }
        v19 = *((_QWORD *)v16 + 7175);
        if ( v19 )
          v20 = *(_QWORD *)(v19 + 8 * v18);
        else
          v20 = *(_QWORD *)&v16[8 * ((unsigned __int64)(unsigned int)v18 >> 10)]
              + 8 * ((v18 & 0x3FF) + 4 * (v18 & 0x3FF) + 1);
        v21 = *(_DWORD *)(v20 + 32) & 0x700;
        if ( ((v21 - 256) & 0xFFFFFCFF) != 0 )
          goto LABEL_46;
        if ( v21 == 512 )
          goto LABEL_46;
        v22 = *(_DWORD *)(v20 + 28);
        v23 = *(_DWORD *)(v20 + 20);
        if ( v23 < v22 )
          goto LABEL_46;
        if ( v23 - v22 < v17 )
          v24 = v23 - v17;
        else
          v24 = *(_DWORD *)(v20 + 28);
        if ( v17 > v23 )
        {
          v45 = v4 - v23 + v17;
          if ( v45 < v4 )
            goto LABEL_45;
          v4 = v45;
          v24 = *(_DWORD *)(v20 + 28);
          v17 = v102;
          v103 = v4;
        }
        v105 = v23 + v4;
        if ( v23 + v4 < v23 )
          goto LABEL_46;
        v102 = v23;
        v17 = v23;
        if ( v21 != 1024 || v24 > 0x989680 )
          goto LABEL_46;
        v25 = v1[2193];
        v26 = *(_QWORD *)v20;
        v27 = *(__int64 *)v20 >> v25;
        v109 = v27;
        if ( v27 > *((_QWORD *)v2 + 1) || v27 < 0 )
          goto LABEL_45;
        v28 = v27 - v108;
        v29 = (double)(int)v109 * 0.64 / (double)(int)*((_QWORD *)v2 + 1);
        v108 = (v26
              - 1
              + *(unsigned int *)(v20 + 16)
              + (unsigned int)v1[2192]
              - ((unsigned int)(v1[2192] - 1) & (v26 + (unsigned int)v1[2192] + *(unsigned int *)(v20 + 16) - 1LL))) >> v25;
        v30 = *((double *)v2 + 2) / sqrt_0(1.0 - v29);
        v31 = 0;
        if ( v28 != -1 )
          v31 = v28;
        v32 = (double)((int)v108 - (int)v109) * v30;
        if ( v31 < 0 )
        {
          v31 = -v31;
        }
        else if ( v31 < *((int *)v2 + 40) )
        {
          v33 = -1;
          v34 = (double)(int)v31 * v30 + v32;
          if ( v34 > 4294967295.0 )
            v35 = -1;
          else
            v35 = (int)(v34 + 0.5);
          goto LABEL_36;
        }
        v40 = sqrt_0((double)(int)v31);
        v33 = 0;
        v41 = 64;
        for ( i = v40 * *((double *)v2 + 4) + *((double *)v2 + 3); v41 <= v31; v41 *= 2 )
          ++v33;
        v43 = v32 + i;
        if ( v43 > 4294967295.0 )
          v35 = -1;
        else
          v35 = (int)(v43 + 0.5);
        v44 = v24 - v35;
        if ( v44 + 9999999 <= 0x1312CFE )
        {
          ++*(_DWORD *)&v2[4 * v33 + 372];
          *(_DWORD *)&v2[4 * v33 + 180] += v44;
        }
LABEL_36:
        v36 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x20u);
        v37 = v36;
        if ( !v36 )
        {
          v1 = EcbGlobals;
          v4 = v103;
LABEL_45:
          v17 = v102;
LABEL_46:
          v3 = v101;
          goto LABEL_41;
        }
        v3 = v101;
        *(_OWORD *)v36 = 0;
        *((_OWORD *)v36 + 1) = 0;
        if ( (unsigned int)v101 > 5 )
        {
          v82 = 1551;
          goto LABEL_100;
        }
        v17 = v102;
        *((_DWORD *)v36 + 4) = v35;
        v4 = v103;
        *((_DWORD *)v36 + 5) = v105;
        *((_DWORD *)v36 + 6) = v33;
        v38 = *(_QWORD *)&v2[8 * v101 + 112];
        if ( v38 )
        {
          v39 = *(_QWORD **)(v38 + 8);
          *(_QWORD *)(v38 + 8) = v37;
          *v39 = v37;
          *v37 = v38;
          v37[1] = v39;
        }
        else
        {
          *v36 = v36;
          v36[1] = v36;
          *(_QWORD *)&v2[8 * v101 + 112] = v36;
        }
        v1 = EcbGlobals;
LABEL_41:
        v16 = v110;
        v18 = (unsigned int)(v106 + 1);
      }
    }
    ++v5;
  }
  v7 = 0;
  v8 = 48;
  do
  {
    v9 = *(_DWORD *)&v2[4 * v7 + 372];
    if ( v9 )
    {
      v92 = *(_DWORD *)&v2[4 * v7 + 180];
      v93 = v92 + v9 / 2;
      if ( v92 < 0 )
        v93 = *(_DWORD *)&v2[4 * v7 + 180] - v9 / 2;
      *(_DWORD *)&v2[4 * v7 + 180] = v93 / v9;
    }
    ++v7;
  }
  while ( v7 != 48 );
  while ( v8 > 0 )
  {
    if ( *(_DWORD *)&v2[4 * v8 + 368] )
    {
      v94 = 0;
      if ( v0 )
      {
        do
        {
          v99 = 0;
          v100 = *(_DWORD *)&v2[4 * v94 + 372];
          v105 = v100;
          if ( v100 )
            v99 = *(_DWORD *)&v2[4 * v94 + 180];
          fprintf(v0, "ALSC, %2d, %20I64d, %20d, %10d\n", 0, v6 << 12, v99, v100);
          *(_QWORD *)&v107 = v6 << 12;
          *((_QWORD *)&v107 + 1) = __PAIR64__(v105, v99);
          EcbBootPlanProcessAvail(&v107, 0);
          v6 *= 2;
          ++v94;
        }
        while ( v94 < v8 );
      }
      else
      {
        for ( j = 0; j < v8; j = v98 + 1 )
        {
          v96 = 0;
          v97 = *(_DWORD *)&v2[4 * j + 372];
          if ( v97 )
            v96 = *(_DWORD *)&v2[4 * j + 180];
          *((_QWORD *)&v107 + 1) = __PAIR64__(v97, v96);
          *(_QWORD *)&v107 = v6 << 12;
          EcbBootPlanProcessAvail(&v107, 0);
          v6 *= 2;
        }
      }
      break;
    }
    --v8;
  }
  v10 = v101;
  v11 = 0;
  v12 = 0;
  if ( v101 <= 0 )
    goto LABEL_9;
  do
  {
    v46 = *(__int64 **)&v2[8 * v12 + 112];
    if ( v46 )
    {
      v47 = v46[1];
      v48 = 0;
      v49 = v47;
      for ( k = *(_DWORD *)(v47 + 20); ; k -= v51 )
      {
        if ( *(int *)(v49 + 24) >= 0 )
        {
          v52 = *(_DWORD *)(v49 + 16);
          v53 = *(_DWORD *)&v2[4 * *(int *)(v49 + 24) + 180];
          if ( v53 >= 0 || v52 > -v53 )
            *(_DWORD *)(v49 + 16) = v52 + v53;
          else
            *(_DWORD *)(v49 + 16) = 0;
        }
        if ( k > *(_DWORD *)(v49 + 20) )
        {
          k = *(_DWORD *)(v49 + 20);
          ++v48;
        }
        else
        {
          *(_DWORD *)(v49 + 20) = k;
        }
        v51 = *(_DWORD *)(v49 + 16);
        if ( k < v51 )
          break;
        v49 = *(_QWORD *)(v49 + 8);
        if ( v49 == v47 )
          goto LABEL_70;
      }
      v87 = *((_DWORD *)v46 + 5);
      v88 = v46;
      v89 = *((_DWORD *)v46 + 4);
      if ( v89 > v87 )
      {
        *((_DWORD *)v46 + 5) = v89;
        v87 = v89;
      }
      v90 = v87 - v89;
      v48 = 0;
      do
      {
        v91 = v90 + *((_DWORD *)v88 + 4);
        if ( v91 < v90 )
        {
          v91 = -1;
          *((_DWORD *)v88 + 4) = ~v90;
        }
        v90 = *((_DWORD *)v88 + 5);
        if ( v90 > v91 )
        {
          ++v48;
        }
        else
        {
          *((_DWORD *)v88 + 5) = v91;
          v90 = v91;
        }
        v88 = (__int64 *)*v88;
      }
      while ( v88 != v46 );
LABEL_70:
      v11 += v48 + 1;
    }
    ++v12;
  }
  while ( v12 < v101 );
  if ( !v11 )
  {
LABEL_9:
    v13 = -1;
    if ( v0 )
      fprintf(v0, "A, %2d, %10d, %10d\n", 0, -1, -1);
    HIDWORD(v104) = -1;
LABEL_99:
    LODWORD(v104) = v13;
    EcbBootPlanProcessAvail(0, &v104);
    v82 = 0;
    goto LABEL_100;
  }
  v54 = v11;
  v55 = 4LL * v11;
  v56 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v55);
  v57 = v56;
  if ( v56 )
  {
    memset_0(v56, 0, v55);
    *((_QWORD *)v2 + 12) = v57;
    v58 = 8 * v54;
    v59 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v58);
    v60 = v59;
    if ( v59 )
    {
      memset_0(v59, 0, v58);
      v61 = 0;
      *((_QWORD *)v2 + 13) = v60;
      v62 = 0;
      do
      {
        v63 = *(__int64 ***)&v2[8 * v62 + 112];
        if ( v63 )
        {
          *(_DWORD *)&v2[4 * v62 + 568] = v61;
          v64 = *((_DWORD *)v63 + 4);
          v65 = *((_DWORD *)v63 + 5) - v64;
          v66 = (__int64 **)*v63;
          if ( *v63 != (__int64 *)v63 )
          {
            do
            {
              v67 = v64 + *((_DWORD *)v66 + 4);
              v68 = *((_DWORD *)v66 + 5) - v67;
              if ( v68 > v65 )
              {
                v84 = v61++;
                *(_DWORD *)(*((_QWORD *)v2 + 12) + 4 * v84) = v64;
                *(_DWORD *)(*((_QWORD *)v2 + 13) + 8 * v84) = v64;
                *(_DWORD *)(*((_QWORD *)v2 + 13) + 8 * v84 + 4) = v65;
              }
              v66 = (__int64 **)*v66;
              v64 = v67;
              v65 = v68;
            }
            while ( v66 != v63 );
            v10 = v101;
          }
          v69 = v61++;
          *(_DWORD *)(*((_QWORD *)v2 + 12) + 4 * v69) = v64;
          *(_DWORD *)(*((_QWORD *)v2 + 13) + 8 * v69) = -1;
          *(_DWORD *)(*((_QWORD *)v2 + 13) + 8 * v69 + 4) = v65;
          *(_DWORD *)&v2[4 * v62 + 592] = v61;
        }
        ++v62;
      }
      while ( v62 < v10 );
      v70 = (void *)*((_QWORD *)v2 + 12);
      *((_DWORD *)v2 + 141) = v61;
      qsort(v70, v61, 4u, EcbBootPlanByIncreasingUlong);
      v71 = 0;
      v72 = 0;
      for ( m = 0; m < *((_DWORD *)v2 + 141); ++m )
      {
        v74 = *(_DWORD *)(*((_QWORD *)v2 + 12) + 4LL * m);
        if ( v74 != v71 )
        {
          v75 = v101;
          v76 = 0;
          v77 = 0;
          do
          {
            v78 = *(_DWORD *)&v2[4 * v77 + 568];
            v79 = *(_DWORD *)&v2[4 * v77 + 592];
            if ( v78 != v79 )
            {
              for ( ; v78 < v79; *(_DWORD *)&v2[4 * v77 + 568] = ++v78 )
              {
                if ( v74 <= *(_DWORD *)(*((_QWORD *)v2 + 13) + 8LL * v78) )
                  break;
              }
              v80 = v76++;
              Base[v80] = *(_DWORD *)(*((_QWORD *)v2 + 13) + 8LL * v78 + 4);
              v75 = v101;
            }
            v77 = (unsigned int)(v77 + 1);
          }
          while ( (int)v77 < v75 );
          qsort(Base, v76, 4u, EcbBootPlanByIncreasingUlong);
          v81 = Base[3 * v76 / 4];
          if ( v81 > v72 && v71 )
          {
            v85 = v71 + v72;
            if ( v0 )
              fprintf(v0, "A, %2d, %10d, %10d\n", 0, v71, v85);
            v104 = __PAIR64__(v85, v71);
            EcbBootPlanProcessAvail(0, &v104);
          }
          v71 = v74;
          v72 = v81;
        }
      }
      v13 = ~v72;
      if ( v0 )
        fprintf(v0, "A, %2d, %10d, %10d\n", 0, v13, -1);
      HIDWORD(v104) = -1;
      goto LABEL_99;
    }
  }
  v82 = 8;
LABEL_100:
  if ( v0 )
    fclose(v0);
  return v82;
}

```

## disassembly

```asm
0x180045a30  mov     rax, rsp
0x180045a33  push    rbp
0x180045a34  push    rbx
0x180045a35  push    rsi
0x180045a36  push    rdi
0x180045a37  push    r12
0x180045a39  push    r13
0x180045a3b  push    r14
0x180045a3d  push    r15
0x180045a3f  lea     rbp, [rax-208h]
0x180045a46  sub     rsp, 2C8h
0x180045a4d  movaps  xmmword ptr [rax-58h], xmm6
0x180045a51  mov     rax, cs:__security_cookie
0x180045a58  xor     rax, rsp
0x180045a5b  mov     [rbp+200h+var_60], rax
0x180045a62  mov     rax, cs:PfSvcGlobals
0x180045a69  xor     r14d, r14d
0x180045a6c  mov     rdx, cs:EcbGlobals
0x180045a73  xorps   xmm0, xmm0
0x180045a76  movups  [rsp+300h+var_2B8+8], xmm0
0x180045a7b  mov     qword ptr [rsp+300h+var_2C0], 0
0x180045a84  test    dword ptr [rax+0F4h], 2000000h
0x180045a8e  lea     rsi, [rdx+2258h]
0x180045a95  jnz     loc_180046204
0x180045a9b  xor     r8d, r8d
0x180045a9e  xor     ebx, ebx
0x180045aa0  mov     [rsp+300h+var_2D0], r8d
0x180045aa5  xor     r12d, r12d
0x180045aa8  mov     dword ptr [rsp+300h+var_2C8], ebx
0x180045aac  lea     r13d, [r8+40h]
0x180045ab0  cmp     r12d, 6
0x180045ab4  jb      short loc_180045B06
0x180045ab6  xor     r9d, r9d
0x180045ab9  lea     edi, [r9+30h]
0x180045abd  mov     r10d, [rsi+r9*4+174h]
0x180045ac5  test    r10d, r10d
0x180045ac8  jnz     loc_180046283
0x180045ace  inc     r9
0x180045ad1  cmp     r9, rdi
0x180045ad4  jnz     short loc_180045ABD
0x180045ad6  test    edi, edi
0x180045ad8  jg      loc_1800462B5
0x180045ade  mov     r12d, [rsp+300h+var_2D0]
0x180045ae3  xor     ebx, ebx
0x180045ae5  xor     r11d, r11d
0x180045ae8  test    r12d, r12d
0x180045aeb  jg      loc_180045E68
0x180045af1  or      ebx, 0FFFFFFFFh
0x180045af4  test    r14, r14
0x180045af7  jnz     loc_1800463EF
0x180045afd  mov     [rsp+300h+var_2BC], ebx
0x180045b01  jmp     loc_1800460FD
0x180045b06  cmp     r12d, 1
0x180045b0a  jnb     loc_180046194
0x180045b10  mov     eax, r12d
0x180045b13  imul    rcx, rax, 0E330h
0x180045b1a  lea     r9, [rcx+2780h]
0x180045b21  lea     rax, [rcx+2778h]
0x180045b28  add     r9, rdx
0x180045b2b  add     rax, rdx
0x180045b2e  mov     [rsp+300h+var_290], r9
0x180045b33  cmp     dword ptr [rax], 0
0x180045b36  jz      loc_180046271
0x180045b3c  xor     r11d, r11d
0x180045b3f  mov     [rsp+34h], r11d
0x180045b44  xor     eax, eax
0x180045b46  mov     [rsp+300h+var_2A0], r11
0x180045b4b  mov     dword ptr [rsp+300h+var_2B8+4], eax
0x180045b4f  cmp     eax, [r9+0E01Ch]
0x180045b56  jnb     loc_180046269
0x180045b5c  mov     r8, [r9+0E038h]
0x180045b63  mov     ecx, eax
0x180045b65  test    r8, r8
0x180045b68  jz      loc_180045D8E
0x180045b6e  mov     r8, [r8+rax*8]
0x180045b72  mov     r9d, [r8+20h]
0x180045b76  and     r9d, 700h
0x180045b7d  lea     eax, [r9-100h]
0x180045b84  test    eax, 0FFFFFCFFh
0x180045b89  jnz     loc_180045DC3
0x180045b8f  cmp     r9d, 200h
0x180045b96  jz      loc_180045DC3
0x180045b9c  mov     r10d, [r8+1Ch]
0x180045ba0  mov     ecx, [r8+14h]
0x180045ba4  cmp     ecx, r10d
0x180045ba7  jb      loc_180045DC3
0x180045bad  mov     eax, ecx
0x180045baf  sub     eax, r10d
0x180045bb2  cmp     eax, r11d
0x180045bb5  jb      loc_180045D83
0x180045bbb  mov     r15d, r10d
0x180045bbe  cmp     r11d, ecx
0x180045bc1  ja      loc_180045E3F
0x180045bc7  lea     eax, [rcx+rbx]
0x180045bca  mov     dword ptr [rsp+300h+var_2B8], eax
0x180045bce  cmp     eax, ecx
0x180045bd0  jb      loc_180045DC3
0x180045bd6  mov     [rsp+34h], ecx
0x180045bda  mov     r11d, ecx
0x180045bdd  cmp     r9d, 400h
0x180045be4  jnz     loc_180045DC3
0x180045bea  cmp     r15d, 989680h
0x180045bf1  ja      loc_180045DC3
0x180045bf7  mov     r11d, [r8+4]
0x180045bfb  mov     eax, [r8]
0x180045bfe  mov     ecx, [rdx+2244h]
0x180045c04  shl     r11, 20h
0x180045c08  or      r11, rax
0x180045c0b  mov     rdi, r11
0x180045c0e  sar     rdi, cl
0x180045c11  mov     [rsp+300h+var_298], rdi
0x180045c16  cmp     rdi, [rsi+8]
0x180045c1a  jg      loc_180045DBE
0x180045c20  test    rdi, rdi
0x180045c23  js      loc_180045DBE
0x180045c29  mov     r9d, [r8+10h]
0x180045c2d  xorps   xmm1, xmm1
0x180045c30  cvtsi2sd xmm1, [rsp+300h+var_298]
0x180045c37  mov     r10d, [rdx+2240h]
0x180045c3e  sub     rdi, [rsp+300h+var_2A0]
0x180045c43  lea     r8, [r9-1]
0x180045c47  xorps   xmm0, xmm0
0x180045c4a  add     r8, r10
0x180045c4d  cvtsi2sd xmm0, qword ptr [rsi+8]
0x180045c53  lea     edx, [r10-1]
0x180045c57  add     r8, r11
0x180045c5a  and     r8, rdx
0x180045c5d  dec     r11
0x180045c60  sub     r10, r8
0x180045c63  mulsd   xmm1, cs:__real@3fe47ae147ae147b
0x180045c6b  lea     rbx, [r9+r10]
0x180045c6f  add     rbx, r11
0x180045c72  divsd   xmm1, xmm0
0x180045c76  sar     rbx, cl
0x180045c79  mov     [rsp+300h+var_2A0], rbx
0x180045c7e  movsd   xmm0, cs:__real@3ff0000000000000
0x180045c86  subsd   xmm0, xmm1; X
0x180045c8a  call    sqrt_0
0x180045c8f  sub     rbx, [rsp+300h+var_298]
0x180045c94  xorps   xmm6, xmm6
0x180045c97  movsd   xmm1, qword ptr [rsi+10h]
0x180045c9c  divsd   xmm1, xmm0
0x180045ca0  cvtsi2sd xmm6, rbx
0x180045ca5  xor     ebx, ebx
0x180045ca7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180045cab  cmovnz  rbx, rdi
0x180045caf  mulsd   xmm6, xmm1
0x180045cb3  test    rbx, rbx
0x180045cb6  js      loc_180045DCA
0x180045cbc  movsxd  rax, dword ptr [rsi+0A0h]
0x180045cc3  cmp     rbx, rax
0x180045cc6  jge     loc_180045DCD
0x180045ccc  xorps   xmm0, xmm0
0x180045ccf  or      edi, 0FFFFFFFFh
0x180045cd2  cvtsi2sd xmm0, rbx
0x180045cd7  mulsd   xmm0, xmm1
0x180045cdb  addsd   xmm0, xmm6
0x180045cdf  comisd  xmm0, cs:__real@41efffffffe00000
0x180045ce7  ja      loc_180046250
0x180045ced  addsd   xmm0, cs:__real@3fe0000000000000
0x180045cf5  cvttsd2si rbx, xmm0
0x180045cfa  mov     rcx, cs:PfSvcGlobals
0x180045d01  xor     edx, edx; dwFlags
0x180045d03  mov     rcx, [rcx+58h]; hHeap
0x180045d07  lea     r8d, [rdx+20h]; dwBytes
0x180045d0b  call    cs:__imp_HeapAlloc
0x180045d11  mov     rcx, rax
0x180045d14  test    rax, rax
0x180045d17  jz      loc_180045DB3
0x180045d1d  movsxd  r8, [rsp+300h+var_2D0]
0x180045d22  xorps   xmm0, xmm0
0x180045d25  movups  xmmword ptr [rax], xmm0
0x180045d28  movups  xmmword ptr [rax+10h], xmm0
0x180045d2c  cmp     r8d, 5
0x180045d30  ja      loc_180046279
0x180045d36  mov     r11d, [rsp+34h]
0x180045d3b  mov     [rax+10h], ebx
0x180045d3e  mov     eax, dword ptr [rsp+300h+var_2B8]
0x180045d42  mov     ebx, dword ptr [rsp+300h+var_2C8]
0x180045d46  mov     [rcx+14h], eax
0x180045d49  mov     [rcx+18h], edi
0x180045d4c  mov     rdx, [rsi+r8*8+70h]
0x180045d51  test    rdx, rdx
0x180045d54  jz      loc_180046258
0x180045d5a  mov     rax, [rdx+8]
0x180045d5e  mov     [rdx+8], rcx
0x180045d62  mov     [rax], rcx
0x180045d65  mov     [rcx], rdx
0x180045d68  mov     [rcx+8], rax
0x180045d6c  mov     rdx, cs:EcbGlobals
0x180045d73  mov     eax, dword ptr [rsp+300h+var_2B8+4]
0x180045d77  mov     r9, [rsp+300h+var_290]
0x180045d7c  inc     eax
0x180045d7e  jmp     loc_180045B4B
0x180045d83  mov     r15d, ecx
0x180045d86  sub     r15d, r11d
0x180045d89  jmp     loc_180045BBE
0x180045d8e  mov     rax, rcx
0x180045d91  and     ecx, 3FFh
0x180045d97  shr     rax, 0Ah
0x180045d9b  lea     r8, ds:1[rcx*4]
0x180045da3  mov     rax, [r9+rax*8]
0x180045da7  add     r8, rcx
0x180045daa  lea     r8, [rax+r8*8]
0x180045dae  jmp     loc_180045B72
0x180045db3  mov     rdx, cs:EcbGlobals
0x180045dba  mov     ebx, dword ptr [rsp+300h+var_2C8]
0x180045dbe  mov     r11d, [rsp+34h]
0x180045dc3  mov     r8d, [rsp+300h+var_2D0]
0x180045dc8  jmp     short loc_180045D73
0x180045dca  neg     rbx
0x180045dcd  xorps   xmm0, xmm0
0x180045dd0  cvtsi2sd xmm0, rbx; X
0x180045dd5  call    sqrt_0
0x180045dda  mulsd   xmm0, qword ptr [rsi+20h]
0x180045ddf  xor     edi, edi
0x180045de1  mov     rax, r13
0x180045de4  addsd   xmm0, qword ptr [rsi+18h]
0x180045de9  cmp     rbx, r13
0x180045dec  jl      short loc_180045DF8
0x180045dee  inc     edi
0x180045df0  add     rax, rax
0x180045df3  cmp     rax, rbx
0x180045df6  jle     short loc_180045DEE
0x180045df8  addsd   xmm6, xmm0
0x180045dfc  comisd  xmm6, cs:__real@41efffffffe00000
0x180045e04  ja      short loc_180045E63
0x180045e06  addsd   xmm6, cs:__real@3fe0000000000000
0x180045e0e  cvttsd2si rbx, xmm6
0x180045e13  sub     r15d, ebx
0x180045e16  lea     eax, [r15+98967Fh]
0x180045e1d  cmp     eax, 1312CFEh
0x180045e22  ja      loc_180045CFA
0x180045e28  movsxd  rax, edi
0x180045e2b  inc     dword ptr [rsi+rax*4+174h]
0x180045e32  add     [rsi+rax*4+0B4h], r15d
0x180045e3a  jmp     loc_180045CFA
0x180045e3f  mov     eax, ebx
0x180045e41  sub     eax, ecx
0x180045e43  add     r11d, eax
0x180045e46  cmp     r11d, ebx
0x180045e49  jb      loc_180045DBE
0x180045e4f  mov     ebx, r11d
0x180045e52  mov     r15d, r10d
0x180045e55  mov     r11d, [rsp+34h]
0x180045e5a  mov     dword ptr [rsp+300h+var_2C8], ebx
0x180045e5e  jmp     loc_180045BC7
0x180045e63  or      ebx, 0FFFFFFFFh
0x180045e66  jmp     short loc_180045E13
0x180045e68  movsxd  rax, r11d
0x180045e6b  mov     r8, [rsi+rax*8+70h]
0x180045e70  test    r8, r8
0x180045e73  jz      short loc_180045EE4
0x180045e75  mov     r15, [r8+8]
0x180045e79  xor     r9d, r9d
0x180045e7c  mov     rcx, r15
0x180045e7f  mov     edx, [r15+14h]
0x180045e83  cmp     dword ptr [rcx+18h], 0
0x180045e87  jge     short loc_180045EB1
0x180045e89  cmp     edx, [rcx+14h]
0x180045e8c  ja      short loc_180045EA9
0x180045e8e  mov     [rcx+14h], edx
0x180045e91  mov     eax, [rcx+10h]
0x180045e94  cmp     edx, eax
0x180045e96  jb      loc_1800461BC
0x180045e9c  mov     rcx, [rcx+8]
0x180045ea0  cmp     rcx, r15
0x180045ea3  jz      short loc_180045EDF
0x180045ea5  sub     edx, eax
0x180045ea7  jmp     short loc_180045E83
0x180045ea9  mov     edx, [rcx+14h]
0x180045eac  inc     r9d
0x180045eaf  jmp     short loc_180045E91
0x180045eb1  movsxd  rax, dword ptr [rcx+18h]
0x180045eb5  mov     r10d, [rcx+10h]
0x180045eb9  mov     edi, [rsi+rax*4+0B4h]
0x180045ec0  test    edi, edi
0x180045ec2  js      short loc_180045ECD
0x180045ec4  lea     eax, [r10+rdi]
0x180045ec8  mov     [rcx+10h], eax
0x180045ecb  jmp     short loc_180045E89
0x180045ecd  mov     eax, edi
0x180045ecf  neg     eax
0x180045ed1  cmp     r10d, eax
0x180045ed4  ja      short loc_180045EC4
0x180045ed6  mov     dword ptr [rcx+10h], 0
0x180045edd  jmp     short loc_180045E89
0x180045edf  inc     ebx
0x180045ee1  add     ebx, r9d
0x180045ee4  inc     r11d
0x180045ee7  cmp     r11d, r12d
0x180045eea  jl      loc_180045E68
0x180045ef0  test    ebx, ebx
0x180045ef2  jz      loc_180045AF1
0x180045ef8  mov     rcx, cs:PfSvcGlobals
0x180045eff  xor     edx, edx; dwFlags
0x180045f01  movsxd  rdi, ebx
0x180045f04  mov     rcx, [rcx+58h]; hHeap
0x180045f08  lea     r15, ds:0[rdi*4]
0x180045f10  mov     r8, r15; dwBytes
  ... truncated ...
```
