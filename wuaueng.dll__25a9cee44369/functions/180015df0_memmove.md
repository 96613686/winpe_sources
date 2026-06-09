# memmove

- ea: `0x180015df0`
- end: `0x18001645d`
- name: `memmove`
- size: `1645`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ab4`
- `0x180006a98`
- `0x180006cec`
- `0x1800073dc`
- `0x1800074f0`
- `0x180007574`
- `0x1800076c4`
- `0x1800077f8`
- `0x180007bbc`
- `0x180007e1c`
- `0x180008b20`
- `0x180008f84`
- `0x1800090a0`
- `0x1800093b8`
- `0x1800094f8`
- `0x180009650`
- `0x1800098b8`
- `0x180009eb8`
- `0x18000a620`
- `0x18000a85c`
- `0x18000abbc`
- `0x18000acb4`
- `0x18000b248`
- `0x180012350`
- `0x180012548`

## callees

- `0x180015dd0`
- `0x180015df0`

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
  __int64 v25; // r9
  __m128i v58; // xmm0
  __m128i v59; // xmm5
  __int64 v60; // r9
  __m128i v61; // xmm2
  __m128i v62; // xmm3
  __m128i v63; // xmm4
  __m128i v64; // xmm2
  __m128i v65; // xmm3
  __m128i v66; // xmm4
  size_t v67; // r9
  __int128 v68; // xmm2
  signed __int64 v69; // rdx
  char *v70; // rcx
  __int128 v71; // xmm0
  unsigned __int64 v72; // rcx
  size_t v73; // r8
  _OWORD *v74; // r9
  __int128 v75; // xmm1
  size_t v76; // r9
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm1
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  __int128 v82; // xmm1
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
        v68 = *(_OWORD *)Src;
        v69 = (_BYTE *)Src - (_BYTE *)_RCX;
        v70 = (char *)_RCX + Size;
        v71 = *(_OWORD *)&v70[v69 - 16];
        v72 = (unsigned __int64)(v70 - 16);
        v73 = Size - 16;
        if ( (v72 & 0xF) != 0 )
        {
          v74 = (_OWORD *)v72;
          v72 &= 0xFFFFFFFFFFFFFFF0uLL;
          v75 = v71;
          v71 = *(_OWORD *)(v72 + v69);
          *v74 = v75;
          v73 = v72 - (_QWORD)result;
        }
        v76 = v73 >> 7;
        if ( v73 >> 7 )
        {
          for ( *(_OWORD *)v72 = v71; ; *(_OWORD *)v72 = v82 )
          {
            v77 = *(_OWORD *)(v72 + v69 - 16);
            v78 = *(_OWORD *)(v72 + v69 - 32);
            v72 -= 128LL;
            *(_OWORD *)(v72 + 112) = v77;
            *(_OWORD *)(v72 + 96) = v78;
            v79 = *(_OWORD *)(v72 + v69 + 64);
            --v76;
            *(_OWORD *)(v72 + 80) = *(_OWORD *)(v72 + v69 + 80);
            *(_OWORD *)(v72 + 64) = v79;
            v80 = *(_OWORD *)(v72 + v69 + 32);
            *(_OWORD *)(v72 + 48) = *(_OWORD *)(v72 + v69 + 48);
            *(_OWORD *)(v72 + 32) = v80;
            v81 = *(_OWORD *)(v72 + v69 + 16);
            v82 = *(_OWORD *)(v72 + v69);
            if ( !v76 )
              break;
            *(_OWORD *)(v72 + 16) = v81;
          }
          *(_OWORD *)(v72 + 16) = v81;
          v73 &= 0x7Fu;
          v71 = v82;
        }
        for ( i = v73 >> 4; i; --i )
        {
          *(_OWORD *)v72 = v71;
          v72 -= 16LL;
          v71 = *(_OWORD *)(v72 + v69);
        }
        if ( (v73 & 0xF) != 0 )
          *(_OWORD *)result = v68;
        *(_OWORD *)v72 = v71;
        return result;
      }
      if ( (unsigned int)_isa_available < 3 )
      {
        if ( Size <= 0x800 || (_favor & 2) == 0 )
        {
          v58 = _mm_loadu_si128((const __m128i *)Src);
          v59 = _mm_loadu_si128((const __m128i *)((char *)Src + Size - 16));
          if ( Size > 0x80 )
          {
            v60 = ((unsigned __int8)_RCX & 0xF) - 16LL;
            _RCX = (char *)_RCX - v60;
            Src = (char *)Src - v60;
            Size += v60;
            if ( Size > 0x80 )
            {
              do
              {
                v61 = _mm_loadu_si128((const __m128i *)Src + 1);
                v62 = _mm_loadu_si128((const __m128i *)Src + 2);
                v63 = _mm_loadu_si128((const __m128i *)Src + 3);
                *(__m128i *)_RCX = _mm_loadu_si128((const __m128i *)Src);
                *((__m128i *)_RCX + 1) = v61;
                *((__m128i *)_RCX + 2) = v62;
                *((__m128i *)_RCX + 3) = v63;
                v64 = _mm_loadu_si128((const __m128i *)Src + 5);
                v65 = _mm_loadu_si128((const __m128i *)Src + 6);
                v66 = _mm_loadu_si128((const __m128i *)Src + 7);
                *((__m128i *)_RCX + 4) = _mm_loadu_si128((const __m128i *)Src + 4);
                *((__m128i *)_RCX + 5) = v64;
                *((__m128i *)_RCX + 6) = v65;
                *((__m128i *)_RCX + 7) = v66;
                _RCX = (char *)_RCX + 128;
                Src = (char *)Src + 128;
                Size -= 128LL;
              }
              while ( Size >= 0x80 );
            }
          }
          v67 = (Size + 15) & 0xFFFFFFFFFFFFFFF0uLL;
          switch ( v67 >> 4 )
          {
            case 0uLL:
              goto LABEL_65;
            case 1uLL:
              goto LABEL_64;
            case 2uLL:
              goto LABEL_63;
            case 3uLL:
              goto LABEL_62;
            case 4uLL:
              goto LABEL_61;
            case 5uLL:
              goto LABEL_60;
            case 6uLL:
              goto LABEL_59;
            case 7uLL:
              goto LABEL_58;
            case 8uLL:
              *(__m128i *)((char *)_RCX + v67 - 128) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 128));
LABEL_58:
              *(__m128i *)((char *)_RCX + v67 - 112) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 112));
LABEL_59:
              *(__m128i *)((char *)_RCX + v67 - 96) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 96));
LABEL_60:
              *(__m128i *)((char *)_RCX + v67 - 80) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 80));
LABEL_61:
              *(__m128i *)((char *)_RCX + v67 - 64) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 64));
LABEL_62:
              *(__m128i *)((char *)_RCX + v67 - 48) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 48));
LABEL_63:
              *(__m128i *)((char *)_RCX + v67 - 32) = _mm_loadu_si128((const __m128i *)((char *)Src + v67 - 32));
LABEL_64:
              *(__m128i *)((char *)_RCX + Size - 16) = v59;
LABEL_65:
              *(__m128i *)result = v58;
              break;
          }
          return result;
        }
        return (void *)memcpy_repmovs();
      }
      if ( Size > 0x2000 && Size <= 0x180000 && (_favor & 2) != 0 )
        return (void *)memcpy_repmovs();
      __asm
      {
        vmovdqu ymm0, ymmword ptr [rdx]
        vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
      }
      if ( Size <= 0x100
        || (v25 = ((unsigned __int8)_RCX & 0x1F) - 32LL,
            _RCX = (char *)_RCX - v25,
            Src = (char *)Src - v25,
            Size += v25,
            Size <= 0x100) )
      {
LABEL_30:
        _R9 = (Size + 31) & 0xFFFFFFFFFFFFFFE0uLL;
        switch ( _R9 >> 5 )
        {
          case 0uLL:
            goto LABEL_39;
          case 1uLL:
            goto LABEL_38;
          case 2uLL:
            goto LABEL_37;
          case 3uLL:
            goto LABEL_36;
          case 4uLL:
            goto LABEL_35;
          case 5uLL:
            goto LABEL_34;
          case 6uLL:
            goto LABEL_33;
          case 7uLL:
            goto LABEL_32;
          case 8uLL:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180016062 case 8
              vmovdqu ymmword ptr [rcx+r9-100h], ymm1
            }
LABEL_32:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180016062 case 7
              vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
            }
LABEL_33:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180016062 case 6
              vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
            }
LABEL_34:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180016062 case 5
              vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
            }
LABEL_35:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180016062 case 4
              vmovdqu ymmword ptr [rcx+r9-80h], ymm1
            }
LABEL_36:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180016062 case 3
              vmovdqu ymmword ptr [rcx+r9-60h], ymm1
            }
LABEL_37:
            __asm
            {
              vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180016062 case 2
              vmovdqu ymmword ptr [rcx+r9-40h], ymm1
            }
LABEL_38:
            __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180016062 case 1 }
LABEL_39:
            __asm
            {
              vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180016062 case 0
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
        goto LABEL_30;
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
          goto LABEL_50;
        case 1uLL:
          goto LABEL_49;
        case 2uLL:
          goto LABEL_48;
        case 3uLL:
          goto LABEL_47;
        case 4uLL:
          goto LABEL_46;
        case 5uLL:
          goto LABEL_45;
        case 6uLL:
          goto LABEL_44;
        case 7uLL:
          goto LABEL_43;
        case 8uLL:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180016192 case 8
            vmovntdq ymmword ptr [rcx+r9-100h], ymm1
          }
LABEL_43:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180016192 case 7
            vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
          }
LABEL_44:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180016192 case 6
            vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
          }
LABEL_45:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180016192 case 5
            vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
          }
LABEL_46:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180016192 case 4
            vmovntdq ymmword ptr [rcx+r9-80h], ymm1
          }
LABEL_47:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180016192 case 3
            vmovntdq ymmword ptr [rcx+r9-60h], ymm1
          }
LABEL_48:
          __asm
          {
            vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180016192 case 2
            vmovntdq ymmword ptr [rcx+r9-40h], ymm1
          }
LABEL_49:
          __asm { vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180016192 case 1 }
LABEL_50:
          __asm { vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180016192 case 0 }
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
0x180015df0  mov     rax, rcx
0x180015df3  lea     r10, cs:180000000h
0x180015dfa  cmp     r8, 0Fh; switch 16 cases
0x180015dfe  ja      def_180015E1B; jumptable 0000000180015E1B default case
0x180015e04  nop     word ptr [rax+rax+00000000h]
0x180015e10  mov     r9d, ds:(jpt_180015E1B - 180000000h)[r10+r8*4]
0x180015e18  add     r9, r10
0x180015e1b  jmp     r9; switch jump
0x180015e1e  retn; jumptable 0000000180015E1B case 0
0x180015e20  mov     r8, [rdx]; jumptable 0000000180015E1B case 15
0x180015e23  mov     ecx, [rdx+8]
0x180015e26  movzx   r9d, word ptr [rdx+0Ch]
0x180015e2b  movzx   r10d, byte ptr [rdx+0Eh]
0x180015e30  mov     [rax], r8
0x180015e33  mov     [rax+8], ecx
0x180015e36  mov     [rax+0Ch], r9w
0x180015e3b  mov     [rax+0Eh], r10b
0x180015e3f  retn
0x180015e40  mov     r8, [rdx]; jumptable 0000000180015E1B case 11
0x180015e43  movzx   ecx, word ptr [rdx+8]
0x180015e47  movzx   r9d, byte ptr [rdx+0Ah]
0x180015e4c  mov     [rax], r8
0x180015e4f  mov     [rax+8], cx
0x180015e53  mov     [rax+0Ah], r9b
0x180015e57  retn
0x180015e58  movzx   ecx, word ptr [rdx]; jumptable 0000000180015E1B case 2
0x180015e5b  mov     [rax], cx
0x180015e5e  retn
0x180015e60  mov     ecx, [rdx]; jumptable 0000000180015E1B case 7
0x180015e62  movzx   r8d, word ptr [rdx+4]
0x180015e67  movzx   r9d, byte ptr [rdx+6]
0x180015e6c  mov     [rax], ecx
0x180015e6e  mov     [rax+4], r8w
0x180015e73  mov     [rax+6], r9b
0x180015e77  retn
0x180015e78  mov     r8, [rdx]; jumptable 0000000180015E1B case 14
0x180015e7b  mov     ecx, [rdx+8]
0x180015e7e  movzx   r9d, word ptr [rdx+0Ch]
0x180015e83  mov     [rax], r8
0x180015e86  mov     [rax+8], ecx
0x180015e89  mov     [rax+0Ch], r9w
0x180015e8e  retn
0x180015e8f  movzx   ecx, word ptr [rdx]; jumptable 0000000180015E1B case 3
0x180015e92  movzx   r8d, byte ptr [rdx+2]
0x180015e97  mov     [rax], cx
0x180015e9a  mov     [rax+2], r8b
0x180015e9e  retn
0x180015ea0  mov     r8, [rdx]; jumptable 0000000180015E1B case 13
0x180015ea3  mov     ecx, [rdx+8]
0x180015ea6  movzx   r9d, byte ptr [rdx+0Ch]
0x180015eab  mov     [rax], r8
0x180015eae  mov     [rax+8], ecx
0x180015eb1  mov     [rax+0Ch], r9b
0x180015eb5  retn
0x180015eb6  mov     r8, [rdx]; jumptable 0000000180015E1B case 10
0x180015eb9  movzx   ecx, word ptr [rdx+8]
0x180015ebd  mov     [rax], r8
0x180015ec0  mov     [rax+8], cx
0x180015ec4  retn
0x180015ec5  mov     r8, [rdx]; jumptable 0000000180015E1B case 9
0x180015ec8  movzx   ecx, byte ptr [rdx+8]
0x180015ecc  mov     [rax], r8
0x180015ecf  mov     [rax+8], cl
0x180015ed2  retn
0x180015ed3  mov     r8, [rdx]; jumptable 0000000180015E1B case 12
0x180015ed6  mov     ecx, [rdx+8]
0x180015ed9  mov     [rax], r8
0x180015edc  mov     [rax+8], ecx
0x180015edf  retn
0x180015ee0  mov     ecx, [rdx]; jumptable 0000000180015E1B case 6
0x180015ee2  movzx   r8d, word ptr [rdx+4]
0x180015ee7  mov     [rax], ecx
0x180015ee9  mov     [rax+4], r8w
0x180015eee  retn
0x180015eef  mov     ecx, [rdx]; jumptable 0000000180015E1B case 5
0x180015ef1  movzx   r8d, byte ptr [rdx+4]
0x180015ef6  mov     [rax], ecx
0x180015ef8  mov     [rax+4], r8b
0x180015efc  retn
0x180015efd  mov     rcx, [rdx]; jumptable 0000000180015E1B case 8
0x180015f00  mov     [rax], rcx
0x180015f03  retn
0x180015f04  movzx   ecx, byte ptr [rdx]; jumptable 0000000180015E1B case 1
0x180015f07  mov     [rax], cl
0x180015f09  retn
0x180015f0a  mov     ecx, [rdx]; jumptable 0000000180015E1B case 4
0x180015f0c  mov     [rax], ecx
0x180015f0e  retn
0x180015f10  cmp     r8, 20h ; ' '; jumptable 0000000180015E1B default case
0x180015f14  ja      short loc_180015F2D
0x180015f16  movdqu  xmm1, xmmword ptr [rdx]
0x180015f1a  movdqu  xmm2, xmmword ptr [rdx+r8-10h]
0x180015f21  movdqu  xmmword ptr [rcx], xmm1
0x180015f25  movdqu  xmmword ptr [rcx+r8-10h], xmm2
0x180015f2c  retn
0x180015f2d  lea     r9, [rdx+r8]
0x180015f31  cmp     rcx, rdx
0x180015f34  cmovbe  r9, rcx
0x180015f38  cmp     rcx, r9
0x180015f3b  jb      loc_180016380
0x180015f41  cmp     cs:__isa_available, 3
0x180015f48  jb      loc_180016230
0x180015f4e  cmp     r8, 2000h
0x180015f55  jbe     short loc_180015F6D
0x180015f57  cmp     r8, 180000h
0x180015f5e  ja      short loc_180015F6D
0x180015f60  test    byte ptr cs:__favor, 2
0x180015f67  jnz     memcpy_repmovs
0x180015f6d  vmovdqu ymm0, ymmword ptr [rdx]
0x180015f71  vmovdqu ymm5, ymmword ptr [rdx+r8-20h]
0x180015f78  cmp     r8, 100h
0x180015f7f  jbe     loc_180016048
0x180015f85  mov     r9, rcx
0x180015f88  and     r9, 1Fh
0x180015f8c  sub     r9, 20h ; ' '
0x180015f90  sub     rcx, r9
0x180015f93  sub     rdx, r9
0x180015f96  add     r8, r9
0x180015f99  cmp     r8, 100h
0x180015fa0  jbe     loc_180016048
0x180015fa6  cmp     r8, 180000h
0x180015fad  ja      loc_1800160F0
0x180015fb3  nop     word ptr [rax+rax+00000000h]
0x180015fc0  vmovdqu ymm1, ymmword ptr [rdx]
0x180015fc4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x180015fc9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x180015fce  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x180015fd3  vmovdqa ymmword ptr [rcx], ymm1
0x180015fd7  vmovdqa ymmword ptr [rcx+20h], ymm2
0x180015fdc  vmovdqa ymmword ptr [rcx+40h], ymm3
0x180015fe1  vmovdqa ymmword ptr [rcx+60h], ymm4
0x180015fe6  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x180015fee  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x180015ff6  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x180015ffe  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x180016006  vmovdqa ymmword ptr [rcx+80h], ymm1
0x18001600e  vmovdqa ymmword ptr [rcx+0A0h], ymm2
0x180016016  vmovdqa ymmword ptr [rcx+0C0h], ymm3
0x18001601e  vmovdqa ymmword ptr [rcx+0E0h], ymm4
0x180016026  add     rcx, 100h
0x18001602d  add     rdx, 100h
0x180016034  sub     r8, 100h
0x18001603b  cmp     r8, 100h
0x180016042  jnb     loc_180015FC0
0x180016048  lea     r9, [r8+1Fh]
0x18001604c  and     r9, 0FFFFFFFFFFFFFFE0h
0x180016050  mov     r11, r9
0x180016053  shr     r11, 5
0x180016057  mov     r11d, ds:(jpt_180016062 - 180000000h)[r10+r11*4]; switch 9 cases
0x18001605f  add     r11, r10
0x180016062  jmp     r11; switch jump
0x180016065  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180016062 case 8
0x18001606f  vmovdqu ymmword ptr [rcx+r9-100h], ymm1
0x180016079  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180016062 case 7
0x180016083  vmovdqu ymmword ptr [rcx+r9-0E0h], ymm1
0x18001608d  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180016062 case 6
0x180016097  vmovdqu ymmword ptr [rcx+r9-0C0h], ymm1
0x1800160a1  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180016062 case 5
0x1800160ab  vmovdqu ymmword ptr [rcx+r9-0A0h], ymm1
0x1800160b5  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180016062 case 4
0x1800160bc  vmovdqu ymmword ptr [rcx+r9-80h], ymm1
0x1800160c3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180016062 case 3
0x1800160ca  vmovdqu ymmword ptr [rcx+r9-60h], ymm1
0x1800160d1  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180016062 case 2
0x1800160d8  vmovdqu ymmword ptr [rcx+r9-40h], ymm1
0x1800160df  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180016062 case 1
0x1800160e6  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180016062 case 0
0x1800160ea  vzeroupper
0x1800160ed  retn
0x1800160f0  vmovdqu ymm1, ymmword ptr [rdx]
0x1800160f4  vmovdqu ymm2, ymmword ptr [rdx+20h]
0x1800160f9  vmovdqu ymm3, ymmword ptr [rdx+40h]
0x1800160fe  vmovdqu ymm4, ymmword ptr [rdx+60h]
0x180016103  vmovntdq ymmword ptr [rcx], ymm1
0x180016107  vmovntdq ymmword ptr [rcx+20h], ymm2
0x18001610c  vmovntdq ymmword ptr [rcx+40h], ymm3
0x180016111  vmovntdq ymmword ptr [rcx+60h], ymm4
0x180016116  vmovdqu ymm1, ymmword ptr [rdx+80h]
0x18001611e  vmovdqu ymm2, ymmword ptr [rdx+0A0h]
0x180016126  vmovdqu ymm3, ymmword ptr [rdx+0C0h]
0x18001612e  vmovdqu ymm4, ymmword ptr [rdx+0E0h]
0x180016136  vmovntdq ymmword ptr [rcx+80h], ymm1
0x18001613e  vmovntdq ymmword ptr [rcx+0A0h], ymm2
0x180016146  vmovntdq ymmword ptr [rcx+0C0h], ymm3
0x18001614e  vmovntdq ymmword ptr [rcx+0E0h], ymm4
0x180016156  add     rcx, 100h
0x18001615d  add     rdx, 100h
0x180016164  sub     r8, 100h
0x18001616b  cmp     r8, 100h
0x180016172  jnb     loc_1800160F0
0x180016178  lea     r9, [r8+1Fh]
0x18001617c  and     r9, 0FFFFFFFFFFFFFFE0h
0x180016180  mov     r11, r9
0x180016183  shr     r11, 5
0x180016187  mov     r11d, ds:(jpt_180016192 - 180000000h)[r10+r11*4]; switch 9 cases
0x18001618f  add     r11, r10
0x180016192  jmp     r11; switch jump
0x180016195  vmovdqu ymm1, ymmword ptr [rdx+r9-100h]; jumptable 0000000180016192 case 8
0x18001619f  vmovntdq ymmword ptr [rcx+r9-100h], ymm1
0x1800161a9  vmovdqu ymm1, ymmword ptr [rdx+r9-0E0h]; jumptable 0000000180016192 case 7
0x1800161b3  vmovntdq ymmword ptr [rcx+r9-0E0h], ymm1
0x1800161bd  vmovdqu ymm1, ymmword ptr [rdx+r9-0C0h]; jumptable 0000000180016192 case 6
0x1800161c7  vmovntdq ymmword ptr [rcx+r9-0C0h], ymm1
0x1800161d1  vmovdqu ymm1, ymmword ptr [rdx+r9-0A0h]; jumptable 0000000180016192 case 5
0x1800161db  vmovntdq ymmword ptr [rcx+r9-0A0h], ymm1
0x1800161e5  vmovdqu ymm1, ymmword ptr [rdx+r9-80h]; jumptable 0000000180016192 case 4
0x1800161ec  vmovntdq ymmword ptr [rcx+r9-80h], ymm1
0x1800161f3  vmovdqu ymm1, ymmword ptr [rdx+r9-60h]; jumptable 0000000180016192 case 3
0x1800161fa  vmovntdq ymmword ptr [rcx+r9-60h], ymm1
0x180016201  vmovdqu ymm1, ymmword ptr [rdx+r9-40h]; jumptable 0000000180016192 case 2
0x180016208  vmovntdq ymmword ptr [rcx+r9-40h], ymm1
0x18001620f  vmovdqu ymmword ptr [rcx+r8-20h], ymm5; jumptable 0000000180016192 case 1
0x180016216  vmovdqu ymmword ptr [rax], ymm0; jumptable 0000000180016192 case 0
0x18001621a  sfence
0x18001621d  vzeroupper
0x180016220  retn
0x180016230  cmp     r8, 800h
0x180016237  jbe     short loc_180016246
0x180016239  test    byte ptr cs:__favor, 2
0x180016240  jnz     memcpy_repmovs
0x180016246  movdqu  xmm0, xmmword ptr [rdx]
0x18001624a  movdqu  xmm5, xmmword ptr [rdx+r8-10h]
0x180016251  cmp     r8, 80h
0x180016258  jbe     loc_1800162EC
0x18001625e  mov     r9, rcx
0x180016261  and     r9, 0Fh
0x180016265  sub     r9, 10h
0x180016269  sub     rcx, r9
0x18001626c  sub     rdx, r9
0x18001626f  add     r8, r9
0x180016272  cmp     r8, 80h
0x180016279  jbe     short loc_1800162EC
0x18001627b  nop     dword ptr [rax+rax+00h]
0x180016280  movdqu  xmm1, xmmword ptr [rdx]
0x180016284  movdqu  xmm2, xmmword ptr [rdx+10h]
0x180016289  movdqu  xmm3, xmmword ptr [rdx+20h]
0x18001628e  movdqu  xmm4, xmmword ptr [rdx+30h]
0x180016293  movdqa  xmmword ptr [rcx], xmm1
0x180016297  movdqa  xmmword ptr [rcx+10h], xmm2
0x18001629c  movdqa  xmmword ptr [rcx+20h], xmm3
0x1800162a1  movdqa  xmmword ptr [rcx+30h], xmm4
0x1800162a6  movdqu  xmm1, xmmword ptr [rdx+40h]
0x1800162ab  movdqu  xmm2, xmmword ptr [rdx+50h]
0x1800162b0  movdqu  xmm3, xmmword ptr [rdx+60h]
0x1800162b5  movdqu  xmm4, xmmword ptr [rdx+70h]
0x1800162ba  movdqa  xmmword ptr [rcx+40h], xmm1
0x1800162bf  movdqa  xmmword ptr [rcx+50h], xmm2
0x1800162c4  movdqa  xmmword ptr [rcx+60h], xmm3
0x1800162c9  movdqa  xmmword ptr [rcx+70h], xmm4
0x1800162ce  add     rcx, 80h
0x1800162d5  add     rdx, 80h
0x1800162dc  sub     r8, 80h
0x1800162e3  cmp     r8, 80h
0x1800162ea  jnb     short loc_180016280
0x1800162ec  lea     r9, [r8+0Fh]
0x1800162f0  and     r9, 0FFFFFFFFFFFFFFF0h
0x1800162f4  mov     r11, r9
0x1800162f7  shr     r11, 4
0x1800162fb  mov     r11d, ds:(jpt_180016306 - 180000000h)[r10+r11*4]; switch 9 cases
0x180016303  add     r11, r10
0x180016306  jmp     r11; switch jump
0x180016309  movdqu  xmm1, xmmword ptr [rdx+r9-80h]; jumptable 0000000180016306 case 8
0x180016310  movdqu  xmmword ptr [rcx+r9-80h], xmm1
0x180016317  movdqu  xmm1, xmmword ptr [rdx+r9-70h]; jumptable 0000000180016306 case 7
0x18001631e  movdqu  xmmword ptr [rcx+r9-70h], xmm1
0x180016325  movdqu  xmm1, xmmword ptr [rdx+r9-60h]; jumptable 0000000180016306 case 6
0x18001632c  movdqu  xmmword ptr [rcx+r9-60h], xmm1
0x180016333  movdqu  xmm1, xmmword ptr [rdx+r9-50h]; jumptable 0000000180016306 case 5
0x18001633a  movdqu  xmmword ptr [rcx+r9-50h], xmm1
0x180016341  movdqu  xmm1, xmmword ptr [rdx+r9-40h]; jumptable 0000000180016306 case 4
0x180016348  movdqu  xmmword ptr [rcx+r9-40h], xmm1
0x18001634f  movdqu  xmm1, xmmword ptr [rdx+r9-30h]; jumptable 0000000180016306 case 3
0x180016356  movdqu  xmmword ptr [rcx+r9-30h], xmm1
0x18001635d  movdqu  xmm1, xmmword ptr [rdx+r9-20h]; jumptable 0000000180016306 case 2
0x180016364  movdqu  xmmword ptr [rcx+r9-20h], xmm1
0x18001636b  movdqu  xmmword ptr [rcx+r8-10h], xmm5; jumptable 0000000180016306 case 1
0x180016372  movdqu  xmmword ptr [rax], xmm0; jumptable 0000000180016306 case 0
0x180016376  retn
0x180016380  movups  xmm2, xmmword ptr [rdx]
0x180016383  sub     rdx, rcx
0x180016386  add     rcx, r8
0x180016389  movups  xmm0, xmmword ptr [rcx+rdx-10h]
0x18001638e  sub     rcx, 10h
0x180016392  sub     r8, 10h
0x180016396  test    cl, 0Fh
0x180016399  jz      short loc_1800163B3
0x18001639b  mov     r9, rcx
0x18001639e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800163a2  movups  xmm1, xmm0
0x1800163a5  movups  xmm0, xmmword ptr [rcx+rdx]
0x1800163a9  movups  xmmword ptr [r9], xmm1
0x1800163ad  mov     r8, rcx
0x1800163b0  sub     r8, rax
0x1800163b3  mov     r9, r8
0x1800163b6  shr     r9, 7
0x1800163ba  jz      short loc_18001642D
0x1800163bc  movaps  xmmword ptr [rcx], xmm0
0x1800163bf  jmp     short loc_1800163D7
0x1800163d0  movaps  xmmword ptr [rcx+10h], xmm0
0x1800163d4  movaps  xmmword ptr [rcx], xmm1
  ... truncated ...
```
