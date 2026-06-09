# RtlReadULongFromUser

- ea: `0x140014400`
- end: `0x140014433`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140009030`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`

## callees

- `0x14000403f`
- `0x140014400`

## pseudocode

```c
__int64 __fastcall RtlReadULongFromUser(unsigned int *a1)
{
  ProbeForRead_0(a1, 4u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x140014400  push    rbx
0x140014402  sub     rsp, 20h
0x140014406  mov     rax, cs:qword_1400117F8
0x14001440d  mov     rbx, rcx
0x140014410  test    rax, rax
0x140014413  jz      short loc_14001441C
0x140014415  call    rax ; qword_1400117F8
0x140014417  nop     dword ptr [rax]
0x14001441a  jmp     short loc_14001442C
0x14001441c  mov     edx, 4; Length
0x140014421  lea     r8d, [rdx-3]; Alignment
0x140014425  call    ProbeForRead_0
0x14001442a  mov     eax, [rbx]
0x14001442c  add     rsp, 20h
0x140014430  pop     rbx
0x140014431  retn
```
