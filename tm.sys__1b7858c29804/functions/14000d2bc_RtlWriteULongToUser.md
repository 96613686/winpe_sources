# RtlWriteULongToUser

- ea: `0x14000d2bc`
- end: `0x14000d2fa`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140003060`
- `0x140012154`
- `0x140013690`
- `0x140014480`
- `0x1400147e0`
- `0x1400168d0`
- `0x140017950`
- `0x14001e120`

## callees

- `0x1400014bf`
- `0x14000d2bc`

## pseudocode

```c
void __fastcall RtlWriteULongToUser(_DWORD *a1, int a2)
{
  ProbeForRead_0(a1, 4u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14000d2bc  mov     [rsp+arg_0], rbx
0x14000d2c1  push    rdi
0x14000d2c2  sub     rsp, 20h
0x14000d2c6  mov     rax, cs:qword_14000A4A0
0x14000d2cd  mov     edi, edx
0x14000d2cf  mov     rbx, rcx
0x14000d2d2  test    rax, rax
0x14000d2d5  jz      short loc_14000D2DE
0x14000d2d7  call    rax ; qword_14000A4A0
0x14000d2d9  nop     dword ptr [rax]
0x14000d2dc  jmp     short loc_14000D2EE
0x14000d2de  mov     edx, 4; Length
0x14000d2e3  lea     r8d, [rdx-3]; Alignment
0x14000d2e7  call    ProbeForRead_0
0x14000d2ec  mov     [rbx], edi
0x14000d2ee  mov     rbx, [rsp+28h+arg_0]
0x14000d2f3  add     rsp, 20h
0x14000d2f7  pop     rdi
0x14000d2f8  retn
```
