# readQuantizerSB

- ea: `0x18002d908`
- end: `0x18002d99a`
- name: `readQuantizerSB`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d9a0`

## callees

- `0x18002d908`
- `0x18002dcdc`

## pseudocode

```c
char __fastcall readQuantizerSB(_BYTE *a1, __int64 a2, unsigned __int64 a3)
{
  char Bit32_SB; // bl
  unsigned __int64 i; // rbp

  if ( a3 >= 0x10 )
    return 0;
  Bit32_SB = 0;
  if ( a3 > 1 )
    Bit32_SB = getBit32_SB(a2, 2);
  *a1 = getBit32_SB(a2, 8);
  if ( Bit32_SB == 1 )
  {
    a1[1] = getBit32_SB(a2, 8);
  }
  else if ( Bit32_SB )
  {
    for ( i = 1; i < a3; ++i )
      a1[i] = getBit32_SB(a2, 8);
  }
  return Bit32_SB;
}

```

## disassembly

```asm
0x18002d908  push    rbx
0x18002d90a  push    rbp
0x18002d90b  push    rsi
0x18002d90c  push    rdi
0x18002d90d  push    r14
0x18002d90f  sub     rsp, 20h
0x18002d913  mov     rdi, r8
0x18002d916  mov     rsi, rdx
0x18002d919  mov     r14, rcx
0x18002d91c  cmp     r8, 10h
0x18002d920  jb      short loc_18002D926
0x18002d922  xor     al, al
0x18002d924  jmp     short loc_18002D98E
0x18002d926  xor     bl, bl
0x18002d928  cmp     rdi, 1
0x18002d92c  jbe     short loc_18002D93D
0x18002d92e  mov     edx, 2
0x18002d933  mov     rcx, rsi
0x18002d936  call    getBit32_SB
0x18002d93b  mov     ebx, eax
0x18002d93d  mov     edx, 8
0x18002d942  mov     rcx, rsi
0x18002d945  call    getBit32_SB
0x18002d94a  mov     [r14], al
0x18002d94d  cmp     bl, 1
0x18002d950  jnz     short loc_18002D965
0x18002d952  mov     edx, 8
0x18002d957  mov     rcx, rsi
0x18002d95a  call    getBit32_SB
0x18002d95f  mov     [r14+1], al
0x18002d963  jmp     short loc_18002D98C
0x18002d965  test    bl, bl
0x18002d967  jz      short loc_18002D98C
0x18002d969  mov     ebp, 1
0x18002d96e  cmp     rdi, rbp
0x18002d971  jbe     short loc_18002D98C
0x18002d973  mov     edx, 8
0x18002d978  mov     rcx, rsi
0x18002d97b  call    getBit32_SB
0x18002d980  mov     [r14+rbp], al
0x18002d984  inc     rbp
0x18002d987  cmp     rbp, rdi
0x18002d98a  jb      short loc_18002D973
0x18002d98c  mov     al, bl
0x18002d98e  add     rsp, 20h
0x18002d992  pop     r14
0x18002d994  pop     rdi
0x18002d995  pop     rsi
0x18002d996  pop     rbp
0x18002d997  pop     rbx
0x18002d998  retn
```
