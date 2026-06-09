# CTSparseBlock<ulong,IASFIndexBlock *,20,0>::RemoveValue(ulong)

- ea: `0x180005a5c`
- end: `0x180005bd5`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUIASFIndexBlock@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005948`

## callees

- `0x180005a5c`
- `0x180005c80`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,IASFIndexBlock *,20,0>::RemoveValue(__int64 a1, unsigned int a2)
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
      if ( (*(_BYTE *)(i + 24) & (unsigned __int8)CTSparseBlock<unsigned long,IASFIndexBlock *,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,IASFIndexBlock *,20,0>::SetValue(a1, v9 - 1, *(_QWORD *)(i + 32));
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
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A158 - v16);
        *(_BYTE *)(v14 + 24) |= j & CTSparseBlock<unsigned long,IASFIndexBlock *,20,0>::s_bLeftBitMasks[v16];
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
0x180005a5c  push    rbx
0x180005a5e  push    rbp
0x180005a5f  push    rsi
0x180005a60  push    rdi
0x180005a61  push    r12
0x180005a63  push    r14
0x180005a65  push    r15
0x180005a67  sub     rsp, 20h
0x180005a6b  mov     ebp, edx
0x180005a6d  mov     rdi, rcx
0x180005a70  mov     rbx, rcx
0x180005a73  test    rcx, rcx
0x180005a76  jz      short loc_180005A8E
0x180005a78  mov     eax, [rbx+8]
0x180005a7b  add     eax, 14h
0x180005a7e  cmp     ebp, eax
0x180005a80  jb      short loc_180005A8E
0x180005a82  mov     rbx, [rbx+0C0h]
0x180005a89  test    rbx, rbx
0x180005a8c  jnz     short loc_180005A78
0x180005a8e  mov     rax, [rcx+0C8h]
0x180005a95  xor     r12d, r12d
0x180005a98  test    rax, rax
0x180005a9b  jz      short loc_180005ABF
0x180005a9d  mov     edx, [rcx+0D0h]
0x180005aa3  mov     ecx, [rax+8]
0x180005aa6  add     ecx, edx
0x180005aa8  cmp     ebp, ecx
0x180005aaa  jnb     short loc_180005ABF
0x180005aac  test    edx, edx
0x180005aae  jnz     short loc_180005AB6
0x180005ab0  lea     r12d, [rdx+1]
0x180005ab4  jmp     short loc_180005ABF
0x180005ab6  lea     eax, [rdx-1]
0x180005ab9  mov     [rdi+0D0h], eax
0x180005abf  xor     r14d, r14d
0x180005ac2  jmp     loc_180005BBA
0x180005ac7  mov     edx, [rbx+8]
0x180005aca  cmp     ebp, edx
0x180005acc  jb      short loc_180005ADA
0x180005ace  mov     esi, ebp
0x180005ad0  mov     r15d, 1
0x180005ad6  sub     esi, edx
0x180005ad8  jmp     short loc_180005B03
0x180005ada  mov     al, [rbx+18h]
0x180005add  xor     r15d, r15d
0x180005ae0  xor     esi, esi
0x180005ae2  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUIASFIndexBlock@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,IASFIndexBlock *,20,0>::s_bSingleBitMasks
0x180005ae8  jz      short loc_180005B03
0x180005aea  mov     r8, [rbx+20h]
0x180005aee  dec     edx
0x180005af0  mov     rcx, rdi
0x180005af3  call    ?SetValue@?$CTSparseBlock@KPEAUIASFIndexBlock@@$0BE@$0A@@@QEAAJKPEAUIASFIndexBlock@@@Z; CTSparseBlock<ulong,IASFIndexBlock *,20,0>::SetValue(ulong,IASFIndexBlock *)
0x180005af8  mov     r14d, eax
0x180005afb  test    eax, eax
0x180005afd  js      loc_180005BC3
0x180005b03  mov     r8d, 13h
0x180005b09  mov     ecx, esi
0x180005b0b  add     rcx, 4
0x180005b0f  lea     edx, [rsi+1]
0x180005b12  sub     r8d, esi
0x180005b15  lea     rdx, [rdx+4]
0x180005b19  shl     r8, 3; Size
0x180005b1d  lea     rdx, [rbx+rdx*8]; Src
0x180005b21  lea     rcx, [rbx+rcx*8]; void *
0x180005b25  call    memmove_0
0x180005b2a  mov     eax, esi
0x180005b2c  shr     eax, 3
0x180005b2f  mov     edx, eax
0x180005b31  lea     r10, [rax+rbx]
0x180005b35  mov     r11b, [r10+18h]
0x180005b39  cmp     eax, 3
0x180005b3c  jnb     short loc_180005B5D
0x180005b3e  shl     byte ptr [rdx+rbx+18h], 1
0x180005b42  cmp     edx, 2
0x180005b45  jnb     short loc_180005B56
0x180005b47  lea     eax, [rdx+1]
0x180005b4a  cmp     byte ptr [rax+rbx+18h], 0
0x180005b4f  jge     short loc_180005B56
0x180005b51  or      byte ptr [rdx+rbx+18h], 1
0x180005b56  inc     edx
0x180005b58  cmp     edx, 3
0x180005b5b  jb      short loc_180005B3E
0x180005b5d  test    r15d, r15d
0x180005b60  jz      short loc_180005B8D
0x180005b62  and     sil, 7
0x180005b66  jbe     short loc_180005B8D
0x180005b68  movzx   ecx, sil
0x180005b6c  lea     rax, qword_18004A158
0x180005b73  sub     rax, rcx
0x180005b76  mov     al, [rax]
0x180005b78  and     [r10+18h], al
0x180005b7c  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUIASFIndexBlock@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,IASFIndexBlock *,20,0>::s_bLeftBitMasks
0x180005b83  mov     al, [rcx+rax]
0x180005b86  and     al, r11b
0x180005b89  or      [r10+18h], al
0x180005b8d  test    r12d, r12d
0x180005b90  jz      short loc_180005BB3
0x180005b92  mov     rax, [rdi+0C8h]
0x180005b99  cmp     [rbx+0C0h], rax
0x180005ba0  jnz     short loc_180005BB3
0x180005ba2  mov     [rdi+0C8h], rbx
0x180005ba9  mov     dword ptr [rdi+0D0h], 13h
0x180005bb3  mov     rbx, [rbx+0C0h]
0x180005bba  test    rbx, rbx
0x180005bbd  jnz     loc_180005AC7
0x180005bc3  mov     eax, r14d
0x180005bc6  add     rsp, 20h
0x180005bca  pop     r15
0x180005bcc  pop     r14
0x180005bce  pop     r12
0x180005bd0  pop     rdi
0x180005bd1  pop     rsi
0x180005bd2  pop     rbp
0x180005bd3  pop     rbx
0x180005bd4  retn
```
