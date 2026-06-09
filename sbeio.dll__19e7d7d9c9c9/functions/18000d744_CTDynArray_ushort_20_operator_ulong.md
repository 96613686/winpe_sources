# CTDynArray<ushort,20>::operator[](ulong)

- ea: `0x18000d744`
- end: `0x18000d7a6`
- name: `??A?$CTDynArray@G$0BE@@@QEBAGK@Z`
- size: `98`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e4e0`
- `0x18000e990`
- `0x18000efd0`
- `0x1800194a0`
- `0x18001c840`
- `0x18001e640`
- `0x180026100`

## callees

- `0x18000d744`

## pseudocode

```c
__int64 __fastcall CTDynArray<unsigned short,20>::operator[](__int64 a1, unsigned int a2)
{
  unsigned __int16 v2; // r10
  __int64 i; // r8
  unsigned int v5; // ecx
  unsigned int v6; // edx

  v2 = 0;
  if ( a2 < *(_DWORD *)(a1 + 88) )
  {
    for ( i = a1; i; i = *(_QWORD *)(i + 64) )
    {
      v5 = *(_DWORD *)(i + 8);
      if ( a2 >= v5 && a2 < v5 + 20 )
      {
        v6 = a2 - v5;
        if ( (*(_BYTE *)(((unsigned __int64)v6 >> 3) + i + 18)
            & (unsigned __int8)CTSparseBlock<unsigned long,unsigned short,20,0>::s_bSingleBitMasks[v6 & 7]) != 0 )
          return *(unsigned __int16 *)(i + 2LL * v6 + 22);
        break;
      }
    }
    if ( (*(_BYTE *)(a1 + 12) & 1) != 0 )
      return *(unsigned __int16 *)(a1 + 16);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d744  xor     r10d, r10d
0x18000d747  mov     r9, rcx
0x18000d74a  cmp     edx, [rcx+58h]
0x18000d74d  jnb     short loc_18000D7A1
0x18000d74f  mov     r8, rcx
0x18000d752  test    r8, r8
0x18000d755  jz      short loc_18000D795
0x18000d757  mov     ecx, [r8+8]
0x18000d75b  cmp     edx, ecx
0x18000d75d  jb      short loc_18000D766
0x18000d75f  lea     eax, [rcx+14h]
0x18000d762  cmp     edx, eax
0x18000d764  jb      short loc_18000D76C
0x18000d766  mov     r8, [r8+40h]
0x18000d76a  jmp     short loc_18000D752
0x18000d76c  sub     edx, ecx
0x18000d76e  mov     ecx, edx
0x18000d770  mov     eax, edx
0x18000d772  and     ecx, 7
0x18000d775  shr     rax, 3
0x18000d779  mov     r11d, edx
0x18000d77c  lea     rdx, ?s_bSingleBitMasks@?$CTSparseBlock@KG$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,ushort,20,0>::s_bSingleBitMasks
0x18000d783  mov     al, [rax+r8+12h]
0x18000d788  test    [rcx+rdx], al
0x18000d78b  jz      short loc_18000D795
0x18000d78d  movzx   r10d, word ptr [r8+r11*2+16h]
0x18000d793  jmp     short loc_18000D7A1
0x18000d795  test    byte ptr [r9+0Ch], 1
0x18000d79a  jz      short loc_18000D7A1
0x18000d79c  movzx   r10d, word ptr [r9+10h]
0x18000d7a1  movzx   eax, r10w
0x18000d7a5  retn
```
