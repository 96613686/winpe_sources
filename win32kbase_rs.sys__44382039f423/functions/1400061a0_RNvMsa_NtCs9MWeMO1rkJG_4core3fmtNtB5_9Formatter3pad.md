# _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter3pad

- ea: `0x1400061a0`
- end: `0x1400065f0`
- name: `_RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter3pad`
- size: `1104`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140004930`
- `0x140007220`
- `0x14000a850`
- `0x1400146d0`

## callees

- `0x1400061a0`
- `0x140006830`
- `0x140017a50`

## pseudocode

```c
char __fastcall RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter3pad(
        __int64 *a1,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  unsigned __int16 *v4; // r15
  unsigned int v5; // esi
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int16 *v8; // rbx
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // r10
  unsigned __int64 v12; // r9
  char v13; // r8
  __int64 *v14; // rdi
  __int64 v15; // rax
  __m128i si128; // xmm2
  __m128i v17; // xmm0
  __m128i v18; // xmm3
  __m128i v19; // xmm0
  __m128i v20; // xmm1
  __m128i v21; // xmm1
  __m128i v22; // xmm4
  __m128i v23; // xmm5
  __m128i v24; // xmm4
  __m128i v25; // xmm5
  __m128i v26; // xmm4
  __m128i v27; // xmm5
  __m128i v28; // xmm4
  __m128i v29; // xmm5
  __m128i v30; // xmm4
  __m128i v31; // xmm5
  __m128i v32; // xmm4
  __m128i v33; // xmm5
  __m128i v34; // xmm0
  unsigned __int64 v35; // r13
  unsigned int v36; // eax
  int v37; // r12d
  char result; // al
  unsigned int v39; // esi
  __int64 v40; // r15
  __int64 v41; // rbp
  __int16 v42; // di
  char v43; // cl
  __int16 v44; // r12
  unsigned __int16 v45; // di
  unsigned __int16 v46; // [rsp+2Ch] [rbp-4Ch]
  unsigned __int16 *v47; // [rsp+30h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = *((_DWORD *)a1 + 4);
  if ( (v5 & 0x18000000) == 0 )
    return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, unsigned __int64))(a1[1] + 24))(*a1, v4, v3);
  if ( (v5 & 0x10000000) != 0 )
  {
    if ( *((_WORD *)a1 + 11) )
    {
      v8 = (unsigned __int16 *)((char *)a2 + a3);
      v9 = 0;
      v10 = *((unsigned __int16 *)a1 + 11);
      while ( 1 )
      {
        v12 = v9;
        if ( a2 == v8 )
          break;
        v13 = *(_BYTE *)a2;
        if ( *(char *)a2 >= 0 )
        {
          v11 = (__int64)a2 + 1;
        }
        else if ( (unsigned __int8)v13 < 0xE0u )
        {
          v11 = (__int64)(a2 + 1);
        }
        else
        {
          v11 = (__int64)a2 - ((unsigned __int8)v13 < 0xF0u) + 4;
        }
        v9 = v12 + v11 - (_QWORD)a2;
        a2 = (unsigned __int16 *)v11;
        if ( !--v10 )
          goto LABEL_18;
      }
    }
    else
    {
      v9 = 0;
LABEL_18:
      v10 = 0;
    }
    v7 = *((unsigned __int16 *)a1 + 11) - v10;
    v3 = v9;
  }
  else if ( a3 >= 0x20 )
  {
    v14 = a1;
    v15 = RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars(a2, a3, a3);
    a1 = v14;
    v7 = v15;
  }
  else if ( a3 )
  {
    if ( a3 >= 4 )
    {
      v6 = a3 & 0x1C;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v17 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(*a2), si128);
      v18 = _mm_load_si128((const __m128i *)&_xmm);
      v19 = _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v17, v17), 212), 212), v18);
      v20 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[1]), si128);
      v21 = _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v20, v20), 212), 212), v18);
      if ( v6 != 4 )
      {
        v22 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[2]), si128);
        v23 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[3]), si128);
        v19 = _mm_add_epi64(
                v19,
                _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v22, v22), 212), 212), v18));
        v21 = _mm_add_epi64(
                v21,
                _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v23, v23), 212), 212), v18));
        if ( (_DWORD)v6 != 8 )
        {
          v24 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[4]), si128);
          v25 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[5]), si128);
          v19 = _mm_add_epi64(
                  v19,
                  _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v24, v24), 212), 212), v18));
          v21 = _mm_add_epi64(
                  v21,
                  _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v25, v25), 212), 212), v18));
          if ( (_DWORD)v6 != 12 )
          {
            v26 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[6]), si128);
            v27 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[7]), si128);
            v19 = _mm_add_epi64(
                    v19,
                    _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v26, v26), 212), 212), v18));
            v21 = _mm_add_epi64(
                    v21,
                    _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v27, v27), 212), 212), v18));
            if ( (_DWORD)v6 != 16 )
            {
              v28 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[8]), si128);
              v29 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[9]), si128);
              v19 = _mm_add_epi64(
                      v19,
                      _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v28, v28), 212), 212), v18));
              v21 = _mm_add_epi64(
                      v21,
                      _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v29, v29), 212), 212), v18));
              if ( (_DWORD)v6 != 20 )
              {
                v30 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[10]), si128);
                v31 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[11]), si128);
                v19 = _mm_add_epi64(
                        v19,
                        _mm_and_si128(
                          _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v30, v30), 212), 212),
                          v18));
                v21 = _mm_add_epi64(
                        v21,
                        _mm_and_si128(
                          _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v31, v31), 212), 212),
                          v18));
                if ( (_DWORD)v6 != 24 )
                {
                  v32 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[12]), si128);
                  v33 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a2[13]), si128);
                  v19 = _mm_add_epi64(
                          v19,
                          _mm_and_si128(
                            _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v32, v32), 212), 212),
                            v18));
                  v21 = _mm_add_epi64(
                          v21,
                          _mm_and_si128(
                            _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v33, v33), 212), 212),
                            v18));
                }
              }
            }
          }
        }
      }
      v34 = _mm_add_epi64(v19, v21);
      v7 = _mm_add_epi64(_mm_shuffle_epi32(v34, 238), v34).m128i_u64[0];
      goto LABEL_29;
    }
    v6 = 0;
    v7 = 0;
    do
    {
      v7 += *((_BYTE *)a2 + v6++) >= 0xC0;
LABEL_29:
      ;
    }
    while ( a3 != v6 );
  }
  else
  {
    v7 = 0;
  }
  v35 = *((unsigned __int16 *)a1 + 10);
  if ( v7 >= v35 )
    return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, unsigned __int64))(a1[1] + 24))(*a1, v4, v3);
  v36 = (v5 >> 29) & 3;
  LOWORD(v37) = 0;
  v47 = v4;
  if ( v36 > 1 )
  {
    if ( v36 == 2 )
      v37 = (unsigned __int16)(v35 - v7) >> 1;
  }
  else if ( v36 )
  {
    LOWORD(v37) = v35 - v7;
  }
  v39 = v5 & 0x1FFFFF;
  v40 = *a1;
  v41 = a1[1];
  v42 = v37 + 1;
  while ( --v42 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(v41 + 32))(v40, v39) )
      return 1;
  }
  v43 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int64))(v41 + 24))(v40, v47, v3);
  result = 1;
  if ( !v43 )
  {
    v46 = v35 - v7 - v37;
    v44 = v7 + v37 - v35;
    v45 = -1;
    while ( v44 + v45 != 0xFFFF )
    {
      ++v45;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(v41 + 32))(v40, v39) )
        return v45 < v46;
    }
    v45 = v46;
    return v45 < v46;
  }
  return result;
}

