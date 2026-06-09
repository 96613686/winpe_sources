# m7_ipps_BitRev2_C

- ea: `0x180025f90`
- end: `0x180026308`
- name: `m7_ipps_BitRev2_C`
- size: `888`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180019b10`
- `0x180019cb0`
- `0x180019eb0`
- `0x18001a900`
- `0x1800387d8`
- `0x1800388c4`

## callees

- `0x180025f90`

## pseudocode

```c
void __fastcall m7_ipps_BitRev2_C(__m128 *a1, double *a2, __int64 a3, __int64 a4)
{
  __m128 *v4; // r12
  double *v5; // r13
  __int64 v6; // rbx
  __int64 v7; // r10
  double *v8; // r8
  __int64 v9; // rax
  __m128 v10; // xmm2
  __m128 v11; // xmm3
  __m128 v12; // xmm4
  __m128 v13; // xmm5
  __m128 v14; // xmm0
  __m128 v15; // xmm4
  __m128 v16; // xmm7
  __m128 v17; // xmm1
  __m128 v18; // xmm5
  __m128 v19; // xmm6
  __m128 v20; // xmm7
  __m128 v21; // xmm0
  __m128 v22; // xmm1
  __m128 v23; // xmm2
  __m128 v24; // xmm3
  __m128 v25; // xmm4
  __m128 v26; // xmm5
  __m128 v27; // xmm6
  __m128 v28; // xmm7
  __int64 v29; // rbx
  __int64 v30; // r10
  __int64 v31; // rax
  __int64 v32; // r12
  __m128 *v33; // r13
  __m128 v34; // xmm2
  __m128 v35; // xmm3
  __m128 v36; // xmm4
  __m128 v37; // xmm5
  __m128 v38; // xmm0
  __m128 v39; // xmm4
  __m128 v40; // xmm7
  __m128 v41; // xmm1
  __m128 v42; // xmm5
  __m128 v43; // xmm6
  __m128 v44; // xmm7
  double *v45; // r13
  __m128 v46; // xmm0
  __m128 v47; // xmm1
  __m128 v48; // xmm2
  __m128 v49; // xmm3
  __m128 v50; // xmm4
  __m128 v51; // xmm5
  __m128 v52; // xmm6
  __m128 v53; // xmm7
  __m128 v54; // xmm0
  __m128 v55; // xmm1
  __m128 v56; // xmm2
  __m128 v57; // xmm3

  v4 = a1;
  v5 = a2;
  if ( a3 == 8 )
  {
    v54 = *a1;
    v55 = a1[1];
    v56 = a1[2];
    v57 = a1[3];
    _mm_storel_ps(a2, *a1);
    _mm_storel_ps(a2 + 1, v56);
    _mm_storel_ps(a2 + 2, v55);
    _mm_storel_ps(a2 + 3, v57);
    _mm_storeh_ps(a2 + 4, v54);
    _mm_storeh_ps(a2 + 5, v56);
    _mm_storeh_ps(a2 + 6, v55);
    _mm_storeh_ps(a2 + 7, v57);
  }
  else if ( a3 <= 0x10000 )
  {
    v29 = a4 + 4 * ((unsigned __int64)a3 >> 4);
    v30 = 2 * a3;
    v31 = 6 * a3;
    v32 = (__int64)&a1[-2] + 2 * a3;
    if ( (v32 & 0xF) != 0 || ((unsigned __int8)a2 & 0xF) != 0 )
    {
      do
      {
        v45 = (double *)((char *)a2 + 4 * *(int *)(v29 - 4));
        v29 -= 4;
        v46 = *(__m128 *)v32;
        v47 = *(__m128 *)(v32 + 16);
        v48 = *(__m128 *)(v30 + v32);
        v49 = *(__m128 *)(v30 + v32 + 16);
        v50 = *(__m128 *)(v32 + 4 * a3);
        v51 = *(__m128 *)(v32 + 4 * a3 + 16);
        v52 = *(__m128 *)(v31 + v32);
        v53 = *(__m128 *)(v31 + v32 + 16);
        _mm_storel_ps(v45, *(__m128 *)v32);
        _mm_storel_ps(v45 + 1, v50);
        _mm_storel_ps(v45 + 2, v48);
        _mm_storel_ps(v45 + 3, v52);
        _mm_storel_ps((double *)((char *)v45 + v30), v47);
        _mm_storel_ps((double *)((char *)v45 + v30 + 8), v51);
        _mm_storel_ps((double *)((char *)v45 + v30 + 16), v49);
        _mm_storel_ps((double *)((char *)v45 + v30 + 24), v53);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3), v46);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3 + 8), v50);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3 + 16), v48);
        _mm_storeh_ps((double *)((char *)v45 + 4 * a3 + 24), v52);
        _mm_storeh_ps((double *)((char *)v45 + v31), v47);
        _mm_storeh_ps((double *)((char *)v45 + v31 + 8), v51);
        _mm_storeh_ps((double *)((char *)v45 + v31 + 16), v49);
        _mm_storeh_ps((double *)((char *)v45 + v31 + 24), v53);
        v32 -= 32;
      }
      while ( v32 >= (__int64)a1 );
    }
    else
    {
      do
      {
        v33 = (__m128 *)((char *)a2 + 4 * *(int *)(v29 - 4));
        v29 -= 4;
        v34 = *(__m128 *)(v30 + v32);
        v35 = *(__m128 *)(v30 + v32 + 16);
        v36 = *(__m128 *)(v32 + 4 * a3);
        v37 = *(__m128 *)(v32 + 4 * a3 + 16);
        v38 = _mm_movelh_ps(*(__m128 *)v32, v36);
        v39 = _mm_movehl_ps(v36, *(__m128 *)v32);
        v40 = *(__m128 *)(v32 + 16);
        v41 = _mm_movelh_ps(v40, v37);
        v42 = _mm_movehl_ps(v37, v40);
        v43 = *(__m128 *)(v31 + v32);
        v44 = *(__m128 *)(v31 + v32 + 16);
        *v33 = v38;
        v33[1] = _mm_movelh_ps(v34, v43);
        *(__m128 *)((char *)v33 + v30) = v41;
        *(__m128 *)((char *)v33 + v30 + 16) = _mm_movelh_ps(v35, v44);
        *(__m128 *)((char *)v33 + 4 * a3) = v39;
        *(__m128 *)((char *)v33 + 4 * a3 + 16) = _mm_movehl_ps(v43, v34);
        *(__m128 *)((char *)v33 + v31) = v42;
        *(__m128 *)((char *)v33 + v31 + 16) = _mm_movehl_ps(v44, v35);
        v32 -= 32;
      }
      while ( v32 >= (__int64)a1 );
    }
  }
  else
  {
    v6 = a4;
    v7 = 2 * a3;
    v8 = (double *)((char *)a2 + 2 * a3);
    v9 = 3 * v7;
    if ( ((unsigned __int8)a1 & 0xF) != 0 || ((unsigned __int8)a2 & 0xF) != 0 )
    {
      do
      {
        v21 = *v4;
        v22 = v4[1];
        v23 = *(__m128 *)((char *)v4 + v7);
        v24 = *(__m128 *)((char *)v4 + v7 + 16);
        v25 = *(__m128 *)((char *)v4 + 2 * v7);
        v26 = *(__m128 *)((char *)v4 + 2 * v7 + 16);
        v27 = *(__m128 *)((char *)v4 + v9);
        v28 = *(__m128 *)((char *)v4 + v9 + 16);
        v4 = (__m128 *)((char *)a1 + 4 * *(int *)(v6 + 4));
        v6 += 4;
        _mm_storel_ps(v5, v21);
        _mm_storel_ps(v5 + 1, v25);
        _mm_storel_ps(v5 + 2, v23);
        _mm_storel_ps(v5 + 3, v27);
        _mm_storel_ps((double *)((char *)v5 + v7), v22);
        _mm_storel_ps((double *)((char *)v5 + v7 + 8), v26);
        _mm_storel_ps((double *)((char *)v5 + v7 + 16), v24);
        _mm_storel_ps((double *)((char *)v5 + v7 + 24), v28);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7), v21);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7 + 8), v25);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7 + 16), v23);
        _mm_storeh_ps((double *)((char *)v5 + 2 * v7 + 24), v27);
        _mm_storeh_ps((double *)((char *)v5 + v9), v22);
        _mm_storeh_ps((double *)((char *)v5 + v9 + 8), v26);
        _mm_storeh_ps((double *)((char *)v5 + v9 + 16), v24);
        _mm_storeh_ps((double *)((char *)v5 + v9 + 24), v28);
        v5 += 4;
      }
      while ( v5 != v8 );
    }
    else
    {
      do
      {
        v10 = *(__m128 *)((char *)v4 + v7);
        v11 = *(__m128 *)((char *)v4 + v7 + 16);
        v12 = *(__m128 *)((char *)v4 + 2 * v7);
        v13 = *(__m128 *)((char *)v4 + 2 * v7 + 16);
        v14 = _mm_movelh_ps(*v4, v12);
        v15 = _mm_movehl_ps(v12, *v4);
        v16 = v4[1];
        v17 = _mm_movelh_ps(v16, v13);
        v18 = _mm_movehl_ps(v13, v16);
        v19 = *(__m128 *)((char *)v4 + v9);
        v20 = *(__m128 *)((char *)v4 + v9 + 16);
        v4 = (__m128 *)((char *)a1 + 4 * *(int *)(v6 + 4));
        v6 += 4;
        *(__m128 *)v5 = v14;
        *((__m128 *)v5 + 1) = _mm_movelh_ps(v10, v19);
        *(__m128 *)((char *)v5 + v7) = v17;
        *(__m128 *)((char *)v5 + v7 + 16) = _mm_movelh_ps(v11, v20);
        *(__m128 *)((char *)v5 + 2 * v7) = v15;
        *(__m128 *)((char *)v5 + 2 * v7 + 16) = _mm_movehl_ps(v19, v10);
        *(__m128 *)((char *)v5 + v9) = v18;
        *(__m128 *)((char *)v5 + v9 + 16) = _mm_movehl_ps(v20, v11);
        v5 += 4;
      }
      while ( v5 != v8 );
    }
  }
}

