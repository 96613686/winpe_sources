# RtlWriteULong64ToUser

- ea: `0x140009050`
- end: `0x140009090`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004030`
- `0x14000b110`

## callees

- `0x14000102f`
- `0x140009050`

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
0x140009050  mov     [rsp+arg_0], rbx
0x140009055  push    rdi
0x140009056  sub     rsp, 20h
0x14000905a  mov     rax, cs:qword_1400082C0
0x140009061  mov     rdi, rdx
0x140009064  mov     rbx, rcx
0x140009067  test    rax, rax
0x14000906a  jz      short loc_140009073
0x14000906c  call    rax ; qword_1400082C0
0x14000906e  nop     dword ptr [rax]
0x140009071  jmp     short loc_140009084
0x140009073  mov     edx, 8; Length
0x140009078  lea     r8d, [rdx-7]; Alignment
0x14000907c  call    ProbeForRead_0
0x140009081  mov     [rbx], rdi
0x140009084  mov     rbx, [rsp+28h+arg_0]
0x140009089  add     rsp, 20h
0x14000908d  pop     rdi
0x14000908e  retn
```
