# CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::RemoveValue(ulong)

- ea: `0x18000b478`
- end: `0x18000b5ee`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAAJK@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd30`

## callees

- `0x18000b478`
- `0x18000b69c`
- `0x18002a07c`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::RemoveValue(__int64 a1, unsigned int a2)
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
  char j; // r11
  unsigned __int8 v15; // si

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
      if ( *(char *)(i + 24) < 0 )
      {
        v8 = CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::SetValue(
               (_DWORD *)a1,
               v9 - 1,
               *(__int64 (__fastcall ***)(_QWORD, _QWORD *))(i + 32));
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
    for ( j = *(_BYTE *)(v12 + i + 24); (unsigned int)v13 < 3; v13 = (unsigned int)(v13 + 1) )
    {
      *(_BYTE *)(v13 + i + 24) *= 2;
      if ( (unsigned int)v13 < 2 && *(char *)((unsigned int)(v13 + 1) + i + 24) < 0 )
        *(_BYTE *)(v13 + i + 24) |= 1u;
    }
    if ( v10 )
    {
      v15 = v11 & 7;
      if ( v15 )
        *(_BYTE *)(v12 + i + 24) = *(_BYTE *)(v12 + i + 24) & *((_BYTE *)&qword_18002EEF8 - v15)
                                 | j
                                 & *((_BYTE *)CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::s_bLeftBitMasks
                                   + v15);
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
0x18000b478  push    rbx
0x18000b47a  push    rbp
0x18000b47b  push    rsi
0x18000b47c  push    rdi
0x18000b47d  push    r12
0x18000b47f  push    r14
0x18000b481  push    r15
0x18000b483  sub     rsp, 20h
0x18000b487  mov     ebp, edx
0x18000b489  mov     rdi, rcx
0x18000b48c  mov     rbx, rcx
0x18000b48f  test    rcx, rcx
0x18000b492  jz      short loc_18000B4AA
0x18000b494  mov     eax, [rbx+8]
0x18000b497  add     eax, 14h
0x18000b49a  cmp     ebp, eax
0x18000b49c  jb      short loc_18000B4AA
0x18000b49e  mov     rbx, [rbx+0C0h]
0x18000b4a5  test    rbx, rbx
0x18000b4a8  jnz     short loc_18000B494
0x18000b4aa  mov     rax, [rcx+0C8h]
0x18000b4b1  xor     r12d, r12d
0x18000b4b4  test    rax, rax
0x18000b4b7  jz      short loc_18000B4DB
0x18000b4b9  mov     edx, [rcx+0D0h]
0x18000b4bf  mov     ecx, [rax+8]
0x18000b4c2  add     ecx, edx
0x18000b4c4  cmp     ebp, ecx
0x18000b4c6  jnb     short loc_18000B4DB
0x18000b4c8  test    edx, edx
0x18000b4ca  jnz     short loc_18000B4D2
0x18000b4cc  lea     r12d, [rdx+1]
0x18000b4d0  jmp     short loc_18000B4DB
0x18000b4d2  lea     eax, [rdx-1]
0x18000b4d5  mov     [rdi+0D0h], eax
0x18000b4db  xor     r14d, r14d
0x18000b4de  jmp     loc_18000B5D3
0x18000b4e3  mov     edx, [rbx+8]
0x18000b4e6  cmp     ebp, edx
0x18000b4e8  jb      short loc_18000B4F6
0x18000b4ea  mov     esi, ebp
0x18000b4ec  mov     r15d, 1
0x18000b4f2  sub     esi, edx
0x18000b4f4  jmp     short loc_18000B51A
0x18000b4f6  xor     r15d, r15d
0x18000b4f9  xor     esi, esi
0x18000b4fb  cmp     [rbx+18h], sil
0x18000b4ff  jge     short loc_18000B51A
0x18000b501  mov     r8, [rbx+20h]
0x18000b505  dec     edx
0x18000b507  mov     rcx, rdi
0x18000b50a  call    ?SetValue@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAAJKPEAUWRITER_SINK_CALLBACK@@@Z; CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::SetValue(ulong,WRITER_SINK_CALLBACK *)
0x18000b50f  mov     r14d, eax
0x18000b512  test    eax, eax
0x18000b514  js      loc_18000B5DC
0x18000b51a  mov     r8d, 13h
0x18000b520  mov     ecx, esi
0x18000b522  add     rcx, 4
0x18000b526  lea     edx, [rsi+1]
0x18000b529  sub     r8d, esi
0x18000b52c  lea     rdx, [rdx+4]
0x18000b530  shl     r8, 3; Size
0x18000b534  lea     rdx, [rbx+rdx*8]; Src
0x18000b538  lea     rcx, [rbx+rcx*8]; void *
0x18000b53c  call    memmove_0
0x18000b541  mov     eax, esi
0x18000b543  shr     eax, 3
0x18000b546  mov     edx, eax
0x18000b548  lea     r10, [rax+rbx]
0x18000b54c  mov     r11b, [r10+18h]
0x18000b550  cmp     eax, 3
0x18000b553  jnb     short loc_18000B574
0x18000b555  shl     byte ptr [rdx+rbx+18h], 1
0x18000b559  cmp     edx, 2
0x18000b55c  jnb     short loc_18000B56D
0x18000b55e  lea     eax, [rdx+1]
0x18000b561  cmp     byte ptr [rax+rbx+18h], 0
0x18000b566  jge     short loc_18000B56D
0x18000b568  or      byte ptr [rdx+rbx+18h], 1
0x18000b56d  inc     edx
0x18000b56f  cmp     edx, 3
0x18000b572  jb      short loc_18000B555
0x18000b574  test    r15d, r15d
0x18000b577  jz      short loc_18000B5A6
0x18000b579  and     sil, 7
0x18000b57d  jbe     short loc_18000B5A6
0x18000b57f  movzx   ecx, sil
0x18000b583  lea     rax, qword_18002EEF8
0x18000b58a  sub     rax, rcx
0x18000b58d  lea     rdx, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::s_bLeftBitMasks
0x18000b594  mov     dl, [rcx+rdx]
0x18000b597  mov     cl, [rax]
0x18000b599  and     dl, r11b
0x18000b59c  and     cl, [r10+18h]
0x18000b5a0  or      dl, cl
0x18000b5a2  mov     [r10+18h], dl
0x18000b5a6  test    r12d, r12d
0x18000b5a9  jz      short loc_18000B5CC
0x18000b5ab  mov     rax, [rdi+0C8h]
0x18000b5b2  cmp     [rbx+0C0h], rax
0x18000b5b9  jnz     short loc_18000B5CC
0x18000b5bb  mov     [rdi+0C8h], rbx
0x18000b5c2  mov     dword ptr [rdi+0D0h], 13h
0x18000b5cc  mov     rbx, [rbx+0C0h]
0x18000b5d3  test    rbx, rbx
0x18000b5d6  jnz     loc_18000B4E3
0x18000b5dc  mov     eax, r14d
0x18000b5df  add     rsp, 20h
0x18000b5e3  pop     r15
0x18000b5e5  pop     r14
0x18000b5e7  pop     r12
0x18000b5e9  pop     rdi
0x18000b5ea  pop     rsi
0x18000b5eb  pop     rbp
0x18000b5ec  pop     rbx
0x18000b5ed  retn
```
