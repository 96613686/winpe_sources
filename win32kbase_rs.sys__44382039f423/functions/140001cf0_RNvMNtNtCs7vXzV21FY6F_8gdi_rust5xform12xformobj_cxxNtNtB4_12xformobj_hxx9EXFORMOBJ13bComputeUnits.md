# _RNvMNtNtCs7vXzV21FY6F_8gdi_rust5xform12xformobj_cxxNtNtB4_12xformobj_hxx9EXFORMOBJ13bComputeUnits

- ea: `0x140001cf0`
- end: `0x140001f47`
- name: `_RNvMNtNtCs7vXzV21FY6F_8gdi_rust5xform12xformobj_cxxNtNtB4_12xformobj_hxx9EXFORMOBJ13bComputeUnits`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001100`

## callees

- `0x140001cf0`
- `0x140002ea0`
- `0x140008b20`
- `0x140008ef0`
- `0x140009020`
- `0x140017a10`
- `0x140018450`

## pseudocode

```c
char __fastcall RNvMNtNtCs7vXzV21FY6F_8gdi_rust5xform12xformobj_cxxNtNtB4_12xformobj_hxx9EXFORMOBJ13bComputeUnits(
        unsigned int **a1,
        int a2,
        _DWORD *a3,
        float *a4,
        float *a5)
{
  __m128i v5; // xmm0
  int v6; // r11d
  unsigned int *v7; // r10
  int v8; // eax
  unsigned int *v9; // rcx
  unsigned int v10; // r11d
  unsigned int v11; // ecx
  __m128i v12; // xmm1
  __m128i v13; // xmm2
  __m128i v14; // xmm0
  __m128i v15; // xmm2
  bool v16; // zf
  __m128i v17; // xmm3
  float v18; // eax
  __m128 v19; // xmm0
  float *v20; // rcx
  unsigned __int32 v21; // xmm1_4
  char result; // al
  _DWORD *v24; // r14
  float *v25; // r15
  unsigned int v26; // esi
  unsigned __int64 v28; // rsi
  __m128i v29; // xmm1
  __int64 v30; // [rsp+0h] [rbp-68h] BYREF
  float v31; // [rsp+24h] [rbp-44h] BYREF
  unsigned __int64 v32; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v33[7]; // [rsp+30h] [rbp-38h] BYREF

  v31 = 0.0;
  v6 = -a2;
  if ( a2 > 0 )
    v6 = a2;
  v7 = *a1;
  if ( !*a1 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_ccdb91336a64480ff5dc1631ec8ffbe4_15_llvm_1499869916920363649);
  if ( __ROR4__(-2023406815 * v6 + 9544368, 2) <= 0x48D158u && (v7[8] & 1) != 0 )
  {
    v8 = v6 / 900;
    v9 = v7 + 3;
    v10 = 0;
    if ( (v8 & 1) == 0 )
      v9 = v7;
    v11 = *v9;
    v12 = _mm_cvtsi32_si128(v11);
    if ( *(float *)v12.m128i_i32 != 0.0 )
    {
      LOBYTE(v10) = (v8 & 1) == 0;
      v13 = _mm_srai_epi32(_mm_slli_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v10), 0), 0x1Fu), 0x1Fu);
      v14 = _mm_and_si128(_mm_cvtsi32_si128(LODWORD(FLOAT_1_0)), v13);
      v15 = _mm_andnot_si128(v13, (__m128i)_xmm);
      v16 = (v8 & 2) == 0;
      v17 = _mm_xor_si128(_mm_load_si128((const __m128i *)&_xmm), v12);
      v18 = COERCE_FLOAT(_mm_cvtsi128_si32(v17));
      if ( v16 )
      {
        v18 = *(float *)&v11;
        v19 = (__m128)_mm_or_si128(v14, v15);
        if ( *(float *)v12.m128i_i32 < 0.0 )
        {
LABEL_22:
          v19 = _mm_xor_ps(v19, (__m128)_xmm);
          LODWORD(v18) = _mm_cvtsi128_si32(v12) + 0x80000000;
          v20 = a5;
          v21 = _mm_movehdup_ps(v19).m128_u32[0];
          if ( a2 >= 0 )
            goto LABEL_14;
          goto LABEL_13;
        }
      }
      else
      {
        v12 = v17;
        v19 = (__m128)_mm_or_si128(v14, v15);
        if ( *(float *)v17.m128i_i32 < 0.0 )
          goto LABEL_22;
      }
      v20 = a5;
      v21 = _mm_movehdup_ps(v19).m128_u32[0];
      if ( a2 >= 0 )
      {
LABEL_14:
        *a3 = v19.m128_i32[0];
        a3[1] = v21;
        *a4 = v18;
        *v20 = 1.0 / v18;
        result = 1;
        goto LABEL_17;
      }
