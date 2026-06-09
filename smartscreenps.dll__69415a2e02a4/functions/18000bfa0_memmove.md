# memmove

- ea: `0x18000bfa0`
- end: `0x18000c61d`
- name: `memmove`
- size: `1661`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003760`
- `0x180003930`
- `0x18000a028`

## callees

- `0x18000bf80`
- `0x18000bfa0`

## pseudocode

```c
void *__cdecl memmove(void *_RCX, const void *Src, size_t Size)
{
  void *result; // rax
  int v4; // ecx
  __int16 v5; // r9
  char v6; // r10
  __int16 v7; // cx
  char v8; // r9
  __int16 v9; // r8
  char v10; // r9
  int v11; // ecx
  __int16 v12; // r9
  char v13; // r8
  int v14; // ecx
  char v15; // r9
  __int16 v16; // cx
  char v17; // cl
  int v18; // ecx
  __int16 v19; // r8
  char v20; // r8
  __m128i v21; // xmm2
  char *v22; // r9
  char *v23; // r9
  __int64 v26; // r9
  __m128i v59; // xmm0
  __m128i v60; // xmm5
  __int64 v61; // r9
  __m128i v62; // xmm2
  __m128i v63; // xmm3
  __m128i v64; // xmm4
  __m128i v65; // xmm2
  __m128i v66; // xmm3
  __m128i v67; // xmm4
  size_t v68; // r9
  __int128 v69; // xmm2
  signed __int64 v70; // rdx
  char *v71; // rcx
  __int128 v72; // xmm0
  unsigned __int64 v73; // rcx
  size_t v74; // r8
  _OWORD *v75; // r9
  __int128 v76; // xmm1
  size_t v77; // r9
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm1
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  size_t i; // r9

  result = _RCX;
  switch ( Size )
  {
    case 0uLL:
      return result;
    case 1uLL:
      *(_BYTE *)_RCX = *(_BYTE *)Src;
      return result;
    case 2uLL:
      *(_WORD *)_RCX = *(_WORD *)Src;
      return result;
    case 3uLL:
      v13 = *((_BYTE *)Src + 2);
      *(_WORD *)_RCX = *(_WORD *)Src;
      *((_BYTE *)_RCX + 2) = v13;
      return result;
    case 4uLL:
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      return result;
    case 5uLL:
      v20 = *((_BYTE *)Src + 4);
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      *((_BYTE *)_RCX + 4) = v20;
      return result;
    case 6uLL:
      v19 = *((_WORD *)Src + 2);
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      *((_WORD *)_RCX + 2) = v19;
      return result;
    case 7uLL:
      v9 = *((_WORD *)Src + 2);
      v10 = *((_BYTE *)Src + 6);
      *(_DWORD *)_RCX = *(_DWORD *)Src;
      *((_WORD *)_RCX + 2) = v9;
      *((_BYTE *)_RCX + 6) = v10;
      return result;
    case 8uLL:
      *(_QWORD *)_RCX = *(_QWORD *)Src;
      return result;
    case 9uLL:
      v17 = *((_BYTE *)Src + 8);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_BYTE *)result + 8) = v17;
      return result;
    case 0xAuLL:
      v16 = *((_WORD *)Src + 4);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_WORD *)result + 4) = v16;
      return result;
    case 0xBuLL:
      v7 = *((_WORD *)Src + 4);
      v8 = *((_BYTE *)Src + 10);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_WORD *)result + 4) = v7;
      *((_BYTE *)result + 10) = v8;
      return result;
    case 0xCuLL:
      v18 = *((_DWORD *)Src + 2);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v18;
      return result;
    case 0xDuLL:
      v14 = *((_DWORD *)Src + 2);
      v15 = *((_BYTE *)Src + 12);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v14;
      *((_BYTE *)result + 12) = v15;
      return result;
    case 0xEuLL:
      v11 = *((_DWORD *)Src + 2);
      v12 = *((_WORD *)Src + 6);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v11;
      *((_WORD *)result + 6) = v12;
      return result;
    case 0xFuLL:
      v4 = *((_DWORD *)Src + 2);
      v5 = *((_WORD *)Src + 6);
      v6 = *((_BYTE *)Src + 14);
      *(_QWORD *)result = *(_QWORD *)Src;
      *((_DWORD *)result + 2) = v4;
      *((_WORD *)result + 6) = v5;
      *((_BYTE *)result + 14) = v6;
      return result;
    default:
      if ( Size <= 0x20 )
      {
        v21 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
        *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
        *(__m128i *)((char *)_RCX + Size - 16) = v21;
        return result;
      }
      v22 = (char *)Src + Size;
      if ( _RCX <= Src )
        v22 = (char *)_RCX;
      if ( _RCX < v22 )
      {
        v69 = *(_OWORD *)Src;
        v70 = (_BYTE *)Src - (_BYTE *)_RCX;
        v71 = (char *)_RCX + Size;
        v72 = *(_OWORD *)&v71[v70 - 16];
        v73 = (unsigned __int64)(v71 - 16);
        v74 = Size - 16;
        if ( (v73 & 0xF) != 0 )
        {
          v75 = (_OWORD *)v73;
          v73 &= 0xFFFFFFFFFFFFFFF0uLL;
          v76 = v72;
          v72 = *(_OWORD *)(v73 + v70);
          *v75 = v76;
          v74 = v73 - (_QWORD)result;
        }
        v77 = v74 >> 7;
        if ( v74 >> 7 )
        {
          for ( *(_OWORD *)v73 = v72; ; *(_OWORD *)v73 = v83 )
          {
            v78 = *(_OWORD *)(v73 + v70 - 16);
            v79 = *(_OWORD *)(v73 + v70 - 32);
            v73 -= 128LL;
            *(_OWORD *)(v73 + 112) = v78;
            *(_OWORD *)(v73 + 96) = v79;
            v80 = *(_OWORD *)(v73 + v70 + 64);
            --v77;
            *(_OWORD *)(v73 + 80) = *(_OWORD *)(v73 + v70 + 80);
            *(_OWORD *)(v73 + 64) = v80;
            v81 = *(_OWORD *)(v73 + v70 + 32);
            *(_OWORD *)(v73 + 48) = *(_OWORD *)(v73 + v70 + 48);
            *(_OWORD *)(v73 + 32) = v81;
            v82 = *(_OWORD *)(v73 + v70 + 16);
            v83 = *(_OWORD *)(v73 + v70);
            if ( !v77 )
              break;
            *(_OWORD *)(v73 + 16) = v82;
          }
          *(_OWORD *)(v73 + 16) = v82;
          v74 &= 0x7Fu;
          v72 = v83;
        }
        for ( i = v74 >> 4; i; --i )
        {
          *(_OWORD *)v73 = v72;
          v73 -= 16LL;
          v72 = *(_OWORD *)(v73 + v70);
        }
        if ( (v74 & 0xF) != 0 )
          *(_OWORD *)result = v69;
        *(_OWORD *)v73 = v72;
        return result;
      }
      if ( (unsigned int)_isa_available < 3 )
      {
        if ( Size <= 0x800 || (_favor & 2) == 0 )
        {
          v59 = _mm_loadu_si128((const __m128i *)Src);
          v60 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
          if ( Size > 0x80 )
          {
            v61 = ((unsigned __int8)_RCX & 0xF) - 16LL;
            _RCX = (char *)_RCX - v61;
            Src = (char *)Src - v61;
            Size += v61;
            if ( Size > 0x80 )
            {
              do
              {
                v62 = _mm_loadu_si128((const __m128i *)Src + 1);
                v63 = _mm_loadu_si128((const __m128i *)Src + 2);
                v64 = _mm_loadu_si128((const __m128i *)Src + 3);
                *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
                *((__m128i *)_RCX + 1) = v62;
                *((__m128i *)_RCX + 2) = v63;
                *((__m128i *)_RCX + 3) = v64;
                v65 = _mm_loadu_si128((const __m128i *)Src + 5);
                v66 = _mm_loadu_si128((const __m128i *)Src + 6);
                v67 = _mm_loadu_si128((const __m128i *)Src + 7);
                *((__m128i *)_RCX + 4) = _mm_loadu_si128((const __m128i *)Src + 4);
                *((__m128i *)_RCX + 5) = v65;
                *((__m128i *)_RCX + 6) = v66;
                *((__m128i *)_RCX + 7) = v67;
                _RCX = (char *)_RCX + 128;
                Src = (char *)Src + 128;
                Size -= 128LL;
              }
              while ( Size >= 0x80 );
            }
          }
          v68 = (Size + 15) & 0xFFFFFFFFFFFFFFF0uLL;
          switch ( v68 >> 4 )
          {
            case 0uLL:
              goto LABEL_68;
            case 1uLL:
              goto LABEL_67;
            case 2uLL:
              goto LABEL_66;
            case 3uLL:
              goto LABEL_65;
            case 4uLL:
              goto LABEL_64;
            case 5uLL:
              goto LABEL_63;
            case 6uLL:
              goto LABEL_62;
            case 7uLL:
              goto LABEL_61;
            case 8uLL:
              *(__m128i *)((char *)_RCX + v68 - 128) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 128));
LABEL_61:
              *(__m128i *)((char *)_RCX + v68 - 112) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 112));
