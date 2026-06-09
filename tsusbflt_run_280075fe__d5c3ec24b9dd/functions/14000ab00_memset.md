# memset

- ea: `0x14000ab00`
- end: `0x14000ac07`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140001150`
- `0x140001e80`
- `0x140003acc`
- `0x140003f90`
- `0x140005754`
- `0x140005a54`
- `0x140005e44`
- `0x14000711c`
- `0x14000818c`
- `0x140008818`
- `0x1400092c8`
- `0x1400097b0`
- `0x140009eb4`
- `0x14000a0fc`
- `0x14000c020`
- `0x140012010`
- `0x140012b70`

## callees

- `0x14000ab00`
- `0x14000ac40`

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
0x14000ab00  mov     rax, rcx
0x14000ab03  movzx   edx, dl
0x14000ab06  mov     r9, 101010101010101h
0x14000ab10  imul    rdx, r9
0x14000ab14  movq    xmm0, rdx
0x14000ab19  movlhps xmm0, xmm0
0x14000ab1c  cmp     r8, 40h ; '@'
0x14000ab20  jb      short loc_14000AB90
0x14000ab22  test    cs:__isa_info, 2
0x14000ab29  jz      short loc_14000AB38
0x14000ab2b  cmp     r8, 320h
0x14000ab32  jnb     __memset_repmovs
0x14000ab38  movups  xmmword ptr [rcx], xmm0
0x14000ab3b  add     r8, rcx
0x14000ab3e  add     rcx, 10h
0x14000ab42  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000ab46  sub     r8, rcx
0x14000ab49  cmp     r8, 40h ; '@'
0x14000ab4d  jb      short loc_14000AB96
0x14000ab4f  lea     rdx, [rcx+r8-10h]
0x14000ab54  lea     r9, [rcx+r8-30h]
0x14000ab59  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000ab5d  shr     r8, 6
0x14000ab61  movaps  xmmword ptr [rcx], xmm0
0x14000ab64  movaps  xmmword ptr [rcx+10h], xmm0
0x14000ab68  add     rcx, 40h ; '@'
0x14000ab6c  dec     r8
0x14000ab6f  movaps  xmmword ptr [rcx-20h], xmm0
0x14000ab73  movaps  xmmword ptr [rcx-10h], xmm0
0x14000ab77  jnz     short loc_14000AB61
0x14000ab79  movaps  xmmword ptr [r9], xmm0
0x14000ab7d  movaps  xmmword ptr [r9+10h], xmm0
0x14000ab82  movaps  xmmword ptr [r9+20h], xmm0
0x14000ab87  movups  xmmword ptr [rdx], xmm0
0x14000ab8a  retn
0x14000ab90  cmp     r8, 10h
0x14000ab94  jb      short loc_14000ABC0
0x14000ab96  lea     r9, [r8+rcx-10h]
0x14000ab9b  and     r8, 20h
0x14000ab9f  movups  xmmword ptr [rcx], xmm0
0x14000aba2  shr     r8, 1
0x14000aba5  movups  xmmword ptr [r9], xmm0
0x14000aba9  movups  xmmword ptr [rcx+r8], xmm0
0x14000abae  neg     r8
0x14000abb1  movups  xmmword ptr [r9+r8], xmm0
0x14000abb6  retn
0x14000abc0  cmp     r8, 4
0x14000abc4  jb      short loc_14000ABF0
0x14000abc6  lea     r9, [r8+rcx-4]
0x14000abcb  and     r8, 8
0x14000abcf  mov     [rcx], edx
0x14000abd1  shr     r8, 1
0x14000abd4  mov     [r9], edx
0x14000abd7  mov     [rcx+r8], edx
0x14000abdb  neg     r8
0x14000abde  mov     [r9+r8], edx
0x14000abe2  retn
0x14000abf0  test    r8, r8
0x14000abf3  jz      short locret_14000AC06
0x14000abf5  mov     [rcx], dl
0x14000abf7  lea     r9, [rcx+r8-2]
0x14000abfc  cmp     r8, 1
0x14000ac00  jz      short locret_14000AC06
0x14000ac02  mov     [r9], dx
0x14000ac06  retn
```
