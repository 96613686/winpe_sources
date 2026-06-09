# RtlWriteUShortToUser

- ea: `0x140009098`
- end: `0x1400090d8`
- name: `RtlWriteUShortToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004040`
- `0x14000b110`

## callees

- `0x14000102f`
- `0x140009098`

## pseudocode

```c
void __fastcall RtlWriteUShortToUser(_WORD *a1, __int16 a2)
{
  ProbeForRead_0(a1, 2u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x140009098  mov     [rsp+arg_0], rbx
0x14000909d  push    rdi
0x14000909e  sub     rsp, 20h
0x1400090a2  mov     rax, cs:qword_1400082A0
0x1400090a9  movzx   edi, dx
0x1400090ac  mov     rbx, rcx
0x1400090af  test    rax, rax
0x1400090b2  jz      short loc_1400090BB
0x1400090b4  call    rax ; qword_1400082A0
0x1400090b6  nop     dword ptr [rax]
0x1400090b9  jmp     short loc_1400090CC
0x1400090bb  mov     edx, 2; Length
0x1400090c0  lea     r8d, [rdx-1]; Alignment
0x1400090c4  call    ProbeForRead_0
0x1400090c9  mov     [rbx], di
0x1400090cc  mov     rbx, [rsp+28h+arg_0]
0x1400090d1  add     rsp, 20h
0x1400090d5  pop     rdi
0x1400090d6  retn
```
