# m7_ipps_cRealRecombine_32f

- ea: `0x180039d90`
- end: `0x180039ecd`
- name: `m7_ipps_cRealRecombine_32f`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019cb0`
- `0x180019eb0`

## callees

- `0x180039d90`

## pseudocode

```c
void __fastcall m7_ipps_cRealRecombine_32f(__int64 a1, __int64 a2, __int64 a3, __m128 *a4)
{
  __int64 v4; // r12
  __int64 v6; // r10
  double *i; // r13
  __m128 v8; // xmm1
  __m128 v9; // xmm2
  __m128 v10; // xmm0
  __m128 v11; // xmm1
  __m128 v12; // xmm4
  __m128 v13; // xmm5
  __m128 v14; // xmm3
  __m128 v15; // xmm2
  __m128 v16; // xmm0
  __m128 v17; // xmm5
  __m128 v18; // xmm4
  __m128 v19; // xmm6
  __m128 v20; // xmm7
  __m128 v21; // xmm0
  __m128 v22; // xmm7
  __m128 v23; // xmm4
  __m128 v24; // xmm6
  __m128 v25; // xmm7
  __m128 v26; // xmm0
  __m128 v27; // xmm3
  __m128 v28; // xmm6
  __m128 v29; // xmm0
  __m128 v30; // xmm5
  __m128 v31; // xmm2
  __m128 v32; // xmm5

  v4 = a1;
  v6 = a1 + 4 * a2;
  for ( i = (double *)(a1 + 8 * a2); ; _mm_storeh_ps(i, v32) )
  {
    v8 = _mm_movelh_ps((__m128)*(unsigned __int64 *)(v4 + 8), (__m128)*(unsigned __int64 *)(v4 + 16));
    v9 = _mm_movelh_ps((__m128)*(unsigned __int64 *)(v4 + 24), (__m128)*(unsigned __int64 *)(v4 + 32));
    v10 = _mm_shuffle_ps(v8, v9, 136);
    v11 = _mm_shuffle_ps(v8, v9, 221);
    v12 = _mm_movelh_ps((__m128)*((unsigned __int64 *)i - 1), (__m128)*((unsigned __int64 *)i - 2));
    v13 = _mm_movelh_ps((__m128)*((unsigned __int64 *)i - 3), (__m128)*((unsigned __int64 *)i - 4));
    v14 = _mm_shuffle_ps(v12, v13, 136);
    v15 = v10;
    v16 = _mm_sub_ps(v10, v14);
    v17 = _mm_shuffle_ps(v12, v13, 221);
    v18 = _mm_add_ps(v17, v11);
    v19 = _mm_mul_ps(*a4, v16);
    v20 = a4[1];
    v21 = _mm_mul_ps(v16, v20);
    v22 = _mm_mul_ps(v20, v18);
    v23 = _mm_add_ps(_mm_mul_ps(v18, *a4), v21);
    v24 = _mm_sub_ps(v22, v19);
    v25 = _mm_sub_ps(v24, v17);
    v26 = _mm_add_ps(v14, v23);
    a4 += 2;
    v27 = _mm_unpacklo_ps(v26, v25);
    v28 = _mm_sub_ps(v24, v11);
    _mm_storel_ps((double *)(v4 + 8), v27);
    _mm_storeh_ps((double *)(v4 + 16), v27);
    v29 = _mm_unpackhi_ps(v26, v25);
    _mm_storel_ps((double *)(v4 + 24), v29);
    v4 += 32;
    v30 = _mm_sub_ps(v15, v23);
    v31 = _mm_unpacklo_ps(v30, v28);
    _mm_storel_ps(i - 1, v31);
    _mm_storeh_ps(i - 2, v31);
    v32 = _mm_unpackhi_ps(v30, v28);
    _mm_storel_ps(i - 3, v32);
    i -= 4;
    if ( v4 == v6 )
      break;
    _mm_storeh_ps((double *)v4, v29);
  }
  *(_DWORD *)(v6 + 4) ^= 0x80000000;
}