LABEL_62:
              *(__m128i *)((char *)_RCX + v68 - 96) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 96));
LABEL_63:
              *(__m128i *)((char *)_RCX + v68 - 80) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 80));
LABEL_64:
              *(__m128i *)((char *)_RCX + v68 - 64) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 64));
LABEL_65:
              *(__m128i *)((char *)_RCX + v68 - 48) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 48));
LABEL_66:
              *(__m128i *)((char *)_RCX + v68 - 32) = _mm_loadu_si128((const __m128i *)((char *)Src + v68 - 32));
LABEL_67:
              *(__m128i *)((char *)_RCX + Size - 16) = v60;
LABEL_68:
              *(__m128i *)result = v59;
              break;
          }
          return result;
        }
        return (void *)memcpy_repmovs();
      }
      if ( Size > 0x2000 && Size <= 0x180000 )
      {
        v23 = (char *)_RCX + 64;
        if ( _RCX > Src )
          v23 = (char *)Src;
        if ( v23 <= Src && (_favor & 2) != 0 )
          return (void *)memcpy_repmovs();
      }
      __asm
      {
        vmovdqu ymm0, ymmword ptr [rdx]
        vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
      }
      if ( Size <= 0x100
        || (v26 = ((unsigned __int8)_RCX & 0x1F) - 32LL,
            _RCX = (char *)_RCX - v26,
            Src = (char *)Src - v26,
            Size += v26,
            Size <= 0x100) )
      {
LABEL_33:
        _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto LABEL_42;
          case 1uLL:
            goto LABEL_41;
          case 2uLL:
            goto LABEL_40;
          case 3uLL:
            goto LABEL_39;
          case 4uLL:
            goto LABEL_38;
          case 5uLL:
            goto LABEL_37;
          case 6uLL:
            goto LABEL_36;
          case 7uLL:
            goto LABEL_35;
          case 8uLL:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C222 case 8
              vmovdqu ymmword ptr [rcx+r9-100h], ymm1
            }
