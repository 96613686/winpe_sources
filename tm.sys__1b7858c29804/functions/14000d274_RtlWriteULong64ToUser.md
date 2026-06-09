# RtlWriteULong64ToUser

- ea: `0x14000d274`
- end: `0x14000d2b4`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140003050`
- `0x140012e50`
- `0x140012ff0`
- `0x140013ff0`
- `0x1400145d0`
- `0x140016c00`
- `0x1400172f0`
- `0x1400175d0`
- `0x140017950`
- `0x14001a870`
- `0x140020450`

## callees

- `0x1400014bf`
- `0x14000d274`

## pseudocode

```c
void __fastcall RtlWriteULong64ToUser(_QWORD *a1, __int64 a2)
{
  ProbeForRead_0(a1, 8u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14000d274  mov     [rsp+arg_0], rbx
0x14000d279  push    rdi
0x14000d27a  sub     rsp, 20h
0x14000d27e  mov     rax, cs:qword_14000A4B0
0x14000d285  mov     rdi, rdx
0x14000d288  mov     rbx, rcx
0x14000d28b  test    rax, rax
0x14000d28e  jz      short loc_14000D297
0x14000d290  call    rax ; qword_14000A4B0
0x14000d292  nop     dword ptr [rax]
0x14000d295  jmp     short loc_14000D2A8
0x14000d297  mov     edx, 8; Length
0x14000d29c  lea     r8d, [rdx-7]; Alignment
0x14000d2a0  call    ProbeForRead_0
0x14000d2a5  mov     [rbx], rdi
0x14000d2a8  mov     rbx, [rsp+28h+arg_0]
0x14000d2ad  add     rsp, 20h
0x14000d2b1  pop     rdi
0x14000d2b2  retn
```
