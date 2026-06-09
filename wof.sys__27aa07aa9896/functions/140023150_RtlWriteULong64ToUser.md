# RtlWriteULong64ToUser

- ea: `0x140023150`
- end: `0x140023190`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140012070`
- `0x140022220`
- `0x1400273b0`
- `0x1400273e0`
- `0x140032ee4`
- `0x1400376f0`
- `0x140037d20`
- `0x14003b9c0`
- `0x14003ba20`

## callees

- `0x14000da43`
- `0x140023150`

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
0x140023150  mov     [rsp+arg_0], rbx
0x140023155  push    rdi
0x140023156  sub     rsp, 20h
0x14002315a  mov     rax, cs:qword_14001E8B0
0x140023161  mov     rdi, rdx
0x140023164  mov     rbx, rcx
0x140023167  test    rax, rax
0x14002316a  jz      short loc_140023173
0x14002316c  call    rax ; qword_14001E8B0
0x14002316e  nop     dword ptr [rax]
0x140023171  jmp     short loc_140023184
0x140023173  mov     edx, 8; Length
0x140023178  lea     r8d, [rdx-7]; Alignment
0x14002317c  call    ProbeForRead_0
0x140023181  mov     [rbx], rdi
0x140023184  mov     rbx, [rsp+28h+arg_0]
0x140023189  add     rsp, 20h
0x14002318d  pop     rdi
0x14002318e  retn
```
