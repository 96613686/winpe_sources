# writePacketHeader

- ea: `0x180034ce4`
- end: `0x180034d35`
- name: `writePacketHeader`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d10`
- `0x18003f294`

## callees

- `0x180003760`

## pseudocode

```c
__int64 __fastcall writePacketHeader(__int64 a1, char a2)
{
  __int64 v4; // r8
  __int64 v5; // r8
  char v6; // r11
  __int64 v7; // r8

  putBit16z(a1, 0, 8);
  putBit16z(a1, 0, v4);
  putBit16z(a1, (unsigned int)(v5 - 7), v5);
  return putBit16z(a1, (unsigned __int8)((a2 & 7) + 8 * v6), v7);
}

```

## disassembly

```asm
0x180034ce4  mov     [rsp+arg_0], rbx
0x180034ce9  push    rdi
0x180034cea  sub     rsp, 20h
0x180034cee  movzx   ebx, dl
0x180034cf1  mov     rdi, rcx
0x180034cf4  xor     edx, edx
0x180034cf6  movzx   r11d, r8b
0x180034cfa  lea     r8d, [rdx+8]
0x180034cfe  call    putBit16z
0x180034d03  xor     edx, edx
0x180034d05  mov     rcx, rdi
0x180034d08  call    putBit16z
0x180034d0d  lea     edx, [r8-7]
0x180034d11  mov     rcx, rdi
0x180034d14  call    putBit16z
0x180034d19  and     ebx, 7
0x180034d1c  mov     rcx, rdi
0x180034d1f  lea     eax, [rbx+r11*8]
0x180034d23  movzx   edx, al
0x180034d26  mov     rbx, [rsp+28h+arg_0]
0x180034d2b  add     rsp, 20h
0x180034d2f  pop     rdi
0x180034d30  jmp     putBit16z
```
