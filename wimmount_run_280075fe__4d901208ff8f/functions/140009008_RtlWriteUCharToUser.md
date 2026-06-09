# RtlWriteUCharToUser

- ea: `0x140009008`
- end: `0x140009047`
- name: `RtlWriteUCharToUser`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004020`
- `0x14000b070`

## callees

- `0x14000102f`
- `0x140009008`

## pseudocode

```c
void __fastcall RtlWriteUCharToUser(_BYTE *a1, char a2)
{
  ProbeForRead_0(a1, 1u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x140009008  mov     [rsp+arg_0], rbx
0x14000900d  push    rdi
0x14000900e  sub     rsp, 20h
0x140009012  mov     rax, cs:qword_140008290
0x140009019  mov     dil, dl
0x14000901c  mov     rbx, rcx
0x14000901f  test    rax, rax
0x140009022  jz      short loc_14000902B
0x140009024  call    rax ; qword_140008290
0x140009026  nop     dword ptr [rax]
0x140009029  jmp     short loc_14000903B
0x14000902b  mov     edx, 1; Length
0x140009030  mov     r8d, edx; Alignment
0x140009033  call    ProbeForRead_0
0x140009038  mov     [rbx], dil
0x14000903b  mov     rbx, [rsp+28h+arg_0]
0x140009040  add     rsp, 20h
0x140009044  pop     rdi
0x140009045  retn
```
