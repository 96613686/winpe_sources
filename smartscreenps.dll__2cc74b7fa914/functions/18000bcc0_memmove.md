# memmove

- ea: `0x18000bcc0`
- end: `0x18000c33d`
- name: `memmove`
- size: `1661`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003760`
- `0x180003930`
- `0x180009dfc`

## callees

- `0x18000bca0`
- `0x18000bcc0`

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
              vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000BF42 case 8
              vmovdqu ymmword ptr [rcx+r9-100h], ymm1
            }
LABEL_35:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000BF42 case 7
              vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
            }
LABEL_36:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000BF42 case 6
              vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
            }
LABEL_37:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000BF42 case 5
              vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
            }
LABEL_38:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000BF42 case 4
              vmovdqu ymmword ptr [rcx+r9-80h], ymm1
            }
LABEL_39:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000BF42 case 3
              vmovdqu ymmword ptr [rcx+r9-60h], ymm1
            }
LABEL_40:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000BF42 case 2
              vmovdqu ymmword ptr [rcx+r9-40h], ymm1
            }
LABEL_41:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000BF42 case 1 }
LABEL_42:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BF42 case 0
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
            vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C072 case 8
            vmovntdq ymmword ptr [rcx+r9-100h], ymm1
          }
LABEL_46:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C072 case 7
            vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
          }
LABEL_47:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C072 case 6
            vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
          }
LABEL_48:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C072 case 5
            vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
          }
LABEL_49:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C072 case 4
            vmovntdq ymmword ptr [rcx+r9-80h], ymm1
          }
LABEL_50:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C072 case 3
            vmovntdq ymmword ptr [rcx+r9-60h], ymm1
          }
LABEL_51:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C072 case 2
            vmovntdq ymmword ptr [rcx+r9-40h], ymm1
          }
LABEL_52:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C072 case 1 }
LABEL_53:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C072 case 0 }
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
0x18000bcc0  mov     rax, rcx
0x18000bcc3  lea     r10, cs:180000000h
0x18000bcca  cmp     r8, 0Fh; switch 16 cases
0x18000bcce  ja      def_18000BCEB; jumptable 000000018000BCEB default case
0x18000bcd4  nop     word ptr [rax+rax+00000000h]
0x18000bce0  mov     r9d, ds:(jpt_18000BCEB - 180000000h)[r10+r8*4]
0x18000bce8  add     r9, r10
0x18000bceb  jmp     r9; switch jump
0x18000bcee  retn; jumptable 000000018000BCEB case 0
0x18000bcf0  mov     r8, [rdx]; jumptable 000000018000BCEB case 15
0x18000bcf3  mov     ecx, [rdx+8]
0x18000bcf6  movzx   r9d, word ptr [rdx+0Ch]
0x18000bcfb  movzx   r10d, byte ptr [rdx+0Eh]
0x18000bd00  mov     [rax], r8
0x18000bd03  mov     [rax+8], ecx
0x18000bd06  mov     [rax+0Ch], r9w
0x18000bd0b  mov     [rax+0Eh], r10b
0x18000bd0f  retn
0x18000bd10  mov     r8, [rdx]; jumptable 000000018000BCEB case 11
0x18000bd13  movzx   ecx, word ptr [rdx+8]
0x18000bd17  movzx   r9d, byte ptr [rdx+0Ah]
0x18000bd1c  mov     [rax], r8
0x18000bd1f  mov     [rax+8], cx
0x18000bd23  mov     [rax+0Ah], r9b
0x18000bd27  retn
0x18000bd28  movzx   ecx, word ptr [rdx]; jumptable 000000018000BCEB case 2
0x18000bd2b  mov     [rax], cx
0x18000bd2e  retn
0x18000bd30  mov     ecx, [rdx]; jumptable 000000018000BCEB case 7
0x18000bd32  movzx   r8d, word ptr [rdx+4]
0x18000bd37  movzx   r9d, byte ptr [rdx+6]
0x18000bd3c  mov     [rax], ecx
0x18000bd3e  mov     [rax+4], r8w
0x18000bd43  mov     [rax+6], r9b
0x18000bd47  retn
0x18000bd48  mov     r8, [rdx]; jumptable 000000018000BCEB case 14
0x18000bd4b  mov     ecx, [rdx+8]
0x18000bd4e  movzx   r9d, word ptr [rdx+0Ch]
0x18000bd53  mov     [rax], r8
0x18000bd56  mov     [rax+8], ecx
0x18000bd59  mov     [rax+0Ch], r9w
0x18000bd5e  retn
0x18000bd5f  movzx   ecx, word ptr [rdx]; jumptable 000000018000BCEB case 3
0x18000bd62  movzx   r8d, byte ptr [rdx+2]
0x18000bd67  mov     [rax], cx
0x18000bd6a  mov     [rax+2], r8b
0x18000bd6e  retn
0x18000bd70  mov     r8, [rdx]; jumptable 000000018000BCEB case 13
0x18000bd73  mov     ecx, [rdx+8]
0x18000bd76  movzx   r9d, byte ptr [rdx+0Ch]
0x18000bd7b  mov     [rax], r8
0x18000bd7e  mov     [rax+8], ecx
0x18000bd81  mov     [rax+0Ch], r9b
0x18000bd85  retn
0x18000bd86  mov     r8, [rdx]; jumptable 000000018000BCEB case 10
0x18000bd89  movzx   ecx, word ptr [rdx+8]
0x18000bd8d  mov     [rax], r8
0x18000bd90  mov     [rax+8], cx
0x18000bd94  retn
0x18000bd95  mov     r8, [rdx]; jumptable 000000018000BCEB case 9
0x18000bd98  movzx   ecx, byte ptr [rdx+8]
0x18000bd9c  mov     [rax], r8
0x18000bd9f  mov     [rax+8], cl
0x18000bda2  retn
0x18000bda3  mov     r8, [rdx]; jumptable 000000018000BCEB case 12
0x18000bda6  mov     ecx, [rdx+8]
0x18000bda9  mov     [rax], r8
0x18000bdac  mov     [rax+8], ecx
0x18000bdaf  retn
0x18000bdb0  mov     ecx, [rdx]; jumptable 000000018000BCEB case 6
0x18000bdb2  movzx   r8d, word ptr [rdx+4]
0x18000bdb7  mov     [rax], ecx
0x18000bdb9  mov     [rax+4], r8w
0x18000bdbe  retn
0x18000bdbf  mov     ecx, [rdx]; jumptable 000000018000BCEB case 5
0x18000bdc1  movzx   r8d, byte ptr [rdx+4]
0x18000bdc6  mov     [rax], ecx
0x18000bdc8  mov     [rax+4], r8b
0x18000bdcc  retn
0x18000bdcd  mov     rcx, [rdx]; jumptable 000000018000BCEB case 8
0x18000bdd0  mov     [rax], rcx
0x18000bdd3  retn
0x18000bdd4  movzx   ecx, byte ptr [rdx]; jumptable 000000018000BCEB case 1
0x18000bdd7  mov     [rax], cl
0x18000bdd9  retn
0x18000bdda  mov     ecx, [rdx]; jumptable 000000018000BCEB case 4
0x18000bddc  mov     [rax], ecx
0x18000bdde  retn
0x18000bde0  cmp     r8, 20h ; ' '; jumptable 000000018000BCEB default case
0x18000bde4  ja      short loc_18000BDFD
0x18000bde6  movdqu  xmm1, xmmword ptr [rdx]
0x18000bdea  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x18000bdf1  movdqu  xmmword ptr [rcx], xmm1
0x18000bdf5  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x18000bdfc  retn
0x18000bdfd  lea     r9, [rdx+r8]
0x18000be01  cmp     rcx, rdx
0x18000be04  cmovbe  r9, rcx
0x18000be08  cmp     rcx, r9
0x18000be0b  jb      loc_18000C260
0x18000be11  cmp     cs:__isa_available, 3
0x18000be18  jb      loc_18000C110
0x18000be1e  cmp     r8, 2000h
0x18000be25  jbe     short loc_18000BE4D
0x18000be27  cmp     r8, 180000h
0x18000be2e  ja      short loc_18000BE4D
0x18000be30  lea     r9, [rcx+40h]
0x18000be34  cmp     rcx, rdx
0x18000be37  cmova   r9, rdx
0x18000be3b  cmp     r9, rdx
0x18000be3e  ja      short loc_18000BE4D
0x18000be40  test    byte ptr cs:__favor, 2
0x18000be47  jnz     memcpy_repmovs
0x18000be4d  vmovdqu ymm0, ymmword ptr [rdx]
0x18000be51  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x18000be58  cmp     r8, 100h
0x18000be5f  jbe     loc_18000BF28
0x18000be65  mov     r9, rcx
0x18000be68  and     r9, 1Fh
0x18000be6c  sub     r9, 20h ; ' '
0x18000be70  sub     rcx, r9
0x18000be73  sub     rdx, r9
0x18000be76  add     r8, r9
0x18000be79  cmp     r8, 100h
0x18000be80  jbe     loc_18000BF28
0x18000be86  cmp     r8, 180000h
0x18000be8d  ja      loc_18000BFD0
0x18000be93  nop     word ptr [rax+rax+00000000h]
0x18000bea0  vmovdqu ymm1, ymmword ptr [rdx]
0x18000bea4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18000bea9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18000beae  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18000beb3  vmovdqa ymmword ptr [rcx], ymm1
0x18000beb7  vmovdqa ymmword ptr [rcx+20h], ymm2
0x18000bebc  vmovdqa ymmword ptr [rcx+40h], ymm3
0x18000bec1  vmovdqa ymmword ptr [rcx+60h], ymm4
0x18000bec6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18000bece  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18000bed6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18000bede  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18000bee6  vmovdqa ymmword ptr [rcx+80h], ymm1
0x18000beee  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x18000bef6  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x18000befe  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x18000bf06  add     rcx, 100h
0x18000bf0d  add     rdx, 100h
0x18000bf14  sub     r8, 100h
0x18000bf1b  cmp     r8, 100h
0x18000bf22  jnb     loc_18000BEA0
0x18000bf28  lea     r9, [r8+1Fh]
0x18000bf2c  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000bf30  mov     r11, r9
0x18000bf33  shr     r11, 5
0x18000bf37  mov     r11d, ds:(jpt_18000BF42 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000bf3f  add     r11, r10
0x18000bf42  jmp     r11; switch jump
0x18000bf45  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000BF42 case 8
0x18000bf4f  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x18000bf59  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000BF42 case 7
0x18000bf63  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x18000bf6d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000BF42 case 6
0x18000bf77  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x18000bf81  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000BF42 case 5
0x18000bf8b  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x18000bf95  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000BF42 case 4
0x18000bf9c  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x18000bfa3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000BF42 case 3
0x18000bfaa  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x18000bfb1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000BF42 case 2
0x18000bfb8  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x18000bfbf  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000BF42 case 1
0x18000bfc6  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000BF42 case 0
0x18000bfca  vzeroupper
0x18000bfcd  retn
0x18000bfd0  vmovdqu ymm1, ymmword ptr [rdx]
0x18000bfd4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x18000bfd9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x18000bfde  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x18000bfe3  vmovntdq ymmword ptr [rcx], ymm1
0x18000bfe7  vmovntdq ymmword ptr [rcx+20h], ymm2
0x18000bfec  vmovntdq ymmword ptr [rcx+40h], ymm3
0x18000bff1  vmovntdq ymmword ptr [rcx+60h], ymm4
0x18000bff6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18000bffe  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x18000c006  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18000c00e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x18000c016  vmovntdq ymmword ptr [rcx+80h], ymm1
0x18000c01e  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x18000c026  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x18000c02e  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x18000c036  add     rcx, 100h
0x18000c03d  add     rdx, 100h
0x18000c044  sub     r8, 100h
0x18000c04b  cmp     r8, 100h
0x18000c052  jnb     loc_18000BFD0
0x18000c058  lea     r9, [r8+1Fh]
0x18000c05c  and     r9, 0FFFFFFFFFFFFFFE0h
0x18000c060  mov     r11, r9
0x18000c063  shr     r11, 5
0x18000c067  mov     r11d, ds:(jpt_18000C072 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000c06f  add     r11, r10
0x18000c072  jmp     r11; switch jump
0x18000c075  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 000000018000C072 case 8
0x18000c07f  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x18000c089  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 000000018000C072 case 7
0x18000c093  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x18000c09d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 000000018000C072 case 6
0x18000c0a7  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x18000c0b1  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 000000018000C072 case 5
0x18000c0bb  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x18000c0c5  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 000000018000C072 case 4
0x18000c0cc  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x18000c0d3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 000000018000C072 case 3
0x18000c0da  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x18000c0e1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 000000018000C072 case 2
0x18000c0e8  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x18000c0ef  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 000000018000C072 case 1
0x18000c0f6  vmovdqu ymmword ptr [rax], ymm0; jumptable 000000018000C072 case 0
0x18000c0fa  sfence
0x18000c0fd  vzeroupper
0x18000c100  retn
0x18000c110  cmp     r8, 800h
0x18000c117  jbe     short loc_18000C126
0x18000c119  test    byte ptr cs:__favor, 2
0x18000c120  jnz     memcpy_repmovs
0x18000c126  movdqu  xmm0, xmmword ptr [rdx]
0x18000c12a  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x18000c131  cmp     r8, 80h
0x18000c138  jbe     loc_18000C1CC
0x18000c13e  mov     r9, rcx
0x18000c141  and     r9, 0Fh
0x18000c145  sub     r9, 10h
0x18000c149  sub     rcx, r9
0x18000c14c  sub     rdx, r9
0x18000c14f  add     r8, r9
0x18000c152  cmp     r8, 80h
0x18000c159  jbe     short loc_18000C1CC
0x18000c15b  nop     dword ptr [rax+rax+00h]
0x18000c160  movdqu  xmm1, xmmword ptr [rdx]
0x18000c164  movdqu  xmm2, xmmword ptr [rdx+10h]
0x18000c169  movdqu  xmm3, xmmword ptr [rdx+20h]
0x18000c16e  movdqu  xmm4, xmmword ptr [rdx+30h]
0x18000c173  movdqa  xmmword ptr [rcx], xmm1
0x18000c177  movdqa  xmmword ptr [rcx+10h], xmm2
0x18000c17c  movdqa  xmmword ptr [rcx+20h], xmm3
0x18000c181  movdqa  xmmword ptr [rcx+30h], xmm4
0x18000c186  movdqu  xmm1, xmmword ptr [rdx+40h]
0x18000c18b  movdqu  xmm2, xmmword ptr [rdx+50h]
0x18000c190  movdqu  xmm3, xmmword ptr [rdx+60h]
0x18000c195  movdqu  xmm4, xmmword ptr [rdx+70h]
0x18000c19a  movdqa  xmmword ptr [rcx+40h], xmm1
0x18000c19f  movdqa  xmmword ptr [rcx+50h], xmm2
0x18000c1a4  movdqa  xmmword ptr [rcx+60h], xmm3
0x18000c1a9  movdqa  xmmword ptr [rcx+70h], xmm4
0x18000c1ae  add     rcx, 80h
0x18000c1b5  add     rdx, 80h
0x18000c1bc  sub     r8, 80h
0x18000c1c3  cmp     r8, 80h
0x18000c1ca  jnb     short loc_18000C160
0x18000c1cc  lea     r9, [r8+0Fh]
0x18000c1d0  and     r9, 0FFFFFFFFFFFFFFF0h
0x18000c1d4  mov     r11, r9
0x18000c1d7  shr     r11, 4
0x18000c1db  mov     r11d, ds:(jpt_18000C1E6 - 180000000h)[r10+r11*4]; switch 9 cases
0x18000c1e3  add     r11, r10
0x18000c1e6  jmp     r11; switch jump
0x18000c1e9  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 000000018000C1E6 case 8
0x18000c1f0  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x18000c1f7  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 000000018000C1E6 case 7
0x18000c1fe  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x18000c205  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 000000018000C1E6 case 6
0x18000c20c  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x18000c213  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 000000018000C1E6 case 5
0x18000c21a  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x18000c221  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 000000018000C1E6 case 4
0x18000c228  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x18000c22f  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 000000018000C1E6 case 3
0x18000c236  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x18000c23d  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 000000018000C1E6 case 2
0x18000c244  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x18000c24b  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 000000018000C1E6 case 1
0x18000c252  movdqu  xmmword ptr [rax], xmm0; jumptable 000000018000C1E6 case 0
0x18000c256  retn
0x18000c260  movups  xmm2, xmmword ptr [rdx]
0x18000c263  sub     rdx, rcx
0x18000c266  add     rcx, r8
0x18000c269  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18000c26e  sub     rcx, 10h
0x18000c272  sub     r8, 10h
0x18000c276  test    cl, 0Fh
0x18000c279  jz      short loc_18000C293
0x18000c27b  mov     r9, rcx
0x18000c27e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c282  movups  xmm1, xmm0
0x18000c285  movups  xmm0, xmmword ptr [rcx+rdx]
0x18000c289  movups  xmmword ptr [r9], xmm1
0x18000c28d  mov     r8, rcx
0x18000c290  sub     r8, rax
0x18000c293  mov     r9, r8
0x18000c296  shr     r9, 7
  ... truncated ...
```
