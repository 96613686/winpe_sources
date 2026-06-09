# readQuantizerSB

- ea: `0x18002d614`
- end: `0x18002d6a5`
- name: `readQuantizerSB`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d6ac`

## callees

- `0x18002d614`
- `0x18002d9e8`

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
0x18002d614  push    rbx
0x18002d616  push    rbp
0x18002d617  push    rsi
0x18002d618  push    rdi
0x18002d619  push    r14
0x18002d61b  sub     rsp, 20h
0x18002d61f  mov     rdi, r8
0x18002d622  mov     rsi, rdx
0x18002d625  mov     r14, rcx
0x18002d628  cmp     r8, 10h
0x18002d62c  jb      short loc_18002D632
0x18002d62e  xor     al, al
0x18002d630  jmp     short loc_18002D69A
0x18002d632  xor     bl, bl
0x18002d634  cmp     rdi, 1
0x18002d638  jbe     short loc_18002D649
0x18002d63a  mov     edx, 2
0x18002d63f  mov     rcx, rsi
0x18002d642  call    getBit32_SB
0x18002d647  mov     ebx, eax
0x18002d649  mov     edx, 8
0x18002d64e  mov     rcx, rsi
0x18002d651  call    getBit32_SB
0x18002d656  mov     [r14], al
0x18002d659  cmp     bl, 1
0x18002d65c  jnz     short loc_18002D671
0x18002d65e  mov     edx, 8
0x18002d663  mov     rcx, rsi
0x18002d666  call    getBit32_SB
0x18002d66b  mov     [r14+1], al
0x18002d66f  jmp     short loc_18002D698
0x18002d671  test    bl, bl
0x18002d673  jz      short loc_18002D698
0x18002d675  mov     ebp, 1
0x18002d67a  cmp     rdi, rbp
0x18002d67d  jbe     short loc_18002D698
0x18002d67f  mov     edx, 8
0x18002d684  mov     rcx, rsi
0x18002d687  call    getBit32_SB
0x18002d68c  mov     [r14+rbp], al
0x18002d690  inc     rbp
0x18002d693  cmp     rbp, rdi
0x18002d696  jb      short loc_18002D67F
0x18002d698  mov     al, bl
0x18002d69a  add     rsp, 20h
0x18002d69e  pop     r14
0x18002d6a0  pop     rdi
0x18002d6a1  pop     rsi
0x18002d6a2  pop     rbp
0x18002d6a3  pop     rbx
0x18002d6a4  retn
```
