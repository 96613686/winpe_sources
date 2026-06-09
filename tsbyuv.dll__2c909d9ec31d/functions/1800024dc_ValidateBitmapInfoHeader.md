# ValidateBitmapInfoHeader

- ea: `0x1800024dc`
- end: `0x180002633`
- name: `ValidateBitmapInfoHeader`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002310`

## callees

- `0x1800024dc`

## pseudocode

```c
_BOOL8 __fastcall ValidateBitmapInfoHeader(unsigned int *a1)
{
  __int64 v1; // rsi
  int v3; // eax
  unsigned __int16 v4; // r9
  unsigned int v5; // r10d
  unsigned int v6; // ecx
  int v7; // r11d
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // r10d
  unsigned int v11; // edx
  unsigned int v12; // r10d
  __int64 v13; // rcx

  v1 = *a1;
  if ( (unsigned int)(v1 - 40) > 0xFD8 )
    return 0;
  if ( !a1[1] )
    return 0;
  v3 = a1[2];
  if ( !v3 )
    return 0;
  v4 = *((_WORD *)a1 + 7);
  v5 = 32;
  if ( v4 )
    v5 = v4;
  if ( v4 > 0xC8u )
    return 0;
  v6 = a1[1];
  v7 = -v3;
  if ( v3 > 0 )
    v7 = v3;
  v8 = v5 * v6;
  if ( v8 / v5 != a1[1] )
    return 0;
  v9 = ((v8 >> 3) + 3) & 0xFFFFFFFC;
  v10 = v7 * v9;
  if ( v9 )
  {
    if ( v10 / v9 != v7 )
      return 0;
  }
  if ( v10 > 0x40000000 )
    return 0;
  if ( a1[5] > 0x40000000 )
    return 0;
  v11 = a1[8];
  if ( v11 > 0x100 )
    return 0;
  if ( !v11 && (unsigned __int16)(v4 - 1) <= 7u )
    v11 = 1 << v4;
  v12 = a1[4];
  if ( v12 == 3 && ((v4 - 16) & 0xFFEF) != 0 )
    return 0;
  v13 = 12;
  if ( v12 != 3 )
    v13 = 0;
  return v1 + v13 + 4 * (unsigned __int64)v11 <= 0x90C
      && (v12 && v12 != 3 || !a1[5] || v7 * (((a1[1] * v4 + 31) >> 3) & 0x1FFFFFFC) <= a1[5]);
}

```

## disassembly

```asm
0x1800024dc  push    rbp
0x1800024de  push    rsi
0x1800024df  push    r14
0x1800024e1  mov     esi, [rcx]
0x1800024e3  mov     r8, rcx
0x1800024e6  lea     eax, [rsi-28h]
0x1800024e9  cmp     eax, 0FD8h
0x1800024ee  ja      loc_18000262C
0x1800024f4  xor     ebp, ebp
0x1800024f6  cmp     [rcx+4], ebp
0x1800024f9  jz      loc_18000262C
0x1800024ff  mov     eax, [rcx+8]
0x180002502  test    eax, eax
0x180002504  jz      loc_18000262C
0x18000250a  movzx   r9d, word ptr [rcx+0Eh]
0x18000250f  lea     r10d, [rbp+20h]
0x180002513  test    r9w, r9w
0x180002517  jz      short loc_18000251D
0x180002519  movzx   r10d, r9w
0x18000251d  mov     ecx, 0C8h
0x180002522  cmp     r9w, cx
0x180002526  ja      loc_18000262C
0x18000252c  mov     ecx, [r8+4]
0x180002530  mov     r11d, eax
0x180002533  neg     r11d
0x180002536  cmovs   r11d, eax
0x18000253a  imul    ecx, r10d
0x18000253e  test    r10d, r10d
0x180002541  jz      short loc_180002554
0x180002543  xor     edx, edx
0x180002545  mov     eax, ecx
0x180002547  div     r10d
0x18000254a  cmp     eax, [r8+4]
0x18000254e  jnz     loc_18000262C
0x180002554  shr     ecx, 3
0x180002557  add     ecx, 3
0x18000255a  and     ecx, 0FFFFFFFCh
0x18000255d  mov     r10d, ecx
0x180002560  imul    r10d, r11d
0x180002564  test    ecx, ecx
0x180002566  jz      short loc_180002578
0x180002568  xor     edx, edx
0x18000256a  mov     eax, r10d
0x18000256d  div     ecx
0x18000256f  cmp     eax, r11d
0x180002572  jnz     loc_18000262C
0x180002578  mov     eax, 40000000h
0x18000257d  cmp     r10d, eax
0x180002580  ja      loc_18000262C
0x180002586  cmp     [r8+14h], eax
0x18000258a  ja      loc_18000262C
0x180002590  mov     edx, [r8+20h]
0x180002594  cmp     edx, 100h
0x18000259a  ja      loc_18000262C
0x1800025a0  mov     r14d, 1
0x1800025a6  test    edx, edx
0x1800025a8  jnz     short loc_1800025C0
0x1800025aa  movzx   eax, r9w
0x1800025ae  sub     ax, r14w
0x1800025b2  cmp     ax, 7
0x1800025b6  ja      short loc_1800025C0
0x1800025b8  mov     ecx, r9d
0x1800025bb  mov     edx, r14d
0x1800025be  shl     edx, cl
0x1800025c0  mov     r10d, [r8+10h]
0x1800025c4  cmp     r10d, 3
0x1800025c8  jnz     short loc_1800025D8
0x1800025ca  lea     eax, [r9-10h]
0x1800025ce  mov     ecx, 0FFEFh
0x1800025d3  test    cx, ax
0x1800025d6  jnz     short loc_18000262C
0x1800025d8  cmp     r10d, 3
0x1800025dc  mov     eax, edx
0x1800025de  mov     ecx, 0Ch
0x1800025e3  cmovnz  rcx, rbp
0x1800025e7  lea     rcx, [rcx+rax*4]
0x1800025eb  add     rcx, rsi
0x1800025ee  cmp     rcx, 90Ch
0x1800025f5  ja      short loc_18000262C
0x1800025f7  test    r10d, r10d
0x1800025fa  jz      short loc_180002602
0x1800025fc  cmp     r10d, 3
0x180002600  jnz     short loc_180002627
0x180002602  cmp     [r8+14h], ebp
0x180002606  jz      short loc_180002627
0x180002608  movzx   ecx, r9w
0x18000260c  imul    ecx, [r8+4]
0x180002611  add     ecx, 1Fh
0x180002614  shr     ecx, 3
0x180002617  and     ecx, 1FFFFFFCh
0x18000261d  imul    ecx, r11d
0x180002621  cmp     ecx, [r8+14h]
0x180002625  ja      short loc_18000262C
0x180002627  mov     eax, r14d
0x18000262a  jmp     short loc_18000262E
0x18000262c  xor     eax, eax
0x18000262e  pop     r14
0x180002630  pop     rsi
0x180002631  pop     rbp
0x180002632  retn
```
