# CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(ulong)

- ea: `0x18002773c`
- end: `0x18002789a`
- name: `?RemoveValue@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027330`

## callees

- `0x18002773c`
- `0x1800278a0`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(
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
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::SetValue(
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
        *(_BYTE *)(v14 + 20) &= *((_BYTE *)&qword_18004A348 - v16);
        *(_BYTE *)(v14 + 20) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::s_bLeftBitMasks
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
0x18002773c  push    rbx
0x18002773e  push    rbp
0x18002773f  push    rsi
0x180027740  push    rdi
0x180027741  push    r12
0x180027743  push    r14
0x180027745  push    r15
0x180027747  sub     rsp, 20h
0x18002774b  mov     ebp, edx
0x18002774d  mov     rdi, rcx
0x180027750  mov     rbx, rcx
0x180027753  test    rcx, rcx
0x180027756  jz      short loc_18002776B
0x180027758  mov     eax, [rbx+8]
0x18002775b  add     eax, 14h
0x18002775e  cmp     ebp, eax
0x180027760  jb      short loc_18002776B
0x180027762  mov     rbx, [rbx+68h]
0x180027766  test    rbx, rbx
0x180027769  jnz     short loc_180027758
0x18002776b  mov     rax, [rcx+70h]
0x18002776f  xor     r12d, r12d
0x180027772  test    rax, rax
0x180027775  jz      short loc_180027793
0x180027777  mov     edx, [rcx+78h]
0x18002777a  mov     ecx, [rax+8]
0x18002777d  add     ecx, edx
0x18002777f  cmp     ebp, ecx
0x180027781  jnb     short loc_180027793
0x180027783  test    edx, edx
0x180027785  jnz     short loc_18002778D
0x180027787  lea     r12d, [rdx+1]
0x18002778b  jmp     short loc_180027793
0x18002778d  lea     eax, [rdx-1]
0x180027790  mov     [rdi+78h], eax
0x180027793  xor     r14d, r14d
0x180027796  jmp     loc_18002787F
0x18002779b  mov     edx, [rbx+8]
0x18002779e  cmp     ebp, edx
0x1800277a0  jb      short loc_1800277AE
0x1800277a2  mov     esi, ebp
0x1800277a4  mov     r15d, 1
0x1800277aa  sub     esi, edx
0x1800277ac  jmp     short loc_1800277D7
0x1800277ae  mov     al, [rbx+14h]
0x1800277b1  xor     r15d, r15d
0x1800277b4  xor     esi, esi
0x1800277b6  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks
0x1800277bc  jz      short loc_1800277D7
0x1800277be  mov     r8d, [rbx+18h]
0x1800277c2  dec     edx
0x1800277c4  mov     rcx, rdi
0x1800277c7  call    ?SetValue@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@QEAAJKUINDEX_SPECIFIER@CASFMarkerObjectBase@@@Z; CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::SetValue(ulong,CASFMarkerObjectBase::INDEX_SPECIFIER)
0x1800277cc  mov     r14d, eax
0x1800277cf  test    eax, eax
0x1800277d1  js      loc_180027888
0x1800277d7  mov     r8d, 13h
0x1800277dd  mov     ecx, esi
0x1800277df  add     rcx, 6
0x1800277e3  lea     edx, [rsi+1]
0x1800277e6  sub     r8d, esi
0x1800277e9  lea     rdx, [rdx+6]
0x1800277ed  shl     r8, 2; Size
0x1800277f1  lea     rdx, [rbx+rdx*4]; Src
0x1800277f5  lea     rcx, [rbx+rcx*4]; void *
0x1800277f9  call    memmove_0
0x1800277fe  mov     eax, esi
0x180027800  shr     eax, 3
0x180027803  mov     edx, eax
0x180027805  lea     r10, [rax+rbx]
0x180027809  mov     r11b, [r10+14h]
0x18002780d  cmp     eax, 3
0x180027810  jnb     short loc_180027831
0x180027812  shl     byte ptr [rdx+rbx+14h], 1
0x180027816  cmp     edx, 2
0x180027819  jnb     short loc_18002782A
0x18002781b  lea     eax, [rdx+1]
0x18002781e  cmp     byte ptr [rax+rbx+14h], 0
0x180027823  jge     short loc_18002782A
0x180027825  or      byte ptr [rdx+rbx+14h], 1
0x18002782a  inc     edx
0x18002782c  cmp     edx, 3
0x18002782f  jb      short loc_180027812
0x180027831  test    r15d, r15d
0x180027834  jz      short loc_180027861
0x180027836  and     sil, 7
0x18002783a  jbe     short loc_180027861
0x18002783c  movzx   ecx, sil
0x180027840  lea     rax, qword_18004A348
0x180027847  sub     rax, rcx
0x18002784a  mov     al, [rax]
0x18002784c  and     [r10+14h], al
0x180027850  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::s_bLeftBitMasks
0x180027857  mov     al, [rcx+rax]
0x18002785a  and     al, r11b
0x18002785d  or      [r10+14h], al
0x180027861  test    r12d, r12d
0x180027864  jz      short loc_18002787B
0x180027866  mov     rax, [rdi+70h]
0x18002786a  cmp     [rbx+68h], rax
0x18002786e  jnz     short loc_18002787B
0x180027870  mov     [rdi+70h], rbx
0x180027874  mov     dword ptr [rdi+78h], 13h
0x18002787b  mov     rbx, [rbx+68h]
0x18002787f  test    rbx, rbx
0x180027882  jnz     loc_18002779B
0x180027888  mov     eax, r14d
0x18002788b  add     rsp, 20h
0x18002788f  pop     r15
0x180027891  pop     r14
0x180027893  pop     r12
0x180027895  pop     rdi
0x180027896  pop     rsi
0x180027897  pop     rbp
0x180027898  pop     rbx
0x180027899  retn
```
