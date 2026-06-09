# CTSparseBlock<ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(ulong)

- ea: `0x18002a110`
- end: `0x18002a26e`
- name: `?RemoveValue@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a080`

## callees

- `0x18002a110`
- `0x18002a2dc`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(
        __int64 a1,
        unsigned int a2)
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

  for ( i = a1; i; i = *(_QWORD *)(i + 104) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 112);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 120);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 120) = v7 - 1;
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
      if ( (*(_BYTE *)(i + 20)
          & CTSparseBlock<unsigned long,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks[0]) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::SetValue(
               a1,
               v9 - 1,
               *(unsigned int *)(i + 24));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 4 * (v11 + 6LL)), (const void *)(i + 4 * (v11 + 1 + 6LL)), 4LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 20); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 20) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 20) < 0 )
        *(_BYTE *)(v13 + i + 20) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 20) &= *((_BYTE *)&qword_18004A3C0 - v16);
        *(_BYTE *)(v14 + 20) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::s_bLeftBitMasks
                                + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 104) == *(_QWORD *)(a1 + 112) )
    {
      *(_QWORD *)(a1 + 112) = i;
      *(_DWORD *)(a1 + 120) = 19;
    }
    i = *(_QWORD *)(i + 104);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002a110  push    rbx
0x18002a112  push    rbp
0x18002a113  push    rsi
0x18002a114  push    rdi
0x18002a115  push    r12
0x18002a117  push    r14
0x18002a119  push    r15
0x18002a11b  sub     rsp, 20h
0x18002a11f  mov     ebp, edx
0x18002a121  mov     rdi, rcx
0x18002a124  mov     rbx, rcx
0x18002a127  test    rcx, rcx
0x18002a12a  jz      short loc_18002A13F
0x18002a12c  mov     eax, [rbx+8]
0x18002a12f  add     eax, 14h
0x18002a132  cmp     ebp, eax
0x18002a134  jb      short loc_18002A13F
0x18002a136  mov     rbx, [rbx+68h]
0x18002a13a  test    rbx, rbx
0x18002a13d  jnz     short loc_18002A12C
0x18002a13f  mov     rax, [rcx+70h]
0x18002a143  xor     r12d, r12d
0x18002a146  test    rax, rax
0x18002a149  jz      short loc_18002A167
0x18002a14b  mov     edx, [rcx+78h]
0x18002a14e  mov     ecx, [rax+8]
0x18002a151  add     ecx, edx
0x18002a153  cmp     ebp, ecx
0x18002a155  jnb     short loc_18002A167
0x18002a157  test    edx, edx
0x18002a159  jnz     short loc_18002A161
0x18002a15b  lea     r12d, [rdx+1]
0x18002a15f  jmp     short loc_18002A167
0x18002a161  lea     eax, [rdx-1]
0x18002a164  mov     [rdi+78h], eax
0x18002a167  xor     r14d, r14d
0x18002a16a  jmp     loc_18002A253
0x18002a16f  mov     edx, [rbx+8]
0x18002a172  cmp     ebp, edx
0x18002a174  jb      short loc_18002A182
0x18002a176  mov     esi, ebp
0x18002a178  mov     r15d, 1
0x18002a17e  sub     esi, edx
0x18002a180  jmp     short loc_18002A1AB
0x18002a182  mov     al, [rbx+14h]
0x18002a185  xor     r15d, r15d
0x18002a188  xor     esi, esi
0x18002a18a  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks
0x18002a190  jz      short loc_18002A1AB
0x18002a192  mov     r8d, [rbx+18h]
0x18002a196  dec     edx
0x18002a198  mov     rcx, rdi
0x18002a19b  call    ?SetValue@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@$0A@@@QEAAJKUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@@Z; CTSparseBlock<ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::SetValue(ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER)
0x18002a1a0  mov     r14d, eax
0x18002a1a3  test    eax, eax
0x18002a1a5  js      loc_18002A25C
0x18002a1ab  mov     r8d, 13h
0x18002a1b1  mov     ecx, esi
0x18002a1b3  add     rcx, 6
0x18002a1b7  lea     edx, [rsi+1]
0x18002a1ba  sub     r8d, esi
0x18002a1bd  lea     rdx, [rdx+6]
0x18002a1c1  shl     r8, 2; Size
0x18002a1c5  lea     rdx, [rbx+rdx*4]; Src
0x18002a1c9  lea     rcx, [rbx+rcx*4]; void *
0x18002a1cd  call    memmove_0
0x18002a1d2  mov     eax, esi
0x18002a1d4  shr     eax, 3
0x18002a1d7  mov     edx, eax
0x18002a1d9  lea     r10, [rax+rbx]
0x18002a1dd  mov     r11b, [r10+14h]
0x18002a1e1  cmp     eax, 3
0x18002a1e4  jnb     short loc_18002A205
0x18002a1e6  shl     byte ptr [rdx+rbx+14h], 1
0x18002a1ea  cmp     edx, 2
0x18002a1ed  jnb     short loc_18002A1FE
0x18002a1ef  lea     eax, [rdx+1]
0x18002a1f2  cmp     byte ptr [rax+rbx+14h], 0
0x18002a1f7  jge     short loc_18002A1FE
0x18002a1f9  or      byte ptr [rdx+rbx+14h], 1
0x18002a1fe  inc     edx
0x18002a200  cmp     edx, 3
0x18002a203  jb      short loc_18002A1E6
0x18002a205  test    r15d, r15d
0x18002a208  jz      short loc_18002A235
0x18002a20a  and     sil, 7
0x18002a20e  jbe     short loc_18002A235
0x18002a210  movzx   ecx, sil
0x18002a214  lea     rax, qword_18004A3C0
0x18002a21b  sub     rax, rcx
0x18002a21e  mov     al, [rax]
0x18002a220  and     [r10+14h], al
0x18002a224  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::s_bLeftBitMasks
0x18002a22b  mov     al, [rcx+rax]
0x18002a22e  and     al, r11b
0x18002a231  or      [r10+14h], al
0x18002a235  test    r12d, r12d
0x18002a238  jz      short loc_18002A24F
0x18002a23a  mov     rax, [rdi+70h]
0x18002a23e  cmp     [rbx+68h], rax
0x18002a242  jnz     short loc_18002A24F
0x18002a244  mov     [rdi+70h], rbx
0x18002a248  mov     dword ptr [rdi+78h], 13h
0x18002a24f  mov     rbx, [rbx+68h]
0x18002a253  test    rbx, rbx
0x18002a256  jnz     loc_18002A16F
0x18002a25c  mov     eax, r14d
0x18002a25f  add     rsp, 20h
0x18002a263  pop     r15
0x18002a265  pop     r14
0x18002a267  pop     r12
0x18002a269  pop     rdi
0x18002a26a  pop     rsi
0x18002a26b  pop     rbp
0x18002a26c  pop     rbx
0x18002a26d  retn
```
