# SymCryptFdefMaskedCopyAsm

- ea: `0x18000f830`
- end: `0x18000f886`
- name: `SymCryptFdefMaskedCopyAsm`
- size: `86`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180028790`
- `0x18002a4b0`
- `0x18002ad80`
- `0x18002bb90`
- `0x18002f1c0`
- `0x180030ad0`
- `0x180031a80`
- `0x180032958`

## callees

- `0x18000f830`

## pseudocode

```c
void __fastcall SymCryptFdefMaskedCopyAsm(const __m128i *a1, __m128i *a2, int a3, unsigned int a4)
{
  int v4; // r8d
  __m128i v5; // xmm0
  __m128i v6; // xmm1

  v4 = 2 * a3;
  v5 = _mm_shuffle_epi32(_mm_cvtsi32_si128(a4), 0);
  v6 = _mm_xor_si128((__m128i)-1LL, v5);
  do
  {
    *a2 = _mm_or_si128(_mm_and_si128(_mm_load_si128(a1), v5), _mm_and_si128(_mm_load_si128(a2), v6));
    a2[1] = _mm_or_si128(_mm_and_si128(_mm_load_si128(a1 + 1), v5), _mm_and_si128(_mm_load_si128(a2 + 1), v6));
    a1 += 2;
    a2 += 2;
    --v4;
  }
  while ( v4 );
}

```

## disassembly

```asm
0x18000f830  add     r8d, r8d
0x18000f833  movd    xmm0, r9d
0x18000f838  pcmpeqd xmm1, xmm1
0x18000f83c  pshufd  xmm0, xmm0, 0
0x18000f841  pxor    xmm1, xmm0
0x18000f845  movdqa  xmm2, xmmword ptr [rcx]
0x18000f849  movdqa  xmm3, xmmword ptr [rdx]
0x18000f84d  pand    xmm2, xmm0
0x18000f851  pand    xmm3, xmm1
0x18000f855  por     xmm2, xmm3
0x18000f859  movdqa  xmmword ptr [rdx], xmm2
0x18000f85d  movdqa  xmm2, xmmword ptr [rcx+10h]
0x18000f862  movdqa  xmm3, xmmword ptr [rdx+10h]
0x18000f867  pand    xmm2, xmm0
0x18000f86b  pand    xmm3, xmm1
0x18000f86f  por     xmm2, xmm3
0x18000f873  movdqa  xmmword ptr [rdx+10h], xmm2
0x18000f878  add     rcx, 20h ; ' '
0x18000f87c  add     rdx, 20h ; ' '
0x18000f880  dec     r8d
0x18000f883  jnz     short loc_18000F845
0x18000f885  retn
```
