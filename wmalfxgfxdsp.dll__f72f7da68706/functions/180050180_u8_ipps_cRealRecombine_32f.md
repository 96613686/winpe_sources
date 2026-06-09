# u8_ipps_cRealRecombine_32f

- ea: `0x180050180`
- end: `0x1800502bd`
- name: `u8_ipps_cRealRecombine_32f`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001af50`
- `0x18001b150`

## callees

- `0x180050180`

## pseudocode

```c
void __fastcall u8_ipps_cRealRecombine_32f(__int64 a1, __int64 a2, __int64 a3, __m128 *a4)
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
0x180050180  push    rsi
0x180050181  push    rdi
0x180050182  push    r12
0x180050184  push    r13
0x180050186  sub     rsp, 28h
0x18005018a  movdqa  [rsp+48h+var_48], xmm7
0x18005018f  movdqa  [rsp+48h+var_38], xmm6
0x180050195  mov     rdi, rcx
0x180050198  mov     rsi, rdx
0x18005019b  mov     rdx, r8
0x18005019e  mov     rcx, r9
0x1800501a1  mov     r12, rdi
0x1800501a4  mov     r11, rcx
0x1800501a7  lea     r10, [r12+rsi*4]
0x1800501ab  lea     r13, [r12+rsi*8]
0x1800501af  jmp     short loc_1800501CA
0x1800501c0  movhps  qword ptr [r12], xmm0
0x1800501c5  movhps  qword ptr [r13+0], xmm5
0x1800501ca  movsd   xmm0, qword ptr [r12+8]
0x1800501d1  movsd   xmm7, qword ptr [r12+10h]
0x1800501d8  movlhps xmm0, xmm7
0x1800501db  movaps  xmm1, xmm0
0x1800501de  movsd   xmm2, qword ptr [r12+18h]
0x1800501e5  movsd   xmm7, qword ptr [r12+20h]
0x1800501ec  movlhps xmm2, xmm7
0x1800501ef  shufps  xmm0, xmm2, 88h
0x1800501f3  shufps  xmm1, xmm2, 0DDh
0x1800501f7  movsd   xmm3, qword ptr [r13-8]
0x1800501fd  movsd   xmm7, qword ptr [r13-10h]
0x180050203  movlhps xmm3, xmm7
0x180050206  movaps  xmm4, xmm3
0x180050209  movsd   xmm5, qword ptr [r13-18h]
0x18005020f  movsd   xmm7, qword ptr [r13-20h]
0x180050215  movlhps xmm5, xmm7
0x180050218  shufps  xmm3, xmm5, 88h
0x18005021c  shufps  xmm4, xmm5, 0DDh
0x180050220  movaps  xmm2, xmm0
0x180050223  subps   xmm0, xmm3
0x180050226  movaps  xmm6, xmmword ptr [r11]
0x18005022a  movaps  xmm5, xmm4
0x18005022d  addps   xmm4, xmm1
0x180050230  mulps   xmm6, xmm0
0x180050233  movaps  xmm7, xmmword ptr [r11+10h]
0x180050238  mulps   xmm0, xmm7
0x18005023b  mulps   xmm7, xmm4
0x18005023e  mulps   xmm4, xmmword ptr [r11]
0x180050242  subps   xmm7, xmm6
0x180050245  addps   xmm4, xmm0
0x180050248  movaps  xmm6, xmm7
0x18005024b  subps   xmm7, xmm5
0x18005024e  addps   xmm3, xmm4
0x180050251  subps   xmm2, xmm4
0x180050254  movaps  xmm0, xmm3
0x180050257  add     r11, 20h ; ' '
0x18005025b  unpcklps xmm3, xmm7
0x18005025e  subps   xmm6, xmm1
0x180050261  movlps  qword ptr [r12+8], xmm3
0x180050267  movhps  qword ptr [r12+10h], xmm3
0x18005026d  unpckhps xmm0, xmm7
0x180050270  movlps  qword ptr [r12+18h], xmm0
0x180050276  add     r12, 20h ; ' '
0x18005027a  movaps  xmm5, xmm2
0x18005027d  unpcklps xmm2, xmm6
0x180050280  movlps  qword ptr [r13-8], xmm2
0x180050285  movhps  qword ptr [r13-10h], xmm2
0x18005028a  unpckhps xmm5, xmm6
0x18005028d  movlps  qword ptr [r13-18h], xmm5
0x180050292  sub     r13, 20h ; ' '
0x180050296  cmp     r12, r10
0x180050299  jnz     loc_1800501C0
0x18005029f  xor     dword ptr [r10+4], 80000000h
0x1800502a7  movdqa  xmm7, [rsp+48h+var_48]
0x1800502ac  movdqa  xmm6, [rsp+48h+var_38]
0x1800502b2  add     rsp, 28h
0x1800502b6  pop     r13
0x1800502b8  pop     r12
0x1800502ba  pop     rdi
0x1800502bb  pop     rsi
0x1800502bc  retn
```
