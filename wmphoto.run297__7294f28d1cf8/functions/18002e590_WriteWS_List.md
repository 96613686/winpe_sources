# WriteWS_List

- ea: `0x18002e590`
- end: `0x18002e65a`
- name: `WriteWS_List`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e590`
- `0x180043630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18002e604`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18002e604`

## pseudocode

```c
__int64 __fastcall WriteWS_List(__int64 *a1, char *a2, unsigned __int64 a3)
{
  size_t v5; // r8
  unsigned int v7; // ecx
  size_t v8; // rsi
  __int64 v9; // r14
  _QWORD *v10; // rax

  v5 = a1[2];
  if ( v5 + a3 < v5 || a1[1] < v5 + a3 )
    return (unsigned int)-103;
  v7 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v8 = a3;
      if ( 4096 - v5 <= a3 )
        v8 = 4096 - v5;
      memcpy_0((void *)(v5 + *a1), a2, v8);
      v5 = v8 + a1[2];
      a1[2] = v5;
      if ( v5 == 4096 )
      {
        v9 = *a1;
        v10 = calloc(1u, 0x1008u);
        if ( !v10 )
          return (unsigned int)-101;
        *(_QWORD *)(v9 - 8) = v10;
        a1[1] += 4096;
        v7 = 0;
        *a1 = (__int64)(v10 + 1);
        *v10 = 0;
        ++a1[3];
        v5 = 0;
        a1[2] = 0;
      }
      else
      {
        v7 = 0;
      }
      a3 -= v8;
      if ( !a3 )
        return v7;
      a2 += v8;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002e590  push    rbx
0x18002e592  push    rbp
0x18002e593  push    rsi
0x18002e594  push    rdi
0x18002e595  push    r14
0x18002e597  push    r15
0x18002e599  sub     rsp, 28h
0x18002e59d  mov     rdi, r8
0x18002e5a0  mov     rbp, rdx
0x18002e5a3  mov     r8, [rcx+10h]
0x18002e5a7  mov     rbx, rcx
0x18002e5aa  lea     rax, [r8+rdi]
0x18002e5ae  cmp     rax, r8
0x18002e5b1  jb      short loc_18002E624
0x18002e5b3  cmp     [rcx+8], rax
0x18002e5b7  jb      short loc_18002E624
0x18002e5b9  xor     ecx, ecx
0x18002e5bb  test    rdi, rdi
0x18002e5be  jz      short loc_18002E615
0x18002e5c0  mov     r15d, 1000h
0x18002e5c6  mov     rcx, [rbx]
0x18002e5c9  mov     rax, r15
0x18002e5cc  sub     rax, r8
0x18002e5cf  mov     rsi, rdi
0x18002e5d2  cmp     rax, rdi
0x18002e5d5  mov     rdx, rbp; Src
0x18002e5d8  cmovbe  rsi, rax
0x18002e5dc  add     rcx, r8; void *
0x18002e5df  mov     r8, rsi; Size
0x18002e5e2  call    memcpy_0
0x18002e5e7  mov     r8, [rbx+10h]
0x18002e5eb  add     r8, rsi
0x18002e5ee  mov     [rbx+10h], r8
0x18002e5f2  cmp     r8, r15
0x18002e5f5  jnz     short loc_18002E62B
0x18002e5f7  mov     r14, [rbx]
0x18002e5fa  mov     edx, 1008h; Size
0x18002e5ff  mov     ecx, 1; Count
0x18002e604  call    cs:__imp_calloc
0x18002e60a  mov     rdx, rax
0x18002e60d  test    rax, rax
0x18002e610  jnz     short loc_18002E637
0x18002e612  lea     ecx, [rax-65h]
0x18002e615  mov     eax, ecx
0x18002e617  add     rsp, 28h
0x18002e61b  pop     r15
0x18002e61d  pop     r14
0x18002e61f  pop     rdi
0x18002e620  pop     rsi
0x18002e621  pop     rbp
0x18002e622  pop     rbx
0x18002e623  retn
0x18002e624  mov     ecx, 0FFFFFF99h
0x18002e629  jmp     short loc_18002E615
0x18002e62b  xor     ecx, ecx
0x18002e62d  sub     rdi, rsi
0x18002e630  jz      short loc_18002E615
0x18002e632  add     rbp, rsi
0x18002e635  jmp     short loc_18002E5C6
0x18002e637  mov     [r14-8], rdx
0x18002e63b  add     rax, 8
0x18002e63f  add     [rbx+8], r15
0x18002e643  xor     ecx, ecx
0x18002e645  mov     [rbx], rax
0x18002e648  xor     eax, eax
0x18002e64a  mov     [rdx], rax
0x18002e64d  inc     qword ptr [rbx+18h]
0x18002e651  xor     r8d, r8d
0x18002e654  mov     [rbx+10h], rax
0x18002e658  jmp     short loc_18002E62D
```
