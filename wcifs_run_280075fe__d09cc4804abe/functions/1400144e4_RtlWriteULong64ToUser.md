# RtlWriteULong64ToUser

- ea: `0x1400144e4`
- end: `0x140014524`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140009060`
- `0x140015dc4`
- `0x140016734`
- `0x140016d68`
- `0x14001771c`

## callees

- `0x14000403f`
- `0x1400144e4`

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
0x1400144e4  mov     [rsp+arg_0], rbx
0x1400144e9  push    rdi
0x1400144ea  sub     rsp, 20h
0x1400144ee  mov     rax, cs:qword_140011810
0x1400144f5  mov     rdi, rdx
0x1400144f8  mov     rbx, rcx
0x1400144fb  test    rax, rax
0x1400144fe  jz      short loc_140014507
0x140014500  call    rax ; qword_140011810
0x140014502  nop     dword ptr [rax]
0x140014505  jmp     short loc_140014518
0x140014507  mov     edx, 8; Length
0x14001450c  lea     r8d, [rdx-7]; Alignment
0x140014510  call    ProbeForRead_0
0x140014515  mov     [rbx], rdi
0x140014518  mov     rbx, [rsp+28h+arg_0]
0x14001451d  add     rsp, 20h
0x140014521  pop     rdi
0x140014522  retn
```
