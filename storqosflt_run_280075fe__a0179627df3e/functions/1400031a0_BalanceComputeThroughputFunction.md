# BalanceComputeThroughputFunction

- ea: `0x1400031a0`
- end: `0x14000344e`
- name: `BalanceComputeThroughputFunction`
- size: `686`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001380`
- `0x140002bf0`

## callees

- `0x1400031a0`
- `0x1400045b0`

## pseudocode

```c
unsigned __int64 __fastcall BalanceComputeThroughputFunction(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // r10
  double v5; // xmm8_8
  double v6; // xmm7_8
  unsigned int v7; // r11d
  unsigned int i; // edi
  __int64 v9; // r9
  double j; // xmm6_8
  double v11; // xmm3_8
  double v12; // xmm3_8
  double v13; // xmm4_8
  double v14; // xmm6_8
  __int64 v15; // r10
  double v16; // xmm0_8
  double v17; // xmm1_8
  double v18; // xmm1_8
  unsigned __int64 v19; // rcx
  unsigned __int64 result; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax

  v3 = a3;
  v4 = a1;
  if ( a2 < 0 )
  {
    v21 = a2;
    a2 &= 1u;
    v5 = (double)(int)(a2 | (v21 >> 1)) + (double)(int)(a2 | (v21 >> 1));
  }
  else
  {
    v5 = (double)(int)a2;
  }
  v6 = *(double *)(a1 + 1000);
  if ( v6 <= 0.0 )
    v6 = DOUBLE_1_0;
  v7 = *(_DWORD *)(a1 + 992);
  for ( i = 0; i < 0x28; ++i )
  {
    v9 = 0;
    for ( j = 0.0; (unsigned int)v9 < v7; v9 = (unsigned int)(v9 + 1) )
    {
      a2 = (unsigned int)v9;
      a1 = *(_QWORD *)(v4 + 16 * (v9 + 2));
      if ( a1 )
      {
        a2 = 2LL * (unsigned int)v9;
        a3 = *(_QWORD *)(v4 + 16LL * (unsigned int)v9 + 40);
        if ( a3 )
        {
          if ( a1 < 0 )
          {
            a1 = *(_QWORD *)(v4 + 16 * (v9 + 2)) & 1LL;
            v22 = a1 | (*(_QWORD *)(v4 + 16 * (v9 + 2)) >> 1);
            v11 = (double)(int)v22 + (double)(int)v22;
          }
          else
          {
            v11 = (double)(int)a1;
          }
          v12 = v11 * 0.0009765625;
          if ( a3 < 0 )
          {
            a3 = *(_QWORD *)(v4 + 16LL * (unsigned int)v9 + 40) & 1LL;
            v23 = a3 | (*(_QWORD *)(v4 + 16LL * (unsigned int)v9 + 40) >> 1);
            v13 = (double)(int)v23 + (double)(int)v23;
          }
          else
          {
            v13 = (double)(int)a3;
          }
          j = j
            + COERCE_DOUBLE(
                COERCE_UNSIGNED_INT64(((v5 - v13) * v12 - v13 * v6) / (v12 + v6) * (v12 / (v12 + v6) + v12 / (v12 + v6)))
              ^ _xmm)
            * (v5
             / (v12 + v6));
        }
      }
    }
    v14 = j * v6 / (v5 * v5);
    if ( v14 == 0.0 )
      break;
    v6 = fmax(0.5, v6 - v14 * 0.5);
  }
  *(double *)(v4 + 1000) = v6;
  v16 = (BalanceSqrt(a1, a2, a3, v9) - 1.0) * v6 * 0.5;
  *(double *)(v15 + 1008) = v16;
  if ( v3 < 0 )
    v17 = (double)(int)(v3 & 1 | ((unsigned __int64)v3 >> 1)) + (double)(int)(v3 & 1 | ((unsigned __int64)v3 >> 1));
  else
    v17 = (double)(int)v3;
  v18 = v17 * v16;
  v19 = 0;
  if ( v18 >= 9.223372036854776e18 )
  {
    v18 = v18 - 9.223372036854776e18;
    if ( v18 < 9.223372036854776e18 )
      v19 = 0x8000000000000000uLL;
  }
  result = v19 + (unsigned int)(int)v18;
  *(_QWORD *)(v15 + 1016) = result;
  return result;
}

