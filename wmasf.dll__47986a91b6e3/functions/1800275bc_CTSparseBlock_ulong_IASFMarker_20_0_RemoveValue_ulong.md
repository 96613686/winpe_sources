# CTSparseBlock<ulong,IASFMarker *,20,0>::RemoveValue(ulong)

- ea: `0x1800275bc`
- end: `0x180027735`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUIASFMarker@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027460`

## callees

- `0x18000edd4`
- `0x1800275bc`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,IASFMarker *,20,0>::RemoveValue(__int64 a1, unsigned int a2)
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
      if ( (*(_BYTE *)(i + 24) & (unsigned __int8)CTSparseBlock<unsigned long,IASFMarker *,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,IASFMarker *,20,0>::SetValue(a1, v9 - 1, *(_QWORD *)(i + 32));
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
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A328 - v16);
        *(_BYTE *)(v14 + 24) |= j & *((_BYTE *)CTSparseBlock<unsigned long,IASFMarker *,20,0>::s_bLeftBitMasks + v16);
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
0x1800275bc  push    rbx
0x1800275be  push    rbp
0x1800275bf  push    rsi
0x1800275c0  push    rdi
0x1800275c1  push    r12
0x1800275c3  push    r14
0x1800275c5  push    r15
0x1800275c7  sub     rsp, 20h
0x1800275cb  mov     ebp, edx
0x1800275cd  mov     rdi, rcx
0x1800275d0  mov     rbx, rcx
0x1800275d3  test    rcx, rcx
0x1800275d6  jz      short loc_1800275EE
0x1800275d8  mov     eax, [rbx+8]
0x1800275db  add     eax, 14h
0x1800275de  cmp     ebp, eax
0x1800275e0  jb      short loc_1800275EE
0x1800275e2  mov     rbx, [rbx+0C0h]
0x1800275e9  test    rbx, rbx
0x1800275ec  jnz     short loc_1800275D8
0x1800275ee  mov     rax, [rcx+0C8h]
0x1800275f5  xor     r12d, r12d
0x1800275f8  test    rax, rax
0x1800275fb  jz      short loc_18002761F
0x1800275fd  mov     edx, [rcx+0D0h]
0x180027603  mov     ecx, [rax+8]
0x180027606  add     ecx, edx
0x180027608  cmp     ebp, ecx
0x18002760a  jnb     short loc_18002761F
0x18002760c  test    edx, edx
0x18002760e  jnz     short loc_180027616
0x180027610  lea     r12d, [rdx+1]
0x180027614  jmp     short loc_18002761F
0x180027616  lea     eax, [rdx-1]
0x180027619  mov     [rdi+0D0h], eax
0x18002761f  xor     r14d, r14d
0x180027622  jmp     loc_18002771A
0x180027627  mov     edx, [rbx+8]
0x18002762a  cmp     ebp, edx
0x18002762c  jb      short loc_18002763A
0x18002762e  mov     esi, ebp
0x180027630  mov     r15d, 1
0x180027636  sub     esi, edx
0x180027638  jmp     short loc_180027663
0x18002763a  mov     al, [rbx+18h]
0x18002763d  xor     r15d, r15d
0x180027640  xor     esi, esi
0x180027642  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUIASFMarker@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,IASFMarker *,20,0>::s_bSingleBitMasks
0x180027648  jz      short loc_180027663
0x18002764a  mov     r8, [rbx+20h]
0x18002764e  dec     edx
0x180027650  mov     rcx, rdi
0x180027653  call    ?SetValue@?$CTSparseBlock@KPEAUIASFMarker@@$0BE@$0A@@@QEAAJKPEAUIASFMarker@@@Z; CTSparseBlock<ulong,IASFMarker *,20,0>::SetValue(ulong,IASFMarker *)
0x180027658  mov     r14d, eax
0x18002765b  test    eax, eax
0x18002765d  js      loc_180027723
0x180027663  mov     r8d, 13h
0x180027669  mov     ecx, esi
0x18002766b  add     rcx, 4
0x18002766f  lea     edx, [rsi+1]
0x180027672  sub     r8d, esi
0x180027675  lea     rdx, [rdx+4]
0x180027679  shl     r8, 3; Size
0x18002767d  lea     rdx, [rbx+rdx*8]; Src
0x180027681  lea     rcx, [rbx+rcx*8]; void *
0x180027685  call    memmove_0
0x18002768a  mov     eax, esi
0x18002768c  shr     eax, 3
0x18002768f  mov     edx, eax
0x180027691  lea     r10, [rax+rbx]
0x180027695  mov     r11b, [r10+18h]
0x180027699  cmp     eax, 3
0x18002769c  jnb     short loc_1800276BD
0x18002769e  shl     byte ptr [rdx+rbx+18h], 1
0x1800276a2  cmp     edx, 2
0x1800276a5  jnb     short loc_1800276B6
0x1800276a7  lea     eax, [rdx+1]
0x1800276aa  cmp     byte ptr [rax+rbx+18h], 0
0x1800276af  jge     short loc_1800276B6
0x1800276b1  or      byte ptr [rdx+rbx+18h], 1
0x1800276b6  inc     edx
0x1800276b8  cmp     edx, 3
0x1800276bb  jb      short loc_18002769E
0x1800276bd  test    r15d, r15d
0x1800276c0  jz      short loc_1800276ED
0x1800276c2  and     sil, 7
0x1800276c6  jbe     short loc_1800276ED
0x1800276c8  movzx   ecx, sil
0x1800276cc  lea     rax, qword_18004A328
0x1800276d3  sub     rax, rcx
0x1800276d6  mov     al, [rax]
0x1800276d8  and     [r10+18h], al
0x1800276dc  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUIASFMarker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,IASFMarker *,20,0>::s_bLeftBitMasks
0x1800276e3  mov     al, [rcx+rax]
0x1800276e6  and     al, r11b
0x1800276e9  or      [r10+18h], al
0x1800276ed  test    r12d, r12d
0x1800276f0  jz      short loc_180027713
0x1800276f2  mov     rax, [rdi+0C8h]
0x1800276f9  cmp     [rbx+0C0h], rax
0x180027700  jnz     short loc_180027713
0x180027702  mov     [rdi+0C8h], rbx
0x180027709  mov     dword ptr [rdi+0D0h], 13h
0x180027713  mov     rbx, [rbx+0C0h]
0x18002771a  test    rbx, rbx
0x18002771d  jnz     loc_180027627
0x180027723  mov     eax, r14d
0x180027726  add     rsp, 20h
0x18002772a  pop     r15
0x18002772c  pop     r14
0x18002772e  pop     r12
0x180027730  pop     rdi
0x180027731  pop     rsi
0x180027732  pop     rbp
0x180027733  pop     rbx
0x180027734  retn
```
