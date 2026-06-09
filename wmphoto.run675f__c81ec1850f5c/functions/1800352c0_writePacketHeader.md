# writePacketHeader

- ea: `0x1800352c0`
- end: `0x180035311`
- name: `writePacketHeader`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004db8`
- `0x18003fa68`

## callees

- `0x180003830`

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
0x1800352c0  mov     [rsp+arg_0], rbx
0x1800352c5  push    rdi
0x1800352c6  sub     rsp, 20h
0x1800352ca  movzx   ebx, dl
0x1800352cd  mov     rdi, rcx
0x1800352d0  xor     edx, edx
0x1800352d2  movzx   r11d, r8b
0x1800352d6  lea     r8d, [rdx+8]
0x1800352da  call    putBit16z
0x1800352df  xor     edx, edx
0x1800352e1  mov     rcx, rdi
0x1800352e4  call    putBit16z
0x1800352e9  lea     edx, [r8-7]
0x1800352ed  mov     rcx, rdi
0x1800352f0  call    putBit16z
0x1800352f5  and     ebx, 7
0x1800352f8  mov     rcx, rdi
0x1800352fb  lea     eax, [rbx+r11*8]
0x1800352ff  movzx   edx, al
0x180035302  mov     rbx, [rsp+28h+arg_0]
0x180035307  add     rsp, 20h
0x18003530b  pop     rdi
0x18003530c  jmp     putBit16z
```
