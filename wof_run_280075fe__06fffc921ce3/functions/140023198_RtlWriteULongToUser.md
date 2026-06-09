# RtlWriteULongToUser

- ea: `0x140023198`
- end: `0x1400231d6`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140012080`
- `0x140022220`
- `0x140022500`
- `0x14002382c`
- `0x14002ebd0`
- `0x1400376a0`
- `0x140037cd0`
- `0x14003ba0c`
- `0x14003befc`
- `0x14003e068`

## callees

- `0x14000da43`
- `0x140023198`

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
0x140023198  mov     [rsp+arg_0], rbx
0x14002319d  push    rdi
0x14002319e  sub     rsp, 20h
0x1400231a2  mov     rax, cs:qword_14001E8A0
0x1400231a9  mov     edi, edx
0x1400231ab  mov     rbx, rcx
0x1400231ae  test    rax, rax
0x1400231b1  jz      short loc_1400231BA
0x1400231b3  call    rax ; qword_14001E8A0
0x1400231b5  nop     dword ptr [rax]
0x1400231b8  jmp     short loc_1400231CA
0x1400231ba  mov     edx, 4; Length
0x1400231bf  lea     r8d, [rdx-3]; Alignment
0x1400231c3  call    ProbeForRead_0
0x1400231c8  mov     [rbx], edi
0x1400231ca  mov     rbx, [rsp+28h+arg_0]
0x1400231cf  add     rsp, 20h
0x1400231d3  pop     rdi
0x1400231d4  retn
```
