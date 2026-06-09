# memset

- ea: `0x140010bc0`
- end: `0x140010cc7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140006dec`
- `0x14000d3ac`
- `0x14000e7bc`
- `0x140012020`
- `0x140018010`
- `0x14001a8f0`

## callees

- `0x140010bc0`
- `0x140010d00`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  void *result; // rax
  __int64 v4; // rdx
  __m128 v5; // xmm0
  char *v6; // r8
  __m128 *v7; // rdx
  _OWORD *v8; // r9
  size_t v9; // r8
  __m128 *v10; // r9
  size_t v11; // r8
  _DWORD *v12; // r9
  size_t v13; // r8

  result = a1;
  v4 = 0x101010101010101LL * (unsigned __int8)Val;
  v5 = _mm_movelh_ps((__m128)(unsigned __int64)v4, (__m128)(unsigned __int64)v4);
  if ( Size >= 0x40 )
  {
    if ( (_isa_info & 2) != 0 && Size >= 0x320 )
      return (void *)_memset_repmovs();
    *(__m128 *)a1 = v5;
    v6 = (char *)a1 + Size;
    a1 = (void *)(((unsigned __int64)a1 + 16) & 0xFFFFFFFFFFFFFFF0uLL);
    Size = v6 - (_BYTE *)a1;
    if ( Size >= 0x40 )
    {
      v7 = (__m128 *)((char *)a1 + Size - 16);
      v8 = (_OWORD *)(((unsigned __int64)a1 + Size - 48) & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = Size >> 6;
      do
      {
        *(__m128 *)a1 = v5;
        *((__m128 *)a1 + 1) = v5;
        a1 = (char *)a1 + 64;
        --v9;
        *((__m128 *)a1 - 2) = v5;
        *((__m128 *)a1 - 1) = v5;
      }
      while ( v9 );
      *v8 = v5;
      v8[1] = v5;
      v8[2] = v5;
      *v7 = v5;
      return result;
    }
LABEL_9:
    v10 = (__m128 *)((char *)a1 + Size - 16);
    *(__m128 *)a1 = v5;
    v11 = (Size & 0x20) >> 1;
    *v10 = v5;
    *(__m128 *)((char *)a1 + v11) = v5;
    *(__m128 *)((char *)v10 - v11) = v5;
    return result;
  }
  if ( Size >= 0x10 )
    goto LABEL_9;
  if ( Size < 4 )
  {
    if ( Size )
    {
      *(_BYTE *)a1 = v4;
      if ( Size != 1 )
        *(_WORD *)((char *)a1 + Size - 2) = v4;
    }
  }
  else
  {
    v12 = (char *)a1 + Size - 4;
    *(_DWORD *)a1 = v4;
    v13 = (Size & 8) >> 1;
    *v12 = v4;
    *(_DWORD *)((char *)a1 + v13) = v4;
    *(_DWORD *)((char *)v12 - v13) = v4;
  }
  return result;
}

```

## disassembly

```asm
0x140010bc0  mov     rax, rcx
0x140010bc3  movzx   edx, dl
0x140010bc6  mov     r9, 101010101010101h
0x140010bd0  imul    rdx, r9
0x140010bd4  movq    xmm0, rdx
0x140010bd9  movlhps xmm0, xmm0
0x140010bdc  cmp     r8, 40h ; '@'
0x140010be0  jb      short loc_140010C50
0x140010be2  test    cs:__isa_info, 2
0x140010be9  jz      short loc_140010BF8
0x140010beb  cmp     r8, 320h
0x140010bf2  jnb     __memset_repmovs
0x140010bf8  movups  xmmword ptr [rcx], xmm0
0x140010bfb  add     r8, rcx
0x140010bfe  add     rcx, 10h
0x140010c02  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140010c06  sub     r8, rcx
0x140010c09  cmp     r8, 40h ; '@'
0x140010c0d  jb      short loc_140010C56
0x140010c0f  lea     rdx, [rcx+r8-10h]
0x140010c14  lea     r9, [rcx+r8-30h]
0x140010c19  and     r9, 0FFFFFFFFFFFFFFF0h
0x140010c1d  shr     r8, 6
0x140010c21  movaps  xmmword ptr [rcx], xmm0
0x140010c24  movaps  xmmword ptr [rcx+10h], xmm0
0x140010c28  add     rcx, 40h ; '@'
0x140010c2c  dec     r8
0x140010c2f  movaps  xmmword ptr [rcx-20h], xmm0
0x140010c33  movaps  xmmword ptr [rcx-10h], xmm0
0x140010c37  jnz     short loc_140010C21
0x140010c39  movaps  xmmword ptr [r9], xmm0
0x140010c3d  movaps  xmmword ptr [r9+10h], xmm0
0x140010c42  movaps  xmmword ptr [r9+20h], xmm0
0x140010c47  movups  xmmword ptr [rdx], xmm0
0x140010c4a  retn
0x140010c50  cmp     r8, 10h
0x140010c54  jb      short loc_140010C80
0x140010c56  lea     r9, [r8+rcx-10h]
0x140010c5b  and     r8, 20h
0x140010c5f  movups  xmmword ptr [rcx], xmm0
0x140010c62  shr     r8, 1
0x140010c65  movups  xmmword ptr [r9], xmm0
0x140010c69  movups  xmmword ptr [rcx+r8], xmm0
0x140010c6e  neg     r8
0x140010c71  movups  xmmword ptr [r9+r8], xmm0
0x140010c76  retn
0x140010c80  cmp     r8, 4
0x140010c84  jb      short loc_140010CB0
0x140010c86  lea     r9, [r8+rcx-4]
0x140010c8b  and     r8, 8
0x140010c8f  mov     [rcx], edx
0x140010c91  shr     r8, 1
0x140010c94  mov     [r9], edx
0x140010c97  mov     [rcx+r8], edx
0x140010c9b  neg     r8
0x140010c9e  mov     [r9+r8], edx
0x140010ca2  retn
0x140010cb0  test    r8, r8
0x140010cb3  jz      short locret_140010CC6
0x140010cb5  mov     [rcx], dl
0x140010cb7  lea     r9, [rcx+r8-2]
0x140010cbc  cmp     r8, 1
0x140010cc0  jz      short locret_140010CC6
0x140010cc2  mov     [r9], dx
0x140010cc6  retn
```
