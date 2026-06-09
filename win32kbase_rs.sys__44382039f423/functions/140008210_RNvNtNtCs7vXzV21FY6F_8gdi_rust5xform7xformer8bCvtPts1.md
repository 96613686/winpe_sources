# _RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer8bCvtPts1

- ea: `0x140008210`
- end: `0x140008732`
- name: `_RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer8bCvtPts1`
- size: `1314`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001490`
- `0x140001500`

## callees

- `0x140008210`
- `0x140008da0`
- `0x140017a10`

## pseudocode

```c
char __fastcall RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer8bCvtPts1(__int64 a1, __m128i *a2, __int64 a3)
{
  __m128i *v4; // rsi
  unsigned int v5; // eax
  __m128i v6; // xmm0
  unsigned __int64 v7; // rdx
  __m128i *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __m128i v11; // xmm1
  unsigned __int64 v12; // r8
  __m128i v13; // xmm3
  __m128i *v14; // r12
  float v15; // xmm6_4
  float v16; // xmm7_4
  __m128i v17; // xmm8
  __m128i v18; // xmm9
  float v19; // xmm1_4
  __m128i v20; // xmm0
  __m128i *v21; // r14
  __m128i v22; // xmm6
  __m128 v23; // xmm7
  __m128 v24; // xmm8
  __m128 v25; // xmm0
  __m128 v26; // xmm1
  __m128 v27; // xmm0
  __int64 v28; // rdi
  __m128i v29; // xmm6
  __m128 v30; // xmm7
  __m128 v31; // xmm8
  unsigned __int64 v32; // r13
  __m128i si128; // xmm9
  __m128 v34; // xmm0
  __m128 v35; // xmm1
  __m128 v36; // xmm0
  __m128i v37; // xmm0
  __m128i *v38; // r15
  float v39; // xmm6_4
  float v40; // xmm7_4
  __m128i v41; // xmm8
  int v42; // eax
  __m128i v43; // xmm1
  __m128i v44; // xmm0
  unsigned __int64 v45; // rcx
  __m128i *v46; // rax
  __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  __m128i v49; // xmm1
  unsigned __int64 v50; // r8
  __m128i v51; // xmm3
  __int64 v53; // [rsp+0h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+28h] [rbp-90h] BYREF
  unsigned int v55; // [rsp+2Ch] [rbp-8Ch] BYREF
  float v56; // [rsp+30h] [rbp-88h] BYREF
  float v57; // [rsp+34h] [rbp-84h] BYREF
  __int64 v58; // [rsp+38h] [rbp-80h]

  v4 = a2;
  v54 = 0;
  v55 = 0;
  v5 = *(_DWORD *)(a1 + 32) & 0xB;
  if ( v5 > 7 )
  {
    if ( v5 == 8 )
    {
      if ( a3 )
      {
        v28 = 8 * a3;
        v29 = _mm_loadl_epi64((const __m128i *)(a1 + 24));
        v30 = _mm_shuffle_ps(_mm_movelh_ps((__m128)*(unsigned int *)(a1 + 8), *(__m128 *)a1), *(__m128 *)a1, 226);
        v31 = _mm_shuffle_ps(
                _mm_movelh_ps((__m128)*(unsigned int *)(a1 + 12), *(__m128 *)(a1 + 4)),
                *(__m128 *)(a1 + 4),
                226);
        v32 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          v34 = _mm_cvtepi32_ps((__m128i)v4->m128i_u64[v32 / 8]);
          v35 = _mm_mul_ps(v30, v34);
          v56 = _mm_movehdup_ps(v35).m128_f32[0] + v35.m128_f32[0];
          v36 = _mm_mul_ps(v34, v31);
          v57 = _mm_movehdup_ps(v36).m128_f32[0] + v36.m128_f32[0];
          RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v56, &v54);
          RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v57, &v55);
          v37 = _mm_add_epi32(_mm_move_epi64(_mm_unpacklo_epi32(_mm_cvtsi32_si128(v54), _mm_cvtsi32_si128(v55))), v29);
          v4->m128i_i64[v32 / 8] = _mm_add_epi32(_mm_srai_epi32(v37, 4u), _mm_and_si128(_mm_srli_epi32(v37, 3u), si128)).m128i_u64[0];
          v32 += 8LL;
        }
        while ( v28 != v32 );
      }
    }
    else if ( v5 == 11 )
    {
      if ( a3 )
      {
        v43 = _mm_loadl_epi64((const __m128i *)(a1 + 24));
        v44 = _mm_add_epi32(_mm_and_si128(_mm_srli_epi32(v43, 3u), (__m128i)_xmm), _mm_srai_epi32(v43, 4u));
        v45 = 8 * a3 - 8;
        v46 = a2;
        if ( v45 < 0x18 )
          goto LABEL_42;
        v47 = (v45 >> 3) + 1;
        v48 = v47 & 0xFFFFFFFFFFFFFFFCuLL;
        v46 = (__m128i *)((char *)v4 + 8 * (v47 & 0xFFFFFFFFFFFFFFFCuLL));
        v49 = _mm_unpacklo_epi32(_mm_shuffle_epi32(v44, 0), _mm_shuffle_epi32(v44, 85));
        v50 = 0;
        do
        {
          v51 = _mm_loadu_si128(&v4[v50 / 2 + 1]);
          v4[v50 / 2] = _mm_add_epi32(_mm_loadu_si128(&v4[v50 / 2]), v49);
          v4[v50 / 2 + 1] = _mm_add_epi32(v51, v49);
          v50 += 4LL;
        }
        while ( v48 != v50 );
        if ( v47 != v48 )
        {
LABEL_42:
          do
          {
            v46->m128i_i64[0] = _mm_add_epi32(_mm_loadl_epi64(v46), v44).m128i_u64[0];
            v46 = (__m128i *)((char *)v46 + 8);
          }
          while ( v46 != (__m128i *)((char *)v4 + 8 * a3) );
        }
      }
    }
    else if ( v5 == 9 && a3 )
    {
      v14 = (__m128i *)((char *)a2 + 8 * a3);
      v15 = *(float *)a1;
      v16 = *(float *)(a1 + 12);
      v17 = _mm_loadl_epi64((const __m128i *)(a1 + 24));
      v18 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v19 = (float)v4->m128i_i32[1];
        v56 = (float)v4->m128i_i32[0] * v15;
        v57 = v19 * v16;
        RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v56, &v54);
        RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v57, &v55);
        v20 = _mm_add_epi32(_mm_move_epi64(_mm_unpacklo_epi32(_mm_cvtsi32_si128(v54), _mm_cvtsi32_si128(v55))), v17);
        v4->m128i_i64[0] = _mm_add_epi32(_mm_srai_epi32(v20, 4u), _mm_and_si128(_mm_srli_epi32(v20, 3u), v18)).m128i_u64[0];
        v4 = (__m128i *)((char *)v4 + 8);
      }
      while ( v4 != v14 );
    }
  }
  else if ( v5 )
  {
    if ( v5 == 1 )
    {
      if ( a3 )
      {
        v38 = (__m128i *)((char *)a2 + 8 * a3);
        v39 = *(float *)a1;
        v40 = *(float *)(a1 + 12);
        v41 = _mm_loadl_epi64((const __m128i *)(a1 + 24));
        do
        {
          v42 = 16 * v4->m128i_i32[1];
          v56 = (float)(16 * v4->m128i_i32[0]) * v39;
          v57 = (float)v42 * v40;
          RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v56, v4);
          RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v57, (char *)v4->m128i_i64 + 4);
          v4->m128i_i64[0] = _mm_add_epi32(_mm_loadl_epi64(v4), v41).m128i_u64[0];
          v4 = (__m128i *)((char *)v4 + 8);
        }
        while ( v4 != v38 );
      }
    }
    else if ( v5 == 3 )
    {
      if ( a3 )
      {
        v6 = _mm_loadl_epi64((const __m128i *)(a1 + 24));
        v7 = 8 * a3 - 8;
        v8 = v4;
        if ( v7 < 0x18 )
          goto LABEL_43;
        v9 = (v7 >> 3) + 1;
        v10 = v9 & 0xFFFFFFFFFFFFFFFCuLL;
        v8 = (__m128i *)((char *)v4 + 8 * (v9 & 0xFFFFFFFFFFFFFFFCuLL));
        v11 = _mm_unpacklo_epi32(_mm_shuffle_epi32(v6, 0), _mm_shuffle_epi32(v6, 85));
        v12 = 0;
        do
        {
          v13 = _mm_loadu_si128(&v4[v12 / 2 + 1]);
          v4[v12 / 2] = _mm_add_epi32(_mm_loadu_si128(&v4[v12 / 2]), v11);
          v4[v12 / 2 + 1] = _mm_add_epi32(v13, v11);
          v12 += 4LL;
        }
        while ( v10 != v12 );
        if ( v9 != v10 )
        {
LABEL_43:
          do
          {
            v8->m128i_i64[0] = _mm_add_epi32(_mm_loadl_epi64(v8), v6).m128i_u64[0];
            v8 = (__m128i *)((char *)v8 + 8);
          }
          while ( v8 != (__m128i *)((char *)v4 + 8 * a3) );
        }
      }
    }
  }
  else if ( a3 )
  {
    v21 = (__m128i *)((char *)a2 + 8 * a3);
    v22 = _mm_loadl_epi64((const __m128i *)(a1 + 24));
    v23 = _mm_shuffle_ps(_mm_movelh_ps((__m128)*(unsigned int *)(a1 + 8), *(__m128 *)a1), *(__m128 *)a1, 226);
    v24 = _mm_shuffle_ps(
            _mm_movelh_ps((__m128)*(unsigned int *)(a1 + 12), *(__m128 *)(a1 + 4)),
            *(__m128 *)(a1 + 4),
            226);
    do
    {
      v25 = _mm_cvtepi32_ps(_mm_slli_epi32(_mm_loadl_epi64(v4), 4u));
      v26 = _mm_mul_ps(v23, v25);
      v56 = _mm_movehdup_ps(v26).m128_f32[0] + v26.m128_f32[0];
      v27 = _mm_mul_ps(v25, v24);
      v57 = _mm_movehdup_ps(v27).m128_f32[0] + v27.m128_f32[0];
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v56, v4);
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v57, (char *)v4->m128i_i64 + 4);
      v4->m128i_i64[0] = _mm_add_epi32(_mm_loadl_epi64(v4), v22).m128i_u64[0];
      v4 = (__m128i *)((char *)v4 + 8);
    }
    while ( v4 != v21 );
  }
  if ( _security_cookie != ((unsigned __int64)&v53 ^ v58) )
    JUMPOUT(0x140008731LL);
  return 1;
}

