# ReadWS_List

- ea: `0x18002e660`
- end: `0x18002e712`
- name: `ReadWS_List`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e660`
- `0x180043630`

## pseudocode

```c
__int64 __fastcall ReadWS_List(_QWORD *a1, char *a2, unsigned __int64 a3)
{
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rdx
  size_t v9; // rbx
  __int64 v10; // rdx

  v4 = a3;
  v5 = a1[2];
  if ( v5 + a3 < v5 )
  {
    return (unsigned int)-103;
  }
  else
  {
    v7 = 0;
    v8 = a1[3] << 12;
    if ( a1[1] < a3 + v8 + v5 )
      v4 = a1[1] - v8 - v5;
    while ( v4 )
    {
      v9 = v4;
      if ( 4096 - v5 <= v4 )
        v9 = 4096 - v5;
      memcpy_0(a2, (const void *)(v5 + *a1), v9);
      a2 += v9;
      v5 = v9 + a1[2];
      v4 -= v9;
      a1[2] = v5;
      if ( v5 == 4096 )
      {
        v10 = *(_QWORD *)(*a1 - 8LL);
        ++a1[3];
        *a1 = v10 + 8;
        v5 = 0;
        a1[2] = 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002e660  push    rbx
0x18002e662  push    rbp
0x18002e663  push    rsi
0x18002e664  push    rdi
0x18002e665  push    r14
0x18002e667  sub     rsp, 20h
0x18002e66b  mov     rsi, rcx
0x18002e66e  mov     rdi, r8
0x18002e671  mov     rcx, [rcx+10h]
0x18002e675  mov     r14, rdx
0x18002e678  lea     rax, [rcx+r8]
0x18002e67c  cmp     rax, rcx
0x18002e67f  jb      short loc_18002E6F4
0x18002e681  mov     rdx, [rsi+18h]
0x18002e685  xor     ebp, ebp
0x18002e687  shl     rdx, 0Ch
0x18002e68b  lea     rax, [rdx+rcx]
0x18002e68f  add     rax, r8
0x18002e692  cmp     [rsi+8], rax
0x18002e696  jb      short loc_18002E706
0x18002e698  test    rdi, rdi
0x18002e69b  jz      short loc_18002E6F9
0x18002e69d  mov     rdx, [rsi]
0x18002e6a0  mov     eax, 1000h
0x18002e6a5  sub     rax, rcx
0x18002e6a8  mov     rbx, rdi
0x18002e6ab  cmp     rax, rdi
0x18002e6ae  cmovbe  rbx, rax
0x18002e6b2  add     rdx, rcx; Src
0x18002e6b5  mov     r8, rbx; Size
0x18002e6b8  mov     rcx, r14; void *
0x18002e6bb  call    memcpy_0
0x18002e6c0  mov     rcx, [rsi+10h]
0x18002e6c4  add     r14, rbx
0x18002e6c7  add     rcx, rbx
0x18002e6ca  sub     rdi, rbx
0x18002e6cd  mov     [rsi+10h], rcx
0x18002e6d1  cmp     rcx, 1000h
0x18002e6d8  jnz     short loc_18002E698
0x18002e6da  mov     rcx, [rsi]
0x18002e6dd  mov     rdx, [rcx-8]
0x18002e6e1  inc     qword ptr [rsi+18h]
0x18002e6e5  add     rdx, 8
0x18002e6e9  mov     [rsi], rdx
0x18002e6ec  xor     ecx, ecx
0x18002e6ee  mov     [rsi+10h], rbp
0x18002e6f2  jmp     short loc_18002E698
0x18002e6f4  mov     ebp, 0FFFFFF99h
0x18002e6f9  mov     eax, ebp
0x18002e6fb  add     rsp, 20h
0x18002e6ff  pop     r14
0x18002e701  pop     rdi
0x18002e702  pop     rsi
0x18002e703  pop     rbp
0x18002e704  pop     rbx
0x18002e705  retn
0x18002e706  mov     rdi, [rsi+8]
0x18002e70a  sub     rdi, rdx
0x18002e70d  sub     rdi, rcx
0x18002e710  jmp     short loc_18002E698
```
