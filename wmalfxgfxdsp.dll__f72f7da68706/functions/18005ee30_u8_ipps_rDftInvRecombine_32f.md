# u8_ipps_rDftInvRecombine_32f

- ea: `0x18005ee30`
- end: `0x18005ef85`
- name: `u8_ipps_rDftInvRecombine_32f`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ea70`

## callees

- `0x18005ee30`

## pseudocode

```c
__int64 __fastcall u8_ipps_rDftInvRecombine_32f(float *a1, float *a2, __int64 a3, __m128 *a4)
{
  __int64 result; // rax
  float v6; // xmm0_4
  unsigned __int64 v7; // rbp
  float *v8; // r10
  double *v9; // rbp
  float *v10; // r13
  __int64 v11; // rbp
  unsigned __int64 *v12; // r12
  double *v13; // rbx
  __m128 v14; // xmm2
  __m128 v15; // xmm1
  __m128 v16; // xmm0
  __m128 v17; // xmm2
  __m128 v18; // xmm3
  __m128 v19; // xmm4
  __m128 v20; // xmm1
  __m128 v21; // xmm2

  result = a3;
  v6 = *a1 - a1[1];
  *a2 = a1[1] + *a1;
  a2[1] = v6;
  v7 = (a3 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
  v8 = &a1[v7];
  v9 = (double *)&a2[v7];
  if ( (a3 & 1) == 0 )
    _mm_storel_ps(v9, _mm_mul_ps((__m128)*(unsigned __int64 *)v8, (__m128)xmmword_1801B72C0));
  v10 = &a1[2 * a3 - 4];
  v11 = (__int64)&a2[2 * a3 - 4];
  v12 = (unsigned __int64 *)(a1 + 2);
  v13 = (double *)(a2 + 2);
  while ( 1 )
  {
    v14 = _mm_movelh_ps((__m128)*v12, (__m128)v12[1]);
    v15 = _mm_xor_ps(
            _mm_movelh_ps((__m128)*((unsigned __int64 *)v10 + 1), (__m128)*(unsigned __int64 *)v10),
            (__m128)xmmword_1801B72B0);
    v16 = _mm_sub_ps(v14, v15);
    v17 = _mm_add_ps(v14, v15);
    v18 = _mm_mul_ps(_mm_moveldup_ps(*a4), v16);
    v19 = _mm_sub_ps(
            _mm_mul_ps(_mm_movehdup_ps(*a4), v16),
            _mm_xor_ps(_mm_shuffle_ps(v18, v18, 177), (__m128)xmmword_1801B72B0));
    v20 = _mm_add_ps(v17, v19);
    v21 = _mm_sub_ps(_mm_xor_ps(v17, (__m128)xmmword_1801B72B0), _mm_xor_ps(v19, (__m128)xmmword_1801B72B0));
    _mm_storel_ps(v13, v20);
    _mm_storel_ps((double *)(v11 + 8), v21);
    ++a4;
    v12 += 2;
    v10 -= 4;
    v13 += 2;
    v11 -= 16;
    if ( (__int64)v12 >= (__int64)v8 )
      break;
    _mm_storeh_ps(v13 - 1, v20);
    _mm_storeh_ps((double *)(v11 + 16), v21);
  }
  if ( (__int64)v12 <= (__int64)v8 )
  {
    _mm_storeh_ps(v13 - 1, v20);
    _mm_storeh_ps((double *)(v11 + 16), v21);
  }
  return result;
}

```

## disassembly

```asm
0x18005ee30  push    rbx
0x18005ee31  push    rsi
0x18005ee32  push    rdi
0x18005ee33  push    rbp
0x18005ee34  push    r12
0x18005ee36  push    r13
0x18005ee38  sub     rsp, 28h
0x18005ee3c  movdqa  [rsp+58h+var_58], xmm7
0x18005ee41  movdqa  [rsp+58h+var_48], xmm6
0x18005ee47  mov     rdi, rcx
0x18005ee4a  mov     rsi, rdx
0x18005ee4d  mov     rdx, r8
0x18005ee50  mov     rcx, r9
0x18005ee53  mov     r12, rdi
0x18005ee56  mov     rbx, rsi
0x18005ee59  mov     rax, rdx
0x18005ee5c  mov     r11, rcx
0x18005ee5f  movss   xmm0, dword ptr [r12]
0x18005ee65  movss   xmm1, dword ptr [r12+4]
0x18005ee6c  addss   xmm1, xmm0
0x18005ee70  subss   xmm0, dword ptr [r12+4]
0x18005ee77  movss   dword ptr [rbx], xmm1
0x18005ee7b  movss   dword ptr [rbx+4], xmm0
0x18005ee80  lea     rbp, [rax+1]
0x18005ee84  and     rbp, 0FFFFFFFFFFFFFFFEh
0x18005ee88  lea     r10, [r12+rbp*4]
0x18005ee8c  lea     rbp, [rbx+rbp*4]
0x18005ee90  test    rax, 1
0x18005ee96  jnz     short loc_18005EEA8
0x18005ee98  movsd   xmm0, qword ptr [r10]
0x18005ee9d  mulps   xmm0, cs:xmmword_1801B72C0
0x18005eea4  movlps  qword ptr [rbp+0], xmm0
0x18005eea8  lea     rbp, ds:0[rax*2]
0x18005eeb0  lea     r13, [r12+rbp*4-10h]
0x18005eeb5  lea     rbp, [rbx+rbp*4-10h]
0x18005eeba  add     r12, 8
0x18005eebe  add     rbx, 8
0x18005eec2  jmp     short loc_18005EED8
0x18005eed0  movhps  qword ptr [rbx-8], xmm1
0x18005eed4  movhps  qword ptr [rbp+10h], xmm2
0x18005eed8  movsd   xmm0, qword ptr [r12]
0x18005eede  movsd   xmm7, qword ptr [r12+8]
0x18005eee5  movlhps xmm0, xmm7
0x18005eee8  movsd   xmm1, qword ptr [r13+8]
0x18005eeee  movsd   xmm7, qword ptr [r13+0]
0x18005eef4  movlhps xmm1, xmm7
0x18005eef7  movaps  xmm2, xmm0
0x18005eefa  xorps   xmm1, cs:xmmword_1801B72B0
0x18005ef01  subps   xmm0, xmm1
0x18005ef04  addps   xmm2, xmm1
0x18005ef07  movsldup xmm3, xmmword ptr [r11]
0x18005ef0c  movshdup xmm4, xmmword ptr [r11]
0x18005ef11  mulps   xmm3, xmm0
0x18005ef14  mulps   xmm4, xmm0
0x18005ef17  shufps  xmm3, xmm3, 0B1h
0x18005ef1b  xorps   xmm3, cs:xmmword_1801B72B0
0x18005ef22  subps   xmm4, xmm3
0x18005ef25  movaps  xmm1, xmm2
0x18005ef28  addps   xmm1, xmm4
0x18005ef2b  xorps   xmm2, cs:xmmword_1801B72B0
0x18005ef32  xorps   xmm4, cs:xmmword_1801B72B0
0x18005ef39  subps   xmm2, xmm4
0x18005ef3c  movlps  qword ptr [rbx], xmm1
0x18005ef3f  movlps  qword ptr [rbp+8], xmm2
0x18005ef43  add     r11, 10h
0x18005ef47  add     r12, 10h
0x18005ef4b  sub     r13, 10h
0x18005ef4f  add     rbx, 10h
0x18005ef53  sub     rbp, 10h
0x18005ef57  cmp     r12, r10
0x18005ef5a  jl      loc_18005EED0
0x18005ef60  cmp     r12, r10
0x18005ef63  jg      short loc_18005EF6D
0x18005ef65  movhps  qword ptr [rbx-8], xmm1
0x18005ef69  movhps  qword ptr [rbp+10h], xmm2
0x18005ef6d  movdqa  xmm7, [rsp+58h+var_58]
0x18005ef72  movdqa  xmm6, [rsp+58h+var_48]
0x18005ef78  add     rsp, 28h
0x18005ef7c  pop     r13
0x18005ef7e  pop     r12
0x18005ef80  pop     rbp
0x18005ef81  pop     rdi
0x18005ef82  pop     rsi
0x18005ef83  pop     rbx
0x18005ef84  retn
```
