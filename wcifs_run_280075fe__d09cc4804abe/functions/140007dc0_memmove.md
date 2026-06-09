# memmove

- ea: `0x140007dc0`
- end: `0x14000806a`
- name: `memmove`
- size: `682`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033a0`
- `0x1400063dc`
- `0x140007234`
- `0x140007c90`
- `0x140007ca0`
- `0x140014c90`
- `0x14001ba50`
- `0x140020b60`
- `0x140023e98`
- `0x14002befc`
- `0x14002c884`

## callees

- `0x140007dc0`

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
0x140007dc0  mov     rax, rcx
0x140007dc3  cmp     r8, 8
0x140007dc7  jb      short loc_140007E00
0x140007dc9  cmp     r8, 10h
0x140007dcd  ja      short loc_140007DE0
0x140007dcf  mov     r11, [rdx]
0x140007dd2  mov     rdx, [rdx+r8-8]
0x140007dd7  mov     [rcx], r11
0x140007dda  mov     [rcx+r8-8], rdx
0x140007ddf  retn
0x140007de0  cmp     r8, 20h ; ' '
0x140007de4  ja      short loc_140007E40
0x140007de6  movups  xmm0, xmmword ptr [rdx]
0x140007de9  movups  xmm1, xmmword ptr [rdx+r8-10h]
0x140007def  movups  xmmword ptr [rcx], xmm0
0x140007df2  movups  xmmword ptr [rcx+r8-10h], xmm1
0x140007df8  retn
0x140007e00  test    r8, r8
0x140007e03  jz      short locret_140007E1A
0x140007e05  sub     rdx, rcx
0x140007e08  jb      short loc_140007E20
0x140007e0a  mov     r11b, [rcx+rdx]
0x140007e0e  inc     rcx
0x140007e11  dec     r8
0x140007e14  mov     [rcx-1], r11b
0x140007e18  jnz     short loc_140007E0A
0x140007e1a  retn
0x140007e20  add     rcx, r8
0x140007e23  mov     r11b, [rcx+rdx-1]
0x140007e28  dec     rcx
0x140007e2b  dec     r8
0x140007e2e  mov     [rcx], r11b
0x140007e31  jnz     short loc_140007E23
0x140007e33  retn
0x140007e40  lea     r11, [rdx+r8]
0x140007e44  sub     rdx, rcx
0x140007e47  jnb     short loc_140007E52
0x140007e49  cmp     r11, rcx
0x140007e4c  ja      loc_140007FC0
0x140007e52  movups  xmm0, xmmword ptr [rcx+rdx]
0x140007e56  add     rcx, 10h
0x140007e5a  test    cl, 0Fh
0x140007e5d  jz      short loc_140007E71
0x140007e5f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140007e63  movups  xmm1, xmmword ptr [rcx+rdx]
0x140007e67  movups  xmmword ptr [rax], xmm0
0x140007e6a  movaps  xmm0, xmm1
0x140007e6d  add     rcx, 10h
0x140007e71  add     r8, rax
0x140007e74  sub     r8, rcx
0x140007e77  mov     r9, r8
0x140007e7a  shr     r9, 6
0x140007e7e  jz      short loc_140007EEF
0x140007e80  cmp     r9, 1000h
0x140007e87  ja      loc_140007F40
0x140007e8d  and     r8, 3Fh
0x140007e91  jmp     short loc_140007EC0
0x140007ec0  movups  xmm1, xmmword ptr [rcx+rdx]
0x140007ec4  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x140007ec9  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x140007ece  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x140007ed3  movaps  xmmword ptr [rcx-10h], xmm0
0x140007ed7  add     rcx, 40h ; '@'
0x140007edb  dec     r9
0x140007ede  movaps  xmmword ptr [rcx-40h], xmm1
0x140007ee2  movaps  xmmword ptr [rcx-30h], xmm2
0x140007ee6  movaps  xmmword ptr [rcx-20h], xmm3
0x140007eea  movaps  xmm0, xmm4
0x140007eed  jnz     short loc_140007EC0
0x140007eef  mov     r9, r8
0x140007ef2  shr     r9, 4
0x140007ef6  jz      short loc_140007F11
0x140007ef8  nop     dword ptr [rax+rax+00000000h]
0x140007f00  movaps  xmmword ptr [rcx-10h], xmm0
0x140007f04  movups  xmm0, xmmword ptr [rcx+rdx]
0x140007f08  add     rcx, 10h
0x140007f0c  dec     r9
0x140007f0f  jnz     short loc_140007F00
0x140007f11  and     r8, 0Fh
0x140007f15  jz      short loc_140007F25
0x140007f17  lea     r11, [rcx+r8-10h]
0x140007f1c  movups  xmm1, xmmword ptr [r11+rdx]
0x140007f21  movups  xmmword ptr [r11], xmm1
0x140007f25  movaps  xmmword ptr [rcx-10h], xmm0
0x140007f29  retn
0x140007f40  mov     r9, r8
0x140007f43  shr     r9, 6
0x140007f47  and     r8, 3Fh
0x140007f4b  prefetchnta byte ptr [rcx+rdx+40h]
0x140007f50  jmp     short loc_140007F80
0x140007f80  movups  xmm1, xmmword ptr [rcx+rdx]
0x140007f84  movups  xmm2, xmmword ptr [rcx+rdx+10h]
0x140007f89  movups  xmm3, xmmword ptr [rcx+rdx+20h]
0x140007f8e  movups  xmm4, xmmword ptr [rcx+rdx+30h]
0x140007f93  movntps xmmword ptr [rcx-10h], xmm0
0x140007f97  add     rcx, 40h ; '@'
0x140007f9b  prefetchnta byte ptr [rcx+rdx+40h]
0x140007fa0  dec     r9
0x140007fa3  movntps xmmword ptr [rcx-40h], xmm1
0x140007fa7  movntps xmmword ptr [rcx-30h], xmm2
0x140007fab  movntps xmmword ptr [rcx-20h], xmm3
0x140007faf  movaps  xmm0, xmm4
0x140007fb2  jnz     short loc_140007F80
0x140007fb4  sfence
0x140007fb7  jmp     loc_140007EEF
0x140007fc0  add     rcx, r8
0x140007fc3  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x140007fc8  sub     rcx, 10h
0x140007fcc  sub     r8, 10h
0x140007fd0  test    cl, 0Fh
0x140007fd3  jz      short loc_140007FED
0x140007fd5  mov     r11, rcx
0x140007fd8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140007fdc  movups  xmm1, xmmword ptr [rcx+rdx]
0x140007fe0  movups  xmmword ptr [r11], xmm0
0x140007fe4  movaps  xmm0, xmm1
0x140007fe7  mov     r8, rcx
0x140007fea  sub     r8, rax
0x140007fed  mov     r9, r8
0x140007ff0  shr     r9, 6
0x140007ff4  jz      short loc_14000802F
0x140007ff6  and     r8, 3Fh
0x140007ffa  jmp     short loc_140008000
0x140008000  movups  xmm1, xmmword ptr [rcx+rdx-10h]
0x140008005  movups  xmm2, xmmword ptr [rcx+rdx-20h]
0x14000800a  movups  xmm3, xmmword ptr [rcx+rdx-30h]
0x14000800f  movups  xmm4, xmmword ptr [rcx+rdx-40h]
0x140008014  movaps  xmmword ptr [rcx], xmm0
0x140008017  sub     rcx, 40h ; '@'
0x14000801b  dec     r9
0x14000801e  movaps  xmmword ptr [rcx+30h], xmm1
0x140008022  movaps  xmmword ptr [rcx+20h], xmm2
0x140008026  movaps  xmmword ptr [rcx+10h], xmm3
0x14000802a  movaps  xmm0, xmm4
0x14000802d  jnz     short loc_140008000
0x14000802f  mov     r9, r8
0x140008032  shr     r9, 4
0x140008036  jz      short loc_140008051
0x140008038  nop     dword ptr [rax+rax+00000000h]
0x140008040  movaps  xmmword ptr [rcx], xmm0
0x140008043  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x140008048  sub     rcx, 10h
0x14000804c  dec     r9
0x14000804f  jnz     short loc_140008040
0x140008051  and     r8, 0Fh
0x140008055  jz      short loc_140008066
0x140008057  mov     r11, rcx
0x14000805a  sub     r11, r8
0x14000805d  movups  xmm1, xmmword ptr [r11+rdx]
0x140008062  movups  xmmword ptr [r11], xmm1
0x140008066  movaps  xmmword ptr [rcx], xmm0
0x140008069  retn
```
