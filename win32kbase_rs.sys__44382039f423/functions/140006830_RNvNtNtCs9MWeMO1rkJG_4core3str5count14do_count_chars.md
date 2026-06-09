# _RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars

- ea: `0x140006830`
- end: `0x140006e43`
- name: `_RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars`
- size: `1555`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005870`
- `0x1400061a0`

## callees

- `0x140006830`

## pseudocode

```c
unsigned __int64 __fastcall RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // r10
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // r8
  unsigned __int64 result; // rax
  unsigned __int64 v6; // r8
  int v7; // edx
  unsigned __int64 v8; // r9
  unsigned __int64 v9; // r11
  __m128i v10; // xmm0
  __int64 v11; // rax
  __m128i v12; // xmm1
  __m128i v13; // xmm3
  __m128i v14; // xmm2
  __m128i v15; // xmm4
  __m128i v16; // xmm5
  __m128i v17; // xmm0
  __m128i v18; // xmm0
  __int64 v19; // r9
  __m128i si128; // xmm1
  __m128i v21; // xmm3
  __m128i v22; // xmm2
  __m128i v23; // xmm4
  __m128i v24; // xmm5
  __m128i v25; // xmm0
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rsi
  unsigned __int64 v29; // rsi
  __m128i v30; // xmm1
  unsigned __int64 v31; // rsi
  int v32; // edi
  const __m128i *v33; // r10
  __int64 v34; // r11
  __int64 v35; // rcx
  const __m128i *v36; // rbx
  unsigned __int64 v37; // r14
  const __m128i *v38; // rsi
  __m128i v39; // xmm4
  unsigned __int64 v40; // r12
  __m128i v41; // xmm6
  __m128i v42; // xmm2
  __m128i v43; // xmm5
  __m128i v44; // xmm3
  __m128i v45; // xmm3
  __m128i v46; // xmm4
  __m128i v47; // xmm7
  __m128i v48; // xmm2
  __m128i v49; // xmm5
  __m128i v50; // xmm4
  __m128i v51; // xmm10
  __m128i v52; // xmm7
  __m128i v53; // xmm9
  __m128i v54; // xmm8
  __m128i v55; // xmm8
  __m128i v56; // xmm6
  __m128i v57; // xmm9
  __m128i v58; // xmm7
  __m128i v59; // xmm6
  __m128i v60; // xmm6
  __m128i v61; // xmm2
  __m128i v62; // xmm3
  __m128i v63; // xmm2
  __int64 v64; // r11
  unsigned __int64 v65; // rax

  v2 = ((a1 + 7) & 0xFFFFFFFFFFFFFFF8uLL) - a1;
  v3 = a2 - v2;
  if ( a2 >= v2 )
  {
    v6 = v3 >> 3;
    if ( v3 >> 3 )
    {
      v7 = v3 & 7;
      if ( ((a1 + 7) & 0xFFFFFFFFFFFFFFF8uLL) == a1 )
      {
        v8 = 0;
      }
      else
      {
        if ( v2 >= 4 )
        {
          v9 = v2 & 4;
          v18 = 0;
          v19 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          v21 = _mm_load_si128((const __m128i *)&_xmm);
          v22 = 0;
          do
          {
            v23 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(*(unsigned __int16 *)(a1 + v19)), si128);
            v22 = _mm_add_epi64(
                    v22,
                    _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v23, v23), 212), 212), v21));
            v24 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(*(unsigned __int16 *)(a1 + v19 + 2)), si128);
            v18 = _mm_add_epi64(
                    v18,
                    _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v24, v24), 212), 212), v21));
            v19 += 4;
          }
          while ( v9 != v19 );
          v25 = _mm_add_epi64(v18, v22);
          v8 = _mm_add_epi64(_mm_shuffle_epi32(v25, 238), v25).m128i_u64[0];
          goto LABEL_18;
        }
        v9 = 0;
        v8 = 0;
        do
        {
          v8 += *(_BYTE *)(a1 + v9++) >= 0xC0;
LABEL_18:
          ;
        }
        while ( v2 != v9 );
      }
      v26 = (a1 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( (v3 & 7) != 0 )
      {
        v27 = v3 & 0x7FFFFFFFFFFFFFF8LL;
        v28 = *(_BYTE *)(v26 + v27) >= 0xC0;
        if ( v7 != 1 )
        {
          v28 += *(_BYTE *)(v26 + v27 + 1) >= 0xC0;
          if ( v7 != 2 )
          {
            v28 += *(_BYTE *)(v26 + v27 + 2) >= 0xC0;
            if ( v7 != 3 )
            {
              v28 += *(_BYTE *)(v26 + v27 + 3) >= 0xC0;
              if ( v7 != 4 )
              {
                v28 += *(_BYTE *)(v26 + v27 + 4) >= 0xC0;
                if ( v7 != 5 )
                {
                  v28 += *(_BYTE *)(v26 + v27 + 5) >= 0xC0;
                  if ( v7 != 6 )
                    v28 += *(_BYTE *)(v26 + v27 + 6) >= 0xC0;
                }
              }
            }
          }
        }
      }
      else
      {
        v28 = 0;
      }
      v29 = v8 + v28;
      v30 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        result = v29;
        if ( !v6 )
          return result;
        v33 = (const __m128i *)v26;
        v34 = 192;
        if ( v6 < 0xC0 )
          v34 = v6;
        v35 = (unsigned int)(8 * v34);
        if ( ((8 * (_WORD)v34) & 0x7E0) != 0 )
        {
          if ( (unsigned __int64)(v35 - 32) >= 0x60 )
          {
            v37 = ((unsigned __int64)(v35 - 32) >> 5) + 1;
            v36 = &v33[2 * (v37 & 0xFFFFFFFFFFFFFFFCuLL)];
            v38 = v33 + 4;
            v39 = 0;
            v40 = v37 & 0xFFFFFFFFFFFFFFFCuLL;
            v41 = 0;
            do
            {
              v42 = _mm_loadu_si128(v38 - 4);
              v43 = _mm_loadu_si128(v38 - 2);
              v44 = _mm_unpacklo_epi64(v42, v43);
              v45 = _mm_add_epi64(
                      _mm_and_si128(
                        _mm_or_si128(_mm_srli_epi64(v44, 6u), _mm_srli_epi64(_mm_xor_si128(v44, (__m128i)-1LL), 7u)),
                        v30),
                      v39);
              v46 = _mm_loadu_si128(v38 - 3);
              v47 = _mm_loadu_si128(v38 - 1);
              v48 = _mm_unpackhi_epi64(v42, v43);
              v49 = _mm_unpacklo_epi64(v46, v47);
              v50 = _mm_unpackhi_epi64(v46, v47);
              v51 = _mm_loadu_si128(v38 + 3);
              v52 = _mm_loadu_si128(v38 + 2);
              v53 = _mm_loadu_si128(v38);
              v54 = _mm_unpacklo_epi64(v53, v52);
              v55 = _mm_add_epi64(
                      _mm_and_si128(
                        _mm_or_si128(_mm_srli_epi64(v54, 6u), _mm_srli_epi64(_mm_xor_si128(v54, (__m128i)-1LL), 7u)),
                        v30),
                      v41);
              v56 = _mm_loadu_si128(v38 + 1);
              v57 = _mm_unpackhi_epi64(v53, v52);
              v58 = _mm_unpacklo_epi64(v56, v51);
              v59 = _mm_unpackhi_epi64(v56, v51);
              v39 = _mm_add_epi64(
                      _mm_and_si128(
                        _mm_or_si128(_mm_srli_epi64(v50, 6u), _mm_srli_epi64(_mm_xor_si128(v50, (__m128i)-1LL), 7u)),
                        v30),
                      _mm_add_epi64(
                        _mm_add_epi64(
                          _mm_and_si128(
                            _mm_or_si128(_mm_srli_epi64(v49, 6u), _mm_srli_epi64(_mm_xor_si128(v49, (__m128i)-1LL), 7u)),
                            v30),
                          _mm_and_si128(
                            _mm_or_si128(_mm_srli_epi64(v48, 6u), _mm_srli_epi64(_mm_xor_si128(v48, (__m128i)-1LL), 7u)),
                            v30)),
                        v45));
              v41 = _mm_add_epi64(
                      _mm_and_si128(
                        _mm_or_si128(_mm_srli_epi64(v59, 6u), _mm_srli_epi64(_mm_xor_si128(v59, (__m128i)-1LL), 7u)),
                        v30),
                      _mm_add_epi64(
                        _mm_add_epi64(
                          _mm_and_si128(
                            _mm_or_si128(_mm_srli_epi64(v58, 6u), _mm_srli_epi64(_mm_xor_si128(v58, (__m128i)-1LL), 7u)),
                            v30),
                          _mm_and_si128(
                            _mm_or_si128(_mm_srli_epi64(v57, 6u), _mm_srli_epi64(_mm_xor_si128(v57, (__m128i)-1LL), 7u)),
                            v30)),
                        v55));
              v38 += 8;
              v40 -= 4LL;
            }
            while ( v40 );
            v60 = _mm_add_epi64(v41, v39);
            v31 = _mm_add_epi64(_mm_shuffle_epi32(v60, 238), v60).m128i_u64[0];
            if ( v37 == (v37 & 0xFFFFFFFFFFFFFFFCuLL) )
              goto LABEL_30;
          }
          else
          {
            v31 = 0;
            v36 = v33;
          }
          do
          {
            v61 = _mm_loadu_si128(v36);
            v62 = _mm_loadu_si128(v36 + 1);
            v63 = _mm_add_epi64(
                    _mm_and_si128(
                      _mm_or_si128(_mm_srli_epi64(v61, 6u), _mm_srli_epi64(_mm_xor_si128(v61, (__m128i)-1LL), 7u)),
                      v30),
                    _mm_and_si128(
                      _mm_or_si128(_mm_srli_epi64(v62, 6u), _mm_srli_epi64(_mm_xor_si128(v62, (__m128i)-1LL), 7u)),
                      v30));
            v31 += _mm_add_epi64(_mm_shuffle_epi32(v63, 238), v63).m128i_u64[0];
            v36 += 2;
          }
          while ( v36 != (const __m128i *)&v33->m128i_i8[(8 * (_WORD)v34) & 0x7E0] );
        }
        else
        {
          v31 = 0;
        }
LABEL_30:
        v26 = (unsigned __int64)v33->m128i_u64 + v35;
        v6 -= v34;
        v32 = v34 & 3;
        v29 = result + ((0x1000100010001LL * ((v31 & 0xFF00FF00FF00FFLL) + ((v31 >> 8) & 0xFF00FF00FF00FFLL))) >> 48);
        if ( (v34 & 3) != 0 )
        {
          v64 = (unsigned __int8)v34 & 0xFC;
          v65 = (((unsigned __int64)~v33->m128i_i64[(unsigned int)v64] >> 7)
               | ((unsigned __int64)v33->m128i_i64[(unsigned int)v64] >> 6))
              & 0x101010101010101LL;
          if ( v32 != 1 )
          {
            v65 += (((unsigned __int64)~v33->m128i_i64[v64 + 1] >> 7) | ((unsigned __int64)v33->m128i_i64[v64 + 1] >> 6))
                 & 0x101010101010101LL;
            if ( v32 != 2 )
              v65 += (((unsigned __int64)~v33[1].m128i_i64[v64] >> 7) | ((unsigned __int64)v33[1].m128i_i64[v64] >> 6))
                   & 0x101010101010101LL;
          }
          return v29 + ((0x1000100010001LL * ((v65 & 0xFF00FF00FF00FFLL) + ((v65 >> 8) & 0xFF00FF00FF00FFLL))) >> 48);
        }
      }
    }
  }
  if ( !a2 )
    return 0;
  if ( a2 >= 4 )
  {
    v4 = a2 & 0xFFFFFFFFFFFFFFFCuLL;
    v10 = 0;
    v11 = 0;
    v12 = _mm_load_si128((const __m128i *)&_xmm);
    v13 = _mm_load_si128((const __m128i *)&_xmm);
    v14 = 0;
    do
    {
      v15 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(*(unsigned __int16 *)(a1 + v11)), v12);
      v14 = _mm_add_epi64(
              v14,
              _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v15, v15), 212), 212), v13));
      v16 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(*(unsigned __int16 *)(a1 + v11 + 2)), v12);
      v10 = _mm_add_epi64(
              v10,
              _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v16, v16), 212), 212), v13));
      v11 += 4;
    }
    while ( v4 != v11 );
    v17 = _mm_add_epi64(v10, v14);
    result = _mm_add_epi64(_mm_shuffle_epi32(v17, 238), v17).m128i_u64[0];
    goto LABEL_46;
  }
  v4 = 0;
  result = 0;
  do
  {
    result += *(_BYTE *)(a1 + v4++) >= 0xC0;
LABEL_46:
    ;
  }
  while ( a2 != v4 );
  return result;
}

