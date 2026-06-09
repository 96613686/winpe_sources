# CTSparseBlock<ulong,ushort,20,0>::RemoveValue(ulong)

- ea: `0x18001fd4c`
- end: `0x18001feaa`
- name: `?RemoveValue@?$CTSparseBlock@KG$0BE@$0A@@@QEAAJK@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017dc0`

## callees

- `0x18000ee4c`
- `0x18001fd4c`
- `0x18002a07c`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned short,20,0>::RemoveValue(__int64 a1, unsigned int a2)
{
  __int64 i; // rbx
  __int64 v5; // rax
  int v6; // r12d
  int v7; // edx
  int v8; // r14d
  unsigned int v9; // edx
  int v10; // r15d
  unsigned int v11; // esi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r10
  char j; // r11
  unsigned __int8 v16; // si

  for ( i = a1; i; i = *(_QWORD *)(i + 64) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 72);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 80);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 80) = v7 - 1;
      else
        v6 = 1;
    }
  }
  v8 = 0;
  while ( i )
  {
    v9 = *(_DWORD *)(i + 8);
    if ( a2 < v9 )
    {
      v10 = 0;
      v11 = 0;
      if ( (*(_BYTE *)(i + 18) & (unsigned __int8)CTSparseBlock<unsigned long,unsigned short,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,unsigned short,20,0>::SetValue(a1, v9 - 1, *(unsigned __int16 *)(i + 22));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 2 * (v11 + 11LL)), (const void *)(i + 2 * (v11 + 1 + 11LL)), 2LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 18); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 18) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 18) < 0 )
        *(_BYTE *)(v13 + i + 18) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 18) &= *((_BYTE *)&qword_180032130 - v16);
        *(_BYTE *)(v14 + 18) |= j & *((_BYTE *)CTSparseBlock<unsigned long,unsigned short,20,0>::s_bLeftBitMasks + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 64) == *(_QWORD *)(a1 + 72) )
    {
      *(_QWORD *)(a1 + 72) = i;
      *(_DWORD *)(a1 + 80) = 19;
    }
    i = *(_QWORD *)(i + 64);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001fd4c  push    rbx