LABEL_35:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C222 case 7
              vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
            }
LABEL_36:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C222 case 6
              vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
            }
LABEL_37:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C222 case 5
              vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
            }
LABEL_38:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C222 case 4
              vmovdqu ymmword ptr [rcx+r9-80h], ymm1
            }
LABEL_39:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C222 case 3
              vmovdqu ymmword ptr [rcx+r9-60h], ymm1
            }
LABEL_40:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C222 case 2
              vmovdqu ymmword ptr [rcx+r9-40h], ymm1
            }
LABEL_41:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C222 case 1 }
LABEL_42:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C222 case 0
              vzeroupper
            }
            break;
        }
        return result;
      }
      if ( Size <= 0x180000 )
      {
        do
        {
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx]
            vmovdqu ymm2, ymmword ptr [rdx+20h]
            vmovdqu ymm3, ymmword ptr [rdx+40h]
            vmovdqu ymm4, ymmword ptr [rdx+60h]
            vmovdqa ymmword ptr [rcx], ymm1
            vmovdqa ymmword ptr [rcx+20h], ymm2
            vmovdqa ymmword ptr [rcx+40h], ymm3
            vmovdqa ymmword ptr [rcx+60h], ymm4
            vmovdqu ymm1, ymmword ptr [rdx+80h]
            vmovdqu ymm2, ymmword ptr [rdx+0A0h]
            vmovdqu ymm3, ymmword ptr [rdx+0C0h]
            vmovdqu ymm4, ymmword ptr [rdx+0E0h]
            vmovdqa ymmword ptr [rcx+80h], ymm1
            vmovdqa ymmword ptr [rcx+0A0h], ymm2
            vmovdqa ymmword ptr [rcx+0C0h], ymm3
            vmovdqa ymmword ptr [rcx+0E0h], ymm4
          }
          _RCX = (char *)_RCX + 256;
          Src = (char *)Src + 256;
          Size -= 256LL;
        }
        while ( Size >= 0x100 );
        goto LABEL_33;
      }
      do
      {
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx]
          vmovdqu ymm2, ymmword ptr [rdx+20h]
          vmovdqu ymm3, ymmword ptr [rdx+40h]
          vmovdqu ymm4, ymmword ptr [rdx+60h]
          vmovntdq ymmword ptr [rcx], ymm1
          vmovntdq ymmword ptr [rcx+20h], ymm2
          vmovntdq ymmword ptr [rcx+40h], ymm3
          vmovntdq ymmword ptr [rcx+60h], ymm4
          vmovdqu ymm1, ymmword ptr [rdx+80h]
          vmovdqu ymm2, ymmword ptr [rdx+0A0h]
          vmovdqu ymm3, ymmword ptr [rdx+0C0h]
          vmovdqu ymm4, ymmword ptr [rdx+0E0h]
          vmovntdq ymmword ptr [rcx+80h], ymm1
          vmovntdq ymmword ptr [rcx+0A0h], ymm2
          vmovntdq ymmword ptr [rcx+0C0h], ymm3
          vmovntdq ymmword ptr [rcx+0E0h], ymm4
        }
        _RCX = (char *)_RCX + 256;
        Src = (char *)Src + 256;
        Size -= 256LL;
      }
      while ( Size >= 0x100 );
      _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
      switch ( _R9 >> 5 )
      {
        case 0uLL:
          goto LABEL_53;
        case 1uLL:
          goto LABEL_52;
        case 2uLL:
          goto LABEL_51;
        case 3uLL:
          goto LABEL_50;
        case 4uLL:
          goto LABEL_49;
        case 5uLL:
          goto LABEL_48;
        case 6uLL:
          goto LABEL_47;
        case 7uLL:
          goto LABEL_46;
        case 8uLL:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C352 case 8
            vmovntdq ymmword ptr [rcx+r9-100h], ymm1
          }