```

## disassembly

```asm
0x1400061a0  push    r15
0x1400061a2  push    r14
0x1400061a4  push    r13
0x1400061a6  push    r12
0x1400061a8  push    rsi
0x1400061a9  push    rdi
0x1400061aa  push    rbp
0x1400061ab  push    rbx
0x1400061ac  sub     rsp, 38h
0x1400061b0  mov     rbx, r8
0x1400061b3  mov     r15, rdx
0x1400061b6  mov     esi, [rcx+10h]
0x1400061b9  test    esi, 18000000h
0x1400061bf  jz      loc_140006509
0x1400061c5  test    esi, 10000000h
0x1400061cb  jnz     short loc_1400061F4
0x1400061cd  cmp     rbx, 20h ; ' '
0x1400061d1  jnb     loc_140006253
0x1400061d7  test    rbx, rbx
0x1400061da  jz      loc_140006281
0x1400061e0  cmp     rbx, 4
0x1400061e4  jnb     loc_140006289
0x1400061ea  xor     eax, eax
0x1400061ec  xor     r14d, r14d
0x1400061ef  jmp     loc_1400064C9
0x1400061f4  movzx   r14d, word ptr [rcx+16h]
0x1400061f9  test    r14, r14
0x1400061fc  jz      short loc_14000626C
0x1400061fe  add     rbx, r15
0x140006201  xor     r8d, r8d
0x140006204  mov     rdx, r15
0x140006207  mov     rax, r14
0x14000620a  jmp     short loc_140006225
0x140006210  lea     r10, [rdx+1]
0x140006214  mov     r8, r10
0x140006217  sub     r8, rdx
0x14000621a  add     r8, r9
0x14000621d  mov     rdx, r10
0x140006220  dec     rax
0x140006223  jz      short loc_14000626F
0x140006225  mov     r9, r8
0x140006228  cmp     rdx, rbx
0x14000622b  jz      short loc_140006273
0x14000622d  movzx   r8d, byte ptr [rdx]
0x140006231  test    r8b, r8b
0x140006234  jns     short loc_140006210
0x140006236  cmp     r8b, 0E0h
0x14000623a  jb      short loc_14000624D
0x14000623c  cmp     r8b, 0F0h
0x140006240  mov     r10, rdx
0x140006243  sbb     r10, 0FFFFFFFFFFFFFFFFh
0x140006247  add     r10, 3
0x14000624b  jmp     short loc_140006214
0x14000624d  lea     r10, [rdx+2]
0x140006251  jmp     short loc_140006214
0x140006253  mov     rdi, rcx
0x140006256  mov     rcx, r15
0x140006259  mov     rdx, rbx
0x14000625c  call    _RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars
0x140006261  mov     rcx, rdi
0x140006264  mov     r14, rax
0x140006267  jmp     loc_1400064DB
0x14000626c  xor     r8d, r8d
0x14000626f  xor     eax, eax
0x140006271  jmp     short loc_140006276
0x140006273  mov     r8, r9
0x140006276  sub     r14, rax
0x140006279  mov     rbx, r8
0x14000627c  jmp     loc_1400064DB
0x140006281  xor     r14d, r14d
0x140006284  jmp     loc_1400064DB
0x140006289  mov     eax, ebx
0x14000628b  and     eax, 1Ch
0x14000628e  movzx   edx, word ptr [r15]
0x140006292  movd    xmm0, edx
0x140006296  movzx   edx, word ptr [r15+2]
0x14000629b  movd    xmm1, edx
0x14000629f  movdqa  xmm2, cs:__xmm@0000000000000000000000000000bfbf
0x1400062a7  pcmpgtb xmm0, xmm2
0x1400062ab  punpcklbw xmm0, xmm0
0x1400062af  pshuflw xmm0, xmm0, 0D4h
0x1400062b4  pshufd  xmm0, xmm0, 0D4h
0x1400062b9  movdqa  xmm3, cs:__xmm@00000000000000010000000000000001
0x1400062c1  pand    xmm0, xmm3
0x1400062c5  pcmpgtb xmm1, xmm2
0x1400062c9  punpcklbw xmm1, xmm1
0x1400062cd  pshuflw xmm1, xmm1, 0D4h
0x1400062d2  pshufd  xmm1, xmm1, 0D4h
0x1400062d7  pand    xmm1, xmm3
0x1400062db  cmp     rax, 4
0x1400062df  jz      loc_1400064B2
0x1400062e5  movzx   edx, word ptr [r15+4]
0x1400062ea  movd    xmm4, edx
0x1400062ee  movzx   edx, word ptr [r15+6]
0x1400062f3  movd    xmm5, edx
0x1400062f7  pcmpgtb xmm4, xmm2
0x1400062fb  punpcklbw xmm4, xmm4
0x1400062ff  pshuflw xmm4, xmm4, 0D4h
0x140006304  pshufd  xmm4, xmm4, 0D4h
0x140006309  pand    xmm4, xmm3
0x14000630d  pcmpgtb xmm5, xmm2
0x140006311  punpcklbw xmm5, xmm5
0x140006315  pshuflw xmm5, xmm5, 0D4h
0x14000631a  pshufd  xmm5, xmm5, 0D4h
0x14000631f  pand    xmm5, xmm3
0x140006323  paddq   xmm0, xmm4
0x140006327  paddq   xmm1, xmm5
0x14000632b  cmp     eax, 8
0x14000632e  jz      loc_1400064B2
0x140006334  movzx   edx, word ptr [r15+8]
0x140006339  movd    xmm4, edx
0x14000633d  movzx   edx, word ptr [r15+0Ah]
0x140006342  movd    xmm5, edx
0x140006346  pcmpgtb xmm4, xmm2
0x14000634a  punpcklbw xmm4, xmm4
0x14000634e  pshuflw xmm4, xmm4, 0D4h
0x140006353  pshufd  xmm4, xmm4, 0D4h
0x140006358  pand    xmm4, xmm3
0x14000635c  pcmpgtb xmm5, xmm2
0x140006360  punpcklbw xmm5, xmm5
0x140006364  pshuflw xmm5, xmm5, 0D4h
0x140006369  pshufd  xmm5, xmm5, 0D4h
0x14000636e  pand    xmm5, xmm3
0x140006372  paddq   xmm0, xmm4
0x140006376  paddq   xmm1, xmm5
0x14000637a  cmp     eax, 0Ch
0x14000637d  jz      loc_1400064B2
0x140006383  movzx   edx, word ptr [r15+0Ch]
0x140006388  movd    xmm4, edx
0x14000638c  movzx   edx, word ptr [r15+0Eh]
0x140006391  movd    xmm5, edx
0x140006395  pcmpgtb xmm4, xmm2
0x140006399  punpcklbw xmm4, xmm4
0x14000639d  pshuflw xmm4, xmm4, 0D4h
0x1400063a2  pshufd  xmm4, xmm4, 0D4h
0x1400063a7  pand    xmm4, xmm3
0x1400063ab  pcmpgtb xmm5, xmm2
0x1400063af  punpcklbw xmm5, xmm5
0x1400063b3  pshuflw xmm5, xmm5, 0D4h
0x1400063b8  pshufd  xmm5, xmm5, 0D4h
0x1400063bd  pand    xmm5, xmm3
0x1400063c1  paddq   xmm0, xmm4
0x1400063c5  paddq   xmm1, xmm5
0x1400063c9  cmp     eax, 10h
0x1400063cc  jz      loc_1400064B2
0x1400063d2  movzx   edx, word ptr [r15+10h]
0x1400063d7  movd    xmm4, edx
0x1400063db  movzx   edx, word ptr [r15+12h]
0x1400063e0  movd    xmm5, edx
0x1400063e4  pcmpgtb xmm4, xmm2
0x1400063e8  punpcklbw xmm4, xmm4
0x1400063ec  pshuflw xmm4, xmm4, 0D4h
0x1400063f1  pshufd  xmm4, xmm4, 0D4h
0x1400063f6  pand    xmm4, xmm3
0x1400063fa  pcmpgtb xmm5, xmm2
0x1400063fe  punpcklbw xmm5, xmm5
0x140006402  pshuflw xmm5, xmm5, 0D4h
0x140006407  pshufd  xmm5, xmm5, 0D4h
0x14000640c  pand    xmm5, xmm3
0x140006410  paddq   xmm0, xmm4
0x140006414  paddq   xmm1, xmm5
0x140006418  cmp     eax, 14h
0x14000641b  jz      loc_1400064B2
0x140006421  movzx   edx, word ptr [r15+14h]
0x140006426  movd    xmm4, edx
0x14000642a  movzx   edx, word ptr [r15+16h]
0x14000642f  movd    xmm5, edx
0x140006433  pcmpgtb xmm4, xmm2
0x140006437  punpcklbw xmm4, xmm4
0x14000643b  pshuflw xmm4, xmm4, 0D4h
0x140006440  pshufd  xmm4, xmm4, 0D4h
0x140006445  pand    xmm4, xmm3
0x140006449  pcmpgtb xmm5, xmm2
0x14000644d  punpcklbw xmm5, xmm5
0x140006451  pshuflw xmm5, xmm5, 0D4h
0x140006456  pshufd  xmm5, xmm5, 0D4h
0x14000645b  pand    xmm5, xmm3
0x14000645f  paddq   xmm0, xmm4
0x140006463  paddq   xmm1, xmm5
0x140006467  cmp     eax, 18h
0x14000646a  jz      short loc_1400064B2
0x14000646c  movzx   edx, word ptr [r15+18h]
0x140006471  movd    xmm4, edx
0x140006475  movzx   edx, word ptr [r15+1Ah]
0x14000647a  movd    xmm5, edx
0x14000647e  pcmpgtb xmm4, xmm2
0x140006482  punpcklbw xmm4, xmm4
0x140006486  pshuflw xmm4, xmm4, 0D4h
0x14000648b  pshufd  xmm4, xmm4, 0D4h
0x140006490  pand    xmm4, xmm3
0x140006494  pcmpgtb xmm5, xmm2
0x140006498  punpcklbw xmm5, xmm5
0x14000649c  pshuflw xmm2, xmm5, 0D4h
0x1400064a1  pshufd  xmm2, xmm2, 0D4h
0x1400064a6  pand    xmm2, xmm3
0x1400064aa  paddq   xmm0, xmm4
0x1400064ae  paddq   xmm1, xmm2
0x1400064b2  paddq   xmm0, xmm1
0x1400064b6  pshufd  xmm1, xmm0, 0EEh
0x1400064bb  paddq   xmm1, xmm0
0x1400064bf  movq    r14, xmm1
0x1400064c4  cmp     rbx, rax
0x1400064c7  jz      short loc_1400064DB
0x1400064c9  xor     edx, edx
0x1400064cb  cmp     byte ptr [r15+rax], 0C0h
0x1400064d0  setnl   dl
0x1400064d3  add     r14, rdx
0x1400064d6  inc     rax
0x1400064d9  jmp     short loc_1400064C4
0x1400064db  movzx   r13d, word ptr [rcx+14h]
0x1400064e0  cmp     r14, r13
0x1400064e3  jnb     short loc_140006509
0x1400064e5  mov     edx, r13d
0x1400064e8  sub     edx, r14d
0x1400064eb  mov     eax, esi
0x1400064ed  shr     eax, 1Dh
0x1400064f0  and     eax, 3
0x1400064f3  xor     r12d, r12d
0x1400064f6  cmp     eax, 1
0x1400064f9  mov     [rsp+78h+var_48], r15
0x1400064fe  jg      short loc_140006534
0x140006500  test    eax, eax
0x140006502  jz      short loc_140006540
0x140006504  mov     r12d, edx
0x140006507  jmp     short loc_140006540
0x140006509  mov     rdx, [rcx]
0x14000650c  mov     rax, [rcx+8]
0x140006510  mov     rax, [rax+18h]
0x140006514  mov     rcx, rdx
0x140006517  mov     rdx, r15
0x14000651a  mov     r8, rbx
0x14000651d  add     rsp, 38h
0x140006521  pop     rbx
0x140006522  pop     rbp
0x140006523  pop     rdi
0x140006524  pop     rsi
0x140006525  pop     r12
0x140006527  pop     r13
0x140006529  pop     r14
0x14000652b  pop     r15
0x14000652d  jmp     cs:__guard_dispatch_icall_fptr
0x140006534  cmp     eax, 2
0x140006537  jnz     short loc_140006540
0x140006539  movzx   r12d, dx
0x14000653d  shr     r12d, 1
0x140006540  mov     [rsp+78h+var_4C], edx
0x140006544  and     esi, 1FFFFFh
0x14000654a  mov     r15, [rcx]
0x14000654d  mov     rbp, [rcx+8]
0x140006551  lea     edi, [r12+1]
0x140006556  nop     word ptr [rax+rax+00000000h]
0x140006560  dec     di
0x140006563  jz      short loc_14000657C
0x140006565  mov     rax, [rbp+20h]
0x140006569  mov     rcx, r15
0x14000656c  mov     edx, esi
0x14000656e  call    cs:__guard_dispatch_icall_fptr
0x140006574  test    al, al
0x140006576  jz      short loc_140006560
0x140006578  mov     al, 1
0x14000657a  jmp     short loc_1400065DF
0x14000657c  mov     rax, [rbp+18h]
0x140006580  mov     rcx, r15
0x140006583  mov     rdx, [rsp+78h+var_48]
0x140006588  mov     r8, rbx
0x14000658b  call    cs:__guard_dispatch_icall_fptr
0x140006591  mov     ecx, eax
0x140006593  mov     al, 1
0x140006595  test    cl, cl
0x140006597  jnz     short loc_1400065DF
0x140006599  sub     [rsp+78h+var_4C], r12d
0x14000659e  add     r12d, r14d
0x1400065a1  sub     r12d, r13d
0x1400065a4  mov     di, 0FFFFh
0x1400065a8  nop     dword ptr [rax+rax+00000000h]
0x1400065b0  lea     eax, [r12+rdi]
0x1400065b4  cmp     ax, 0FFFFh
0x1400065b8  jz      short loc_1400065D1
0x1400065ba  mov     rax, [rbp+20h]
0x1400065be  mov     rcx, r15
0x1400065c1  mov     edx, esi
0x1400065c3  call    cs:__guard_dispatch_icall_fptr
0x1400065c9  inc     edi
0x1400065cb  test    al, al
0x1400065cd  jz      short loc_1400065B0
0x1400065cf  jmp     short loc_1400065D7
0x1400065d1  mov     eax, [rsp+78h+var_4C]
0x1400065d5  mov     edi, eax
0x1400065d7  cmp     di, word ptr [rsp+78h+var_4C]
0x1400065dc  setb    al
0x1400065df  add     rsp, 38h
0x1400065e3  pop     rbx
0x1400065e4  pop     rbp
0x1400065e5  pop     rdi
0x1400065e6  pop     rsi
0x1400065e7  pop     r12
0x1400065e9  pop     r13
0x1400065eb  pop     r14
0x1400065ed  pop     r15
0x1400065ef  retn
  ... truncated ...
```
