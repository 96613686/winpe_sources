# _RINvNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable7ipnsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB6_SBT_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2p_10RegionCore16subtract_complex0E0EB2p_

- ea: `0x1400162d0`
- end: `0x14001643c`
- name: `_RINvNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable7ipnsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB6_SBT_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2p_10RegionCore16subtract_complex0E0EB2p_`
- size: `364`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cc10`

## callees

- `0x1400162d0`
- `0x140016650`

## pseudocode

```c
void __fastcall RINvNtNtNtCs9MWeMO1rkJG_4core5slice4sort8unstable7ipnsortRNtNtCscTDbrdTM4KX_15onecore_windows6windef6__RECTLNCINvMB6_SBT_20sort_unstable_by_keylNCNvMs_CsdcpJtfrLhSH_7rgncoreNtB2p_10RegionCore16subtract_complex0E0EB2p_(
        __m128i *a1,
        unsigned __int64 a2)
{
  int v2; // eax
  int v3; // r8d
  __int64 v4; // r9
  int v5; // r10d
  int v6; // r11d
  unsigned __int64 v7; // r9
  int v8; // r10d
  int v9; // r11d
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  __m128i *v12; // r10
  __int64 v13; // r11
  __int64 v14; // rsi
  __m128i v15; // xmm0
  __m128i v16; // xmm1
  __m128i v17; // xmm2
  __int64 v18; // rax
  __int64 *v19; // r9
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx

  if ( a2 >= 2 )
  {
    v2 = *(_DWORD *)(a1->m128i_i64[1] + 4);
    v3 = *(_DWORD *)(a1->m128i_i64[0] + 4);
    v4 = 2;
    if ( v2 >= v3 )
    {
      if ( a2 != 2 )
      {
        v8 = *(_DWORD *)(a1->m128i_i64[1] + 4);
        while ( 1 )
        {
          v9 = v8;
          v8 = *(_DWORD *)(a1->m128i_i64[v4] + 4);
          if ( v8 < v9 )
            break;
          if ( a2 == ++v4 )
            goto LABEL_14;
        }
      }
    }
    else if ( a2 != 2 )
    {
      v5 = *(_DWORD *)(a1->m128i_i64[1] + 4);
      while ( 1 )
      {
        v6 = v5;
        v5 = *(_DWORD *)(a1->m128i_i64[v4] + 4);
        if ( v5 >= v6 )
          break;
        if ( a2 == ++v4 )
          goto LABEL_14;
      }
    }
    if ( v4 != a2 )
    {
      _BitScanReverse64(&v7, a2 | 1);
      core::slice::sort::unstable::quicksort::quicksort_ref__onecore_windows::windef::_RECTL__core::slice::impl_0::sort_unstable_by_key::closure_env_0_ref__onecore_windows::windef::_RECTL__i32_rgncore::impl_1::subtract_complex::closure_env_0___(
        a1,
        a2,
        0,
        (2 * (v7 ^ 0x3F)) ^ 0x7E);
      return;
    }
LABEL_14:
    if ( v2 < v3 )
    {
      v10 = a2 >> 1;
      if ( a2 < 8 )
      {
        v11 = 0;
LABEL_20:
        v18 = -(__int64)v10;
        v19 = &a1->m128i_i64[v11];
        v20 = -v11;
        v21 = (__int64)&a1->m128i_i64[a2 - 1];
        do
        {
          v22 = *v19;
          *v19 = *(_QWORD *)(v21 + 8 * v20);
          *(_QWORD *)(v21 + 8 * v20--) = v22;
          ++v19;
        }
        while ( v18 != v20 );
        return;
      }
      v11 = v10 & 0x7FFFFFFFFFFFFFCLL;
      v12 = a1 + 1;
      v13 = (__int64)&a1[-1].m128i_i64[a2];
      v14 = 0;
      do
      {
        v15 = _mm_loadu_si128(v12 - 1);
        v16 = _mm_loadu_si128(v12);
        v17 = _mm_shuffle_epi32(_mm_loadu_si128((const __m128i *)(v13 + 8 * v14 - 16)), 78);
        v12[-1] = _mm_shuffle_epi32(_mm_loadu_si128((const __m128i *)(v13 + 8 * v14)), 78);
        *v12 = v17;
        *(__m128i *)(v13 + 8 * v14) = _mm_shuffle_epi32(v15, 78);
        *(__m128i *)(v13 + 8 * v14 - 16) = _mm_shuffle_epi32(v16, 78);
        v14 -= 4;
        v12 += 2;
      }
      while ( -(__int64)(v10 & 0xFFFFFFFFFFFFFFFCuLL) != v14 );
      if ( v10 != v11 )
        goto LABEL_20;
    }
  }
}