```

## disassembly

```asm
0x180039d90  push    rsi
0x180039d91  push    rdi
0x180039d92  push    r12
0x180039d94  push    r13
0x180039d96  sub     rsp, 28h
0x180039d9a  movdqa  [rsp+48h+var_48], xmm7
0x180039d9f  movdqa  [rsp+48h+var_38], xmm6
0x180039da5  mov     rdi, rcx
0x180039da8  mov     rsi, rdx
0x180039dab  mov     rdx, r8
0x180039dae  mov     rcx, r9
0x180039db1  mov     r12, rdi
0x180039db4  mov     r11, rcx
0x180039db7  lea     r10, [r12+rsi*4]
0x180039dbb  lea     r13, [r12+rsi*8]
0x180039dbf  jmp     short loc_180039DDA
0x180039dd0  movhps  qword ptr [r12], xmm0
0x180039dd5  movhps  qword ptr [r13+0], xmm5
0x180039dda  movsd   xmm0, qword ptr [r12+8]
0x180039de1  movsd   xmm7, qword ptr [r12+10h]
0x180039de8  movlhps xmm0, xmm7
0x180039deb  movaps  xmm1, xmm0
0x180039dee  movsd   xmm2, qword ptr [r12+18h]
0x180039df5  movsd   xmm7, qword ptr [r12+20h]
0x180039dfc  movlhps xmm2, xmm7
0x180039dff  shufps  xmm0, xmm2, 88h
0x180039e03  shufps  xmm1, xmm2, 0DDh
0x180039e07  movsd   xmm3, qword ptr [r13-8]
0x180039e0d  movsd   xmm7, qword ptr [r13-10h]
0x180039e13  movlhps xmm3, xmm7
0x180039e16  movaps  xmm4, xmm3
0x180039e19  movsd   xmm5, qword ptr [r13-18h]
0x180039e1f  movsd   xmm7, qword ptr [r13-20h]
0x180039e25  movlhps xmm5, xmm7
0x180039e28  shufps  xmm3, xmm5, 88h
0x180039e2c  shufps  xmm4, xmm5, 0DDh
0x180039e30  movaps  xmm2, xmm0
0x180039e33  subps   xmm0, xmm3
0x180039e36  movaps  xmm6, xmmword ptr [r11]
0x180039e3a  movaps  xmm5, xmm4
0x180039e3d  addps   xmm4, xmm1
0x180039e40  mulps   xmm6, xmm0
0x180039e43  movaps  xmm7, xmmword ptr [r11+10h]
0x180039e48  mulps   xmm0, xmm7
0x180039e4b  mulps   xmm7, xmm4
0x180039e4e  mulps   xmm4, xmmword ptr [r11]
0x180039e52  subps   xmm7, xmm6
0x180039e55  addps   xmm4, xmm0
0x180039e58  movaps  xmm6, xmm7
0x180039e5b  subps   xmm7, xmm5
0x180039e5e  addps   xmm3, xmm4
0x180039e61  subps   xmm2, xmm4
0x180039e64  movaps  xmm0, xmm3
0x180039e67  add     r11, 20h ; ' '
0x180039e6b  unpcklps xmm3, xmm7
0x180039e6e  subps   xmm6, xmm1
0x180039e71  movlps  qword ptr [r12+8], xmm3
0x180039e77  movhps  qword ptr [r12+10h], xmm3
0x180039e7d  unpckhps xmm0, xmm7
0x180039e80  movlps  qword ptr [r12+18h], xmm0
0x180039e86  add     r12, 20h ; ' '
0x180039e8a  movaps  xmm5, xmm2
0x180039e8d  unpcklps xmm2, xmm6
0x180039e90  movlps  qword ptr [r13-8], xmm2
0x180039e95  movhps  qword ptr [r13-10h], xmm2
0x180039e9a  unpckhps xmm5, xmm6
0x180039e9d  movlps  qword ptr [r13-18h], xmm5
0x180039ea2  sub     r13, 20h ; ' '
0x180039ea6  cmp     r12, r10
0x180039ea9  jnz     loc_180039DD0
0x180039eaf  xor     dword ptr [r10+4], 80000000h
0x180039eb7  movdqa  xmm7, [rsp+48h+var_48]
0x180039ebc  movdqa  xmm6, [rsp+48h+var_38]
0x180039ec2  add     rsp, 28h
0x180039ec6  pop     r13
0x180039ec8  pop     r12
0x180039eca  pop     rdi
0x180039ecb  pop     rsi
0x180039ecc  retn
```
