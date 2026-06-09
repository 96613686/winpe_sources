# _RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer7bCvtVts

- ea: `0x140008030`
- end: `0x1400081fd`
- name: `_RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer7bCvtVts`
- size: `461`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400022a0`
- `0x1400023c0`
- `0x140002500`
- `0x140003210`

## callees

- `0x140008030`
- `0x140008da0`
- `0x140017a10`
- `0x140018400`

## pseudocode

```c
char __fastcall RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer7bCvtVts(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  float v8; // xmm6_4
  float v9; // xmm7_4
  __int64 v10; // rax
  __int64 v11; // r12
  float v12; // xmm1_4
  __m128 v13; // xmm6
  __m128 v14; // xmm7
  __int64 v15; // r12
  __m128i v16; // xmm0
  __m128 v17; // xmm0
  __m128 v18; // xmm1
  __m128 v19; // xmm0
  __int64 v21; // [rsp+0h] [rbp-A8h] BYREF
  float v22; // [rsp+38h] [rbp-70h] BYREF
  float v23; // [rsp+3Ch] [rbp-6Ch] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-68h] BYREF

  v24[0] = a3;
  if ( a3 != a5 )
    RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_(
      0,
      (__int64)v24,
      (__int64)&a5,
      (__int64)anon_d052ab7a191f147c7505ce516cc0d814_0_llvm_10903518121862351502,
      69,
      (__int64)&off_14001B1E8);
  if ( (*(_DWORD *)(a1 + 32) & 3) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 3) == 1 && a3 )
    {
      v8 = *(float *)a1;
      v9 = *(float *)(a1 + 12);
      v10 = 0;
      do
      {
        v11 = v10 + 1;
        v12 = (float)*(int *)(a2 + 8 * v10 + 4) * v9;
        v22 = (float)*(int *)(a2 + 8 * v10) * v8;
        v23 = v12;
        RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v22, a4);
        RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v23, a4 + 4);
        a4 += 8;
        v10 = v11;
      }
      while ( a3 != v11 );
    }
  }
  else if ( a3 )
  {
    v13 = _mm_shuffle_ps(_mm_movelh_ps((__m128)*(unsigned int *)(a1 + 8), *(__m128 *)a1), *(__m128 *)a1, 226);
    v14 = _mm_shuffle_ps(
            _mm_movelh_ps((__m128)*(unsigned int *)(a1 + 12), *(__m128 *)(a1 + 4)),
            *(__m128 *)(a1 + 4),
            226);
    v15 = 0;
    do
    {
      v16 = (__m128i)*(unsigned __int64 *)(a2 + 8 * v15++);
      v17 = _mm_cvtepi32_ps(v16);
      v18 = _mm_mul_ps(v13, v17);
      v23 = _mm_movehdup_ps(v18).m128_f32[0] + v18.m128_f32[0];
      v19 = _mm_mul_ps(v17, v14);
      v22 = _mm_movehdup_ps(v19).m128_f32[0] + v19.m128_f32[0];
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v23, a4);
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v22, a4 + 4);
      a4 += 8;
    }
    while ( a3 != v15 );
  }
  if ( _security_cookie != ((unsigned __int64)&v21 ^ v24[1]) )
    JUMPOUT(0x1400081FCLL);
  return 1;
}