```

## disassembly

```asm
0x140006830  push    r15
0x140006832  push    r14
0x140006834  push    r12
0x140006836  push    rsi
0x140006837  push    rdi
0x140006838  push    rbx
0x140006839  sub     rsp, 68h
0x14000683d  movdqa  [rsp+98h+var_48], xmm11
0x140006844  movdqa  [rsp+98h+var_58], xmm10
0x14000684b  movdqa  [rsp+98h+var_68], xmm9
0x140006852  movdqa  [rsp+98h+var_78], xmm8
0x140006859  movdqa  [rsp+98h+var_88], xmm7
0x14000685f  movdqa  [rsp+98h+var_98], xmm6
0x140006864  lea     r9, [rcx+7]
0x140006868  and     r9, 0FFFFFFFFFFFFFFF8h
0x14000686c  mov     r10, r9
0x14000686f  sub     r10, rcx
0x140006872  mov     rax, rdx
0x140006875  sub     rax, r10
0x140006878  jnb     short loc_14000688F
0x14000687a  test    rdx, rdx
0x14000687d  jz      short loc_1400068BF
0x14000687f  cmp     rdx, 4
0x140006883  jnb     short loc_1400068C6
0x140006885  xor     r8d, r8d
0x140006888  xor     eax, eax
0x14000688a  jmp     loc_140006E00
0x14000688f  mov     r8, rax
0x140006892  shr     r8, 3
0x140006896  jz      short loc_14000687A
0x140006898  mov     edx, eax
0x14000689a  and     edx, 7
0x14000689d  cmp     r9, rcx
0x1400068a0  jnz     short loc_1400068AA
0x1400068a2  xor     r9d, r9d
0x1400068a5  jmp     loc_1400069FA
0x1400068aa  cmp     r10, 4
0x1400068ae  jnb     loc_140006959
0x1400068b4  xor     r11d, r11d
0x1400068b7  xor     r9d, r9d
0x1400068ba  jmp     loc_1400069E4
0x1400068bf  xor     eax, eax
0x1400068c1  jmp     loc_140006E14
0x1400068c6  mov     r8, rdx
0x1400068c9  and     r8, 0FFFFFFFFFFFFFFFCh
0x1400068cd  pxor    xmm0, xmm0
0x1400068d1  xor     eax, eax
0x1400068d3  movdqa  xmm1, cs:__xmm@0000000000000000000000000000bfbf
0x1400068db  movdqa  xmm3, cs:__xmm@00000000000000010000000000000001
0x1400068e3  pxor    xmm2, xmm2
0x1400068e7  nop     word ptr [rax+rax+00000000h]
0x1400068f0  movzx   r9d, word ptr [rcx+rax]
0x1400068f5  movd    xmm4, r9d
0x1400068fa  movzx   r9d, word ptr [rcx+rax+2]
0x140006900  movd    xmm5, r9d
0x140006905  pcmpgtb xmm4, xmm1
0x140006909  punpcklbw xmm4, xmm4
0x14000690d  pshuflw xmm4, xmm4, 0D4h
0x140006912  pshufd  xmm4, xmm4, 0D4h
0x140006917  pand    xmm4, xmm3
0x14000691b  paddq   xmm2, xmm4
0x14000691f  pcmpgtb xmm5, xmm1
0x140006923  punpcklbw xmm5, xmm5
0x140006927  pshuflw xmm4, xmm5, 0D4h
0x14000692c  pshufd  xmm4, xmm4, 0D4h
0x140006931  pand    xmm4, xmm3
0x140006935  paddq   xmm0, xmm4
0x140006939  add     rax, 4
0x14000693d  cmp     r8, rax
0x140006940  jnz     short loc_1400068F0
0x140006942  paddq   xmm0, xmm2
0x140006946  pshufd  xmm1, xmm0, 0EEh
0x14000694b  paddq   xmm1, xmm0
0x14000694f  movq    rax, xmm1
0x140006954  jmp     loc_140006DFB
0x140006959  mov     r11d, r10d
0x14000695c  and     r11d, 4
0x140006960  pxor    xmm0, xmm0
0x140006964  xor     r9d, r9d
0x140006967  movdqa  xmm1, cs:__xmm@0000000000000000000000000000bfbf
0x14000696f  movdqa  xmm3, cs:__xmm@00000000000000010000000000000001
0x140006977  pxor    xmm2, xmm2
0x14000697b  nop     dword ptr [rax+rax+00h]
0x140006980  movzx   esi, word ptr [rcx+r9]
0x140006985  movd    xmm4, esi
0x140006989  movzx   esi, word ptr [rcx+r9+2]
0x14000698f  movd    xmm5, esi
0x140006993  pcmpgtb xmm4, xmm1
0x140006997  punpcklbw xmm4, xmm4
0x14000699b  pshuflw xmm4, xmm4, 0D4h
0x1400069a0  pshufd  xmm4, xmm4, 0D4h
0x1400069a5  pand    xmm4, xmm3
0x1400069a9  paddq   xmm2, xmm4
0x1400069ad  pcmpgtb xmm5, xmm1
0x1400069b1  punpcklbw xmm5, xmm5
0x1400069b5  pshuflw xmm4, xmm5, 0D4h
0x1400069ba  pshufd  xmm4, xmm4, 0D4h
0x1400069bf  pand    xmm4, xmm3
0x1400069c3  paddq   xmm0, xmm4
0x1400069c7  add     r9, 4
0x1400069cb  cmp     r11, r9
0x1400069ce  jnz     short loc_140006980
0x1400069d0  paddq   xmm0, xmm2
0x1400069d4  pshufd  xmm1, xmm0, 0EEh
0x1400069d9  paddq   xmm1, xmm0
0x1400069dd  movq    r9, xmm1
0x1400069e2  jmp     short loc_1400069F5
0x1400069e4  xor     esi, esi
0x1400069e6  cmp     byte ptr [rcx+r11], 0C0h
0x1400069eb  setnl   sil
0x1400069ef  add     r9, rsi
0x1400069f2  inc     r11
0x1400069f5  cmp     r10, r11
0x1400069f8  jnz     short loc_1400069E4
0x1400069fa  add     rcx, r10
0x1400069fd  test    rdx, rdx
0x140006a00  jz      loc_140006A95
0x140006a06  mov     r10, 7FFFFFFFFFFFFFF8h
0x140006a10  and     rax, r10
0x140006a13  xor     esi, esi
0x140006a15  cmp     byte ptr [rcx+rax], 0C0h
0x140006a19  setnl   sil
0x140006a1d  cmp     edx, 1
0x140006a20  jz      short loc_140006A97
0x140006a22  xor     r10d, r10d
0x140006a25  cmp     byte ptr [rcx+rax+1], 0C0h
0x140006a2a  setnl   r10b
0x140006a2e  add     rsi, r10
0x140006a31  cmp     edx, 2
0x140006a34  jz      short loc_140006A97
0x140006a36  xor     r10d, r10d
0x140006a39  cmp     byte ptr [rcx+rax+2], 0C0h
0x140006a3e  setnl   r10b
0x140006a42  add     rsi, r10
0x140006a45  cmp     edx, 3
0x140006a48  jz      short loc_140006A97
0x140006a4a  xor     r10d, r10d
0x140006a4d  cmp     byte ptr [rcx+rax+3], 0C0h
0x140006a52  setnl   r10b
0x140006a56  add     rsi, r10
0x140006a59  cmp     edx, 4
0x140006a5c  jz      short loc_140006A97
0x140006a5e  xor     r10d, r10d
0x140006a61  cmp     byte ptr [rcx+rax+4], 0C0h
0x140006a66  setnl   r10b
0x140006a6a  add     rsi, r10
0x140006a6d  cmp     edx, 5
0x140006a70  jz      short loc_140006A97
0x140006a72  xor     r10d, r10d
0x140006a75  cmp     byte ptr [rcx+rax+5], 0C0h
0x140006a7a  setnl   r10b
0x140006a7e  add     rsi, r10
0x140006a81  cmp     edx, 6
0x140006a84  jz      short loc_140006A97
0x140006a86  xor     edx, edx
0x140006a88  cmp     byte ptr [rcx+rax+6], 0C0h
0x140006a8d  setnl   dl
0x140006a90  add     rsi, rdx
0x140006a93  jmp     short loc_140006A97
0x140006a95  xor     esi, esi
0x140006a97  add     rsi, r9
0x140006a9a  mov     r9, 0FF00FF00FF00FFh
0x140006aa4  mov     rdx, 1000100010001h
0x140006aae  pcmpeqd xmm0, xmm0
0x140006ab2  movdqa  xmm1, cs:__xmm@01010101010101010101010101010101
0x140006aba  jmp     short loc_140006AF2
0x140006ac0  xor     esi, esi
0x140006ac2  add     rcx, r10
0x140006ac5  sub     r8, r11
0x140006ac8  mov     edi, r11d
0x140006acb  and     edi, 3
0x140006ace  mov     rbx, rsi
0x140006ad1  and     rbx, r9
0x140006ad4  shr     rsi, 8
0x140006ad8  and     rsi, r9
0x140006adb  add     rsi, rbx
0x140006ade  imul    rsi, rdx
0x140006ae2  shr     rsi, 30h
0x140006ae6  add     rsi, rax
0x140006ae9  test    rdi, rdi
0x140006aec  jnz     loc_140006D70
0x140006af2  mov     rax, rsi
0x140006af5  test    r8, r8
0x140006af8  jz      loc_140006E14
0x140006afe  mov     r10, rcx
0x140006b01  cmp     r8, 0C0h
0x140006b08  mov     r11d, 0C0h
0x140006b0e  cmovb   r11, r8
0x140006b12  lea     ecx, ds:0[r11*8]
0x140006b1a  mov     edi, ecx
0x140006b1c  and     edi, 7E0h
0x140006b22  jz      short loc_140006AC0
0x140006b24  lea     r14, [rcx-20h]
0x140006b28  cmp     r14, 60h ; '`'
0x140006b2c  jnb     short loc_140006B40
0x140006b2e  xor     esi, esi
0x140006b30  mov     rbx, r10
0x140006b33  jmp     loc_140006D02
0x140006b40  shr     r14, 5
0x140006b44  inc     r14
0x140006b47  mov     r15, r14
0x140006b4a  and     r15, 0FFFFFFFFFFFFFFFCh
0x140006b4e  mov     rbx, r15
0x140006b51  shl     rbx, 5
0x140006b55  add     rbx, r10
0x140006b58  lea     rsi, [r10+40h]
0x140006b5c  pxor    xmm4, xmm4
0x140006b60  mov     r12, r15
0x140006b63  pxor    xmm6, xmm6
0x140006b67  nop     word ptr [rax+rax+00000000h]
0x140006b70  movdqu  xmm2, xmmword ptr [rsi-40h]
0x140006b75  movdqu  xmm5, xmmword ptr [rsi-20h]
0x140006b7a  movdqa  xmm3, xmm2
0x140006b7e  punpcklqdq xmm3, xmm5
0x140006b82  movdqa  xmm7, xmm3
0x140006b86  pxor    xmm7, xmm0
0x140006b8a  psrlq   xmm7, 7
0x140006b8f  psrlq   xmm3, 6
0x140006b94  por     xmm3, xmm7
0x140006b98  pand    xmm3, xmm1
0x140006b9c  paddq   xmm3, xmm4
0x140006ba0  movdqu  xmm4, xmmword ptr [rsi-30h]
0x140006ba5  movdqu  xmm7, xmmword ptr [rsi-10h]
0x140006baa  punpckhqdq xmm2, xmm5
0x140006bae  movdqa  xmm5, xmm4
0x140006bb2  punpcklqdq xmm5, xmm7
0x140006bb6  punpckhqdq xmm4, xmm7
0x140006bba  movdqu  xmm10, xmmword ptr [rsi+30h]
0x140006bc0  movdqu  xmm7, xmmword ptr [rsi+20h]
0x140006bc5  movdqu  xmm9, xmmword ptr [rsi]
0x140006bca  movdqa  xmm8, xmm9
0x140006bcf  punpcklqdq xmm8, xmm7
0x140006bd4  movdqa  xmm11, xmm8
0x140006bd9  pxor    xmm11, xmm0
0x140006bde  psrlq   xmm11, 7
0x140006be4  psrlq   xmm8, 6
0x140006bea  por     xmm8, xmm11
0x140006bef  pand    xmm8, xmm1
0x140006bf4  paddq   xmm8, xmm6
0x140006bf9  movdqu  xmm6, xmmword ptr [rsi+10h]
0x140006bfe  punpckhqdq xmm9, xmm7
0x140006c03  movdqa  xmm7, xmm6
0x140006c07  punpcklqdq xmm7, xmm10
0x140006c0c  punpckhqdq xmm6, xmm10
0x140006c11  movdqa  xmm10, xmm2
0x140006c16  pxor    xmm10, xmm0
0x140006c1b  movdqa  xmm11, xmm9
0x140006c20  pxor    xmm11, xmm0
0x140006c25  psrlq   xmm10, 7
0x140006c2b  psrlq   xmm11, 7
0x140006c31  psrlq   xmm2, 6
0x140006c36  por     xmm2, xmm10
0x140006c3b  psrlq   xmm9, 6
0x140006c41  por     xmm9, xmm11
0x140006c46  pand    xmm2, xmm1
0x140006c4a  pand    xmm9, xmm1
0x140006c4f  movdqa  xmm10, xmm5
0x140006c54  pxor    xmm10, xmm0
0x140006c59  movdqa  xmm11, xmm7
0x140006c5e  pxor    xmm11, xmm0
0x140006c63  psrlq   xmm10, 7
0x140006c69  psrlq   xmm11, 7
0x140006c6f  psrlq   xmm5, 6
0x140006c74  por     xmm5, xmm10
0x140006c79  psrlq   xmm7, 6
0x140006c7e  por     xmm7, xmm11
0x140006c83  pand    xmm5, xmm1
0x140006c87  paddq   xmm5, xmm2
0x140006c8b  paddq   xmm5, xmm3
0x140006c8f  pand    xmm7, xmm1
0x140006c93  paddq   xmm7, xmm9
0x140006c98  paddq   xmm7, xmm8
0x140006c9d  movdqa  xmm2, xmm4
0x140006ca1  pxor    xmm2, xmm0
0x140006ca5  movdqa  xmm3, xmm6
0x140006ca9  pxor    xmm3, xmm0
0x140006cad  psrlq   xmm2, 7
0x140006cb2  psrlq   xmm3, 7
0x140006cb7  psrlq   xmm4, 6
0x140006cbc  por     xmm4, xmm2
0x140006cc0  psrlq   xmm6, 6
0x140006cc5  por     xmm6, xmm3
0x140006cc9  pand    xmm4, xmm1
0x140006ccd  paddq   xmm4, xmm5
0x140006cd1  pand    xmm6, xmm1
0x140006cd5  paddq   xmm6, xmm7
0x140006cd9  sub     rsi, 0FFFFFFFFFFFFFF80h
0x140006cdd  add     r12, 0FFFFFFFFFFFFFFFCh
0x140006ce1  jnz     loc_140006B70
0x140006ce7  paddq   xmm6, xmm4
0x140006ceb  pshufd  xmm2, xmm6, 0EEh
0x140006cf0  paddq   xmm2, xmm6
0x140006cf4  movq    rsi, xmm2
0x140006cf9  cmp     r14, r15
0x140006cfc  jz      loc_140006AC2
0x140006d02  add     rdi, r10
0x140006d05  nop     word ptr [rax+rax+00000000h]
0x140006d10  movdqu  xmm2, xmmword ptr [rbx]
0x140006d14  movdqu  xmm3, xmmword ptr [rbx+10h]
0x140006d19  movdqa  xmm4, xmm2
  ... truncated ...
```
