# SymCryptFdefIntCopyMixedSize

- ea: `0x18002c15c`
- end: `0x18002c1f8`
- name: `SymCryptFdefIntCopyMixedSize`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180022c8c`
- `0x180028790`
- `0x180029120`

## callees

- `0x180009780`
- `0x18002c15c`
- `0x18003392c`

## pseudocode

```c
__int64 __fastcall SymCryptFdefIntCopyMixedSize(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  unsigned int v5; // esi
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  _QWORD *v8; // rax
  int v9; // ecx
  __int64 v10; // rdx

  v2 = 0;
  if ( a1 != a2 )
  {
    v5 = *(_DWORD *)(a1 + 4);
    if ( v5 >= *(_DWORD *)(a2 + 4) )
      v5 = *(_DWORD *)(a2 + 4);
    memcpy_0((void *)(a2 + 32), (const void *)(a1 + 32), v5 << 6);
    v6 = *(_DWORD *)(a2 + 4);
    if ( v6 > v5 )
      SymCryptWipeAsm(a2 + 32 + 64LL * v5, (v6 - v5) << 6);
    v7 = *(_DWORD *)(a1 + 4);
    if ( v7 > v5 )
    {
      v8 = (_QWORD *)(a1 + 32 + 64LL * v5);
      v9 = (8 * (v7 - v5)) & 0x1FFFFFFF;
      v10 = 0;
      if ( v9 )
      {
        do
        {
          v10 |= *v8++;
          --v9;
        }
        while ( v9 );
        if ( v10 )
          return 32781;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002c15c  push    rbx
0x18002c15e  push    rbp
0x18002c15f  push    rsi
0x18002c160  push    rdi
0x18002c161  push    r14
0x18002c163  sub     rsp, 20h
0x18002c167  xor     ebx, ebx
0x18002c169  mov     rbp, rdx
0x18002c16c  mov     rdi, rcx
0x18002c16f  cmp     rcx, rdx
0x18002c172  jz      short loc_18002C1EA
0x18002c174  mov     eax, [rdx+4]
0x18002c177  lea     rdx, [rcx+20h]; Src
0x18002c17b  mov     esi, [rcx+4]
0x18002c17e  cmp     esi, eax
0x18002c180  lea     rcx, [rbp+20h]; void *
0x18002c184  cmovnb  esi, eax
0x18002c187  mov     r8d, esi
0x18002c18a  shl     r8d, 6; MaxCount
0x18002c18e  call    memcpy_0
0x18002c193  mov     ecx, [rbp+4]
0x18002c196  mov     eax, esi
0x18002c198  shl     eax, 4
0x18002c19b  mov     r14d, eax
0x18002c19e  cmp     ecx, esi
0x18002c1a0  jbe     short loc_18002C1B6
0x18002c1a2  sub     ecx, esi
0x18002c1a4  shl     ecx, 6
0x18002c1a7  mov     edx, ecx
0x18002c1a9  lea     rcx, [rbp+20h]
0x18002c1ad  lea     rcx, [rcx+rax*4]
0x18002c1b1  call    SymCryptWipeAsm
0x18002c1b6  mov     ecx, [rdi+4]
0x18002c1b9  cmp     ecx, esi
0x18002c1bb  jbe     short loc_18002C1EA
0x18002c1bd  sub     ecx, esi
0x18002c1bf  lea     rax, [rdi+20h]
0x18002c1c3  shl     ecx, 6
0x18002c1c6  lea     rax, [rax+r14*4]
0x18002c1ca  shr     ecx, 3
0x18002c1cd  xor     edx, edx
0x18002c1cf  test    ecx, ecx
0x18002c1d1  jz      short loc_18002C1EA
0x18002c1d3  or      rdx, [rax]
0x18002c1d6  lea     rax, [rax+8]
0x18002c1da  add     ecx, 0FFFFFFFFh
0x18002c1dd  jnz     short loc_18002C1D3
0x18002c1df  test    rdx, rdx
0x18002c1e2  mov     eax, 800Dh
0x18002c1e7  cmovnz  ebx, eax
0x18002c1ea  mov     eax, ebx
0x18002c1ec  add     rsp, 20h
0x18002c1f0  pop     r14
0x18002c1f2  pop     rdi
0x18002c1f3  pop     rsi
0x18002c1f4  pop     rbp
0x18002c1f5  pop     rbx
0x18002c1f6  retn
```