0x18001fd4e  push    rbp
0x18001fd4f  push    rsi
0x18001fd50  push    rdi
0x18001fd51  push    r12
0x18001fd53  push    r14
0x18001fd55  push    r15
0x18001fd57  sub     rsp, 20h
0x18001fd5b  mov     ebp, edx
0x18001fd5d  mov     rdi, rcx
0x18001fd60  mov     rbx, rcx
0x18001fd63  test    rcx, rcx
0x18001fd66  jz      short loc_18001FD7B
0x18001fd68  mov     eax, [rbx+8]
0x18001fd6b  add     eax, 14h
0x18001fd6e  cmp     ebp, eax
0x18001fd70  jb      short loc_18001FD7B
0x18001fd72  mov     rbx, [rbx+40h]
0x18001fd76  test    rbx, rbx
0x18001fd79  jnz     short loc_18001FD68
0x18001fd7b  mov     rax, [rcx+48h]
0x18001fd7f  xor     r12d, r12d
0x18001fd82  test    rax, rax
0x18001fd85  jz      short loc_18001FDA3
0x18001fd87  mov     edx, [rcx+50h]
0x18001fd8a  mov     ecx, [rax+8]
0x18001fd8d  add     ecx, edx
0x18001fd8f  cmp     ebp, ecx
0x18001fd91  jnb     short loc_18001FDA3
0x18001fd93  test    edx, edx
0x18001fd95  jnz     short loc_18001FD9D
0x18001fd97  lea     r12d, [rdx+1]
0x18001fd9b  jmp     short loc_18001FDA3
0x18001fd9d  lea     eax, [rdx-1]
0x18001fda0  mov     [rdi+50h], eax
0x18001fda3  xor     r14d, r14d
0x18001fda6  jmp     loc_18001FE8F
0x18001fdab  mov     edx, [rbx+8]
0x18001fdae  cmp     ebp, edx
0x18001fdb0  jb      short loc_18001FDBE
0x18001fdb2  mov     esi, ebp
0x18001fdb4  mov     r15d, 1
0x18001fdba  sub     esi, edx
0x18001fdbc  jmp     short loc_18001FDE8
0x18001fdbe  mov     al, [rbx+12h]
0x18001fdc1  xor     r15d, r15d
0x18001fdc4  xor     esi, esi
0x18001fdc6  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KG$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,ushort,20,0>::s_bSingleBitMasks
0x18001fdcc  jz      short loc_18001FDE8
0x18001fdce  movzx   r8d, word ptr [rbx+16h]
0x18001fdd3  dec     edx
0x18001fdd5  mov     rcx, rdi
0x18001fdd8  call    ?SetValue@?$CTSparseBlock@KG$0BE@$0A@@@QEAAJKG@Z; CTSparseBlock<ulong,ushort,20,0>::SetValue(ulong,ushort)
0x18001fddd  mov     r14d, eax
0x18001fde0  test    eax, eax
0x18001fde2  js      loc_18001FE98
0x18001fde8  mov     r8d, 13h
0x18001fdee  mov     ecx, esi
0x18001fdf0  add     rcx, 0Bh
0x18001fdf4  lea     edx, [rsi+1]
0x18001fdf7  sub     r8d, esi
0x18001fdfa  lea     rdx, [rdx+0Bh]
0x18001fdfe  add     r8, r8; Size
0x18001fe01  lea     rdx, [rbx+rdx*2]; Src
0x18001fe05  lea     rcx, [rbx+rcx*2]; void *
0x18001fe09  call    memmove_0
0x18001fe0e  mov     eax, esi
0x18001fe10  shr     eax, 3
0x18001fe13  mov     edx, eax
0x18001fe15  lea     r10, [rax+rbx]
0x18001fe19  mov     r11b, [r10+12h]
0x18001fe1d  cmp     eax, 3
0x18001fe20  jnb     short loc_18001FE41
0x18001fe22  shl     byte ptr [rdx+rbx+12h], 1
0x18001fe26  cmp     edx, 2
0x18001fe29  jnb     short loc_18001FE3A
0x18001fe2b  lea     eax, [rdx+1]
0x18001fe2e  cmp     byte ptr [rax+rbx+12h], 0
0x18001fe33  jge     short loc_18001FE3A
0x18001fe35  or      byte ptr [rdx+rbx+12h], 1
0x18001fe3a  inc     edx
0x18001fe3c  cmp     edx, 3
0x18001fe3f  jb      short loc_18001FE22
0x18001fe41  test    r15d, r15d
0x18001fe44  jz      short loc_18001FE71
0x18001fe46  and     sil, 7
0x18001fe4a  jbe     short loc_18001FE71
0x18001fe4c  movzx   ecx, sil
0x18001fe50  lea     rax, qword_180032130
0x18001fe57  sub     rax, rcx
0x18001fe5a  mov     al, [rax]
0x18001fe5c  and     [r10+12h], al
0x18001fe60  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KG$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,ushort,20,0>::s_bLeftBitMasks
0x18001fe67  mov     al, [rcx+rax]
0x18001fe6a  and     al, r11b
0x18001fe6d  or      [r10+12h], al
0x18001fe71  test    r12d, r12d
0x18001fe74  jz      short loc_18001FE8B
0x18001fe76  mov     rax, [rdi+48h]
0x18001fe7a  cmp     [rbx+40h], rax
0x18001fe7e  jnz     short loc_18001FE8B
0x18001fe80  mov     [rdi+48h], rbx
0x18001fe84  mov     dword ptr [rdi+50h], 13h
0x18001fe8b  mov     rbx, [rbx+40h]
0x18001fe8f  test    rbx, rbx
0x18001fe92  jnz     loc_18001FDAB
0x18001fe98  mov     eax, r14d
0x18001fe9b  add     rsp, 20h
0x18001fe9f  pop     r15
0x18001fea1  pop     r14
0x18001fea3  pop     r12
0x18001fea5  pop     rdi
0x18001fea6  pop     rsi
0x18001fea7  pop     rbp
0x18001fea8  pop     rbx
0x18001fea9  retn
```