LABEL_46:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C352 case 7
            vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
          }
LABEL_47:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C352 case 6
            vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
          }
LABEL_48:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C352 case 5
            vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
          }
LABEL_49:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C352 case 4
            vmovntdq ymmword ptr [rcx+r9-80h], ymm1
          }
LABEL_50:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C352 case 3
            vmovntdq ymmword ptr [rcx+r9-60h], ymm1
          }
LABEL_51:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C352 case 2
            vmovntdq ymmword ptr [rcx+r9-40h], ymm1
          }
LABEL_52:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C352 case 1 }
LABEL_53:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C352 case 0 }
          _mm_sfence();
          __asm { vzeroupper }
          break;
      }
      return result;
  }
}

```

## disassembly

```asm
0x18000bfa0  mov     rax, rcx
0x18000bfa3  lea     r10, cs:180000000h
0x18000bfaa  cmp     r8, 0Fh; switch 16 cases
0x18000bfae  ja      def_18000BFCB; jumptable 000000018000BFCB default case
0x18000bfb4  nop     word ptr [rax+rax+00000000h]
0x18000bfc0  mov     r9d, ds:(jpt_18000BFCB - 180000000h)[r10+r8*4]
0x18000bfc8  add     r9, r10
0x18000bfcb  jmp     r9; switch jump
0x18000bfce  retn; jumptable 000000018000BFCB case 0
0x18000bfd0  mov     r8, [rdx]; jumptable 000000018000BFCB case 15
0x18000bfd3  mov     ecx, [rdx+8]
0x18000bfd6  movzx   r9d, word ptr [rdx+0Ch]
0x18000bfdb  movzx   r10d, byte ptr [rdx+0Eh]
0x18000bfe0  mov     [rax], r8
0x18000bfe3  mov     [rax+8], ecx
0x18000bfe6  mov     [rax+0Ch], r9w
0x18000bfeb  mov     [rax+0Eh], r10b
0x18000bfef  retn
0x18000bff0  mov     r8, [rdx]; jumptable 000000018000BFCB case 11
0x18000bff3  movzx   ecx, word ptr [rdx+8]
0x18000bff7  movzx   r9d, byte ptr [rdx+0Ah]
0x18000bffc  mov     [rax], r8
0x18000bfff  mov     [rax+8], cx
0x18000c003  mov     [rax+0Ah], r9b
0x18000c007  retn
0x18000c008  movzx   ecx, word ptr [rdx]; jumptable 000000018000BFCB case 2
0x18000c00b  mov     [rax], cx
0x18000c00e  retn
0x18000c010  mov     ecx, [rdx]; jumptable 000000018000BFCB case 7
0x18000c012  movzx   r8d, word ptr [rdx+4]
0x18000c017  movzx   r9d, byte ptr [rdx+6]
0x18000c01c  mov     [rax], ecx
0x18000c01e  mov     [rax+4], r8w
0x18000c023  mov     [rax+6], r9b
0x18000c027  retn
0x18000c028  mov     r8, [rdx]; jumptable 000000018000BFCB case 14
0x18000c02b  mov     ecx, [rdx+8]
0x18000c02e  movzx   r9d, word ptr [rdx+0Ch]
0x18000c033  mov     [rax], r8
0x18000c036  mov     [rax+8], ecx
0x18000c039  mov     [rax+0Ch], r9w
0x18000c03e  retn
0x18000c03f  movzx   ecx, word ptr [rdx]; jumptable 000000018000BFCB case 3
0x18000c042  movzx   r8d, byte ptr [rdx+2]
0x18000c047  mov     [rax], cx
0x18000c04a  mov     [rax+2], r8b
0x18000c04e  retn
0x18000c050  mov     r8, [rdx]; jumptable 000000018000BFCB case 13
0x18000c053  mov     ecx, [rdx+8]
0x18000c056  movzx   r9d, byte ptr [rdx+0Ch]
0x18000c05b  mov     [rax], r8
0x18000c05e  mov     [rax+8], ecx
0x18000c061  mov     [rax+0Ch], r9b
0x18000c065  retn
0x18000c066  mov     r8, [rdx]; jumptable 000000018000BFCB case 10
0x18000c069  movzx   ecx, word ptr [rdx+8]
0x18000c06d  mov     [rax], r8
0x18000c070  mov     [rax+8], cx
0x18000c074  retn
0x18000c075  mov     r8, [rdx]; jumptable 000000018000BFCB case 9
0x18000c078  movzx   ecx, byte ptr [rdx+8]
0x18000c07c  mov     [rax], r8
0x18000c07f  mov     [rax+8], cl
0x18000c082  retn
0x18000c083  mov     r8, [rdx]; jumptable 000000018000BFCB case 12
0x18000c086  mov     ecx, [rdx+8]
0x18000c089  mov     [rax], r8
0x18000c08c  mov     [rax+8], ecx
0x18000c08f  retn
0x18000c090  mov     ecx, [rdx]; jumptable 000000018000BFCB case 6
0x18000c092  movzx   r8d, word ptr [rdx+4]
0x18000c097  mov     [rax], ecx
0x18000c099  mov     [rax+4], r8w
0x18000c09e  retn
0x18000c09f  mov     ecx, [rdx]; jumptable 000000018000BFCB case 5
0x18000c0a1  movzx   r8d, byte ptr [rdx+4]
0x18000c0a6  mov     [rax], ecx
0x18000c0a8  mov     [rax+4], r8b
0x18000c0ac  retn
0x18000c0ad  mov     rcx, [rdx]; jumptable 000000018000BFCB case 8
0x18000c0b0  mov     [rax], rcx
0x18000c0b3  retn
0x18000c0b4  movzx   ecx, byte ptr [rdx]; jumptable 000000018000BFCB case 1
0x18000c0b7  mov     [rax], cl
0x18000c0b9  retn
0x18000c0ba  mov     ecx, [rdx]; jumptable 000000018000BFCB case 4
0x18000c0bc  mov     [rax], ecx
0x18000c0be  retn
0x18000c0c0  cmp     r8, 20h ; ' '; jumptable 000000018000BFCB default case
0x18000c0c4  ja      short loc_18000C0DD
0x18000c0c6  movdqu  xmm1, xmmword ptr [rdx]
0x18000c0ca  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x18000c0d1  movdqu  xmmword ptr [rcx], xmm1
0x18000c0d5  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x18000c0dc  retn
0x18000c0dd  lea     r9, [rdx+r8]
0x18000c0e1  cmp     rcx, rdx
0x18000c0e4  cmovbe  r9, rcx
0x18000c0e8  cmp     rcx, r9
0x18000c0eb  jb      loc_18000C540
0x18000c0f1  cmp     cs:__isa_available, 3
0x18000c0f8  jb      loc_18000C3F0
0x18000c0fe  cmp     r8, 2000h
0x18000c105  jbe     short loc_18000C12D
0x18000c107  cmp     r8, 180000h
0x18000c10e  ja      short loc_18000C12D
0x18000c110  lea     r9, [rcx+40h]
0x18000c114  cmp     rcx, rdx
0x18000c117  cmova   r9, rdx
0x18000c11b  cmp     r9, rdx
0x18000c11e  ja      short loc_18000C12D
0x18000c120  test    byte ptr cs:__favor, 2
0x18000c127  jnz     memcpy_repmovs
0x18000c12d  vmovdqu ymm0, ymmword ptr [rdx]
0x18000c131  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x18000c138  cmp     r8, 100h
0x18000c13f  jbe     loc_18000C208
0x18000c145  mov     r9, rcx
0x18000c148  and     r9, 1Fh
0x18000c14c  sub     r9, 20h ; ' '
0x18000c150  sub     rcx, r9
0x18000c153  sub     rdx, r9
0x18000c156  add     r8, r9
0x18000c159  cmp     r8, 100h
0x18000c160  jbe     loc_18000C208
0x18000c166  cmp     r8, 180000h
0x18000c16d  ja      loc_18000C2B0
0x18000c173  nop     word ptr [rax+rax+00000000h]
0x18000c180  vmovdqu ymm1, ymmword ptr [rdx]
0x18000c184  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18000c189  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18000c18e  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18000c193  vmovdqa ymmword ptr [rcx], ymm1
0x18000c197  vmovdqa ymmword ptr [rcx+20h], ymm2
0x18000c19c  vmovdqa ymmword ptr [rcx+40h], ymm3
0x18000c1a1  vmovdqa ymmword ptr [rcx+60h], ymm4
0x18000c1a6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18000c1ae  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18000c1b6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18000c1be  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18000c1c6  vmovdqa ymmword ptr [rcx+80h], ymm1
0x18000c1ce  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x18000c1d6  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x18000c1de  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x18000c1e6  add     rcx, 100h
0x18000c1ed  add     rdx, 100h
0x18000c1f4  sub     r8, 100h
0x18000c1fb  cmp     r8, 100h
0x18000c202  jnb     loc_18000C180
0x18000c208  lea     r9, [r8+1Fh]
0x18000c20c  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000c210  mov     r11, r9
0x18000c213  shr     r11, 5
0x18000c217  mov     r11d, ds:(jpt_18000C222 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000c21f  add     r11, r10
0x18000c222  jmp     r11; switch jump
0x18000c225  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C222 case 8
0x18000c22f  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x18000c239  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C222 case 7
0x18000c243  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x18000c24d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C222 case 6
0x18000c257  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x18000c261  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C222 case 5
0x18000c26b  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x18000c275  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C222 case 4
0x18000c27c  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x18000c283  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C222 case 3
0x18000c28a  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x18000c291  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C222 case 2
0x18000c298  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x18000c29f  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C222 case 1
0x18000c2a6  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C222 case 0
0x18000c2aa  vzeroupper
0x18000c2ad  retn
0x18000c2b0  vmovdqu ymm1, ymmword ptr [rdx]
0x18000c2b4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18000c2b9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18000c2be  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18000c2c3  vmovntdq ymmword ptr [rcx], ymm1
0x18000c2c7  vmovntdq ymmword ptr [rcx+20h], ymm2
0x18000c2cc  vmovntdq ymmword ptr [rcx+40h], ymm3
0x18000c2d1  vmovntdq ymmword ptr [rcx+60h], ymm4
0x18000c2d6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18000c2de  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18000c2e6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18000c2ee  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18000c2f6  vmovntdq ymmword ptr [rcx+80h], ymm1
0x18000c2fe  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x18000c306  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x18000c30e  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x18000c316  add     rcx, 100h
0x18000c31d  add     rdx, 100h
0x18000c324  sub     r8, 100h
0x18000c32b  cmp     r8, 100h
0x18000c332  jnb     loc_18000C2B0
0x18000c338  lea     r9, [r8+1Fh]
0x18000c33c  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000c340  mov     r11, r9
0x18000c343  shr     r11, 5
0x18000c347  mov     r11d, ds:(jpt_18000C352 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000c34f  add     r11, r10
0x18000c352  jmp     r11; switch jump
0x18000c355  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C352 case 8
0x18000c35f  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x18000c369  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C352 case 7
0x18000c373  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x18000c37d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C352 case 6
0x18000c387  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x18000c391  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C352 case 5
0x18000c39b  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x18000c3a5  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C352 case 4
0x18000c3ac  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x18000c3b3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C352 case 3
0x18000c3ba  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x18000c3c1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C352 case 2
0x18000c3c8  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x18000c3cf  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C352 case 1
0x18000c3d6  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C352 case 0
0x18000c3da  sfence
0x18000c3dd  vzeroupper
0x18000c3e0  retn
0x18000c3f0  cmp     r8, 800h
0x18000c3f7  jbe     short loc_18000C406
0x18000c3f9  test    byte ptr cs:__favor, 2
0x18000c400  jnz     memcpy_repmovs
0x18000c406  movdqu  xmm0, xmmword ptr [rdx]
0x18000c40a  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x18000c411  cmp     r8, 80h
0x18000c418  jbe     loc_18000C4AC
0x18000c41e  mov     r9, rcx
0x18000c421  and     r9, 0Fh
0x18000c425  sub     r9, 10h
0x18000c429  sub     rcx, r9
0x18000c42c  sub     rdx, r9
0x18000c42f  add     r8, r9
0x18000c432  cmp     r8, 80h
0x18000c439  jbe     short loc_18000C4AC
0x18000c43b  nop     dword ptr [rax+rax+00h]
0x18000c440  movdqu  xmm1, xmmword ptr [rdx]
0x18000c444  movdqu  xmm2, xmmword ptr [rdx+10h]
0x18000c449  movdqu  xmm3, xmmword ptr [rdx+20h]
0x18000c44e  movdqu  xmm4, xmmword ptr [rdx+30h]
0x18000c453  movdqa  xmmword ptr [rcx], xmm1
0x18000c457  movdqa  xmmword ptr [rcx+10h], xmm2
0x18000c45c  movdqa  xmmword ptr [rcx+20h], xmm3
0x18000c461  movdqa  xmmword ptr [rcx+30h], xmm4
0x18000c466  movdqu  xmm1, xmmword ptr [rdx+40h]
0x18000c46b  movdqu  xmm2, xmmword ptr [rdx+50h]
0x18000c470  movdqu  xmm3, xmmword ptr [rdx+60h]
0x18000c475  movdqu  xmm4, xmmword ptr [rdx+70h]
0x18000c47a  movdqa  xmmword ptr [rcx+40h], xmm1
0x18000c47f  movdqa  xmmword ptr [rcx+50h], xmm2
0x18000c484  movdqa  xmmword ptr [rcx+60h], xmm3
0x18000c489  movdqa  xmmword ptr [rcx+70h], xmm4
0x18000c48e  add     rcx, 80h
0x18000c495  add     rdx, 80h
0x18000c49c  sub     r8, 80h
0x18000c4a3  cmp     r8, 80h
0x18000c4aa  jnb     short loc_18000C440
0x18000c4ac  lea     r9, [r8+0Fh]
0x18000c4b0  and     r9, 0FFFFFFFFFFFFFFF0h
0x18000c4b4  mov     r11, r9
0x18000c4b7  shr     r11, 4
0x18000c4bb  mov     r11d, ds:(jpt_18000C4C6 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000c4c3  add     r11, r10
0x18000c4c6  jmp     r11; switch jump
0x18000c4c9  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 000000018000C4C6 case 8
0x18000c4d0  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x18000c4d7  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 000000018000C4C6 case 7
0x18000c4de  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x18000c4e5  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 000000018000C4C6 case 6
0x18000c4ec  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x18000c4f3  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 000000018000C4C6 case 5
0x18000c4fa  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x18000c501  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 000000018000C4C6 case 4
0x18000c508  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x18000c50f  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 000000018000C4C6 case 3
0x18000c516  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x18000c51d  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 000000018000C4C6 case 2
0x18000c524  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x18000c52b  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 000000018000C4C6 case 1
0x18000c532  movdqu  xmmword ptr [rax], xmm0; jumptable 000000018000C4C6 case 0
0x18000c536  retn
0x18000c540  movups  xmm2, xmmword ptr [rdx]
0x18000c543  sub     rdx, rcx
0x18000c546  add     rcx, r8
0x18000c549  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18000c54e  sub     rcx, 10h
0x18000c552  sub     r8, 10h
0x18000c556  test    cl, 0Fh
0x18000c559  jz      short loc_18000C573
0x18000c55b  mov     r9, rcx
0x18000c55e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c562  movups  xmm1, xmm0
0x18000c565  movups  xmm0, xmmword ptr [rcx+rdx]
0x18000c569  movups  xmmword ptr [r9], xmm1
0x18000c56d  mov     r8, rcx
0x18000c570  sub     r8, rax
0x18000c573  mov     r9, r8
0x18000c576  shr     r9, 7
  ... truncated ...
```