```

## disassembly

```asm
0x140008210  push    r15
0x140008212  push    r14
0x140008214  push    r13
0x140008216  push    r12
0x140008218  push    rsi
0x140008219  push    rdi
0x14000821a  push    rbx
0x14000821b  sub     rsp, 80h
0x140008222  movdqa  [rsp+0B8h+var_48], xmm9
0x140008229  movaps  [rsp+0B8h+var_58], xmm8
0x14000822f  movaps  [rsp+0B8h+var_68], xmm7
0x140008234  movdqa  [rsp+0B8h+var_78], xmm6
0x14000823a  mov     rdi, r8
0x14000823d  mov     rsi, rdx
0x140008240  mov     rax, cs:__security_cookie
0x140008247  xor     rax, rsp
0x14000824a  mov     [rsp+0B8h+var_80], rax
0x14000824f  mov     [rsp+0B8h+var_90], 0
0x140008257  mov     [rsp+0B8h+var_8C], 0
0x14000825f  mov     eax, [rcx+20h]
0x140008262  and     eax, 0Bh
0x140008265  cmp     eax, 7
0x140008268  jg      loc_14000832A
0x14000826e  test    eax, eax
0x140008270  jz      loc_1400083FB
0x140008276  cmp     eax, 1
0x140008279  jz      loc_14000858C
0x14000827f  cmp     eax, 3
0x140008282  jnz     loc_1400086E5
0x140008288  test    rdi, rdi
0x14000828b  jz      loc_1400086E5
0x140008291  lea     rdx, ds:0[rdi*8]
0x140008299  movq    xmm0, qword ptr [rcx+18h]
0x14000829e  add     rdx, 0FFFFFFFFFFFFFFF8h
0x1400082a2  mov     rax, rsi
0x1400082a5  cmp     rdx, 18h
0x1400082a9  jb      short loc_140008304
0x1400082ab  shr     rdx, 3
0x1400082af  inc     rdx
0x1400082b2  mov     rcx, rdx
0x1400082b5  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400082b9  lea     rax, [rsi+rcx*8]
0x1400082bd  pshufd  xmm1, xmm0, 0
0x1400082c2  pshufd  xmm2, xmm0, 55h ; 'U'
0x1400082c7  punpckldq xmm1, xmm2
0x1400082cb  xor     r8d, r8d
0x1400082ce  xchg    ax, ax
0x1400082d0  movdqu  xmm2, xmmword ptr [rsi+r8*8]
0x1400082d6  movdqu  xmm3, xmmword ptr [rsi+r8*8+10h]
0x1400082dd  paddd   xmm2, xmm1
0x1400082e1  movdqu  xmmword ptr [rsi+r8*8], xmm2
0x1400082e7  paddd   xmm3, xmm1
0x1400082eb  movdqu  xmmword ptr [rsi+r8*8+10h], xmm3
0x1400082f2  add     r8, 4
0x1400082f6  cmp     rcx, r8
0x1400082f9  jnz     short loc_1400082D0
0x1400082fb  cmp     rdx, rcx
0x1400082fe  jz      loc_1400086E5
0x140008304  lea     rcx, [rsi+rdi*8]
0x140008308  nop     dword ptr [rax+rax+00000000h]
0x140008310  movq    xmm1, qword ptr [rax]
0x140008314  paddd   xmm1, xmm0
0x140008318  movq    qword ptr [rax], xmm1
0x14000831c  add     rax, 8
0x140008320  cmp     rax, rcx
0x140008323  jnz     short loc_140008310
0x140008325  jmp     loc_1400086E5
0x14000832a  cmp     eax, 8
0x14000832d  jz      loc_1400084A3
0x140008333  cmp     eax, 0Bh
0x140008336  jz      loc_140008622
0x14000833c  cmp     eax, 9
0x14000833f  jnz     loc_1400086E5
0x140008345  test    rdi, rdi
0x140008348  jz      loc_1400086E5
0x14000834e  lea     r12, [rsi+rdi*8]
0x140008352  movss   xmm6, dword ptr [rcx]
0x140008356  movss   xmm7, dword ptr [rcx+0Ch]
0x14000835b  movq    xmm8, qword ptr [rcx+18h]
0x140008361  lea     rdi, [rsp+0B8h+var_88]
0x140008366  lea     rbx, [rsp+0B8h+var_90]
0x14000836b  lea     r14, [rsp+0B8h+var_84]
0x140008370  lea     r15, [rsp+0B8h+var_8C]
0x140008375  movdqa  xmm9, cs:__xmm@00000000000000000000000100000001
0x14000837e  xchg    ax, ax
0x140008380  xorps   xmm0, xmm0
0x140008383  cvtsi2ss xmm0, dword ptr [rsi]
0x140008387  xorps   xmm1, xmm1
0x14000838a  cvtsi2ss xmm1, dword ptr [rsi+4]
0x14000838f  mulss   xmm0, xmm6
0x140008393  movss   [rsp+0B8h+var_88], xmm0
0x140008399  mulss   xmm1, xmm7
0x14000839d  movss   [rsp+0B8h+var_84], xmm1
0x1400083a3  mov     rcx, rdi
0x1400083a6  mov     rdx, rbx
0x1400083a9  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x1400083ae  mov     rcx, r14
0x1400083b1  mov     rdx, r15
0x1400083b4  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x1400083b9  movd    xmm0, [rsp+0B8h+var_8C]
0x1400083bf  movd    xmm1, [rsp+0B8h+var_90]
0x1400083c5  punpckldq xmm1, xmm0
0x1400083c9  movq    xmm0, xmm1
0x1400083cd  paddd   xmm0, xmm8
0x1400083d2  movdqa  xmm1, xmm0
0x1400083d6  psrld   xmm1, 3
0x1400083db  pand    xmm1, xmm9
0x1400083e0  psrad   xmm0, 4
0x1400083e5  paddd   xmm0, xmm1
0x1400083e9  movq    qword ptr [rsi], xmm0
0x1400083ed  add     rsi, 8
0x1400083f1  cmp     rsi, r12
0x1400083f4  jnz     short loc_140008380
0x1400083f6  jmp     loc_1400086E5
0x1400083fb  test    rdi, rdi
0x1400083fe  jz      loc_1400086E5
0x140008404  lea     r14, [rsi+rdi*8]
0x140008408  movups  xmm0, xmmword ptr [rcx]
0x14000840b  movups  xmm1, xmmword ptr [rcx+4]
0x14000840f  movq    xmm6, qword ptr [rcx+18h]
0x140008414  movss   xmm7, dword ptr [rcx+8]
0x140008419  movlhps xmm7, xmm0
0x14000841c  shufps  xmm7, xmm0, 0E2h
0x140008420  movss   xmm8, dword ptr [rcx+0Ch]
0x140008426  movlhps xmm8, xmm1
0x14000842a  shufps  xmm8, xmm1, 0E2h
0x14000842f  lea     rdi, [rsp+0B8h+var_88]
0x140008434  lea     rbx, [rsp+0B8h+var_84]
0x140008439  nop     dword ptr [rax+00000000h]
0x140008440  movq    xmm0, qword ptr [rsi]
0x140008444  pslld   xmm0, 4
0x140008449  cvtdq2ps xmm0, xmm0
0x14000844c  movaps  xmm1, xmm7
0x14000844f  mulps   xmm1, xmm0
0x140008452  movshdup xmm2, xmm1
0x140008456  addss   xmm2, xmm1
0x14000845a  movss   [rsp+0B8h+var_88], xmm2
0x140008460  mulps   xmm0, xmm8
0x140008464  movshdup xmm1, xmm0
0x140008468  addss   xmm1, xmm0
0x14000846c  movss   [rsp+0B8h+var_84], xmm1
0x140008472  mov     rcx, rdi
0x140008475  mov     rdx, rsi
0x140008478  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x14000847d  lea     rdx, [rsi+4]
0x140008481  mov     rcx, rbx
0x140008484  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140008489  movq    xmm0, qword ptr [rsi]
0x14000848d  paddd   xmm0, xmm6
0x140008491  movq    qword ptr [rsi], xmm0
0x140008495  add     rsi, 8
0x140008499  cmp     rsi, r14
0x14000849c  jnz     short loc_140008440
0x14000849e  jmp     loc_1400086E5
0x1400084a3  test    rdi, rdi
0x1400084a6  jz      loc_1400086E5
0x1400084ac  shl     rdi, 3
0x1400084b0  movups  xmm0, xmmword ptr [rcx]
0x1400084b3  movups  xmm1, xmmword ptr [rcx+4]
0x1400084b7  movq    xmm6, qword ptr [rcx+18h]
0x1400084bc  movss   xmm7, dword ptr [rcx+8]
0x1400084c1  movlhps xmm7, xmm0
0x1400084c4  shufps  xmm7, xmm0, 0E2h
0x1400084c8  movss   xmm8, dword ptr [rcx+0Ch]
0x1400084ce  movlhps xmm8, xmm1
0x1400084d2  shufps  xmm8, xmm1, 0E2h
0x1400084d7  xor     r13d, r13d
0x1400084da  lea     rbx, [rsp+0B8h+var_88]
0x1400084df  lea     r14, [rsp+0B8h+var_90]
0x1400084e4  lea     r15, [rsp+0B8h+var_84]
0x1400084e9  lea     r12, [rsp+0B8h+var_8C]
0x1400084ee  movdqa  xmm9, cs:__xmm@00000000000000000000000100000001
0x1400084f7  nop     word ptr [rax+rax+00000000h]
0x140008500  movsd   xmm0, qword ptr [rsi+r13]
0x140008506  cvtdq2ps xmm0, xmm0
0x140008509  movaps  xmm1, xmm7
0x14000850c  mulps   xmm1, xmm0
0x14000850f  movshdup xmm2, xmm1
0x140008513  addss   xmm2, xmm1
0x140008517  movss   [rsp+0B8h+var_88], xmm2
0x14000851d  mulps   xmm0, xmm8
0x140008521  movshdup xmm1, xmm0
0x140008525  addss   xmm1, xmm0
0x140008529  movss   [rsp+0B8h+var_84], xmm1
0x14000852f  mov     rcx, rbx
0x140008532  mov     rdx, r14
0x140008535  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x14000853a  mov     rcx, r15
0x14000853d  mov     rdx, r12
0x140008540  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140008545  movd    xmm0, [rsp+0B8h+var_8C]
0x14000854b  movd    xmm1, [rsp+0B8h+var_90]
0x140008551  punpckldq xmm1, xmm0
0x140008555  movq    xmm0, xmm1
0x140008559  paddd   xmm0, xmm6
0x14000855d  movdqa  xmm1, xmm0
0x140008561  psrld   xmm1, 3
0x140008566  pand    xmm1, xmm9
0x14000856b  psrad   xmm0, 4
0x140008570  paddd   xmm0, xmm1
0x140008574  movq    qword ptr [rsi+r13], xmm0
0x14000857a  add     r13, 8
0x14000857e  cmp     rdi, r13
0x140008581  jnz     loc_140008500
0x140008587  jmp     loc_1400086E5
0x14000858c  test    rdi, rdi
0x14000858f  jz      loc_1400086E5
0x140008595  lea     r15, [rsi+rdi*8]
0x140008599  movss   xmm6, dword ptr [rcx]
0x14000859d  movss   xmm7, dword ptr [rcx+0Ch]
0x1400085a2  movq    xmm8, qword ptr [rcx+18h]
0x1400085a8  lea     rdi, [rsp+0B8h+var_88]
0x1400085ad  lea     rbx, [rsp+0B8h+var_84]
0x1400085b2  nop     word ptr [rax+rax+00000000h]
0x1400085c0  mov     eax, [rsi]
0x1400085c2  shl     eax, 4
0x1400085c5  xorps   xmm0, xmm0
0x1400085c8  cvtsi2ss xmm0, eax
0x1400085cc  mulss   xmm0, xmm6
0x1400085d0  mov     eax, [rsi+4]
0x1400085d3  shl     eax, 4
0x1400085d6  xorps   xmm1, xmm1
0x1400085d9  cvtsi2ss xmm1, eax
0x1400085dd  movss   [rsp+0B8h+var_88], xmm0
0x1400085e3  lea     r14, [rsi+4]
0x1400085e7  mulss   xmm1, xmm7
0x1400085eb  movss   [rsp+0B8h+var_84], xmm1
0x1400085f1  mov     rcx, rdi
0x1400085f4  mov     rdx, rsi
0x1400085f7  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x1400085fc  mov     rcx, rbx
0x1400085ff  mov     rdx, r14
0x140008602  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140008607  movq    xmm0, qword ptr [rsi]
0x14000860b  paddd   xmm0, xmm8
0x140008610  movq    qword ptr [rsi], xmm0
0x140008614  add     rsi, 8
0x140008618  cmp     rsi, r15
0x14000861b  jnz     short loc_1400085C0
0x14000861d  jmp     loc_1400086E5
0x140008622  test    rdi, rdi
0x140008625  jz      loc_1400086E5
0x14000862b  movq    xmm1, qword ptr [rcx+18h]
0x140008630  movdqa  xmm0, xmm1
0x140008634  psrld   xmm0, 3
0x140008639  psrad   xmm1, 4
0x14000863e  pand    xmm0, cs:__xmm@00000000000000000000000100000001
0x140008646  paddd   xmm0, xmm1
0x14000864a  lea     rcx, ds:0[rdi*8]
0x140008652  add     rcx, 0FFFFFFFFFFFFFFF8h
0x140008656  mov     rax, rsi
0x140008659  cmp     rcx, 18h
0x14000865d  jb      short loc_1400086C0
0x14000865f  shr     rcx, 3
0x140008663  inc     rcx
0x140008666  mov     rdx, rcx
0x140008669  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14000866d  lea     rax, [rsi+rdx*8]
0x140008671  pshufd  xmm1, xmm0, 0
0x140008676  pshufd  xmm2, xmm0, 55h ; 'U'
0x14000867b  punpckldq xmm1, xmm2
0x14000867f  xor     r8d, r8d
0x140008682  nop     word ptr [rax+rax+00000000h]
0x140008690  movdqu  xmm2, xmmword ptr [rsi+r8*8]
0x140008696  movdqu  xmm3, xmmword ptr [rsi+r8*8+10h]
0x14000869d  paddd   xmm2, xmm1
0x1400086a1  movdqu  xmmword ptr [rsi+r8*8], xmm2
0x1400086a7  paddd   xmm3, xmm1
0x1400086ab  movdqu  xmmword ptr [rsi+r8*8+10h], xmm3
0x1400086b2  add     r8, 4
0x1400086b6  cmp     rdx, r8
0x1400086b9  jnz     short loc_140008690
0x1400086bb  cmp     rcx, rdx
0x1400086be  jz      short loc_1400086E5
0x1400086c0  lea     rcx, [rsi+rdi*8]
0x1400086c4  nop     word ptr [rax+rax+00000000h]
0x1400086d0  movq    xmm1, qword ptr [rax]
0x1400086d4  paddd   xmm1, xmm0
0x1400086d8  movq    qword ptr [rax], xmm1
0x1400086dc  add     rax, 8
0x1400086e0  cmp     rax, rcx
0x1400086e3  jnz     short loc_1400086D0
0x1400086e5  mov     rax, [rsp+0B8h+var_80]
0x1400086ea  xor     rax, rsp
0x1400086ed  mov     rcx, cs:__security_cookie
0x1400086f4  cmp     rcx, rax
0x1400086f7  jnz     short loc_140008724
0x1400086f9  mov     al, 1
0x1400086fb  movaps  xmm6, [rsp+0B8h+var_78]
0x140008700  movaps  xmm7, [rsp+0B8h+var_68]
0x140008705  movaps  xmm8, [rsp+0B8h+var_58]
0x14000870b  movaps  xmm9, [rsp+0B8h+var_48]
0x140008711  add     rsp, 80h
0x140008718  pop     rbx
0x140008719  pop     rdi
0x14000871a  pop     rsi
0x14000871b  pop     r12
0x14000871d  pop     r13
0x14000871f  pop     r14
0x140008721  pop     r15
  ... truncated ...
```