LABEL_13:
      v21 ^= _xmm;
      goto LABEL_14;
    }
  }
  else
  {
    v24 = a3;
    v25 = a4;
    *(float *)v5.m128i_i32 = (float)v6 / 10.0;
    v26 = _mm_cvtsi128_si32(v5);
    LODWORD(v32) = RNvNtCsgPq7HM4PUSd_12gdi_bindings7draweng5efCos(v26);
    HIDWORD(v32) = RNvNtCsgPq7HM4PUSd_12gdi_bindings7draweng5efSin(v26);
    RNvMNtNtCs7vXzV21FY6F_8gdi_rust5xform12xformobj_hxxNtB2_9EXFORMOBJ19bXform_vectorfl_mut(a1, &v32, 1);
    v28 = v32;
    v33[0] = v32;
    RNvMNtCsgPq7HM4PUSd_12gdi_bindings4trigNtNtB4_6efloat6EFLOAT8eqLength(&v31, v33);
    v29 = (__m128i)LODWORD(v31);
    if ( v31 != 0.0 )
    {
      v19 = _mm_div_ps((__m128)v28, _mm_moveldup_ps((__m128)LODWORD(v31)));
      *(float *)v29.m128i_i32 = v31 * 16.0;
      v18 = COERCE_FLOAT(_mm_cvtsi128_si32(v29));
      a4 = v25;
      a3 = v24;
      v20 = a5;
      v21 = _mm_movehdup_ps(v19).m128_u32[0];
      if ( a2 >= 0 )
        goto LABEL_14;
      goto LABEL_13;
    }
  }
  result = 0;
LABEL_17:
  if ( _security_cookie != ((unsigned __int64)&v30 ^ v33[1]) )
    JUMPOUT(0x140001F46LL);
  return result;
}

