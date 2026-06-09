# memcmp

- ea: `0x140017dd0`
- end: `0x140017e97`
- name: `memcmp`
- size: `199`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003860`
- `0x1400049f0`
- `0x14000f800`
- `0x140012770`

## callees

- `0x140017dd0`

## pseudocode

```c
int __cdecl memcmp(const void *Buf1, const void *Buf2, size_t Size)
{
  signed __int64 v3; // rdx
  bool v4; // cf
  size_t v6; // r9
  unsigned __int64 v7; // rax
  size_t v8; // r9

  v3 = (_BYTE *)Buf2 - (_BYTE *)Buf1;
  if ( Size < 8 )
    goto LABEL_6;
  for ( ; ((unsigned __int8)Buf1 & 7) != 0; --Size )
  {
    v4 = *(_BYTE *)Buf1 < *((_BYTE *)Buf1 + v3);
    if ( *(_BYTE *)Buf1 != *((_BYTE *)Buf1 + v3) )
      return -v4 - (v4 - 1);
    Buf1 = (char *)Buf1 + 1;
  }
  if ( !(Size >> 3) )
  {
LABEL_6:
    if ( !Size )
      return 0;
    while ( 1 )
    {
      v4 = *(_BYTE *)Buf1 < *((_BYTE *)Buf1 + v3);
      if ( *(_BYTE *)Buf1 != *((_BYTE *)Buf1 + v3) )
        break;
      Buf1 = (char *)Buf1 + 1;
      if ( !--Size )
        return 0;
    }
    return -v4 - (v4 - 1);
  }
  v6 = Size >> 5;
  if ( Size >> 5 )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)Buf1;
      if ( *(_QWORD *)Buf1 != *(_QWORD *)((char *)Buf1 + v3) )
        break;
      v7 = *((_QWORD *)Buf1 + 1);
      if ( v7 != *(_QWORD *)((char *)Buf1 + v3 + 8) )
        goto LABEL_24;
      v7 = *((_QWORD *)Buf1 + 2);
      if ( v7 != *(_QWORD *)((char *)Buf1 + v3 + 16) )
        goto LABEL_23;
      v7 = *((_QWORD *)Buf1 + 3);
      if ( v7 != *(_QWORD *)((char *)Buf1 + v3 + 24) )
      {
        Buf1 = (char *)Buf1 + 8;
LABEL_23:
        Buf1 = (char *)Buf1 + 8;
LABEL_24:
        Buf1 = (char *)Buf1 + 8;
        break;
      }
      Buf1 = (char *)Buf1 + 32;
      if ( !--v6 )
      {
        Size &= 0x1Fu;
        goto LABEL_18;
      }
    }
  }
  else
  {
LABEL_18:
    v8 = Size >> 3;
    if ( !(Size >> 3) )
      goto LABEL_6;
    while ( 1 )
    {
      v7 = *(_QWORD *)Buf1;
      if ( *(_QWORD *)Buf1 != *(_QWORD *)((char *)Buf1 + v3) )
        break;
      Buf1 = (char *)Buf1 + 8;
      if ( !--v8 )
      {
        Size &= 7u;
        goto LABEL_6;
      }
    }
  }
  v4 = _byteswap_uint64(v7) < _byteswap_uint64(*(_QWORD *)((char *)Buf1 + v3));
  return -v4 - (v4 - 1);
}

```

## disassembly

```asm
0x140017dd0  sub     rdx, rcx
0x140017dd3  cmp     r8, 8
0x140017dd7  jb      short loc_140017DFB
0x140017dd9  test    cl, 7
0x140017ddc  jz      short loc_140017DF2
0x140017dde  xchg    ax, ax
0x140017de0  mov     al, [rcx]
0x140017de2  cmp     al, [rcx+rdx]
0x140017de5  jnz     short loc_140017E13
0x140017de7  inc     rcx
0x140017dea  dec     r8
0x140017ded  test    cl, 7
0x140017df0  jnz     short loc_140017DE0
0x140017df2  mov     r9, r8
0x140017df5  shr     r9, 3
0x140017df9  jnz     short loc_140017E1A
0x140017dfb  test    r8, r8
0x140017dfe  jz      short loc_140017E0F
0x140017e00  mov     al, [rcx]
0x140017e02  cmp     al, [rcx+rdx]
0x140017e05  jnz     short loc_140017E13
0x140017e07  inc     rcx
0x140017e0a  dec     r8
0x140017e0d  jnz     short loc_140017E00
0x140017e0f  xor     rax, rax
0x140017e12  retn
0x140017e13  sbb     eax, eax
0x140017e15  sbb     eax, 0FFFFFFFFh
0x140017e18  retn
0x140017e1a  shr     r9, 2
0x140017e1e  jz      short loc_140017E57
0x140017e20  mov     rax, [rcx]
0x140017e23  cmp     rax, [rcx+rdx]
0x140017e27  jnz     short loc_140017E84
0x140017e29  mov     rax, [rcx+8]
0x140017e2d  cmp     rax, [rcx+rdx+8]
0x140017e32  jnz     short loc_140017E80
0x140017e34  mov     rax, [rcx+10h]
0x140017e38  cmp     rax, [rcx+rdx+10h]
0x140017e3d  jnz     short loc_140017E7C
0x140017e3f  mov     rax, [rcx+18h]
0x140017e43  cmp     rax, [rcx+rdx+18h]
0x140017e48  jnz     short loc_140017E78
0x140017e4a  add     rcx, 20h ; ' '
0x140017e4e  dec     r9
0x140017e51  jnz     short loc_140017E20
0x140017e53  and     r8, 1Fh
0x140017e57  mov     r9, r8
0x140017e5a  shr     r9, 3
0x140017e5e  jz      short loc_140017DFB
0x140017e60  mov     rax, [rcx]
0x140017e63  cmp     rax, [rcx+rdx]
0x140017e67  jnz     short loc_140017E84
0x140017e69  add     rcx, 8
0x140017e6d  dec     r9
0x140017e70  jnz     short loc_140017E60
0x140017e72  and     r8, 7
0x140017e76  jmp     short loc_140017DFB
0x140017e78  add     rcx, 8
0x140017e7c  add     rcx, 8
0x140017e80  add     rcx, 8
0x140017e84  mov     rcx, [rdx+rcx]
0x140017e88  bswap   rax
0x140017e8b  bswap   rcx
0x140017e8e  cmp     rax, rcx
0x140017e91  sbb     eax, eax
0x140017e93  sbb     eax, 0FFFFFFFFh
0x140017e96  retn
```
