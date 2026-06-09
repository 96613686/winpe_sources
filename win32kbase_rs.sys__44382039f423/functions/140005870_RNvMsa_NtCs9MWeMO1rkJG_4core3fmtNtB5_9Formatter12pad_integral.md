# _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter12pad_integral

- ea: `0x140005870`
- end: `0x140005d75`
- name: `_RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter12pad_integral`
- size: `1285`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140007240`
- `0x140007300`
- `0x1400073a0`
- `0x140007540`
- `0x140007730`
- `0x1400079b0`
- `0x140007b00`
- `0x140007bb0`

## callees

- `0x140005870`
- `0x140006830`
- `0x140006e50`
- `0x140017a50`

## pseudocode

```c
char __fastcall RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter12pad_integral(
        __int64 a1,
        char a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // rdi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // r14
  char v18; // cl
  char result; // al
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  __m128i si128; // xmm2
  __m128i v23; // xmm0
  __m128i v24; // xmm3
  __m128i v25; // xmm0
  __m128i v26; // xmm1
  __m128i v27; // xmm1
  __m128i v28; // xmm4
  __m128i v29; // xmm5
  __m128i v30; // xmm4
  __m128i v31; // xmm5
  __m128i v32; // xmm4
  __m128i v33; // xmm5
  __m128i v34; // xmm4
  __m128i v35; // xmm5
  __m128i v36; // xmm4
  __m128i v37; // xmm5
  __m128i v38; // xmm4
  __m128i v39; // xmm5
  __m128i v40; // xmm0
  unsigned int v41; // eax
  int v42; // eax
  __int64 v43; // rbp
  __int64 v44; // rbx
  __int64 v45; // r13
  char v46; // cl
  __int16 v47; // si
  unsigned int v48; // ebx
  __int64 v49; // r13
  __int64 v50; // r14
  __int16 v51; // bp
  char v52; // cl
  char v53; // cl
  __int16 v54; // r15
  unsigned __int16 v55; // si
  bool v56; // zf
  unsigned __int16 v57; // [rsp+28h] [rbp-60h]
  unsigned __int16 v58; // [rsp+28h] [rbp-60h]
  unsigned int v59; // [rsp+2Ch] [rbp-5Ch]
  __int16 v60; // [rsp+40h] [rbp-48h]

  v9 = *(_DWORD *)(a1 + 16);
  v10 = 43;
  if ( (v9 & 0x200000) == 0 )
    v10 = 1114112;
  v11 = (*(_DWORD *)(a1 + 16) & 0x200000u) >> 21;
  v12 = 45;
  if ( a2 )
    v12 = v10;
  v59 = v12;
  v13 = 1;
  if ( a2 )
    v13 = v11;
  v14 = a6 + v13;
  if ( (v9 & 0x800000) != 0 )
  {
    if ( a4 >= 0x20 )
    {
      v21 = RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars(a3, a4, v10);
    }
    else if ( a4 )
    {
      if ( a4 >= 4 )
      {
        v20 = a4 & 0x1C;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v23 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(*a3), si128);
        v24 = _mm_load_si128((const __m128i *)&_xmm);
        v25 = _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v23, v23), 212), 212), v24);
        v26 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[1]), si128);
        v27 = _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v26, v26), 212), 212), v24);
        if ( v20 != 4 )
        {
          v28 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[2]), si128);
          v29 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[3]), si128);
          v25 = _mm_add_epi64(
                  v25,
                  _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v28, v28), 212), 212), v24));
          v27 = _mm_add_epi64(
                  v27,
                  _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v29, v29), 212), 212), v24));
          if ( (_DWORD)v20 != 8 )
          {
            v30 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[4]), si128);
            v31 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[5]), si128);
            v25 = _mm_add_epi64(
                    v25,
                    _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v30, v30), 212), 212), v24));
            v27 = _mm_add_epi64(
                    v27,
                    _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v31, v31), 212), 212), v24));
            if ( (_DWORD)v20 != 12 )
            {
              v32 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[6]), si128);
              v33 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[7]), si128);
              v25 = _mm_add_epi64(
                      v25,
                      _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v32, v32), 212), 212), v24));
              v27 = _mm_add_epi64(
                      v27,
                      _mm_and_si128(_mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v33, v33), 212), 212), v24));
              if ( (_DWORD)v20 != 16 )
              {
                v34 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[8]), si128);
                v35 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[9]), si128);
                v25 = _mm_add_epi64(
                        v25,
                        _mm_and_si128(
                          _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v34, v34), 212), 212),
                          v24));
                v27 = _mm_add_epi64(
                        v27,
                        _mm_and_si128(
                          _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v35, v35), 212), 212),
                          v24));
                if ( (_DWORD)v20 != 20 )
                {
                  v36 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[10]), si128);
                  v37 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[11]), si128);
                  v25 = _mm_add_epi64(
                          v25,
                          _mm_and_si128(
                            _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v36, v36), 212), 212),
                            v24));
                  v27 = _mm_add_epi64(
                          v27,
                          _mm_and_si128(
                            _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v37, v37), 212), 212),
                            v24));
                  if ( (_DWORD)v20 != 24 )
                  {
                    v38 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[12]), si128);
                    v39 = _mm_cmpgt_epi8(_mm_cvtsi32_si128(a3[13]), si128);
                    v25 = _mm_add_epi64(
                            v25,
                            _mm_and_si128(
                              _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v38, v38), 212), 212),
                              v24));
                    v27 = _mm_add_epi64(
                            v27,
                            _mm_and_si128(
                              _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v39, v39), 212), 212),
                              v24));
                  }
                }
              }
            }
          }
        }
        v40 = _mm_add_epi64(v25, v27);
        v21 = _mm_add_epi64(_mm_shuffle_epi32(v40, 238), v40).m128i_u64[0];
        goto LABEL_26;
      }
      v20 = 0;
      v21 = 0;
      do
      {
        v21 += *((_BYTE *)a3 + v20++) >= 0xC0;
LABEL_26:
        ;
      }
      while ( a4 != v20 );
    }
    else
    {
      v21 = 0;
    }
    v14 += v21;
    v15 = *(unsigned __int16 *)(a1 + 20);
    if ( v14 >= v15 )
      goto LABEL_9;
  }
  else
  {
    a3 = 0;
    v15 = *(unsigned __int16 *)(a1 + 20);
    if ( v14 >= v15 )
    {
LABEL_9:
      v16 = *(_QWORD *)a1;
      v17 = *(_QWORD *)(a1 + 8);
      v18 = core::fmt::impl_12::pad_integral::write_prefix(v16, v17, v59, (__int64)a3, a4);
      result = 1;
      if ( !v18 )
        return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v17 + 24))(v16, a5, a6);
      return result;
    }
  }
  if ( (v9 & 0x1000000) == 0 )
  {
    v57 = v15 - v14;
    v41 = (v9 >> 29) & 3;
    if ( v41 > 1 )
    {
      if ( v41 == 2 )
      {
        v42 = v57 >> 1;
        goto LABEL_40;
      }
    }
    else if ( !v41 )
    {
      LOWORD(v42) = 0;
      goto LABEL_40;
    }
    LOWORD(v42) = v15 - v14;
LABEL_40:
    v48 = v9 & 0x1FFFFF;
    v49 = *(_QWORD *)a1;
    v50 = *(_QWORD *)(a1 + 8);
    v60 = v42;
    v51 = v42 + 1;
    while ( --v51 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64))(v50 + 32))(v49, v48, v10) )
        return 1;
    }
    v52 = core::fmt::impl_12::pad_integral::write_prefix(v49, v50, v59, (__int64)a3, a4);
    result = 1;
    if ( !v52 )
    {
      v53 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v50 + 24))(v49, a5, a6);
      result = 1;
      if ( !v53 )
      {
        v58 = v57 - v60;
        v54 = v14 + v60 - v15;
        v55 = -1;
        while ( v54 + v55 != 0xFFFF )
        {
          ++v55;
          if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(v50 + 32))(v49, v48) )
            return v55 < v58;
        }
        v55 = v58;
        return v55 < v58;
      }
    }
    return result;
  }
  v43 = *(_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 16) = v43 & 0x9FE00000 | 0x20000030;
  v44 = *(_QWORD *)a1;
  v45 = *(_QWORD *)(a1 + 8);
  v46 = core::fmt::impl_12::pad_integral::write_prefix(*(_QWORD *)a1, v45, v59, (__int64)a3, a4);
  result = 1;
  if ( !v46 )
  {
    v47 = v15 - v14 + 1;
    while ( --v47 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(v45 + 32))(v44, 48) )
        return 1;
    }
    v56 = (*(unsigned __int8 (__fastcall **)(__int64, __int64, __int64))(v45 + 24))(v44, a5, a6) == 0;
    result = 1;
    if ( v56 )
    {
      *(_QWORD *)(a1 + 16) = v43;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140005870  push    r15
0x140005872  push    r14
0x140005874  push    r13
0x140005876  push    r12
0x140005878  push    rsi
0x140005879  push    rdi
0x14000587a  push    rbp
0x14000587b  push    rbx
0x14000587c  sub     rsp, 48h
0x140005880  mov     r12, r9
0x140005883  mov     r15, r8
0x140005886  mov     r14, rcx
0x140005889  mov     r13, [rsp+88h+arg_28]
0x140005891  mov     rbp, [rsp+88h+arg_20]
0x140005899  mov     ebx, [rcx+10h]
0x14000589c  mov     eax, ebx
0x14000589e  and     eax, 200000h
0x1400058a3  mov     ecx, 110000h
0x1400058a8  mov     r8d, 2Bh ; '+'
0x1400058ae  cmovz   r8d, ecx
0x1400058b2  shr     eax, 15h
0x1400058b5  test    dl, dl
0x1400058b7  mov     ecx, 2Dh ; '-'
0x1400058bc  cmovnz  ecx, r8d
0x1400058c0  mov     [rsp+88h+var_5C], ecx
0x1400058c4  mov     edi, 1
0x1400058c9  cmovnz  rdi, rax
0x1400058cd  add     rdi, r13
0x1400058d0  test    ebx, 800000h
0x1400058d6  jnz     short loc_140005938
0x1400058d8  xor     r15d, r15d
0x1400058db  movzx   esi, word ptr [r14+14h]
0x1400058e0  cmp     rdi, rsi
0x1400058e3  jb      loc_140005BCD
0x1400058e9  mov     rbx, [r14]
0x1400058ec  mov     r14, [r14+8]
0x1400058f0  mov     [rsp+88h+var_68], r12
0x1400058f5  mov     rcx, rbx
0x1400058f8  mov     rdx, r14
0x1400058fb  mov     r8d, [rsp+88h+var_5C]
0x140005900  mov     r9, r15
0x140005903  call    core__fmt__impl$12__pad_integral__write_prefix
0x140005908  mov     ecx, eax
0x14000590a  mov     al, 1
0x14000590c  test    cl, cl
0x14000590e  jnz     loc_140005D64
0x140005914  mov     rax, [r14+18h]
0x140005918  mov     rcx, rbx
0x14000591b  mov     rdx, rbp
0x14000591e  mov     r8, r13
0x140005921  add     rsp, 48h
0x140005925  pop     rbx
0x140005926  pop     rbp
0x140005927  pop     rdi
0x140005928  pop     rsi
0x140005929  pop     r12
0x14000592b  pop     r13
0x14000592d  pop     r14
0x14000592f  pop     r15
0x140005931  jmp     cs:__guard_dispatch_icall_fptr
0x140005938  cmp     r12, 20h ; ' '
0x14000593c  jnb     short loc_140005952
0x14000593e  test    r12, r12
0x140005941  jz      short loc_140005962
0x140005943  cmp     r12, 4
0x140005947  jnb     short loc_140005969
0x140005949  xor     ecx, ecx
0x14000594b  xor     eax, eax
0x14000594d  jmp     loc_140005BA7
0x140005952  mov     rcx, r15
0x140005955  mov     rdx, r12
0x140005958  call    _RNvNtNtCs9MWeMO1rkJG_4core3str5count14do_count_chars
0x14000595d  jmp     loc_140005BBC
0x140005962  xor     eax, eax
0x140005964  jmp     loc_140005BBC
0x140005969  mov     ecx, r12d
0x14000596c  and     ecx, 1Ch
0x14000596f  movzx   eax, word ptr [r15]
0x140005973  movd    xmm0, eax
0x140005977  movzx   eax, word ptr [r15+2]
0x14000597c  movd    xmm1, eax
0x140005980  movdqa  xmm2, cs:__xmm@0000000000000000000000000000bfbf
0x140005988  pcmpgtb xmm0, xmm2
0x14000598c  punpcklbw xmm0, xmm0
0x140005990  pshuflw xmm0, xmm0, 0D4h
0x140005995  pshufd  xmm0, xmm0, 0D4h
0x14000599a  movdqa  xmm3, cs:__xmm@00000000000000010000000000000001
0x1400059a2  pand    xmm0, xmm3
0x1400059a6  pcmpgtb xmm1, xmm2
0x1400059aa  punpcklbw xmm1, xmm1
0x1400059ae  pshuflw xmm1, xmm1, 0D4h
0x1400059b3  pshufd  xmm1, xmm1, 0D4h
0x1400059b8  pand    xmm1, xmm3
0x1400059bc  cmp     rcx, 4
0x1400059c0  jz      loc_140005B93
0x1400059c6  movzx   eax, word ptr [r15+4]
0x1400059cb  movd    xmm4, eax
0x1400059cf  movzx   eax, word ptr [r15+6]
0x1400059d4  movd    xmm5, eax
0x1400059d8  pcmpgtb xmm4, xmm2
0x1400059dc  punpcklbw xmm4, xmm4
0x1400059e0  pshuflw xmm4, xmm4, 0D4h
0x1400059e5  pshufd  xmm4, xmm4, 0D4h
0x1400059ea  pand    xmm4, xmm3
0x1400059ee  pcmpgtb xmm5, xmm2
0x1400059f2  punpcklbw xmm5, xmm5
0x1400059f6  pshuflw xmm5, xmm5, 0D4h
0x1400059fb  pshufd  xmm5, xmm5, 0D4h
0x140005a00  pand    xmm5, xmm3
0x140005a04  paddq   xmm0, xmm4
0x140005a08  paddq   xmm1, xmm5
0x140005a0c  cmp     ecx, 8
0x140005a0f  jz      loc_140005B93
0x140005a15  movzx   eax, word ptr [r15+8]
0x140005a1a  movd    xmm4, eax
0x140005a1e  movzx   eax, word ptr [r15+0Ah]
0x140005a23  movd    xmm5, eax
0x140005a27  pcmpgtb xmm4, xmm2
0x140005a2b  punpcklbw xmm4, xmm4
0x140005a2f  pshuflw xmm4, xmm4, 0D4h
0x140005a34  pshufd  xmm4, xmm4, 0D4h
0x140005a39  pand    xmm4, xmm3
0x140005a3d  pcmpgtb xmm5, xmm2
0x140005a41  punpcklbw xmm5, xmm5
0x140005a45  pshuflw xmm5, xmm5, 0D4h
0x140005a4a  pshufd  xmm5, xmm5, 0D4h
0x140005a4f  pand    xmm5, xmm3
0x140005a53  paddq   xmm0, xmm4
0x140005a57  paddq   xmm1, xmm5
0x140005a5b  cmp     ecx, 0Ch
0x140005a5e  jz      loc_140005B93
0x140005a64  movzx   eax, word ptr [r15+0Ch]
0x140005a69  movd    xmm4, eax
0x140005a6d  movzx   eax, word ptr [r15+0Eh]
0x140005a72  movd    xmm5, eax
0x140005a76  pcmpgtb xmm4, xmm2
0x140005a7a  punpcklbw xmm4, xmm4
0x140005a7e  pshuflw xmm4, xmm4, 0D4h
0x140005a83  pshufd  xmm4, xmm4, 0D4h
0x140005a88  pand    xmm4, xmm3
0x140005a8c  pcmpgtb xmm5, xmm2
0x140005a90  punpcklbw xmm5, xmm5
0x140005a94  pshuflw xmm5, xmm5, 0D4h
0x140005a99  pshufd  xmm5, xmm5, 0D4h
0x140005a9e  pand    xmm5, xmm3
0x140005aa2  paddq   xmm0, xmm4
0x140005aa6  paddq   xmm1, xmm5
0x140005aaa  cmp     ecx, 10h
0x140005aad  jz      loc_140005B93
0x140005ab3  movzx   eax, word ptr [r15+10h]
0x140005ab8  movd    xmm4, eax
0x140005abc  movzx   eax, word ptr [r15+12h]
0x140005ac1  movd    xmm5, eax
0x140005ac5  pcmpgtb xmm4, xmm2
0x140005ac9  punpcklbw xmm4, xmm4
0x140005acd  pshuflw xmm4, xmm4, 0D4h
0x140005ad2  pshufd  xmm4, xmm4, 0D4h
0x140005ad7  pand    xmm4, xmm3
0x140005adb  pcmpgtb xmm5, xmm2
0x140005adf  punpcklbw xmm5, xmm5
0x140005ae3  pshuflw xmm5, xmm5, 0D4h
0x140005ae8  pshufd  xmm5, xmm5, 0D4h
0x140005aed  pand    xmm5, xmm3
0x140005af1  paddq   xmm0, xmm4
0x140005af5  paddq   xmm1, xmm5
0x140005af9  cmp     ecx, 14h
0x140005afc  jz      loc_140005B93
0x140005b02  movzx   eax, word ptr [r15+14h]
0x140005b07  movd    xmm4, eax
0x140005b0b  movzx   eax, word ptr [r15+16h]
0x140005b10  movd    xmm5, eax
0x140005b14  pcmpgtb xmm4, xmm2
0x140005b18  punpcklbw xmm4, xmm4
0x140005b1c  pshuflw xmm4, xmm4, 0D4h
0x140005b21  pshufd  xmm4, xmm4, 0D4h
0x140005b26  pand    xmm4, xmm3
0x140005b2a  pcmpgtb xmm5, xmm2
0x140005b2e  punpcklbw xmm5, xmm5
0x140005b32  pshuflw xmm5, xmm5, 0D4h
0x140005b37  pshufd  xmm5, xmm5, 0D4h
0x140005b3c  pand    xmm5, xmm3
0x140005b40  paddq   xmm0, xmm4
0x140005b44  paddq   xmm1, xmm5
0x140005b48  cmp     ecx, 18h
0x140005b4b  jz      short loc_140005B93
0x140005b4d  movzx   eax, word ptr [r15+18h]
0x140005b52  movd    xmm4, eax
0x140005b56  movzx   eax, word ptr [r15+1Ah]
0x140005b5b  movd    xmm5, eax
0x140005b5f  pcmpgtb xmm4, xmm2
0x140005b63  punpcklbw xmm4, xmm4
0x140005b67  pshuflw xmm4, xmm4, 0D4h
0x140005b6c  pshufd  xmm4, xmm4, 0D4h
0x140005b71  pand    xmm4, xmm3
0x140005b75  pcmpgtb xmm5, xmm2
0x140005b79  punpcklbw xmm5, xmm5
0x140005b7d  pshuflw xmm2, xmm5, 0D4h
0x140005b82  pshufd  xmm2, xmm2, 0D4h
0x140005b87  pand    xmm2, xmm3
0x140005b8b  paddq   xmm0, xmm4
0x140005b8f  paddq   xmm1, xmm2
0x140005b93  paddq   xmm0, xmm1
0x140005b97  pshufd  xmm1, xmm0, 0EEh
0x140005b9c  paddq   xmm1, xmm0
0x140005ba0  movq    rax, xmm1
0x140005ba5  jmp     short loc_140005BB7
0x140005ba7  xor     edx, edx
0x140005ba9  cmp     byte ptr [r15+rcx], 0C0h
0x140005bae  setnl   dl
0x140005bb1  add     rax, rdx
0x140005bb4  inc     rcx
0x140005bb7  cmp     r12, rcx
0x140005bba  jnz     short loc_140005BA7
0x140005bbc  add     rdi, rax
0x140005bbf  movzx   esi, word ptr [r14+14h]
0x140005bc4  cmp     rdi, rsi
0x140005bc7  jnb     loc_1400058E9
0x140005bcd  test    ebx, 1000000h
0x140005bd3  mov     [rsp+88h+var_50], r13
0x140005bd8  mov     [rsp+88h+var_58], rbp
0x140005bdd  jnz     short loc_140005BFC
0x140005bdf  mov     eax, esi
0x140005be1  sub     eax, edi
0x140005be3  mov     [rsp+88h+var_60], eax
0x140005be7  mov     eax, ebx
0x140005be9  shr     eax, 1Dh
0x140005bec  and     eax, 3
0x140005bef  cmp     eax, 1
0x140005bf2  jg      short loc_140005C61
0x140005bf4  test    eax, eax
0x140005bf6  jnz     short loc_140005C6F
0x140005bf8  xor     eax, eax
0x140005bfa  jmp     short loc_140005C73
0x140005bfc  mov     rbp, [r14+10h]
0x140005c00  mov     eax, ebp
0x140005c02  and     eax, 9FE00000h
0x140005c07  or      eax, 20000030h
0x140005c0c  mov     [r14+10h], eax
0x140005c10  mov     rbx, [r14]
0x140005c13  mov     r13, [r14+8]
0x140005c17  mov     [rsp+88h+var_68], r12
0x140005c1c  mov     rcx, rbx
0x140005c1f  mov     rdx, r13
0x140005c22  mov     r8d, [rsp+88h+var_5C]
0x140005c27  mov     r9, r15
0x140005c2a  call    core__fmt__impl$12__pad_integral__write_prefix
0x140005c2f  mov     ecx, eax
0x140005c31  mov     al, 1
0x140005c33  test    cl, cl
0x140005c35  jnz     loc_140005D64
0x140005c3b  sub     esi, edi
0x140005c3d  inc     esi
0x140005c3f  nop
0x140005c40  dec     si
0x140005c43  jz      loc_140005D31
0x140005c49  mov     rax, [r13+20h]
0x140005c4d  mov     rcx, rbx
0x140005c50  mov     edx, 30h ; '0'
0x140005c55  call    cs:__guard_dispatch_icall_fptr
0x140005c5b  test    al, al
0x140005c5d  jz      short loc_140005C40
0x140005c5f  jmp     short loc_140005CA8
0x140005c61  cmp     eax, 2
0x140005c64  jnz     short loc_140005C6F
0x140005c66  movzx   eax, word ptr [rsp+88h+var_60]
0x140005c6b  shr     eax, 1
0x140005c6d  jmp     short loc_140005C73
0x140005c6f  mov     eax, [rsp+88h+var_60]
0x140005c73  and     ebx, 1FFFFFh
0x140005c79  mov     r13, [r14]
0x140005c7c  mov     r14, [r14+8]
0x140005c80  mov     qword ptr [rsp+88h+var_48], rax
0x140005c85  lea     ebp, [rax+1]
0x140005c88  nop     dword ptr [rax+rax+00000000h]
0x140005c90  dec     bp
0x140005c93  jz      short loc_140005CAF
0x140005c95  mov     rax, [r14+20h]
0x140005c99  mov     rcx, r13
0x140005c9c  mov     edx, ebx
0x140005c9e  call    cs:__guard_dispatch_icall_fptr
0x140005ca4  test    al, al
0x140005ca6  jz      short loc_140005C90
0x140005ca8  mov     al, 1
0x140005caa  jmp     loc_140005D64
0x140005caf  mov     [rsp+88h+var_68], r12
0x140005cb4  mov     rcx, r13
0x140005cb7  mov     rdx, r14
0x140005cba  mov     r8d, [rsp+88h+var_5C]
0x140005cbf  mov     r9, r15
0x140005cc2  call    core__fmt__impl$12__pad_integral__write_prefix
0x140005cc7  mov     ecx, eax
0x140005cc9  mov     al, 1
0x140005ccb  test    cl, cl
0x140005ccd  jnz     loc_140005D64
0x140005cd3  mov     rax, [r14+18h]
0x140005cd7  mov     rcx, r13
0x140005cda  mov     rdx, [rsp+88h+var_58]
0x140005cdf  mov     r8, [rsp+88h+var_50]
0x140005ce4  call    cs:__guard_dispatch_icall_fptr
0x140005cea  mov     ecx, eax
  ... truncated ...
```
