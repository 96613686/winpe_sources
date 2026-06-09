# CTSparseBlock<ulong,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::RemoveValue(ulong)

- ea: `0x1800241c8`
- end: `0x180024341`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023ed0`

## callees

- `0x1800241c8`
- `0x180024690`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::RemoveValue(
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

  for ( i = a1; i; i = *(_QWORD *)(i + 192) )
  {
    if ( a2 < *(_DWORD *)(i + 8) + 20 )
      break;
  }
  v5 = *(_QWORD *)(a1 + 200);
  v6 = 0;
  if ( v5 )
  {
    v7 = *(_DWORD *)(a1 + 208);
    if ( a2 < v7 + *(_DWORD *)(v5 + 8) )
    {
      if ( v7 )
        *(_DWORD *)(a1 + 208) = v7 - 1;
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
      if ( (*(_BYTE *)(i + 24)
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::SetValue(
               a1,
               v9 - 1,
               *(_QWORD *)(i + 32));
        if ( v8 < 0 )
          return (unsigned int)v8;
      }
    }
    else
    {
      v10 = 1;
      v11 = a2 - v9;
    }
    memmove_0((void *)(i + 8 * (v11 + 4LL)), (const void *)(i + 8 * (v11 + 1 + 4LL)), 8LL * (19 - v11));
    v12 = v11 >> 3;
    v13 = v12;
    v14 = v12 + i;
    for ( j = *(_BYTE *)(v12 + i + 24); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 24) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 24) < 0 )
        *(_BYTE *)(v13 + i + 24) |= 1u;
    }
    if ( v10 )
    {
      v16 = v11 & 7;
      if ( v16 )
      {
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A290 - v16);
        *(_BYTE *)(v14 + 24) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::s_bLeftBitMasks
                                + v16);
      }
    }
    if ( v6 && *(_QWORD *)(i + 192) == *(_QWORD *)(a1 + 200) )
    {
      *(_QWORD *)(a1 + 200) = i;
      *(_DWORD *)(a1 + 208) = 19;
    }
    i = *(_QWORD *)(i + 192);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800241c8  push    rbx
0x1800241ca  push    rbp
0x1800241cb  push    rsi
0x1800241cc  push    rdi
0x1800241cd  push    r12
0x1800241cf  push    r14
0x1800241d1  push    r15
0x1800241d3  sub     rsp, 20h
0x1800241d7  mov     ebp, edx
0x1800241d9  mov     rdi, rcx
0x1800241dc  mov     rbx, rcx
0x1800241df  test    rcx, rcx
0x1800241e2  jz      short loc_1800241FA
0x1800241e4  mov     eax, [rbx+8]
0x1800241e7  add     eax, 14h
0x1800241ea  cmp     ebp, eax
0x1800241ec  jb      short loc_1800241FA
0x1800241ee  mov     rbx, [rbx+0C0h]
0x1800241f5  test    rbx, rbx
0x1800241f8  jnz     short loc_1800241E4
0x1800241fa  mov     rax, [rcx+0C8h]
0x180024201  xor     r12d, r12d
0x180024204  test    rax, rax
0x180024207  jz      short loc_18002422B
0x180024209  mov     edx, [rcx+0D0h]
0x18002420f  mov     ecx, [rax+8]
0x180024212  add     ecx, edx
0x180024214  cmp     ebp, ecx
0x180024216  jnb     short loc_18002422B
0x180024218  test    edx, edx
0x18002421a  jnz     short loc_180024222
0x18002421c  lea     r12d, [rdx+1]
0x180024220  jmp     short loc_18002422B
0x180024222  lea     eax, [rdx-1]
0x180024225  mov     [rdi+0D0h], eax
0x18002422b  xor     r14d, r14d
0x18002422e  jmp     loc_180024326
0x180024233  mov     edx, [rbx+8]
0x180024236  cmp     ebp, edx
0x180024238  jb      short loc_180024246
0x18002423a  mov     esi, ebp
0x18002423c  mov     r15d, 1
0x180024242  sub     esi, edx
0x180024244  jmp     short loc_18002426F
0x180024246  mov     al, [rbx+18h]
0x180024249  xor     r15d, r15d
0x18002424c  xor     esi, esi
0x18002424e  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::s_bSingleBitMasks
0x180024254  jz      short loc_18002426F
0x180024256  mov     r8, [rbx+20h]
0x18002425a  dec     edx
0x18002425c  mov     rcx, rdi
0x18002425f  call    ?SetValue@?$CTSparseBlock@KPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJKPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::SetValue(ulong,CASFMutualExclusionObjectBase::EXCLUSION_REC *)
0x180024264  mov     r14d, eax
0x180024267  test    eax, eax
0x180024269  js      loc_18002432F
0x18002426f  mov     r8d, 13h
0x180024275  mov     ecx, esi
0x180024277  add     rcx, 4
0x18002427b  lea     edx, [rsi+1]
0x18002427e  sub     r8d, esi
0x180024281  lea     rdx, [rdx+4]
0x180024285  shl     r8, 3; Size
0x180024289  lea     rdx, [rbx+rdx*8]; Src
0x18002428d  lea     rcx, [rbx+rcx*8]; void *
0x180024291  call    memmove_0
0x180024296  mov     eax, esi
0x180024298  shr     eax, 3
0x18002429b  mov     edx, eax
0x18002429d  lea     r10, [rax+rbx]
0x1800242a1  mov     r11b, [r10+18h]
0x1800242a5  cmp     eax, 3
0x1800242a8  jnb     short loc_1800242C9
0x1800242aa  shl     byte ptr [rdx+rbx+18h], 1
0x1800242ae  cmp     edx, 2
0x1800242b1  jnb     short loc_1800242C2
0x1800242b3  lea     eax, [rdx+1]
0x1800242b6  cmp     byte ptr [rax+rbx+18h], 0
0x1800242bb  jge     short loc_1800242C2
0x1800242bd  or      byte ptr [rdx+rbx+18h], 1
0x1800242c2  inc     edx
0x1800242c4  cmp     edx, 3
0x1800242c7  jb      short loc_1800242AA
0x1800242c9  test    r15d, r15d
0x1800242cc  jz      short loc_1800242F9
0x1800242ce  and     sil, 7
0x1800242d2  jbe     short loc_1800242F9
0x1800242d4  movzx   ecx, sil
0x1800242d8  lea     rax, qword_18004A290
0x1800242df  sub     rax, rcx
0x1800242e2  mov     al, [rax]
0x1800242e4  and     [r10+18h], al
0x1800242e8  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::s_bLeftBitMasks
0x1800242ef  mov     al, [rcx+rax]
0x1800242f2  and     al, r11b
0x1800242f5  or      [r10+18h], al
0x1800242f9  test    r12d, r12d
0x1800242fc  jz      short loc_18002431F
0x1800242fe  mov     rax, [rdi+0C8h]
0x180024305  cmp     [rbx+0C0h], rax
0x18002430c  jnz     short loc_18002431F
0x18002430e  mov     [rdi+0C8h], rbx
0x180024315  mov     dword ptr [rdi+0D0h], 13h
0x18002431f  mov     rbx, [rbx+0C0h]
0x180024326  test    rbx, rbx
0x180024329  jnz     loc_180024233
0x18002432f  mov     eax, r14d
0x180024332  add     rsp, 20h
0x180024336  pop     r15
0x180024338  pop     r14
0x18002433a  pop     r12
0x18002433c  pop     rdi
0x18002433d  pop     rsi
0x18002433e  pop     rbp
0x18002433f  pop     rbx
0x180024340  retn
```