```

## disassembly

```asm
0x140001cf0  push    r15
0x140001cf2  push    r14
0x140001cf4  push    rsi
0x140001cf5  push    rdi
0x140001cf6  push    rbx
0x140001cf7  sub     rsp, 40h
0x140001cfb  mov     rax, cs:__security_cookie
0x140001d02  xor     rax, rsp
0x140001d05  mov     [rsp+68h+var_30], rax
0x140001d0a  mov     [rsp+68h+var_44], 0
0x140001d12  mov     r11d, edx
0x140001d15  neg     r11d
0x140001d18  cmovs   r11d, edx
0x140001d1c  mov     r10, [rcx]
0x140001d1f  test    r10, r10
0x140001d22  jz      loc_140001F2D
0x140001d28  imul    eax, r11d, 87654321h
0x140001d2f  add     eax, 91A2B0h
0x140001d34  ror     eax, 2
0x140001d37  cmp     eax, 48D158h
0x140001d3c  ja      loc_140001E26
0x140001d42  mov     eax, [r10+20h]
0x140001d46  and     eax, 1
0x140001d49  jz      loc_140001E26
0x140001d4f  movsxd  rax, r11d
0x140001d52  imul    rax, 0FFFFFFFF91A2B3C5h
0x140001d59  shr     rax, 20h
0x140001d5d  add     eax, r11d
0x140001d60  mov     ecx, eax
0x140001d62  shr     ecx, 1Fh
0x140001d65  sar     eax, 9
0x140001d68  add     eax, ecx
0x140001d6a  lea     rcx, [r10+0Ch]
0x140001d6e  xor     r11d, r11d
0x140001d71  test    al, 1
0x140001d73  setz    bl
0x140001d76  cmovz   rcx, r10
0x140001d7a  mov     ecx, [rcx]
0x140001d7c  movd    xmm1, ecx
0x140001d80  xorps   xmm0, xmm0
0x140001d83  ucomiss xmm1, xmm0
0x140001d86  jnz     short loc_140001D8E
0x140001d88  jnp     loc_140001E94
0x140001d8e  mov     r11b, bl
0x140001d91  movd    xmm0, r11d
0x140001d96  pshufd  xmm2, xmm0, 0
0x140001d9b  pslld   xmm2, 1Fh
0x140001da0  psrad   xmm2, 1Fh
0x140001da5  movd    xmm0, cs:__real@3f800000
0x140001dad  pand    xmm0, xmm2
0x140001db1  pandn   xmm2, cs:__xmm@00000000000000003f80000000000000
0x140001db9  test    al, 2
0x140001dbb  movdqa  xmm3, cs:__xmm@80000000800000008000000080000000
0x140001dc3  pxor    xmm3, xmm1
0x140001dc7  movd    eax, xmm3
0x140001dcb  cmovz   eax, ecx
0x140001dce  jz      loc_140001EF3
0x140001dd4  movdqa  xmm1, xmm3
0x140001dd8  por     xmm0, xmm2
0x140001ddc  pxor    xmm2, xmm2
0x140001de0  ucomiss xmm2, xmm1
0x140001de3  ja      loc_140001F04
0x140001de9  mov     rcx, [rsp+68h+arg_20]
0x140001df1  movshdup xmm1, xmm0
0x140001df5  test    edx, edx
0x140001df7  jns     short loc_140001E00
0x140001df9  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x140001e00  movss   dword ptr [r8], xmm0
0x140001e05  movss   dword ptr [r8+4], xmm1
0x140001e0b  mov     [r9], eax
0x140001e0e  movd    xmm0, eax
0x140001e12  movss   xmm1, cs:__real@3f800000
0x140001e1a  divss   xmm1, xmm0
0x140001e1e  movss   dword ptr [rcx], xmm1
0x140001e22  mov     al, 1
0x140001e24  jmp     short loc_140001E96
0x140001e26  mov     ebx, edx
0x140001e28  mov     r14, r8
0x140001e2b  mov     r15, r9
0x140001e2e  cvtsi2ss xmm0, r11d
0x140001e33  divss   xmm0, cs:__real@41200000
0x140001e3b  movd    esi, xmm0
0x140001e3f  mov     rdi, rcx
0x140001e42  mov     ecx, esi
0x140001e44  call    _RNvNtCsgPq7HM4PUSd_12gdi_bindings7draweng5efCos
0x140001e49  mov     dword ptr [rsp+68h+var_40], eax
0x140001e4d  mov     ecx, esi
0x140001e4f  call    _RNvNtCsgPq7HM4PUSd_12gdi_bindings7draweng5efSin
0x140001e54  mov     dword ptr [rsp+68h+var_40+4], eax
0x140001e58  lea     rdx, [rsp+68h+var_40]
0x140001e5d  mov     r8d, 1
0x140001e63  mov     rcx, rdi
0x140001e66  call    _RNvMNtNtCs7vXzV21FY6F_8gdi_rust5xform12xformobj_hxxNtB2_9EXFORMOBJ19bXform_vectorfl_mut
0x140001e6b  mov     rsi, [rsp+68h+var_40]
0x140001e70  mov     [rsp+68h+var_38], rsi
0x140001e75  lea     rcx, [rsp+68h+var_44]
0x140001e7a  lea     rdx, [rsp+68h+var_38]
0x140001e7f  call    _RNvMNtCsgPq7HM4PUSd_12gdi_bindings4trigNtNtB4_6efloat6EFLOAT8eqLength
0x140001e84  movss   xmm1, [rsp+68h+var_44]
0x140001e8a  xorps   xmm0, xmm0
0x140001e8d  ucomiss xmm1, xmm0
0x140001e90  jnz     short loc_140001EBA
0x140001e92  jp      short loc_140001EBA
0x140001e94  xor     eax, eax
0x140001e96  mov     rcx, [rsp+68h+var_30]
0x140001e9b  xor     rcx, rsp
0x140001e9e  mov     rdx, cs:__security_cookie
0x140001ea5  cmp     rdx, rcx
0x140001ea8  jnz     loc_140001F39
0x140001eae  add     rsp, 40h
0x140001eb2  pop     rbx
0x140001eb3  pop     rdi
0x140001eb4  pop     rsi
0x140001eb5  pop     r14
0x140001eb7  pop     r15
0x140001eb9  retn
0x140001eba  movq    xmm0, rsi
0x140001ebf  movsldup xmm2, xmm1
0x140001ec3  divps   xmm0, xmm2
0x140001ec6  mulss   xmm1, cs:__real@41800000
0x140001ece  movd    eax, xmm1
0x140001ed2  mov     r9, r15
0x140001ed5  mov     r8, r14
0x140001ed8  mov     edx, ebx
0x140001eda  mov     rcx, [rsp+68h+arg_20]
0x140001ee2  movshdup xmm1, xmm0
0x140001ee6  test    edx, edx
0x140001ee8  jns     loc_140001E00
0x140001eee  jmp     loc_140001DF9
0x140001ef3  por     xmm0, xmm2
0x140001ef7  pxor    xmm2, xmm2
0x140001efb  ucomiss xmm2, xmm1
0x140001efe  jbe     loc_140001DE9
0x140001f04  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x140001f0b  movd    eax, xmm1
0x140001f0f  add     eax, 80000000h
0x140001f14  mov     rcx, [rsp+68h+arg_20]
0x140001f1c  movshdup xmm1, xmm0
0x140001f20  test    edx, edx
0x140001f22  js      loc_140001DF9
0x140001f28  jmp     loc_140001E00
0x140001f2d  lea     rcx, anon_ccdb91336a64480ff5dc1631ec8ffbe4_15_llvm_1499869916920363649
0x140001f34  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x140001f39  mov     rcx, [rsp+68h+var_30]
0x140001f3e  xor     rcx, rsp; StackCookie
0x140001f41  call    __security_check_cookie
```
