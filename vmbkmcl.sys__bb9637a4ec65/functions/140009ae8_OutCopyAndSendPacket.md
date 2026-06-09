# OutCopyAndSendPacket

- ea: `0x140009ae8`
- end: `0x140009b79`
- name: `OutCopyAndSendPacket`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400035a0`
- `0x140003660`
- `0x14000a3dc`
- `0x14000a810`

## callees

- `0x1400037e0`
- `0x140009ae8`
- `0x140011f80`

## pseudocode

```c
__int64 __fastcall OutCopyAndSendPacket(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, char a6)
{
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  __int64 i; // rbx
  unsigned int v12; // edi

  v6 = *(_DWORD *)(a1 + 172);
  v7 = 0;
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    v12 = *(_DWORD *)(a3 + 4 * i);
    if ( v6 < v12 )
      return 3221225507LL;
    memmove((void *)(a1 + v7 + 240LL), *(const void **)(a2 + 8 * i), v12);
    v7 += v12;
    v6 -= v12;
  }
  return OutSendPacket(a1, a1 + 240, v7, a5, a6 & 0xFE);
}

```

## disassembly

```asm
0x140009ae8  push    rbx
0x140009aea  push    rbp
0x140009aeb  push    rsi
0x140009aec  push    rdi
0x140009aed  push    r12
0x140009aef  push    r14
0x140009af1  push    r15
0x140009af3  sub     rsp, 30h
0x140009af7  mov     r14d, [rcx+0ACh]
0x140009afe  xor     ebp, ebp
0x140009b00  xor     ebx, ebx
0x140009b02  mov     r15, r8
0x140009b05  mov     r12, rdx
0x140009b08  mov     rsi, rcx
0x140009b0b  cmp     ebx, 1
0x140009b0e  jnb     short loc_140009B41
0x140009b10  mov     edi, [r15+rbx*4]
0x140009b14  cmp     r14d, edi
0x140009b17  jb      short loc_140009B3A
0x140009b19  mov     rdx, [r12+rbx*8]; Src
0x140009b1d  mov     r8d, edi; Size
0x140009b20  mov     ecx, ebp
0x140009b22  add     rcx, 0F0h
0x140009b29  add     rcx, rsi; void *
0x140009b2c  call    memmove
0x140009b31  add     ebp, edi
0x140009b33  sub     r14d, edi
0x140009b36  inc     ebx
0x140009b38  jmp     short loc_140009B0B
0x140009b3a  mov     eax, 0C0000023h
0x140009b3f  jmp     short loc_140009B69
0x140009b41  mov     eax, [rsp+68h+arg_28]
0x140009b48  lea     rdx, [rsi+0F0h]
0x140009b4f  mov     r9b, [rsp+68h+arg_20]
0x140009b57  and     eax, 0FFFFFFFEh
0x140009b5a  mov     r8d, ebp
0x140009b5d  mov     [rsp+68h+var_48], eax
0x140009b61  mov     rcx, rsi
0x140009b64  call    OutSendPacket
0x140009b69  add     rsp, 30h
0x140009b6d  pop     r15
0x140009b6f  pop     r14
0x140009b71  pop     r12
0x140009b73  pop     rdi
0x140009b74  pop     rsi
0x140009b75  pop     rbp
0x140009b76  pop     rbx
0x140009b77  retn
```