```

## disassembly

```asm
0x180025f90  push    rbx
0x180025f91  push    rsi
0x180025f92  push    rdi
0x180025f93  push    rbp
0x180025f94  push    r12
0x180025f96  push    r13
0x180025f98  sub     rsp, 28h
0x180025f9c  movdqa  [rsp+58h+var_58], xmm7
0x180025fa1  movdqa  [rsp+58h+var_48], xmm6
0x180025fa7  mov     rdi, rcx
0x180025faa  mov     rsi, rdx
0x180025fad  mov     rdx, r8
0x180025fb0  mov     rcx, r9
0x180025fb3  mov     r12, rdi
0x180025fb6  mov     r13, rsi
0x180025fb9  mov     r10, rdx
0x180025fbc  cmp     r10, 8
0x180025fc0  jz      loc_1800262B1
0x180025fc6  cmp     r10, 10000h
0x180025fcd  jle     loc_18002613F
0x180025fd3  mov     rbx, rcx
0x180025fd6  mov     r11, r12
0x180025fd9  shl     r10, 1
0x180025fdc  lea     rax, [r10+r13]
0x180025fe0  mov     r8, rax
0x180025fe3  lea     rax, [r10+r10*2]
0x180025fe7  test    r12, 0Fh
0x180025fee  jnz     loc_18002609B
0x180025ff4  test    r13, 0Fh
0x180025ffb  jnz     loc_18002609B
0x180026001  movaps  xmm0, xmmword ptr [r12]
0x180026006  movaps  xmm1, xmmword ptr [r12+10h]
0x18002600c  movaps  xmm2, xmmword ptr [r10+r12]
0x180026011  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x180026017  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18002601c  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x180026022  movaps  xmm7, xmm0
0x180026025  movlhps xmm0, xmm4
0x180026028  movhlps xmm4, xmm7
0x18002602b  movaps  xmm7, xmm1
0x18002602e  movlhps xmm1, xmm5
0x180026031  movhlps xmm5, xmm7
0x180026034  movaps  xmm6, xmmword ptr [rax+r12]
0x180026039  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x18002603f  movsxd  r12, dword ptr [rbx+4]
0x180026043  lea     r12, [r11+r12*4]
0x180026047  add     rbx, 4
0x18002604b  movaps  xmmword ptr [r13+0], xmm0
0x180026050  movaps  xmm0, xmm2
0x180026053  movlhps xmm2, xmm6
0x180026056  movhlps xmm6, xmm0
0x180026059  movaps  xmm0, xmm3
0x18002605c  movlhps xmm3, xmm7
0x18002605f  movhlps xmm7, xmm0
0x180026062  movaps  xmmword ptr [r13+10h], xmm2
0x180026067  movaps  xmmword ptr [r10+r13], xmm1
0x18002606c  movaps  xmmword ptr [r10+r13+10h], xmm3
0x180026072  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x180026078  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x18002607e  movaps  xmmword ptr [rax+r13], xmm5
0x180026083  movaps  xmmword ptr [rax+r13+10h], xmm7
0x180026089  add     r13, 20h ; ' '
0x18002608d  cmp     r13, r8
0x180026090  jnz     loc_180026001
0x180026096  jmp     loc_1800262F0
0x18002609b  movups  xmm0, xmmword ptr [r12]
0x1800260a0  movups  xmm1, xmmword ptr [r12+10h]
0x1800260a6  movups  xmm2, xmmword ptr [r10+r12]
0x1800260ab  movups  xmm3, xmmword ptr [r10+r12+10h]
0x1800260b1  movups  xmm4, xmmword ptr [r12+r10*2]
0x1800260b6  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x1800260bc  movups  xmm6, xmmword ptr [rax+r12]
0x1800260c1  movups  xmm7, xmmword ptr [rax+r12+10h]
0x1800260c7  movsxd  r12, dword ptr [rbx+4]
0x1800260cb  lea     r12, [r11+r12*4]
0x1800260cf  add     rbx, 4
0x1800260d3  movlps  qword ptr [r13+0], xmm0
0x1800260d8  movlps  qword ptr [r13+8], xmm4
0x1800260dd  movlps  qword ptr [r13+10h], xmm2
0x1800260e2  movlps  qword ptr [r13+18h], xmm6
0x1800260e7  movlps  qword ptr [r10+r13], xmm1
0x1800260ec  movlps  qword ptr [r10+r13+8], xmm5
0x1800260f2  movlps  qword ptr [r10+r13+10h], xmm3
0x1800260f8  movlps  qword ptr [r10+r13+18h], xmm7
0x1800260fe  movhps  qword ptr [r13+r10*2+0], xmm0
0x180026104  movhps  qword ptr [r13+r10*2+8], xmm4
0x18002610a  movhps  qword ptr [r13+r10*2+10h], xmm2
0x180026110  movhps  qword ptr [r13+r10*2+18h], xmm6
0x180026116  movhps  qword ptr [rax+r13], xmm1
0x18002611b  movhps  qword ptr [rax+r13+8], xmm5
0x180026121  movhps  qword ptr [rax+r13+10h], xmm3
0x180026127  movhps  qword ptr [rax+r13+18h], xmm7
0x18002612d  add     r13, 20h ; ' '
0x180026131  cmp     r13, r8
0x180026134  jnz     loc_18002609B
0x18002613a  jmp     loc_1800262F0
0x18002613f  mov     rbx, rcx
0x180026142  mov     rax, r10
0x180026145  shr     rax, 4
0x180026149  lea     rbx, [rbx+rax*4]
0x18002614d  shl     r10, 1
0x180026150  lea     rax, [r10+r10*2]
0x180026154  mov     r11, r13
0x180026157  lea     r12, [r10+r12-20h]
0x18002615c  test    r12, 0Fh
0x180026163  jnz     loc_180026210
0x180026169  test    r13, 0Fh
0x180026170  jnz     loc_180026210
0x180026176  movsxd  r13, dword ptr [rbx-4]
0x18002617a  lea     r13, [r11+r13*4]
0x18002617e  sub     rbx, 4
0x180026182  movaps  xmm0, xmmword ptr [r12]
0x180026187  movaps  xmm1, xmmword ptr [r12+10h]
0x18002618d  movaps  xmm2, xmmword ptr [r10+r12]
0x180026192  movaps  xmm3, xmmword ptr [r10+r12+10h]
0x180026198  movaps  xmm4, xmmword ptr [r12+r10*2]
0x18002619d  movaps  xmm5, xmmword ptr [r12+r10*2+10h]
0x1800261a3  movaps  xmm7, xmm0
0x1800261a6  movlhps xmm0, xmm4
0x1800261a9  movhlps xmm4, xmm7
0x1800261ac  movaps  xmm7, xmm1
0x1800261af  movlhps xmm1, xmm5
0x1800261b2  movhlps xmm5, xmm7
0x1800261b5  movaps  xmm6, xmmword ptr [rax+r12]
0x1800261ba  movaps  xmm7, xmmword ptr [rax+r12+10h]
0x1800261c0  movaps  xmmword ptr [r13+0], xmm0
0x1800261c5  movaps  xmm0, xmm2
0x1800261c8  movlhps xmm2, xmm6
0x1800261cb  movhlps xmm6, xmm0
0x1800261ce  movaps  xmm0, xmm3
0x1800261d1  movlhps xmm3, xmm7
0x1800261d4  movhlps xmm7, xmm0
0x1800261d7  movaps  xmmword ptr [r13+10h], xmm2
0x1800261dc  movaps  xmmword ptr [r10+r13], xmm1
0x1800261e1  movaps  xmmword ptr [r10+r13+10h], xmm3
0x1800261e7  movaps  xmmword ptr [r13+r10*2+0], xmm4
0x1800261ed  movaps  xmmword ptr [r13+r10*2+10h], xmm6
0x1800261f3  movaps  xmmword ptr [rax+r13], xmm5
0x1800261f8  movaps  xmmword ptr [rax+r13+10h], xmm7
0x1800261fe  sub     r12, 20h ; ' '
0x180026202  cmp     r12, rdi
0x180026205  jge     loc_180026176
0x18002620b  jmp     loc_1800262F0
0x180026210  movsxd  r13, dword ptr [rbx-4]
0x180026214  lea     r13, [r11+r13*4]
0x180026218  sub     rbx, 4
0x18002621c  movups  xmm0, xmmword ptr [r12]
0x180026221  movups  xmm1, xmmword ptr [r12+10h]
0x180026227  movups  xmm2, xmmword ptr [r10+r12]
0x18002622c  movups  xmm3, xmmword ptr [r10+r12+10h]
0x180026232  movups  xmm4, xmmword ptr [r12+r10*2]
0x180026237  movups  xmm5, xmmword ptr [r12+r10*2+10h]
0x18002623d  movups  xmm6, xmmword ptr [rax+r12]
0x180026242  movups  xmm7, xmmword ptr [rax+r12+10h]
0x180026248  movlps  qword ptr [r13+0], xmm0
0x18002624d  movlps  qword ptr [r13+8], xmm4
0x180026252  movlps  qword ptr [r13+10h], xmm2
0x180026257  movlps  qword ptr [r13+18h], xmm6
0x18002625c  movlps  qword ptr [r10+r13], xmm1
0x180026261  movlps  qword ptr [r10+r13+8], xmm5
0x180026267  movlps  qword ptr [r10+r13+10h], xmm3
0x18002626d  movlps  qword ptr [r10+r13+18h], xmm7
0x180026273  movhps  qword ptr [r13+r10*2+0], xmm0
0x180026279  movhps  qword ptr [r13+r10*2+8], xmm4
0x18002627f  movhps  qword ptr [r13+r10*2+10h], xmm2
0x180026285  movhps  qword ptr [r13+r10*2+18h], xmm6
0x18002628b  movhps  qword ptr [rax+r13], xmm1
0x180026290  movhps  qword ptr [rax+r13+8], xmm5
0x180026296  movhps  qword ptr [rax+r13+10h], xmm3
0x18002629c  movhps  qword ptr [rax+r13+18h], xmm7
0x1800262a2  sub     r12, 20h ; ' '
0x1800262a6  cmp     r12, rdi
0x1800262a9  jge     loc_180026210
0x1800262af  jmp     short loc_1800262F0
0x1800262b1  movups  xmm0, xmmword ptr [r12]
0x1800262b6  movups  xmm1, xmmword ptr [r12+10h]
0x1800262bc  movups  xmm2, xmmword ptr [r12+20h]
0x1800262c2  movups  xmm3, xmmword ptr [r12+30h]
0x1800262c8  movlps  qword ptr [r13+0], xmm0
0x1800262cd  movlps  qword ptr [r13+8], xmm2
0x1800262d2  movlps  qword ptr [r13+10h], xmm1
0x1800262d7  movlps  qword ptr [r13+18h], xmm3
0x1800262dc  movhps  qword ptr [r13+20h], xmm0
0x1800262e1  movhps  qword ptr [r13+28h], xmm2
0x1800262e6  movhps  qword ptr [r13+30h], xmm1
0x1800262eb  movhps  qword ptr [r13+38h], xmm3
0x1800262f0  movdqa  xmm7, [rsp+58h+var_58]
0x1800262f5  movdqa  xmm6, [rsp+58h+var_48]
0x1800262fb  add     rsp, 28h
0x1800262ff  pop     r13
0x180026301  pop     r12
0x180026303  pop     rbp
0x180026304  pop     rdi
0x180026305  pop     rsi
0x180026306  pop     rbx
0x180026307  retn
```
