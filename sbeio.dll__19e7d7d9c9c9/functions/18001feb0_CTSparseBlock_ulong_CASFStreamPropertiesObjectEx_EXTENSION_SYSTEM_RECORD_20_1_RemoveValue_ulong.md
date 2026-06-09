# CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::RemoveValue(ulong)

- ea: `0x18001feb0`
- end: `0x180020029`
- name: `?RemoveValue@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@QEAAJK@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017588`

## callees

- `0x18001feb0`
- `0x180025614`
- `0x18002a07c`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::RemoveValue(
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
          & CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bSingleBitMasks[0]) != 0 )
      {
        v8 = CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::SetValue(
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
        *(_BYTE *)(v14 + 24) &= *((_BYTE *)&qword_180032180 - v16);
        *(_BYTE *)(v14 + 24) |= j
                              & *((_BYTE *)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bLeftBitMasks
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
0x18001feb0  push    rbx
0x18001feb2  push    rbp
0x18001feb3  push    rsi
0x18001feb4  push    rdi
0x18001feb5  push    r12
0x18001feb7  push    r14
0x18001feb9  push    r15
0x18001febb  sub     rsp, 20h
0x18001febf  mov     ebp, edx
0x18001fec1  mov     rdi, rcx
0x18001fec4  mov     rbx, rcx
0x18001fec7  test    rcx, rcx
0x18001feca  jz      short loc_18001FEE2
0x18001fecc  mov     eax, [rbx+8]
0x18001fecf  add     eax, 14h
0x18001fed2  cmp     ebp, eax
0x18001fed4  jb      short loc_18001FEE2
0x18001fed6  mov     rbx, [rbx+0C0h]
0x18001fedd  test    rbx, rbx
0x18001fee0  jnz     short loc_18001FECC
0x18001fee2  mov     rax, [rcx+0C8h]
0x18001fee9  xor     r12d, r12d
0x18001feec  test    rax, rax
0x18001feef  jz      short loc_18001FF13
0x18001fef1  mov     edx, [rcx+0D0h]
0x18001fef7  mov     ecx, [rax+8]
0x18001fefa  add     ecx, edx
0x18001fefc  cmp     ebp, ecx
0x18001fefe  jnb     short loc_18001FF13
0x18001ff00  test    edx, edx
0x18001ff02  jnz     short loc_18001FF0A
0x18001ff04  lea     r12d, [rdx+1]
0x18001ff08  jmp     short loc_18001FF13
0x18001ff0a  lea     eax, [rdx-1]
0x18001ff0d  mov     [rdi+0D0h], eax
0x18001ff13  xor     r14d, r14d
0x18001ff16  jmp     loc_18002000E
0x18001ff1b  mov     edx, [rbx+8]
0x18001ff1e  cmp     ebp, edx
0x18001ff20  jb      short loc_18001FF2E
0x18001ff22  mov     esi, ebp
0x18001ff24  mov     r15d, 1
0x18001ff2a  sub     esi, edx
0x18001ff2c  jmp     short loc_18001FF57
0x18001ff2e  mov     al, [rbx+18h]
0x18001ff31  xor     r15d, r15d
0x18001ff34  xor     esi, esi
0x18001ff36  test    cs:?s_bSingleBitMasks@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@0PAEA, al; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bSingleBitMasks
0x18001ff3c  jz      short loc_18001FF57
0x18001ff3e  mov     r8, [rbx+20h]
0x18001ff42  dec     edx
0x18001ff44  mov     rcx, rdi
0x18001ff47  call    ?SetValue@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@QEAAJKPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::SetValue(ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *)
0x18001ff4c  mov     r14d, eax
0x18001ff4f  test    eax, eax
0x18001ff51  js      loc_180020017
0x18001ff57  mov     r8d, 13h
0x18001ff5d  mov     ecx, esi
0x18001ff5f  add     rcx, 4
0x18001ff63  lea     edx, [rsi+1]
0x18001ff66  sub     r8d, esi
0x18001ff69  lea     rdx, [rdx+4]
0x18001ff6d  shl     r8, 3; Size
0x18001ff71  lea     rdx, [rbx+rdx*8]; Src
0x18001ff75  lea     rcx, [rbx+rcx*8]; void *
0x18001ff79  call    memmove_0
0x18001ff7e  mov     eax, esi
0x18001ff80  shr     eax, 3
0x18001ff83  mov     edx, eax
0x18001ff85  lea     r10, [rax+rbx]
0x18001ff89  mov     r11b, [r10+18h]
0x18001ff8d  cmp     eax, 3
0x18001ff90  jnb     short loc_18001FFB1
0x18001ff92  shl     byte ptr [rdx+rbx+18h], 1
0x18001ff96  cmp     edx, 2
0x18001ff99  jnb     short loc_18001FFAA
0x18001ff9b  lea     eax, [rdx+1]
0x18001ff9e  cmp     byte ptr [rax+rbx+18h], 0
0x18001ffa3  jge     short loc_18001FFAA
0x18001ffa5  or      byte ptr [rdx+rbx+18h], 1
0x18001ffaa  inc     edx
0x18001ffac  cmp     edx, 3
0x18001ffaf  jb      short loc_18001FF92
0x18001ffb1  test    r15d, r15d
0x18001ffb4  jz      short loc_18001FFE1
0x18001ffb6  and     sil, 7
0x18001ffba  jbe     short loc_18001FFE1
0x18001ffbc  movzx   ecx, sil
0x18001ffc0  lea     rax, qword_180032180
0x18001ffc7  sub     rax, rcx
0x18001ffca  mov     al, [rax]
0x18001ffcc  and     [r10+18h], al
0x18001ffd0  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bLeftBitMasks
0x18001ffd7  mov     al, [rcx+rax]
0x18001ffda  and     al, r11b
0x18001ffdd  or      [r10+18h], al
0x18001ffe1  test    r12d, r12d
0x18001ffe4  jz      short loc_180020007
0x18001ffe6  mov     rax, [rdi+0C8h]
0x18001ffed  cmp     [rbx+0C0h], rax
0x18001fff4  jnz     short loc_180020007
0x18001fff6  mov     [rdi+0C8h], rbx
0x18001fffd  mov     dword ptr [rdi+0D0h], 13h
0x180020007  mov     rbx, [rbx+0C0h]
0x18002000e  test    rbx, rbx
0x180020011  jnz     loc_18001FF1B
0x180020017  mov     eax, r14d
0x18002001a  add     rsp, 20h
0x18002001e  pop     r15
0x180020020  pop     r14
0x180020022  pop     r12
0x180020024  pop     rdi
0x180020025  pop     rsi
0x180020026  pop     rbp
0x180020027  pop     rbx
0x180020028  retn
```
