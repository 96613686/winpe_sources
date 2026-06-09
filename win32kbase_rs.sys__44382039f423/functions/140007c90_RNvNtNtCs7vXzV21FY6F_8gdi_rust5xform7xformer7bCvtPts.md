# _RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer7bCvtPts

- ea: `0x140007c90`
- end: `0x140008020`
- name: `_RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer7bCvtPts`
- size: `912`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002000`
- `0x140002150`
- `0x140004890`

## callees

- `0x140007c90`
- `0x140008da0`
- `0x140017a10`
- `0x140018650`

## pseudocode

```c
char __fastcall RNvNtNtCs7vXzV21FY6F_8gdi_rust5xform7xformer7bCvtPts(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  __int64 v6; // rdi
  int v7; // eax
  int v8; // eax
  int v9; // ecx
  __int64 j; // rdx
  int v11; // r8d
  bool v12; // of
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  int v17; // eax
  int v18; // ecx
  __int64 i; // rdx
  int v20; // r8d
  int v21; // r8d
  int v22; // r8d
  int v23; // r8d
  int v24; // ebx
  int v25; // ebp
  __m128 v26; // xmm6
  __m128 v27; // xmm7
  __int64 v28; // r14
  __m128 v29; // xmm0
  __m128 v30; // xmm1
  __m128 v31; // xmm0
  int v32; // eax
  int v33; // eax
  float v34; // xmm6_4
  float v35; // xmm7_4
  int v36; // ebx
  int v37; // ebp
  __int64 v38; // r14
  float v39; // xmm1_4
  int v40; // eax
  int v41; // eax
  __int64 v43; // [rsp+0h] [rbp-A8h] BYREF
  int v44; // [rsp+24h] [rbp-84h]
  int v45; // [rsp+28h] [rbp-80h] BYREF
  int v46; // [rsp+2Ch] [rbp-7Ch] BYREF
  float v47; // [rsp+30h] [rbp-78h] BYREF
  float v48; // [rsp+34h] [rbp-74h] BYREF
  __int64 v49; // [rsp+38h] [rbp-70h]

  v45 = 0;
  v46 = 0;
  if ( a3 < a5 )
    RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(
      (__int64)anon_d052ab7a191f147c7505ce516cc0d814_0_llvm_10903518121862351502,
      69,
      (__int64)&off_14001B1D0);
  v6 = a2;
  v7 = *(_DWORD *)(a1 + 32) & 0xB;
  LOBYTE(a2) = 1;
  v44 = a2;
  if ( v7 > 7 )
  {
    if ( v7 != 8 )
    {
      if ( v7 != 9 )
      {
        if ( v7 == 11 && a5 )
        {
          v17 = *(_DWORD *)(a1 + 24);
          v18 = *(_DWORD *)(a1 + 28);
          LOBYTE(a2) = 1;
          v44 = a2;
          for ( i = 0; i != a5; ++i )
          {
            while ( 1 )
            {
              v20 = 16 * *(_DWORD *)(v6 + 8 * i);
              v12 = __OFADD__(v17, v20);
              v21 = v17 + v20;
              if ( v12 )
                v44 = 0;
              *(_DWORD *)(a4 + 8 * i) = v21;
              v22 = 16 * *(_DWORD *)(v6 + 8 * i + 4);
              v12 = __OFADD__(v18, v22);
              v23 = v18 + v22;
              if ( v12 )
                break;
              *(_DWORD *)(a4 + 8 * i++ + 4) = v23;
              if ( a5 == i )
                goto LABEL_42;
            }
            v44 = 0;
            *(_DWORD *)(a4 + 8 * i + 4) = v23;
          }
        }
        goto LABEL_42;
      }
      goto LABEL_34;
    }
    goto LABEL_26;
  }
  if ( !v7 )
  {
LABEL_26:
    if ( !a5 )
      goto LABEL_42;
    v24 = *(_DWORD *)(a1 + 24);
    v25 = *(_DWORD *)(a1 + 28);
    v26 = _mm_shuffle_ps(_mm_movelh_ps((__m128)*(unsigned int *)(a1 + 8), *(__m128 *)a1), *(__m128 *)a1, 226);
    v27 = _mm_shuffle_ps(
            _mm_movelh_ps((__m128)*(unsigned int *)(a1 + 12), *(__m128 *)(a1 + 4)),
            *(__m128 *)(a1 + 4),
            226);
    LOBYTE(v7) = 1;
    v44 = v7;
    v28 = 0;
    while ( 1 )
    {
      v29 = _mm_cvtepi32_ps((__m128i)*(unsigned __int64 *)(v6 + 8 * v28));
      v30 = _mm_mul_ps(v26, v29);
      v48 = _mm_movehdup_ps(v30).m128_f32[0] + v30.m128_f32[0];
      v31 = _mm_mul_ps(v29, v27);
      v47 = _mm_movehdup_ps(v31).m128_f32[0] + v31.m128_f32[0];
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v48, &v45);
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v47, &v46);
      v32 = v24 + v45;
      if ( __OFADD__(v24, v45) )
      {
        v44 = 0;
        *(_DWORD *)(a4 + 8 * v28) = v32;
        v33 = v25 + v46;
        if ( __OFADD__(v25, v46) )
LABEL_33:
          v44 = 0;
      }
      else
      {
        *(_DWORD *)(a4 + 8 * v28) = v32;
        v33 = v25 + v46;
        if ( __OFADD__(v25, v46) )
          goto LABEL_33;
      }
      *(_DWORD *)(a4 + 8 * v28++ + 4) = v33;
      if ( a5 == v28 )
        goto LABEL_42;
    }
  }
  if ( v7 == 1 )
  {
LABEL_34:
    if ( !a5 )
      goto LABEL_42;
    v34 = *(float *)a1;
    v35 = *(float *)(a1 + 12);
    v36 = *(_DWORD *)(a1 + 24);
    v37 = *(_DWORD *)(a1 + 28);
    LOBYTE(v7) = 1;
    v44 = v7;
    v38 = 0;
    while ( 1 )
    {
      v39 = (float)*(int *)(v6 + 8 * v38 + 4) * v35;
      v47 = (float)*(int *)(v6 + 8 * v38) * v34;
      v48 = v39;
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v47, &v45);
      RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL(&v48, &v46);
      v40 = v36 + v45;
      if ( __OFADD__(v36, v45) )
      {
        v44 = 0;
        *(_DWORD *)(a4 + 8 * v38) = v40;
        v41 = v37 + v46;
        if ( __OFADD__(v37, v46) )
LABEL_41:
          v44 = 0;
      }
      else
      {
        *(_DWORD *)(a4 + 8 * v38) = v40;
        v41 = v37 + v46;
        if ( __OFADD__(v37, v46) )
          goto LABEL_41;
      }
      *(_DWORD *)(a4 + 8 * v38++ + 4) = v41;
      if ( a5 == v38 )
        goto LABEL_42;
    }
  }
  if ( v7 == 3 && a5 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = *(_DWORD *)(a1 + 28);
    LOBYTE(a2) = 1;
    v44 = a2;
    for ( j = 0; a5 != j; ++j )
    {
      v11 = *(_DWORD *)(v6 + 8 * j);
      v12 = __OFADD__(v8, v11);
      v13 = v8 + v11;
      if ( v12 )
      {
        v44 = 0;
        *(_DWORD *)(a4 + 8 * j) = v13;
        v16 = *(_DWORD *)(v6 + 8 * j + 4);
        v12 = __OFADD__(v9, v16);
        v15 = v9 + v16;
        if ( v12 )
LABEL_13:
          v44 = 0;
      }
      else
      {
        *(_DWORD *)(a4 + 8 * j) = v13;
        v14 = *(_DWORD *)(v6 + 8 * j + 4);
        v12 = __OFADD__(v9, v14);
        v15 = v9 + v14;
        if ( v12 )
          goto LABEL_13;
      }
      *(_DWORD *)(a4 + 8 * j + 4) = v15;
    }
  }
