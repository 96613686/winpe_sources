# RtlWriteUCharToUser

- ea: `0x14001449c`
- end: `0x1400144db`
- name: `RtlWriteUCharToUser`
- size: `63`
- prototype: `void __fastcall(_BYTE *, char)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140009050`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`

## callees

- `0x14000403f`
- `0x14001449c`

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
0x14001449c  mov     [rsp+arg_0], rbx
0x1400144a1  push    rdi
0x1400144a2  sub     rsp, 20h
0x1400144a6  mov     rax, cs:qword_1400117E0
0x1400144ad  mov     dil, dl
0x1400144b0  mov     rbx, rcx
0x1400144b3  test    rax, rax
0x1400144b6  jz      short loc_1400144BF
0x1400144b8  call    rax ; qword_1400117E0
0x1400144ba  nop     dword ptr [rax]
0x1400144bd  jmp     short loc_1400144CF
0x1400144bf  mov     edx, 1; Length
0x1400144c4  mov     r8d, edx; Alignment
0x1400144c7  call    ProbeForRead_0
0x1400144cc  mov     [rbx], dil
0x1400144cf  mov     rbx, [rsp+28h+arg_0]
0x1400144d4  add     rsp, 20h
0x1400144d8  pop     rdi
0x1400144d9  retn
```