```

## disassembly

```asm
0x1400031a0  mov     rax, rsp
0x1400031a3  mov     [rax+8], rbx
0x1400031a7  push    rdi
0x1400031a8  sub     rsp, 0A0h
0x1400031af  movaps  xmmword ptr [rax-18h], xmm6
0x1400031b3  mov     rbx, r8
0x1400031b6  movaps  xmmword ptr [rax-28h], xmm7
0x1400031ba  mov     r10, rcx
0x1400031bd  movaps  xmmword ptr [rax-38h], xmm8
0x1400031c2  xorps   xmm8, xmm8
0x1400031c6  movaps  xmmword ptr [rax-48h], xmm9
0x1400031cb  movaps  xmmword ptr [rax-58h], xmm10
0x1400031d0  movaps  xmmword ptr [rax-68h], xmm11
0x1400031d5  movaps  xmmword ptr [rax-78h], xmm12
0x1400031da  movaps  [rsp+0A8h+var_88], xmm13
0x1400031e0  test    rdx, rdx
0x1400031e3  js      loc_1400033DB
0x1400031e9  cvtsi2sd xmm8, rdx
0x1400031ee  movsd   xmm7, qword ptr [rcx+3E8h]
0x1400031f6  xorps   xmm11, xmm11
0x1400031fa  comisd  xmm7, xmm11
0x1400031ff  movsd   xmm12, cs:__real@3ff0000000000000
0x140003208  jbe     loc_1400033F6
0x14000320e  mov     r11d, [rcx+3E0h]
0x140003215  movaps  xmm13, xmm8
0x140003219  movsd   xmm10, cs:__real@3fe0000000000000
0x140003222  xor     edi, edi
0x140003224  movsd   xmm9, cs:__xmm@80000000000000008000000000000000
0x14000322d  movsd   xmm5, cs:__real@3f50000000000000
0x140003235  mulsd   xmm13, xmm8
0x14000323a  nop     word ptr [rax+rax+00h]
0x140003240  xor     r9d, r9d
0x140003243  movaps  xmm6, xmm11
0x140003247  test    r11d, r11d
0x14000324a  jz      loc_1400032E4
0x140003250  lea     rax, [r9+2]
0x140003254  mov     edx, r9d
0x140003257  add     rax, rax
0x14000325a  mov     rcx, [r10+rax*8]
0x14000325e  test    rcx, rcx
0x140003261  jz      short loc_1400032D8
0x140003263  add     rdx, rdx
0x140003266  mov     r8, [r10+rdx*8+28h]
0x14000326b  test    r8, r8
0x14000326e  jz      short loc_1400032D8
0x140003270  xorps   xmm3, xmm3
0x140003273  test    rcx, rcx
0x140003276  js      loc_1400033FF
0x14000327c  cvtsi2sd xmm3, rcx
0x140003281  mulsd   xmm3, xmm5
0x140003285  xorps   xmm4, xmm4
0x140003288  test    r8, r8
0x14000328b  js      loc_140003419
0x140003291  cvtsi2sd xmm4, r8
0x140003296  movaps  xmm0, xmm3
0x140003299  movaps  xmm1, xmm8
0x14000329d  subsd   xmm1, xmm4
0x1400032a1  movaps  xmm2, xmm3
0x1400032a4  addsd   xmm2, xmm7
0x1400032a8  mulsd   xmm4, xmm7
0x1400032ac  mulsd   xmm1, xmm3
0x1400032b0  divsd   xmm0, xmm2
0x1400032b4  subsd   xmm1, xmm4
0x1400032b8  addsd   xmm0, xmm0
0x1400032bc  divsd   xmm1, xmm2
0x1400032c0  mulsd   xmm1, xmm0
0x1400032c4  movaps  xmm0, xmm8
0x1400032c8  divsd   xmm0, xmm2
0x1400032cc  xorps   xmm1, xmm9
0x1400032d0  mulsd   xmm1, xmm0
0x1400032d4  addsd   xmm6, xmm1
0x1400032d8  inc     r9d
0x1400032db  cmp     r9d, r11d
0x1400032de  jb      loc_140003250
0x1400032e4  mulsd   xmm6, xmm7
0x1400032e8  divsd   xmm6, xmm13
0x1400032ed  ucomisd xmm6, xmm11
0x1400032f2  jp      short loc_1400032F6
0x1400032f4  jz      short loc_140003315
0x1400032f6  movaps  xmm0, xmm7
0x1400032f9  mulsd   xmm6, xmm10
0x1400032fe  inc     edi
0x140003300  movaps  xmm7, xmm10
0x140003304  subsd   xmm0, xmm6
0x140003308  maxsd   xmm7, xmm0
0x14000330c  cmp     edi, 28h ; '('
0x14000330f  jb      loc_140003240
0x140003315  movsd   xmm0, cs:__real@4010000000000000
0x14000331d  movaps  xmm1, xmm7
0x140003320  mulsd   xmm1, cs:__real@3f747ae147ae147b
0x140003328  movsd   qword ptr [r10+3E8h], xmm7
0x140003331  divsd   xmm0, xmm1
0x140003335  addsd   xmm0, xmm12
0x14000333a  call    BalanceSqrt
0x14000333f  subsd   xmm0, xmm12
0x140003344  xorps   xmm1, xmm1
0x140003347  mulsd   xmm0, xmm7
0x14000334b  mulsd   xmm0, xmm10
0x140003350  movsd   qword ptr [r10+3F0h], xmm0
0x140003359  test    rbx, rbx
0x14000335c  js      loc_140003434
0x140003362  cvtsi2sd xmm1, rbx
0x140003367  mulsd   xmm1, xmm0
0x14000336b  xor     ecx, ecx
0x14000336d  movsd   xmm0, cs:__real@43e0000000000000
0x140003375  comisd  xmm1, xmm0
0x140003379  jb      short loc_140003392
0x14000337b  subsd   xmm1, xmm0
0x14000337f  comisd  xmm1, xmm0
0x140003383  jnb     short loc_140003392
0x140003385  mov     rax, 8000000000000000h
0x14000338f  mov     rcx, rax
0x140003392  lea     r11, [rsp+0A8h+var_8]
0x14000339a  mov     rbx, [r11+10h]
0x14000339e  movaps  xmm6, xmmword ptr [r11-10h]
0x1400033a3  movaps  xmm7, xmmword ptr [r11-20h]
0x1400033a8  movaps  xmm8, xmmword ptr [r11-30h]
0x1400033ad  movaps  xmm9, xmmword ptr [r11-40h]
0x1400033b2  movaps  xmm10, xmmword ptr [r11-50h]
0x1400033b7  movaps  xmm11, xmmword ptr [r11-60h]
0x1400033bc  movaps  xmm12, xmmword ptr [r11-70h]
0x1400033c1  movaps  xmm13, xmmword ptr [r11-80h]
0x1400033c6  cvttsd2si rax, xmm1
0x1400033cb  add     rax, rcx
0x1400033ce  mov     [r10+3F8h], rax
0x1400033d5  mov     rsp, r11
0x1400033d8  pop     rdi
0x1400033d9  retn
0x1400033db  mov     rax, rdx
0x1400033de  and     edx, 1
0x1400033e1  shr     rax, 1
0x1400033e4  or      rax, rdx
0x1400033e7  cvtsi2sd xmm8, rax
0x1400033ec  addsd   xmm8, xmm8
0x1400033f1  jmp     loc_1400031EE
0x1400033f6  movaps  xmm7, xmm12
0x1400033fa  jmp     loc_14000320E
0x1400033ff  mov     rax, rcx
0x140003402  and     ecx, 1
0x140003405  shr     rax, 1
0x140003408  or      rax, rcx
0x14000340b  cvtsi2sd xmm3, rax
0x140003410  addsd   xmm3, xmm3
0x140003414  jmp     loc_140003281
0x140003419  mov     rax, r8
0x14000341c  and     r8d, 1
0x140003420  shr     rax, 1
0x140003423  or      rax, r8
0x140003426  cvtsi2sd xmm4, rax
0x14000342b  addsd   xmm4, xmm4
0x14000342f  jmp     loc_140003296
0x140003434  mov     rax, rbx
0x140003437  and     ebx, 1
0x14000343a  shr     rax, 1
0x14000343d  or      rax, rbx
0x140003440  cvtsi2sd xmm1, rax
0x140003445  addsd   xmm1, xmm1
0x140003449  jmp     loc_140003367
```
