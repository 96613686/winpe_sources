# ParsePathElement

- ea: `0x1400018f4`
- end: `0x140001970`
- name: `ParsePathElement`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x1400018f4`

## pseudocode

```c
__int64 __fastcall ParsePathElement(__int16 *a1, __int64 a2, __int64 a3)
{
  unsigned __int16 v3; // r9
  unsigned __int64 v4; // r10
  __int64 i; // rcx
  __int16 v6; // r9
  __int64 result; // rax

  v3 = *a1;
  v4 = *((_QWORD *)a1 + 1);
  for ( i = 0; v3; v3 -= 2 )
  {
    if ( *(_WORD *)v4 != 92 )
      break;
    v4 += 2LL;
  }
  if ( v3 >> 1 )
  {
    do
    {
      if ( *(_WORD *)(v4 + 2 * i) == 92 )
        break;
      i = (unsigned int)(i + 1);
    }
    while ( (unsigned int)i < v3 >> 1 );
  }
  *(_WORD *)(a2 + 2) = 2 * i;
  *(_WORD *)a2 = 2 * i;
  v6 = v3 - 2 * i;
  *(_QWORD *)(a2 + 8) = v4 & -(__int64)(-2 * (_WORD)i != 0);
  *(_WORD *)(a3 + 2) = v6;
  *(_WORD *)a3 = v6;
  result = (2 * i + v4) & -(__int64)(v6 != 0);
  *(_QWORD *)(a3 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x1400018f4  movzx   r9d, word ptr [rcx]
0x1400018f8  mov     r11, rdx
0x1400018fb  mov     r10, [rcx+8]
0x1400018ff  xor     ecx, ecx
0x140001901  test    r9w, r9w
0x140001905  jz      short loc_14000191D
0x140001907  cmp     word ptr [r10], 5Ch ; '\'
0x14000190c  jnz     short loc_14000191D
0x14000190e  add     r10, 2
0x140001912  mov     eax, 0FFFEh
0x140001917  add     r9w, ax
0x14000191b  jnz     short loc_140001907
0x14000191d  movzx   edx, r9w
0x140001921  shr     edx, 1
0x140001923  jz      short loc_140001933
0x140001925  cmp     word ptr [r10+rcx*2], 5Ch ; '\'
0x14000192b  jz      short loc_140001933
0x14000192d  inc     ecx
0x14000192f  cmp     ecx, edx
0x140001931  jb      short loc_140001925
0x140001933  lea     rdx, [rcx+rcx]
0x140001937  mov     [r11+2], dx
0x14000193c  movzx   eax, dx
0x14000193f  neg     ax
0x140001942  mov     [r11], dx
0x140001946  sbb     rcx, rcx
0x140001949  sub     r9w, dx
0x14000194d  and     rcx, r10
0x140001950  mov     [r11+8], rcx
0x140001954  lea     rcx, [rdx+r10]
0x140001958  mov     [r8+2], r9w
0x14000195d  mov     [r8], r9w
0x140001961  neg     r9w
0x140001965  sbb     rax, rax
0x140001968  and     rax, rcx
0x14000196b  mov     [r8+8], rax
0x14000196f  retn
```