```

## disassembly

```asm
0x1400162d0  push    rsi
0x1400162d1  cmp     rdx, 2
0x1400162d5  jb      loc_14001643A
0x1400162db  mov     r8, [rcx]
0x1400162de  mov     rax, [rcx+8]
0x1400162e2  mov     eax, [rax+4]
0x1400162e5  mov     r8d, [r8+4]
0x1400162e9  mov     r9d, 2
0x1400162ef  cmp     eax, r8d
0x1400162f2  jge     short loc_14001631A
0x1400162f4  cmp     rdx, 2
0x1400162f8  jz      short loc_140016320
0x1400162fa  mov     r10d, eax
0x1400162fd  nop     dword ptr [rax]
0x140016300  mov     r11d, r10d
0x140016303  mov     r10, [rcx+r9*8]
0x140016307  mov     r10d, [r10+4]
0x14001630b  cmp     r10d, r11d
0x14001630e  jge     short loc_140016320
0x140016310  inc     r9
0x140016313  cmp     rdx, r9
0x140016316  jnz     short loc_140016300
0x140016318  jmp     short loc_140016368
0x14001631a  cmp     rdx, 2
0x14001631e  jnz     short loc_140016344
0x140016320  cmp     r9, rdx
0x140016323  jz      short loc_140016368
0x140016325  mov     rax, rdx
0x140016328  or      rax, 1
0x14001632c  bsr     r9, rax
0x140016330  xor     r9d, 3Fh
0x140016334  add     r9d, r9d
0x140016337  xor     r9d, 7Eh
0x14001633b  xor     r8d, r8d
0x14001633e  pop     rsi
0x14001633f  jmp     core__slice__sort__unstable__quicksort__quicksort_ref$_onecore_windows__windef___RECTL__core__slice__impl$0__sort_unstable_by_key__closure_env$0_ref$_onecore_windows__windef___RECTL__i32_rgncore__impl$1__subtract_complex__closure_env$0___
0x140016344  mov     r10d, eax
0x140016347  nop     word ptr [rax+rax+00000000h]
0x140016350  mov     r11d, r10d
0x140016353  mov     r10, [rcx+r9*8]
0x140016357  mov     r10d, [r10+4]
0x14001635b  cmp     r10d, r11d
0x14001635e  jl      short loc_140016320
0x140016360  inc     r9
0x140016363  cmp     rdx, r9
0x140016366  jnz     short loc_140016350
0x140016368  cmp     eax, r8d
0x14001636b  jge     loc_14001643A
0x140016371  mov     rax, rdx
0x140016374  shr     rax, 1
0x140016377  cmp     rdx, 8
0x14001637b  jnb     short loc_140016385
0x14001637d  xor     r8d, r8d
0x140016380  jmp     loc_140016406
0x140016385  mov     r8, 7FFFFFFFFFFFFFCh
0x14001638f  and     r8, rax
0x140016392  mov     r9, rax
0x140016395  and     r9, 0FFFFFFFFFFFFFFFCh
0x140016399  neg     r9
0x14001639c  lea     r10, [rcx+10h]
0x1400163a0  lea     r11, [rcx+rdx*8]
0x1400163a4  add     r11, 0FFFFFFFFFFFFFFF0h
0x1400163a8  xor     esi, esi
0x1400163aa  nop     word ptr [rax+rax+00h]
0x1400163b0  movdqu  xmm0, xmmword ptr [r10-10h]
0x1400163b6  movdqu  xmm1, xmmword ptr [r10]
0x1400163bb  movdqu  xmm2, xmmword ptr [r11+rsi*8-10h]
0x1400163c2  movdqu  xmm3, xmmword ptr [r11+rsi*8]
0x1400163c8  pshufd  xmm3, xmm3, 4Eh ; 'N'
0x1400163cd  pshufd  xmm2, xmm2, 4Eh ; 'N'
0x1400163d2  movdqu  xmmword ptr [r10-10h], xmm3
0x1400163d8  movdqu  xmmword ptr [r10], xmm2
0x1400163dd  pshufd  xmm0, xmm0, 4Eh ; 'N'
0x1400163e2  pshufd  xmm1, xmm1, 4Eh ; 'N'
0x1400163e7  movdqu  xmmword ptr [r11+rsi*8], xmm0
0x1400163ed  movdqu  xmmword ptr [r11+rsi*8-10h], xmm1
0x1400163f4  add     rsi, 0FFFFFFFFFFFFFFFCh
0x1400163f8  add     r10, 20h ; ' '
0x1400163fc  cmp     r9, rsi
0x1400163ff  jnz     short loc_1400163B0
0x140016401  cmp     rax, r8
0x140016404  jz      short loc_14001643A
0x140016406  neg     rax
0x140016409  lea     r9, [rcx+r8*8]
0x14001640d  neg     r8
0x140016410  lea     rcx, [rcx+rdx*8]
0x140016414  add     rcx, 0FFFFFFFFFFFFFFF8h
0x140016418  nop     dword ptr [rax+rax+00000000h]
0x140016420  mov     rdx, [r9]
0x140016423  mov     r10, [rcx+r8*8]
0x140016427  mov     [r9], r10
0x14001642a  mov     [rcx+r8*8], rdx
0x14001642e  dec     r8
0x140016431  add     r9, 8
0x140016435  cmp     rax, r8
0x140016438  jnz     short loc_140016420
0x14001643a  pop     rsi
0x14001643b  retn
```