LABEL_42:
  if ( _security_cookie != ((unsigned __int64)&v43 ^ v49) )
    JUMPOUT(0x14000801FLL);
  return v44 & 1;
}

```

## disassembly

```asm
0x140007c90  push    r15
0x140007c92  push    r14
0x140007c94  push    r13
0x140007c96  push    r12
0x140007c98  push    rsi
0x140007c99  push    rdi
0x140007c9a  push    rbp
0x140007c9b  push    rbx
0x140007c9c  sub     rsp, 68h
0x140007ca0  movaps  [rsp+0A8h+var_58], xmm7
0x140007ca5  movaps  [rsp+0A8h+var_68], xmm6
0x140007caa  mov     rax, cs:__security_cookie
0x140007cb1  xor     rax, rsp
0x140007cb4  mov     [rsp+0A8h+var_70], rax
0x140007cb9  mov     [rsp+0A8h+var_80], 0
0x140007cc1  mov     [rsp+0A8h+var_7C], 0
0x140007cc9  cmp     r8, [rsp+0A8h+arg_20]
0x140007cd1  jb      loc_140007FFA
0x140007cd7  mov     rsi, r9
0x140007cda  mov     rdi, rdx
0x140007cdd  mov     eax, [rcx+20h]
0x140007ce0  and     eax, 0Bh
0x140007ce3  mov     dl, 1
0x140007ce5  mov     [rsp+0A8h+var_84], edx
0x140007ce9  cmp     eax, 7
0x140007cec  jg      loc_140007D7E
0x140007cf2  test    eax, eax
0x140007cf4  jz      loc_140007E1F
0x140007cfa  cmp     eax, 1
0x140007cfd  jz      loc_140007EFF
0x140007d03  cmp     eax, 3
0x140007d06  jnz     loc_140007FC5
0x140007d0c  cmp     [rsp+0A8h+arg_20], 0
0x140007d15  jz      loc_140007FC5
0x140007d1b  mov     eax, [rcx+18h]
0x140007d1e  mov     ecx, [rcx+1Ch]
0x140007d21  mov     dl, 1
0x140007d23  mov     [rsp+0A8h+var_84], edx
0x140007d27  xor     edx, edx
0x140007d29  nop     dword ptr [rax+00000000h]
0x140007d30  mov     r8d, [rdi+rdx*8]
0x140007d34  add     r8d, eax
0x140007d37  jo      short loc_140007D5E
0x140007d39  mov     [rsi+rdx*8], r8d
0x140007d3d  mov     r8d, [rdi+rdx*8+4]
0x140007d42  add     r8d, ecx
0x140007d45  jo      short loc_140007D74
0x140007d47  mov     [rsi+rdx*8+4], r8d
0x140007d4c  inc     rdx
0x140007d4f  cmp     [rsp+0A8h+arg_20], rdx
0x140007d57  jnz     short loc_140007D30
0x140007d59  jmp     loc_140007FC5
0x140007d5e  mov     [rsp+0A8h+var_84], 0
0x140007d66  mov     [rsi+rdx*8], r8d
0x140007d6a  mov     r8d, [rdi+rdx*8+4]
0x140007d6f  add     r8d, ecx
0x140007d72  jno     short loc_140007D47
0x140007d74  mov     [rsp+0A8h+var_84], 0
0x140007d7c  jmp     short loc_140007D47
0x140007d7e  cmp     eax, 8
0x140007d81  jz      loc_140007E1F
0x140007d87  cmp     eax, 9
0x140007d8a  jz      loc_140007EFF
0x140007d90  cmp     eax, 0Bh
0x140007d93  jnz     loc_140007FC5
0x140007d99  cmp     [rsp+0A8h+arg_20], 0
0x140007da2  jz      loc_140007FC5
0x140007da8  mov     eax, [rcx+18h]
0x140007dab  mov     ecx, [rcx+1Ch]
0x140007dae  mov     dl, 1
0x140007db0  mov     [rsp+0A8h+var_84], edx
0x140007db4  xor     edx, edx
0x140007db6  nop     word ptr [rax+rax+00000000h]
0x140007dc0  mov     r8d, [rdi+rdx*8]
0x140007dc4  shl     r8d, 4
0x140007dc8  add     r8d, eax
0x140007dcb  jo      short loc_140007DF6
0x140007dcd  mov     [rsi+rdx*8], r8d
0x140007dd1  mov     r8d, [rdi+rdx*8+4]
0x140007dd6  shl     r8d, 4
0x140007dda  add     r8d, ecx
0x140007ddd  jo      short loc_140007E00
0x140007ddf  mov     [rsi+rdx*8+4], r8d
0x140007de4  inc     rdx
0x140007de7  cmp     [rsp+0A8h+arg_20], rdx
0x140007def  jnz     short loc_140007DC0
0x140007df1  jmp     loc_140007FC5
0x140007df6  mov     [rsp+0A8h+var_84], 0
0x140007dfe  jmp     short loc_140007DCD
0x140007e00  mov     [rsp+0A8h+var_84], 0
0x140007e08  mov     [rsi+rdx*8+4], r8d
0x140007e0d  inc     rdx
0x140007e10  cmp     [rsp+0A8h+arg_20], rdx
0x140007e18  jnz     short loc_140007DC0
0x140007e1a  jmp     loc_140007FC5
0x140007e1f  cmp     [rsp+0A8h+arg_20], 0
0x140007e28  jz      loc_140007FC5
0x140007e2e  movups  xmm0, xmmword ptr [rcx]
0x140007e31  movups  xmm1, xmmword ptr [rcx+4]
0x140007e35  mov     ebx, [rcx+18h]
0x140007e38  mov     ebp, [rcx+1Ch]
0x140007e3b  movss   xmm6, dword ptr [rcx+8]
0x140007e40  movlhps xmm6, xmm0
0x140007e43  shufps  xmm6, xmm0, 0E2h
0x140007e47  movss   xmm7, dword ptr [rcx+0Ch]
0x140007e4c  movlhps xmm7, xmm1
0x140007e4f  shufps  xmm7, xmm1, 0E2h
0x140007e53  mov     al, 1
0x140007e55  mov     [rsp+0A8h+var_84], eax
0x140007e59  xor     r14d, r14d
0x140007e5c  lea     r15, [rsp+0A8h+var_80]
0x140007e61  lea     r12, [rsp+0A8h+var_78]
0x140007e66  lea     r13, [rsp+0A8h+var_7C]
0x140007e6b  nop     dword ptr [rax+rax+00h]
0x140007e70  movsd   xmm0, qword ptr [rdi+r14*8]
0x140007e76  cvtdq2ps xmm0, xmm0
0x140007e79  movaps  xmm1, xmm6
0x140007e7c  mulps   xmm1, xmm0
0x140007e7f  movshdup xmm2, xmm1
0x140007e83  addss   xmm2, xmm1
0x140007e87  movss   [rsp+0A8h+var_74], xmm2
0x140007e8d  mulps   xmm0, xmm7
0x140007e90  movshdup xmm1, xmm0
0x140007e94  addss   xmm1, xmm0
0x140007e98  movss   [rsp+0A8h+var_78], xmm1
0x140007e9e  lea     rcx, [rsp+0A8h+var_74]
0x140007ea3  mov     rdx, r15
0x140007ea6  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140007eab  mov     rcx, r12
0x140007eae  mov     rdx, r13
0x140007eb1  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140007eb6  mov     eax, [rsp+0A8h+var_80]
0x140007eba  add     eax, ebx
0x140007ebc  jo      short loc_140007EE1
0x140007ebe  mov     [rsi+r14*8], eax
0x140007ec2  mov     eax, [rsp+0A8h+var_7C]
0x140007ec6  add     eax, ebp
0x140007ec8  jo      short loc_140007EF5
0x140007eca  mov     [rsi+r14*8+4], eax
0x140007ecf  inc     r14
0x140007ed2  cmp     [rsp+0A8h+arg_20], r14
0x140007eda  jnz     short loc_140007E70
0x140007edc  jmp     loc_140007FC5
0x140007ee1  mov     [rsp+0A8h+var_84], 0
0x140007ee9  mov     [rsi+r14*8], eax
0x140007eed  mov     eax, [rsp+0A8h+var_7C]
0x140007ef1  add     eax, ebp
0x140007ef3  jno     short loc_140007ECA
0x140007ef5  mov     [rsp+0A8h+var_84], 0
0x140007efd  jmp     short loc_140007ECA
0x140007eff  cmp     [rsp+0A8h+arg_20], 0
0x140007f08  jz      loc_140007FC5
0x140007f0e  movss   xmm6, dword ptr [rcx]
0x140007f12  movss   xmm7, dword ptr [rcx+0Ch]
0x140007f17  mov     ebx, [rcx+18h]
0x140007f1a  mov     ebp, [rcx+1Ch]
0x140007f1d  mov     al, 1
0x140007f1f  mov     [rsp+0A8h+var_84], eax
0x140007f23  xor     r14d, r14d
0x140007f26  lea     r15, [rsp+0A8h+var_80]
0x140007f2b  lea     r12, [rsp+0A8h+var_74]
0x140007f30  lea     r13, [rsp+0A8h+var_7C]
0x140007f35  nop     word ptr [rax+rax+00000000h]
0x140007f40  xorps   xmm0, xmm0
0x140007f43  cvtsi2ss xmm0, dword ptr [rdi+r14*8]
0x140007f49  xorps   xmm1, xmm1
0x140007f4c  cvtsi2ss xmm1, dword ptr [rdi+r14*8+4]
0x140007f53  mulss   xmm0, xmm6
0x140007f57  mulss   xmm1, xmm7
0x140007f5b  movss   [rsp+0A8h+var_78], xmm0
0x140007f61  movss   [rsp+0A8h+var_74], xmm1
0x140007f67  lea     rcx, [rsp+0A8h+var_78]
0x140007f6c  mov     rdx, r15
0x140007f6f  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140007f74  mov     rcx, r12
0x140007f77  mov     rdx, r13
0x140007f7a  call    _RNvMsc_NtCsgPq7HM4PUSd_12gdi_bindings6efloatNtB5_6EFLOAT6bEfToL
0x140007f7f  mov     eax, [rsp+0A8h+var_80]
0x140007f83  add     eax, ebx
0x140007f85  jo      short loc_140007FA7
0x140007f87  mov     [rsi+r14*8], eax
0x140007f8b  mov     eax, [rsp+0A8h+var_7C]
0x140007f8f  add     eax, ebp
0x140007f91  jo      short loc_140007FBB
0x140007f93  mov     [rsi+r14*8+4], eax
0x140007f98  inc     r14
0x140007f9b  cmp     [rsp+0A8h+arg_20], r14
0x140007fa3  jnz     short loc_140007F40
0x140007fa5  jmp     short loc_140007FC5
0x140007fa7  mov     [rsp+0A8h+var_84], 0
0x140007faf  mov     [rsi+r14*8], eax
0x140007fb3  mov     eax, [rsp+0A8h+var_7C]
0x140007fb7  add     eax, ebp
0x140007fb9  jno     short loc_140007F93
0x140007fbb  mov     [rsp+0A8h+var_84], 0
0x140007fc3  jmp     short loc_140007F93
0x140007fc5  mov     rax, [rsp+0A8h+var_70]
0x140007fca  xor     rax, rsp
0x140007fcd  mov     rcx, cs:__security_cookie
0x140007fd4  cmp     rcx, rax
0x140007fd7  jnz     short loc_140008012
0x140007fd9  mov     eax, [rsp+0A8h+var_84]
0x140007fdd  and     al, 1
0x140007fdf  movaps  xmm6, [rsp+0A8h+var_68]
0x140007fe4  movaps  xmm7, [rsp+0A8h+var_58]
0x140007fe9  add     rsp, 68h
0x140007fed  pop     rbx
0x140007fee  pop     rbp
0x140007fef  pop     rdi
0x140007ff0  pop     rsi
0x140007ff1  pop     r12
0x140007ff3  pop     r13
0x140007ff5  pop     r14
0x140007ff7  pop     r15
0x140007ff9  retn
0x140007ffa  lea     rcx, anon_d052ab7a191f147c7505ce516cc0d814_0_llvm_10903518121862351502
0x140008001  lea     r8, off_14001B1D0; "gdi_rust\\src\\xform\\xformer.rs"
0x140008008  mov     edx, 45h ; 'E'
0x14000800d  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x140008012  mov     rcx, [rsp+0A8h+var_70]
0x140008017  xor     rcx, rsp; StackCookie
0x14000801a  call    __security_check_cookie
```
