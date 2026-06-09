# CTSparseBlock<ulong,CASFStreamSelector::OUTPUT *,20,0>::RemoveValue(ulong)

- ea: `0x180039b64`
- end: `0x180039cdd`
- name: `?RemoveValue@?$CTSparseBlock@KPEAUOUTPUT@CASFStreamSelector@@$0BE@$0A@@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800350b4`

## callees

- `0x180039b64`
- `0x18003b038`
- `0x18003f2ac`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamSelector::OUTPUT *,20,0>::RemoveValue(
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
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFStreamSelector::OUTPUT *,20,0>::s_bSingleBitMasks) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFStreamSelector::OUTPUT *,20,0>::SetValue(a1, v9 - 1, *(_QWORD *)(i + 32));
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
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_18004A440 - v16);
        *(_BYTE *)(v14 + 24) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFStreamSelector::OUTPUT *,20,0>::s_bLeftBitMasks
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
0x180039b64  push    rbx
0x180039b66  push    rbp
0x180039b67  push    rsi
0x180039b68  push    rdi
0x180039b69  push    r12
0x180039b6b  push    r14
0x180039b6d  push    r15
0x180039b6f  sub     rsp, 20h
0x180039b73  mov     ebp, edx
0x180039b75  mov     rdi, rcx
0x180039b78  mov     rbx, rcx
0x180039b7b  test    rcx, rcx
0x180039b7e  jz      short loc_180039B96
0x180039b80  mov     eax, [rbx+8]
0x180039b83  add     eax, 14h
0x180039b86  cmp     ebp, eax
0x180039b88  jb      short loc_180039B96
0x180039b8a  mov     rbx, [rbx+0C0h]
0x180039b91  test    rbx, rbx
0x180039b94  jnz     short loc_180039B80
0x180039b96  mov     rax, [rcx+0C8h]
0x180039b9d  xor     r12d, r12d
0x180039ba0  test    rax, rax
0x180039ba3  jz      short loc_180039BC7
0x180039ba5  mov     edx, [rcx+0D0h]
0x180039bab  mov     ecx, [rax+8]
0x180039bae  add     ecx, edx
0x180039bb0  cmp     ebp, ecx
0x180039bb2  jnb     short loc_180039BC7
0x180039bb4  test    edx, edx
0x180039bb6  jnz     short loc_180039BBE
0x180039bb8  lea     r12d, [rdx+1]
0x180039bbc  jmp     short loc_180039BC7
0x180039bbe  lea     eax, [rdx-1]
0x180039bc1  mov     [rdi+0D0h], eax
0x180039bc7  xor     r14d, r14d
0x180039bca  jmp     loc_180039CC2
0x180039bcf  mov     edx, [rbx+8]
0x180039bd2  cmp     ebp, edx
0x180039bd4  jb      short loc_180039BE2
0x180039bd6  mov     esi, ebp
0x180039bd8  mov     r15d, 1
0x180039bde  sub     esi, edx
0x180039be0  jmp     short loc_180039C0B
0x180039be2  mov     al, [rbx+18h]
0x180039be5  xor     r15d, r15d
0x180039be8  xor     esi, esi
0x180039bea  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAUOUTPUT@CASFStreamSelector@@$0BE@$0A@@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFStreamSelector::OUTPUT *,20,0>::s_bSingleBitMasks
0x180039bf0  jz      short loc_180039C0B
0x180039bf2  mov     r8, [rbx+20h]
0x180039bf6  dec     edx
0x180039bf8  mov     rcx, rdi
0x180039bfb  call    ?SetValue@?$CTSparseBlock@KPEAUOUTPUT@CASFStreamSelector@@$0BE@$0A@@@QEAAJKPEAUOUTPUT@CASFStreamSelector@@@Z; CTSparseBlock<ulong,CASFStreamSelector::OUTPUT *,20,0>::SetValue(ulong,CASFStreamSelector::OUTPUT *)
0x180039c00  mov     r14d, eax
0x180039c03  test    eax, eax
0x180039c05  js      loc_180039CCB
0x180039c0b  mov     r8d, 13h
0x180039c11  mov     ecx, esi
0x180039c13  add     rcx, 4
0x180039c17  lea     edx, [rsi+1]
0x180039c1a  sub     r8d, esi
0x180039c1d  lea     rdx, [rdx+4]
0x180039c21  shl     r8, 3; Size
0x180039c25  lea     rdx, [rbx+rdx*8]; Src
0x180039c29  lea     rcx, [rbx+rcx*8]; void *
0x180039c2d  call    memmove_0
0x180039c32  mov     eax, esi
0x180039c34  shr     eax, 3
0x180039c37  mov     edx, eax
0x180039c39  lea     r10, [rax+rbx]
0x180039c3d  mov     r11b, [r10+18h]
0x180039c41  cmp     eax, 3
0x180039c44  jnb     short loc_180039C65
0x180039c46  shl     byte ptr [rdx+rbx+18h], 1
0x180039c4a  cmp     edx, 2
0x180039c4d  jnb     short loc_180039C5E
0x180039c4f  lea     eax, [rdx+1]
0x180039c52  cmp     byte ptr [rax+rbx+18h], 0
0x180039c57  jge     short loc_180039C5E
0x180039c59  or      byte ptr [rdx+rbx+18h], 1
0x180039c5e  inc     edx
0x180039c60  cmp     edx, 3
0x180039c63  jb      short loc_180039C46
0x180039c65  test    r15d, r15d
0x180039c68  jz      short loc_180039C95
0x180039c6a  and     sil, 7
0x180039c6e  jbe     short loc_180039C95
0x180039c70  movzx   ecx, sil
0x180039c74  lea     rax, qword_18004A440
0x180039c7b  sub     rax, rcx
0x180039c7e  mov     al, [rax]
0x180039c80  and     [r10+18h], al
0x180039c84  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUOUTPUT@CASFStreamSelector@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamSelector::OUTPUT *,20,0>::s_bLeftBitMasks
0x180039c8b  mov     al, [rcx+rax]
0x180039c8e  and     al, r11b
0x180039c91  or      [r10+18h], al
0x180039c95  test    r12d, r12d
0x180039c98  jz      short loc_180039CBB
0x180039c9a  mov     rax, [rdi+0C8h]
0x180039ca1  cmp     [rbx+0C0h], rax
0x180039ca8  jnz     short loc_180039CBB
0x180039caa  mov     [rdi+0C8h], rbx
0x180039cb1  mov     dword ptr [rdi+0D0h], 13h
0x180039cbb  mov     rbx, [rbx+0C0h]
0x180039cc2  test    rbx, rbx
0x180039cc5  jnz     loc_180039BCF
0x180039ccb  mov     eax, r14d
0x180039cce  add     rsp, 20h
0x180039cd2  pop     r15
0x180039cd4  pop     r14
0x180039cd6  pop     r12
0x180039cd8  pop     rdi
0x180039cd9  pop     rsi
0x180039cda  pop     rbp
0x180039cdb  pop     rbx
0x180039cdc  retn
```