```

## disassembly

```asm
0x140008030  push    r15
0x140008032  push    r14
0x140008034  push    r12
0x140008036  push    rsi
0x140008037  push    rdi
0x140008038  push    rbx
0x140008039  sub     rsp, 78h
0x14000803d  movaps  [rsp+0A8h+var_48], xmm7
0x140008042  movaps  [rsp+0A8h+var_58], xmm6
0x140008047  mov     rax, cs:__security_cookie
0x14000804e  xor     rax, rsp
0x140008051  mov     [rsp+0A8h+var_60], rax
0x140008056  mov     [rsp+0A8h+var_68], r8
0x14000805b  cmp     r8, [rsp+0A8h+arg_20]
0x140008063  jnz     loc_1400081BF
0x140008069  mov     rsi, r9
0x14000806c  mov     rdi, r8
0x14000806f  mov     rbx, rdx
0x140008072  mov     eax, [rcx+20h]
0x140008075  and     eax, 3
0x140008078  jz      loc_140008101
0x14000807e  cmp     eax, 1
0x140008081  jnz     loc_140008191
0x140008087  test    rdi, rdi
0x14000808a  jz      loc_140008191
0x140008090  movss   xmm6, dword ptr [rcx]
0x140008094  movss   xmm7, dword ptr [rcx+0Ch]
0x140008099  xor     eax, eax
0x14000809b  lea     r14, [rsp+0A8h+var_70]
0x1400080a0  lea     r15, [rsp+0A8h+var_6C]
0x1400080a5  nop     word ptr [rax+rax+00000000h]
0x1400080b0  xorps   xmm0, xmm0
0x1400080b3  cvtsi2ss xmm0, dword ptr [rbx+rax*8]
0x1400080b8  lea     r12, [rax+1]
0x1400080bc  xorps   xmm1, xmm1
0x1400080bf  cvtsi2ss xmm1, dword ptr [rbx+rax*8+4]
0x1400080c5  mulss   xmm0, xmm6
0x1400080c9  mulss   xmm1, xmm7
0x1400080cd  movss   [rsp+0A8h+var_70], xmm0
0x1400080d3  movss   [rsp+0A8h+var_6C], xmm1
0x1400080d9  mov     rcx, r14
0x1400080dc  mov     rdx, rsi
0x1400080df  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x1400080e4  lea     rdx, [rsi+4]
0x1400080e8  mov     rcx, r15
0x1400080eb  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x1400080f0  add     rsi, 8
0x1400080f4  mov     rax, r12
0x1400080f7  cmp     rdi, r12
0x1400080fa  jnz     short loc_1400080B0
0x1400080fc  jmp     loc_140008191
0x140008101  test    rdi, rdi
0x140008104  jz      loc_140008191
0x14000810a  movups  xmm0, xmmword ptr [rcx]
0x14000810d  movups  xmm1, xmmword ptr [rcx+4]
0x140008111  movss   xmm6, dword ptr [rcx+8]
0x140008116  movlhps xmm6, xmm0
0x140008119  shufps  xmm6, xmm0, 0E2h
0x14000811d  movss   xmm7, dword ptr [rcx+0Ch]
0x140008122  movlhps xmm7, xmm1
0x140008125  shufps  xmm7, xmm1, 0E2h
0x140008129  xor     r12d, r12d
0x14000812c  lea     r14, [rsp+0A8h+var_6C]
0x140008131  lea     r15, [rsp+0A8h+var_70]
0x140008136  nop     word ptr [rax+rax+00000000h]
0x140008140  movsd   xmm0, qword ptr [rbx+r12*8]
0x140008146  inc     r12
0x140008149  cvtdq2ps xmm0, xmm0
0x14000814c  movaps  xmm1, xmm6
0x14000814f  mulps   xmm1, xmm0
0x140008152  movshdup xmm2, xmm1
0x140008156  addss   xmm2, xmm1
0x14000815a  movss   [rsp+0A8h+var_6C], xmm2
0x140008160  mulps   xmm0, xmm7
0x140008163  movshdup xmm1, xmm0
0x140008167  addss   xmm1, xmm0
0x14000816b  movss   [rsp+0A8h+var_70], xmm1
0x140008171  mov     rcx, r14
0x140008174  mov     rdx, rsi
0x140008177  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x14000817c  lea     rdx, [rsi+4]
0x140008180  mov     rcx, r15
0x140008183  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140008188  add     rsi, 8
0x14000818c  cmp     rdi, r12
0x14000818f  jnz     short loc_140008140
0x140008191  mov     rax, [rsp+0A8h+var_60]
0x140008196  xor     rax, rsp
0x140008199  mov     rcx, cs:__security_cookie
0x1400081a0  cmp     rcx, rax
0x1400081a3  jnz     short loc_1400081EF
0x1400081a5  mov     al, 1
0x1400081a7  movaps  xmm6, [rsp+0A8h+var_58]
0x1400081ac  movaps  xmm7, [rsp+0A8h+var_48]
0x1400081b1  add     rsp, 78h
0x1400081b5  pop     rbx
0x1400081b6  pop     rdi
0x1400081b7  pop     rsi
0x1400081b8  pop     r12
0x1400081ba  pop     r14
0x1400081bc  pop     r15
0x1400081be  retn
0x1400081bf  lea     rax, off_14001B1E8; "gdi_rust\\src\\xform\\xformer.rs"
0x1400081c6  mov     [rsp+0A8h+var_80], rax
0x1400081cb  mov     [rsp+0A8h+var_88], 45h ; 'E'
0x1400081d4  lea     r9, anon_d052ab7a191f147c7505ce516cc0d814_0_llvm_10903518121862351502
0x1400081db  lea     rdx, [rsp+0A8h+var_68]
0x1400081e0  lea     r8, [rsp+0A8h+arg_20]
0x1400081e8  xor     ecx, ecx
0x1400081ea  call    _RINvNtCs9MWeMO1rkJG_4core9panicking13assert_failedjjEB4_
0x1400081ef  mov     rcx, [rsp+0A8h+var_60]
0x1400081f4  xor     rcx, rsp; StackCookie
0x1400081f7  call    __security_check_cookie
```
