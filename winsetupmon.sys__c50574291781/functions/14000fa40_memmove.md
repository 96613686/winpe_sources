# memmove

- ea: `0x14000fa40`
- end: `0x14000fcea`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x140001748`
- `0x140007e14`
- `0x140007fec`
- `0x140008c08`
- `0x14000bfb8`
- `0x14000c2bc`
- `0x14000c590`
- `0x14000c9b0`
- `0x14000cad0`
- `0x14000cdc0`
- `0x14000cfa0`
- `0x14000d5e0`
- `0x14000f930`
- `0x14000f940`
- `0x14002052c`
- `0x1400205f0`
- `0x1400218f0`

## callees

- `0x14000fa40`

## pseudocode

```c
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  void *result; // rax
  __int64 v4; // r11
  __int64 v5; // rdx
  __int128 v6; // xmm1
  bool v7; // cf
  signed __int64 v8; // rdx
  char v9; // r11
  _BYTE *v10; // rcx
  char v11; // r11
  char *v12; // r11
  signed __int64 v13; // rdx
  __m128 v14; // xmm0
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  __m128 v17; // xmm1
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r9
  __int128 v20; // xmm1
  __int128 v21; // xmm2
  __int128 v22; // xmm3
  __m128 v23; // xmm4
  unsigned __int64 j; // r9
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  __m128 v27; // xmm1
  __m128 v28; // xmm2
  __m128 v29; // xmm3
  __m128 v30; // xmm4
  char *v31; // rcx
  __int128 v32; // xmm0
  unsigned __int64 v33; // rcx
  size_t v34; // r8
  _OWORD *v35; // r11
  __int128 v36; // xmm1
  size_t v37; // r9
  __int128 v38; // xmm1
  __int128 v39; // xmm2
  __int128 v40; // xmm3
  __int128 v41; // xmm4
  size_t i; // r9
  size_t v43; // r8

  result = a1;
  if ( Size < 8 )
  {
    if ( Size )
    {
      v7 = Src < a1;
      v8 = (_BYTE *)Src - (_BYTE *)a1;
      if ( v7 )
      {
        v10 = (char *)a1 + Size;
        do
        {
          v11 = v10[v8 - 1];
          --v10;
          --Size;
          *v10 = v11;
        }
        while ( Size );
      }
      else
      {
        do
        {
          v9 = *((_BYTE *)a1 + v8);
          a1 = (char *)a1 + 1;
          --Size;
          *((char *)a1 - 1) = v9;
        }
        while ( Size );
      }
    }
  }
  else if ( Size > 0x10 )
  {
    if ( Size > 0x20 )
    {
      v12 = (char *)Src + Size;
      v7 = Src < a1;
      v13 = (_BYTE *)Src - (_BYTE *)a1;
      if ( v7 && v12 > a1 )
      {
        v31 = (char *)a1 + Size;
        v32 = *(_OWORD *)&v31[v13 - 16];
        v33 = (unsigned __int64)(v31 - 16);
        v34 = Size - 16;
        if ( (v33 & 0xF) != 0 )
        {
          v35 = (_OWORD *)v33;
          v33 &= 0xFFFFFFFFFFFFFFF0uLL;
          v36 = *(_OWORD *)(v33 + v13);
          *v35 = v32;
          v32 = v36;
          v34 = v33 - (_QWORD)result;
        }
        v37 = v34 >> 6;
        if ( v34 >> 6 )
        {
          v34 &= 0x3Fu;
          do
          {
            v38 = *(_OWORD *)(v33 + v13 - 16);
            v39 = *(_OWORD *)(v33 + v13 - 32);
            v40 = *(_OWORD *)(v33 + v13 - 48);
            v41 = *(_OWORD *)(v33 + v13 - 64);
            *(_OWORD *)v33 = v32;
            v33 -= 64LL;
            --v37;
            *(_OWORD *)(v33 + 48) = v38;
            *(_OWORD *)(v33 + 32) = v39;
            *(_OWORD *)(v33 + 16) = v40;
            v32 = v41;
          }
          while ( v37 );
        }
        for ( i = v34 >> 4; i; --i )
        {
          *(_OWORD *)v33 = v32;
          v32 = *(_OWORD *)(v33 + v13 - 16);
          v33 -= 16LL;
        }
        v43 = v34 & 0xF;
        if ( v43 )
          *(_OWORD *)(v33 - v43) = *(_OWORD *)(v33 - v43 + v13);
        *(_OWORD *)v33 = v32;
      }
      else
      {
        v14 = *(__m128 *)((char *)a1 + v13);
        v15 = (unsigned __int64)a1 + 16;
        if ( (v15 & 0xF) != 0 )
        {
          v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
          v17 = *(__m128 *)(v16 + v13);
          *(__m128 *)result = v14;
          v14 = v17;
          v15 = v16 + 16;
        }
        v18 = (unsigned __int64)result + Size - v15;
        v19 = v18 >> 6;
        if ( v18 >> 6 )
        {
          if ( v19 > 0x1000 )
          {
            v26 = v18 >> 6;
            v18 &= 0x3Fu;
            _mm_prefetch((const char *)(v15 + v13 + 64), 0);
            do
            {
              v27 = *(__m128 *)(v15 + v13);
              v28 = *(__m128 *)(v15 + v13 + 16);
              v29 = *(__m128 *)(v15 + v13 + 32);
              v30 = *(__m128 *)(v15 + v13 + 48);
              _mm_stream_ps((float *)(v15 - 16), v14);
              v15 += 64LL;
              _mm_prefetch((const char *)(v15 + v13 + 64), 0);
              --v26;
              _mm_stream_ps((float *)(v15 - 64), v27);
              _mm_stream_ps((float *)(v15 - 48), v28);
              _mm_stream_ps((float *)(v15 - 32), v29);
              v14 = v30;
            }
            while ( v26 );
            _mm_sfence();
          }
          else
          {
            v18 &= 0x3Fu;
            do
            {
              v20 = *(_OWORD *)(v15 + v13);
              v21 = *(_OWORD *)(v15 + v13 + 16);
              v22 = *(_OWORD *)(v15 + v13 + 32);
              v23 = *(__m128 *)(v15 + v13 + 48);
              *(__m128 *)(v15 - 16) = v14;
              v15 += 64LL;
              --v19;
              *(_OWORD *)(v15 - 64) = v20;
              *(_OWORD *)(v15 - 48) = v21;
              *(_OWORD *)(v15 - 32) = v22;
              v14 = v23;
            }
            while ( v19 );
          }
        }
        for ( j = v18 >> 4; j; --j )
        {
          *(__m128 *)(v15 - 16) = v14;
          v14 = *(__m128 *)(v15 + v13);
          v15 += 16LL;
        }
        v25 = v18 & 0xF;
        if ( v25 )
          *(_OWORD *)(v15 + v25 - 16) = *(_OWORD *)(v15 + v25 - 16 + v13);
        *(__m128 *)(v15 - 16) = v14;
      }
    }
    else
    {
      v6 = *(_OWORD *)((char *)Src + Size - 16);
      *(_OWORD *)a1 = *(_OWORD *)Src;
      *(_OWORD *)((char *)a1 + Size - 16) = v6;
    }
  }
  else
  {
    v4 = *(_QWORD *)Src;
    v5 = *(_QWORD *)((char *)Src + Size - 8);
    *(_QWORD *)a1 = v4;
    *(_QWORD *)((char *)a1 + Size - 8) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000fa40  mov     rax, rcx
0x14000fa43  cmp     r8, 8
0x14000fa47  jb      short loc_14000FA80
0x14000fa49  cmp     r8, 10h
0x14000fa4d  ja      short loc_14000FA60
0x14000fa4f  mov     r11, [rdx]
0x14000fa52  mov     rdx, [rdx+r8-8]
0x14000fa57  mov     [rcx], r11
0x14000fa5a  mov     [rcx+r8-8], rdx
0x14000fa5f  retn
0x14000fa60  cmp     r8, 20h ; ' '
0x14000fa64  ja      short loc_14000FAC0
0x14000fa66  movups  xmm0, xmmword ptr [rdx]
0x14000fa69  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x14000fa6f  movups  xmmword ptr [rcx], xmm0
0x14000fa72  movups  xmmword ptr [rcx+r8-10h], xmm1
0x14000fa78  retn
0x14000fa80  test    r8, r8
0x14000fa83  jz      short locret_14000FA9A
0x14000fa85  sub     rdx, rcx
0x14000fa88  jb      short loc_14000FAA0
0x14000fa8a  mov     r11b, [rcx+rdx]
0x14000fa8e  inc     rcx
0x14000fa91  dec     r8
0x14000fa94  mov     [rcx-1], r11b
0x14000fa98  jnz     short loc_14000FA8A
0x14000fa9a  retn
0x14000faa0  add     rcx, r8
0x14000faa3  mov     r11b, [rcx+rdx-1]
0x14000faa8  dec     rcx
0x14000faab  dec     r8
0x14000faae  mov     [rcx], r11b
0x14000fab1  jnz     short loc_14000FAA3
0x14000fab3  retn
0x14000fac0  lea     r11, [rdx+r8]
0x14000fac4  sub     rdx, rcx
0x14000fac7  jnb     short loc_14000FAD2
0x14000fac9  cmp     r11, rcx
0x14000facc  ja      loc_14000FC40
0x14000fad2  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000fad6  add     rcx, 10h
0x14000fada  test    cl, 0Fh
0x14000fadd  jz      short loc_14000FAF1
0x14000fadf  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000fae3  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000fae7  movups  xmmword ptr [rax], xmm0
0x14000faea  movaps  xmm0, xmm1
0x14000faed  add     rcx, 10h
0x14000faf1  add     r8, rax
0x14000faf4  sub     r8, rcx
0x14000faf7  mov     r9, r8
0x14000fafa  shr     r9, 6
0x14000fafe  jz      short loc_14000FB6F
0x14000fb00  cmp     r9, 1000h
0x14000fb07  ja      loc_14000FBC0
0x14000fb0d  and     r8, 3Fh
0x14000fb11  jmp     short loc_14000FB40
0x14000fb40  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000fb44  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000fb49  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000fb4e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000fb53  movaps  xmmword ptr [rcx-10h], xmm0
0x14000fb57  add     rcx, 40h ; '@'
0x14000fb5b  dec     r9
0x14000fb5e  movaps  xmmword ptr [rcx-40h], xmm1
0x14000fb62  movaps  xmmword ptr [rcx-30h], xmm2
0x14000fb66  movaps  xmmword ptr [rcx-20h], xmm3
0x14000fb6a  movaps  xmm0, xmm4
0x14000fb6d  jnz     short loc_14000FB40
0x14000fb6f  mov     r9, r8
0x14000fb72  shr     r9, 4
0x14000fb76  jz      short loc_14000FB91
0x14000fb78  nop     dword ptr [rax+rax+00000000h]
0x14000fb80  movaps  xmmword ptr [rcx-10h], xmm0
0x14000fb84  movups  xmm0, xmmword ptr [rcx+rdx]
0x14000fb88  add     rcx, 10h
0x14000fb8c  dec     r9
0x14000fb8f  jnz     short loc_14000FB80
0x14000fb91  and     r8, 0Fh
0x14000fb95  jz      short loc_14000FBA5
0x14000fb97  lea     r11, [rcx+r8-10h]
0x14000fb9c  movups  xmm1, xmmword ptr [r11+rdx]
0x14000fba1  movups  xmmword ptr [r11], xmm1
0x14000fba5  movaps  xmmword ptr [rcx-10h], xmm0
0x14000fba9  retn
0x14000fbc0  mov     r9, r8
0x14000fbc3  shr     r9, 6
0x14000fbc7  and     r8, 3Fh
0x14000fbcb  prefetchnta byte ptr [rcx+rdx+40h]
0x14000fbd0  jmp     short loc_14000FC00
0x14000fc00  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000fc04  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x14000fc09  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x14000fc0e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x14000fc13  movntps xmmword ptr [rcx-10h], xmm0
0x14000fc17  add     rcx, 40h ; '@'
0x14000fc1b  prefetchnta byte ptr [rcx+rdx+40h]
0x14000fc20  dec     r9
0x14000fc23  movntps xmmword ptr [rcx-40h], xmm1
0x14000fc27  movntps xmmword ptr [rcx-30h], xmm2
0x14000fc2b  movntps xmmword ptr [rcx-20h], xmm3
0x14000fc2f  movaps  xmm0, xmm4
0x14000fc32  jnz     short loc_14000FC00
0x14000fc34  sfence
0x14000fc37  jmp     loc_14000FB6F
0x14000fc40  add     rcx, r8
0x14000fc43  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000fc48  sub     rcx, 10h
0x14000fc4c  sub     r8, 10h
0x14000fc50  test    cl, 0Fh
0x14000fc53  jz      short loc_14000FC6D
0x14000fc55  mov     r11, rcx
0x14000fc58  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000fc5c  movups  xmm1, xmmword ptr [rcx+rdx]
0x14000fc60  movups  xmmword ptr [r11], xmm0
0x14000fc64  movaps  xmm0, xmm1
0x14000fc67  mov     r8, rcx
0x14000fc6a  sub     r8, rax
0x14000fc6d  mov     r9, r8
0x14000fc70  shr     r9, 6
0x14000fc74  jz      short loc_14000FCAF
0x14000fc76  and     r8, 3Fh
0x14000fc7a  jmp     short loc_14000FC80
0x14000fc80  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x14000fc85  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000fc8a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000fc8f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x14000fc94  movaps  xmmword ptr [rcx], xmm0
0x14000fc97  sub     rcx, 40h ; '@'
0x14000fc9b  dec     r9
0x14000fc9e  movaps  xmmword ptr [rcx+30h], xmm1
0x14000fca2  movaps  xmmword ptr [rcx+20h], xmm2
0x14000fca6  movaps  xmmword ptr [rcx+10h], xmm3
0x14000fcaa  movaps  xmm0, xmm4
0x14000fcad  jnz     short loc_14000FC80
0x14000fcaf  mov     r9, r8
0x14000fcb2  shr     r9, 4
0x14000fcb6  jz      short loc_14000FCD1
0x14000fcb8  nop     dword ptr [rax+rax+00000000h]
0x14000fcc0  movaps  xmmword ptr [rcx], xmm0
0x14000fcc3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x14000fcc8  sub     rcx, 10h
0x14000fccc  dec     r9
0x14000fccf  jnz     short loc_14000FCC0
0x14000fcd1  and     r8, 0Fh
0x14000fcd5  jz      short loc_14000FCE6
0x14000fcd7  mov     r11, rcx
0x14000fcda  sub     r11, r8
0x14000fcdd  movups  xmm1, xmmword ptr [r11+rdx]
0x14000fce2  movups  xmmword ptr [r11], xmm1
0x14000fce6  movaps  xmmword ptr [rcx], xmm0
0x14000fce9  retn
```
