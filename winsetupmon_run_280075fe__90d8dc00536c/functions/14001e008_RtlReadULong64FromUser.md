# RtlReadULong64FromUser

- ea: `0x14001e008`
- end: `0x14001e03c`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007668`
- `0x140011020`

## callees

- `0x1400012a6`
- `0x14001e008`

## pseudocode

```c
__int64 __fastcall RtlReadULong64FromUser(volatile void *a1)
{
  ProbeForRead_0(a1, 8u, 1u);
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x14001e008  push    rbx
0x14001e00a  sub     rsp, 20h
0x14001e00e  mov     rax, cs:qword_14001B5A8
0x14001e015  mov     rbx, rcx
0x14001e018  test    rax, rax
0x14001e01b  jz      short loc_14001E024
0x14001e01d  call    rax ; qword_14001B5A8
0x14001e01f  nop     dword ptr [rax]
0x14001e022  jmp     short loc_14001E035
0x14001e024  mov     edx, 8; Length
0x14001e029  lea     r8d, [rdx-7]; Alignment
0x14001e02d  call    ProbeForRead_0
0x14001e032  mov     rax, [rbx]
0x14001e035  add     rsp, 20h
0x14001e039  pop     rbx
0x14001e03a  retn
```
